---
title: STL与pb_ds（持续更新）
date: 2025/04/10 22:30:00
tags:
  - C++
  - Algorithm
  - fzu_ACM_weekly_train
cover: "https://155tut.github.io/2025/04/10/stl-and-pbds/head.webp"
---
**首先是工程中良好的习惯：局部引用或每次引用**

```c++
#include <iostream>
#include <cstdio>//  EXIT_SUCCESS和EXIT_FAILURE
#include <vector>
void func(){
    std::vector<int> b(5);// 每次引用
    return;
}
int main(int argc, char* argv[]){
    using std::vector;//  局部引用
    vector<int> a(5);
    func();
    return EXIT_SUCCESS;
}
```

**不过比赛中为了思路连续性一般选择最简单的写法**

```c++
#include <bist/stdc++.h>
using namespace std;
int main(){
    ios::sync_with_stdio(0);
    cin.tie(0);
    
    return 0;
}
```

以及：

**不！要！在赛时强行用自己不熟悉的数据结构！**

不然查错都无从下手

------

## std::

#### 通用

```c++
#include <containerName>
using std::containerName;
containerName<typeName,...> name //  模板声明，可嵌套
name.functionname(...) //  成员函数
```

##### 迭代器

本质：经stl封装后的指针

```c++
vector<int> test;
for(int i = 0; i < test.size(); i++)
    cout << test[i] << endl; //  下标遍历
for (vector<int>::iterator iter = data.begin(); iter != data.end(); iter++)
  cout << *iter << endl; //  可使用auto
```

迭代器在stl中的定义注定了其区间都是左闭右开的，如上面循环的终止条件，以及`contianer.find(x) != container.end()`这样的用法等

**序列式**

#### vector 可变数组

**定义**

```c++
vector <int> a; //  最简单的定义
a.reverse(3); //  初始化（std::allocator）分配a[0] ~ a[2]的空间
vector <int> a(3, 0); //  等效前两行，3个元素，初值为0
vector <int> a = {0, 0 ,0}; //  列表初始化，等效前两行
vector <int> b(a); //  拷贝一份a
vector <int> c(b.begin(), b.begin() + 3) // 把b[[0, 3)]即b[0] ~ b[2]拷贝到c中
vector <vector <int>> m(3, vector <int> (3, 0)); //  二维数组的初始化
vector <vector <int>> m = {{0}, {0,0}, {0, 0, 0}}; //  列表初始化（可不规则，本质：每一维都是独立的vector）
```



#### deque 双端队列



#### list 双向链表



**关联式**

#### (unordered_)(multi)set（无序）（多重）集合



#### (unordered_)(multi)map （无序）（多重）映射



**适配器**

#### stack 栈

基于std::deque

#### queue 队列

基于std::deque

#### priority_queue 优先队列（大根堆）



## __gnu_pbds::

#### priority_queue 堆



#### tree 平衡树



## etc

以上内容大部分来自[STL 容器简介 - OI Wiki](https://oi-wiki.org/lang/csl/container/)和[pb_ds 简介 - OI Wiki](https://oi-wiki.org/lang/pb-ds/)，意在提醒自己基础用法，之后会择日重写或封装一些更高级的数据结构

~~真的不是水，很容易忘的~~
