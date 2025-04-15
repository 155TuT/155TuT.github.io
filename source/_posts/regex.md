---
title: 正则表达式
date: 2025/04/08
tags:
  - C++
  - uncanny_feat
  - std
cover: "https://155tut.github.io/2025/04/08/regex/head.webp"
---
## 基础

### 历史
C++11引入`<regex>`，C++14优化底层实现，C++17增加了并行处理支持，C++20引入`std::regex`的CTAD特性（类模板参数推导）使其更简洁：

```c++
// C++17之前
std::regex re("\\d+", std::regex_constants::optimize);
// C++20之后
std::regex re("\\d+", std::regex::optimize);  // 自动推导模板参数
```

### 对比
相较于其他语言的正则实现：
- **Java**: 自1.4版本起引入`java.util.regex`，有完整Unicode支持
- **Python**: 通过re模块提供丰富实用方法
- **JS**: 原生集成正则字面量语法

`<regex>`的特点：

- 编译期语法检查
- **与STL算法的集成**

---

## 用法

### 基本语法

#### 基本组成

- **字符类**：如 `[abc]` 表示匹配 a、b 或 c 中的任意一个字符，a-z表示匹配a到z中任意一个字符
- **量词**：如 `*`（零次或多次）、`+`（一次或多次）、`?`（零次或一次）
- **边界匹配**：如 `^`（行初）、`$`（行末）
- **分组**：圆括号 `()` 

#### 主要类和函数

- `std::regex`：表示一个正则表达式对象。
- `std::regex_match`：检查整个字符串是否与正则表达式匹配。
- `std::regex_search`：在字符串中搜索与正则表达式匹配的部分
- `std::regex_replace`：替换字符串中与正则表达式匹配的部分。
- `std::sregex_iterator`：迭代器，用于遍历所有匹配项。

### 核心组件
1. **std::regex**：存储正则表达式
2. **std::smatch**：存储匹配结果
3. **std::regex_iterator**：迭代式搜索
4. **std::regex_token_iterator**：子匹配迭代器

### 基本步骤
```c++
std::string email = "test@example.com";
std::regex pattern(  // 模式串
    R"(^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$)", 
    std::regex::icase | std::regex::optimize
);

if (std::regex_match(email, pattern)) {  // 完全匹配检测
    std::cout << "Valid email" << std::endl;
}
```

### 搜索演示
```c++
std::string log = "Error 404 at 15:30, Warn 500 at 16:45";
std::regex error_re(R"(\bError\s+(\d+)\b)"); 

std::smatch match;
if (std::regex_search(log, match, error_re)) {  // 首次匹配
    std::cout << "Error code: " << match[1] << std::endl;  // 捕获组访问
}

// 迭代搜索所有数字
std::sregex_iterator it(log.begin(), log.end(), std::regex(R"(\d+)"));
std::sregex_iterator end;
while (it != end) {
    std::cout << "Found number: " << it->str() << std::endl;
    ++it;
}
```

---

## 优化

### 预编译
```c++
// 头文件中
extern const std::regex DATE_RE;  

// 源文件中
const std::regex DATE_RE(  // 避免重复构造
    R"(^(19|20)\d\d[-/.](0[1-9]|1[012])[-/.](0[1-9]|[12][0-9]|3[01])$)", 
    std::regex::optimize | std::regex::nosubs
);
```

------

## 对比

| 方法        | 时间复杂度     | 适用场景     |
| ----------- | -------------- | ------------ |
| KMP算法     | O(n+m)         | 固定模式匹配 |
| Boyer-Moore | O(n/m)         | 长模式搜索   |
| 正则表达式  | O(2^m)最坏情况 | 复杂模式匹配 |
| Rabin-Karp  | O(n+m)         | 多模式匹配   |

---

## 注意

1. **贪心匹配**
```c++
std::regex greedy_re(R"(<.*>)");  // 贪心匹配整个标签
std::regex lazy_re(R"(<.*?>)");   // 非贪心匹配单个标签
```

2. **锚点误用**
```c++
std::regex wrong_date_re(R"(\d{4}-\d{2}-\d{2})");  // 可能匹配部分字符串
std::regex correct_date_re(R"(^\d{4}-\d{2}-\d{2}$)");  // 精确匹配整个字符串
```

3. **性能**
```c++
std::regex danger_re("(a+)+b");  // 指数级时间复杂度
```

---

## 场景

✅ ：
- 复杂模式匹配
- 可配置的模式规则
- 多级文本提取

⛔ ：
- 简单固定字符串操作
- 性能敏感的底层处理
- 需要严格线性时间的场景

~~竞赛用的很少，但是个人感觉很有趣，遂学~~
