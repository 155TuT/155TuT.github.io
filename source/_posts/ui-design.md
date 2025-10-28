---
title: West2Online设计组第一阶段考核心得
date: 2025/10/28 20:30:00
tags:
  - UI
  - Design
  - West2Online
  - Gossip
cover: "https://155tut.github.io/2025/10/28/ui-design/head.webp"
---
> “该说些什么，你知道的，我不懂的。”

## 考核信息

### 时间

- 要求：9.11 ~ 10.17
- 个人完成：9.27 ~ 10.10
- 工时：30h-（零基础学习 + 制作）

### 内容

- **要求**：
  1. 掌握figma操作
  2. 绘制icon
  3. 临摹+绘制ui
  4. 加入prototyping design
  5. 制作组件库
- **作业链接**：
  - [figma](https://www.figma.com/design/4XCc8SiF5AqmvznEVEq0oo/test4fuu_refresh)

## 心得

**网上好的设计课程真的很少**，figma设计严格意义上来说难度介于Windows Print3D和ps中间，找个大专生都能学会操作，因此可以说上手门槛很低，但**想要做好任何设计，熟练使用工具都只是第一步**。就像学计算机语言也只是编程的第一步，这些设计软件只不过是你表达设计观念的载体。设计时是否真的有做到**换位思考**，是否**遵循了设计原则**，又是**哪些理由让你选择了这些设计原则**，都是设计时所必须考虑的，而这些又全都依赖于你在自行临摹与设计（实践）过程中的体会，因此大部分手把手教的课程其实效果都没有你想的那么好，很厉害的人教的东西涵盖大量艺术鉴赏与迁移，中等偏下的人又怕你学会了超过他们。因此好的课程才如此之少。不过换位思考一下，这也同样意味着**人人都能做设计**，你其实没有理由学不会，只需要发挥出自己的积累与审美即可。

### figma基础

#### 资源

- [clash verge](https://github.com/clash-verge-rev/clash-verge-rev) ：figam已不支持大陆地区访问，建议科学上网
- [figma learn](https://help.figma.com/hc/en-us/categories/360002042553-Figma-Design) ：全英文但有配套视频的figma详细使用教程
- 其他
  - [贝塞尔曲线与钢笔](https://www.bilibili.com/video/BV1ggJfzJEYC) *bilibili*

#### 要点

首先是figma本身，由易到难的重点为：Figma插件的安装与使用，Frame与Rectangle的区别，圆的各类参数，钢笔工具，Variables，Auto Layout，Vector Path与图形的转换，组件与母版的创建与使用，Prototyping（如有疏漏请联系作者）

然后是一定要养成的好习惯：

1. 为所有**能称得上层级**的东西挂一个Auto Layout，实在找不到规律的就挂Frame，这对适配与鲁棒性很重要，对与前端的对接更重要
2. 易于阅读的线条与空隙原则上不能小于2px，纤细感的描边线条原则上为1px
3. 最好不要使用任何非整数像素的线条，不然只会以灰度形式呈现在屏幕上，会有一定的虚影，因此一定要计算一下各元素是否在整数像素上
4. 所有颜色与字体样式均挂到Variables里，统一视觉效果，便于后续修改
5. button，list，card，bar等元素如有复用最好采用组件与母版，便于后续修改

以及个人小建议：学一下快捷键可以省很多时间；试试弄一个教育认证也可以通过使用变量与开发模式省很多制作原型动画的时间，效果也会更好，还能使用直接接入figma的ai来辅助创作。不过如何骗取教育认证还请自行研究，作者不会提供任何相关信息

### icon绘制

#### 资源

- [apple design](https://developer.apple.com/design) ：苹果官方设计规范
- [material design](https://m3.material.io/) ：google官方设计规范
- [shadcnui](https://ui.shadcn.com/) ：规范的开源设计
- 其他
  - [图标网格](https://www.bilibili.com/video/BV1Yp421D7kp) *bilibili*

#### 要点

在实际工程中，几乎**没有人会为项目重构一整套icon**，因此制作与筛选对应风格的icon变成了这个阶段中最重要的一点。但在这个阶段，你其实是在践行并强化你所学到的理论，让其不至于是纸上空谈：重点不在你绘制的icon本身，而在于你考虑到与遵循了的设计原则，思考一些原则存在的必要性，为什么官方的icon在无论什么比例看着都很顺眼，自己画的为什么像小孩子过家家一样没眼看。这并不是什么羞于启齿的事，每个富有热情的创作者都要在这种极简而克制的简单项目中平衡信息密度、创作热情与实际效果

> **幻想当然和童年一样具备无数可能，但创作和长大一样，是削减可能性直至那一抹绚烂刻入凡尘的过程**

以及一些需要注意的点：做icon交互动画时要使用同一个元素进行变形，不然智能动画无法识别，因此这也是你实践组件、母版与变体的最佳时机；最好为同一icon绘制多种风格如彩色，填充，outline等，在考虑实际可阅读性，角标、信息与动画时，能做的调整真的非常少，因此这才是icon绘制中最大的难点，当然设计好了这种tiny的也更有助于你把控下一步骤的整体比例

### ui临摹与绘制

#### 资源

- [encycolorpedia](https://encycolorpedia.com) ：颜色搭配
- 其他
  - [app设计入门](https://www.bilibili.com/video/BV1Rv411r7qK) *bilibili*
  - [色彩搭配法则](https://www.bilibili.com/video/BV1xG411E7fw) *bilibili*
  - [交互式组件](https://www.bilibili.com/video/BV1bG411t7GH) *bilibili*
  - [页面动画](https://www.bilibili.com/video/BV13F411z7BA) *bilibili*
  - [层次感](https://www.bilibili.com/video/BV13P4wzkEMi) *youtube搬运*
  - [产品导向的样例分析](https://www.bilibili.com/video/BV1TCWCzjEbd) *youtube搬运*
  - [同元素页面重构](https://www.bilibili.com/video/BV1n2sFzEEzF) *youtube搬运*
  - [原理导向的设计勘误](https://www.bilibili.com/video/BV1uu4izTE6j) *youtube搬运*

#### 要点

终于到了整场考核最难的一点，这里需要的你的积累与迁移越多越好，因此我在”其他“中放了很多高质量的临摹视频供你参考。到这一步你已经掌握了大部分布局原则与技巧，需要学习的也只有全局细节上的协调：圆角，图形层次，颜色层次，字体字重...这里其实考核要求的难度并不高，但是学到这里已经意味着你在这里使用的设计知识可以反哺与迁移到大部分其他领域的设计上了：绘画，摄影，海报甚至音乐，电影，建筑，雕塑...一切设计知识都是你的好伙伴，你需要做的就是在学习中逐渐内化规则，融会贯通，推陈出新，这才是最耗费时间、最难的一环：审美培养，也是真正意义上对接设计组考核主题的一项能力

## 写在最后

其实没写博客的这半年有很多思考，可能是大一玩够了，也可能是积累到了，总觉得自己的产出太过儿戏，一直在专注思考关于自己真正的提升，期间也尝试了很多方向。不过真正能体现成长的或许是一个这样微不足道的例子：

> 所有所谓的弯路都是对世界参数的拟合与学习，你偶然深入学习的贝塞尔曲线，体素与透视会让你在十五分钟内使用没接触过的inkscape直接绘出他人所需的[icon.svg](https://github.com/OIerDb-ng/OIerDb/pull/147)

加油，155TuT，无限进步！

~~其实这篇文章也只是作为第二阶段考核成果存在的，确实是对经验分享这件事失去了很多兴致~~

> 因考核要求同步发表于[飞书](https://ecn391pn069m.feishu.cn/wiki/IjC6wclCXiXRDhk2OiFcKlN1nJe?from=from_copylink)
