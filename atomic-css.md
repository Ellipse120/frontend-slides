---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: true
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS (experimental)
css: unocss
download: false
---

# Atomic CSS

路赛

---

# 关注的问题

- 在大规模使用 CSS 时，渴望发现潜在的可维护性问题，即使目前可能还没有遇到这些问题。

- 你已经经历了与 CSS 的斗争，并且正在寻找克服这些困难的解决方案。

- 你听说过某些流行语，例如特异性、语义、作用域、封装、原子 CSS、CSS-in-JS、设计标记或类型安全，但并没有完全理解它们的含义。

- 即使你掌握了一些特定的工具和技术，你也想了解整个 CSS 生态系统。

- 你只是好奇地想了解 CSS 工具是如何随着时间的推移而演变的，或者为什么今天存在特定的技术。

<!-- 一个几个月生命周期的项目，开发者通常会自己使用认为合适的任何方式编写 CSS。 不管怎样，项目的结果不会有多大影响。

当我们考虑有多个开发人员在同一个代码库上工作的团队时，写得不好的 CSS 会在几年内极大地影响项目的开发。CSS使用混乱，作用域污染,important，inline style等滥用, 可读性、可维护性不理想 -->

---

# Timeline of scalable CSS evolution milestones and turning points

<img src="https://andreipfeiffer.dev/_next/static/media/scalable-css-evolution-light.00a21e8e.gif" />

---

# Preface

软件项目的代码将随着新功能的实现而不断增长。 因此，当我们谈论软件可扩展性时，我们会考虑在显着增加代码大小时维护工作的比例因子。

每当问题的严重性与代码的大小成比例增加时，我们就会担心:

- 可伸缩性

- 可维护性

- 体积

---

# 本文讨论的内容

- Atomic CSS 概述，基本原则

- 实用 CSS 类(Utility CSS)，任何 Atomic CSS 方法的核心

- 原子 CSS 框架，可以更容易地采用

- Atomic CSS 的局限性和缺点

---

# Atomic CSS 在 2013 年作为一个完全不同的范式分支出来，目前是标准语义 CSS 方法的替代方案

<img src="https://andreipfeiffer.dev/_next/static/media/atomic-css-light.d2b63654.gif" />

---

# 曾经存在的非议

- HTML体积会变大

```css
<!-- Example of Twitter HTML code using Atomic CSS -->
<img class="css-18t94o4 css-1dbjc4n r-1niwhzg r-sdzlij r-1phboty r-4iw3lz r-1xk2f4g r-109y4c4 r-1ii58gl r-25kp3t r-1ny4l3l r-1udh08x r-wwvuq4 r-u8s1d r-o7ynqc r-6416eg r-lrvibr r-92ng3h" />

```

https://windicss.org/features/shortcuts.html#shortcuts

- Devtools中调试麻烦

https://windicss.org/integrations/vite.html#design-in-devtools

<!-- "Design in DevTools" 
https://windicss.org/integrations/vite.html#design-in-devtools


-->

- ::before, ::after不易实现

https://windicss.org/utilities/general/variants.html

- 有一定学习成本

---

# 共生

- 原子 CSS 框架也称为实用程序优先(Utility First)

- 正如大多数语义 CSS 框架还包括用于颜色、显示属性、定位等的单一用途实用程序一样，也可以编写自己的语义 CSS 自定义类来覆盖原子 CSS 框架的特性

- 语义和原子（非语义）方法在基本层面上是完全相反的。 但是，我们可以采取务实和不拘一格的心态，而不是教条主义和单一的思想流派。

- 最后，所有这些框架都只是工具。 它们由开发人员构建，以帮助其他开发人员编写可维护的 CSS 代码。

- 客观地说，Atomic CSS 解决了 Semantic CSS 的大部分问题，即代码重复、特异性、增加代码输出或复杂的选择器等。 因此，原子 CSS 被证明是语义 CSS 的有效替代品。

---
layout: 'center'
class: 'text-center'
---

# 主流技术

<div class="grid grid-cols-3 gap-4">
  <div><TailwindCSS /></div>
  <div><WindiCSS /></div>
  <div><UnoCSS /></div>
</div>

---
layout: 'center'
class: 'text-center'
---

#

<div grid="~ place-center h-full" text="6xl blue-500">
 Live Code
</div>