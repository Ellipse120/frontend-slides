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

# 争议

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

# 概念

> 本质上，你可以将原子化的 CSS 框架理解为这类 CSS 的统称：

```css
.m-0 {
  margin: 0;
}
.text-red {
  color: red;
}
.bg-red {
	background-color: red;
}
```

目前主流的工具有 [Tailwind CSS](https://tailwindcss.com/), [UnoCSS](https://uno.antfu.me/), [Windi CSS](https://cn.windicss.org/)，[Tachyons](https://tachyons.io/)，也有一些UI组件库提供了一些这样的Class，如[Bootstrap](https://getbootstrap.com/docs/5.1/utilities/api/)，[Quasar](https://quasar.dev/)，[Primefaces](https://www.primefaces.org/primeflex/margin)，[Chakra UI](https://chakra-ui.com/docs/features/style-props)等。

---

# 原子化 CSS 的工作原理

制作原子化 CSS 的传统方案其实就是提供所有你可能需要用到的 CSS 工具。例如，你可能会用预处理器（这里选用的是 SCSS）生成如下代码：

```scss
// style.scss

@for $i from 1 through 10 {
  .m-#{$i} {
    margin: $i / 4 rem;
  }
}
```

编译结果为：

```css
.m-1 { margin: 0.25 rem; }
.m-2 { margin: 0.5 rem; }
/* ... */
.m-10 { margin: 2.5 rem; }
```

---

# 问题

现在我们可以直接使用 **`class="m-1"`** 来设置边距。但正如所见，用这种方法时，我们不能使用除了 1 到 10 之外的边距，而且，即使你只使用了其中一条 CSS 规则，但还是要为其余几条规则的文件体积买单。如果之后你还想支持不同的 margin 方向，使用比如 **`mt`** 代表 **`margin-top`**，**`mb`** 代表 **`margin-bottom`** 等，加上这 4 个方向以后，你的 CSS 大小会变成原来的 5 倍。如果再有使用到像 **`:hover`** 和 **`:focus`** 这样的伪类时，体积还会得更变大。以此类推，每多加一个工具类，往往意味着你 CSS 文件的大小也会随之增加。这也就是为什么传统的 Tailwind 生成的 CSS 文件会有数 MB 的大小。

为了解决这个问题，Tailwind 通过使用 [PurgeCSS](https://purgecss.com/) 来扫描你的大包产物并删除你不需要的规则。这得以使其在生产环境中 CSS 文件缩减为几 KB。然而，请注意，这个清除操作仅在生成构建下有效，而开发环境下仍要使用包含了所有规则巨大的 CSS 文件。这在 Webpack 中表现可能并不明显，但在 Vite 中却有着巨大的影响，毕竟其他内容的加载都非常快。

---
layout: two-cols
---
# Traditional
<img class="h-2/3 w-full mr-2" src="https://antfu.me/images/unocss-traditional-way.png" alt="traditional" />

::right::

# On-Demand
<img class="h-2/3 w-full" src="https://antfu.me/images/unocss-on-demand-way.png" alt="on-demand" />

---
layout: intro
---

# 结论

> 通过调换 "生成" 和 "扫描" 的顺序，"按需" 会为你节省浪费的计算开销和传输成本，同时可以灵活地实现预生成无法实现的动态需求。另外，这种方法可以同时在开发和生产中使用，提供了一致的开发体验，使得 HMR (Hot Module Replacement, 热更新) 更加高效。

---

# 简单实现原理

Windi CSS 和 Tailwind JIT 都采用了预先扫描源代码的方式来实现按需生成，简单代码示例：

```jsx
import glob from 'fast-glob'
import { promises as fs } from 'fs'

// 通常这个是可以配置的
const include = ['src/**/*.{jsx,tsx,vue,html}']

async function scan() {
  const files = await glob(include)

  for (const file of files) {
    const content = await fs.readFile(file, 'utf8')
    // 将文件内容传递给生成器并配对 class 的使用情况
  }
}

await scan()
// 扫描会在构建/服务器启动前完成
await buildOrStartDevServer()
```

---

为了在开发期间提供 HMR，通常会启动一个 [文件系统监听器](https://github.com/paulmillr/chokidar)：

```jsx
import chokidar from 'chokidar'

chokidar.watch(include).on('change', (event, path) => {
  // 重新读取文件
  const content = await fs.readFile(file, 'utf8')
  // 将新的内容重新传递给生成器
  // 清除 CSS 模块的缓存并触发 HMR 事件
})
```

<br />
<br />

> 如果是新项目，推荐使用UnoCSS或者WindiCSS，具体特性可去官网阅读文档。

---
layout: 'center'
class: 'text-center'
---

# 主流技术

<div class="grid grid-cols-3 gap-4 place-items-center mt-8">
  <div><TailwindCSS /></div>
  <div><WindiCSS /></div>
  <div><UnoCSS /></div>
</div>

---

# Compare

| **_TailwindCSS_(2017.11.02)** | **_WindiCSS_(2020.12.29)** | **_UnoCSS_(2021.10.23)** 
| --- | --- | --- |
| 公司驱动开发 | 个人主导+社区驱动开发 | 个人主导+社区驱动开发 |
| 依赖 **PostCSS**, **autoprefixer** | **0** 依赖 | **0** 依赖
| 4883 <IcOutlineCommit />, 251 <PhUsersBold />, 2.8M <CarbonColumnDependency /> | 941 <IcOutlineCommit />, 54 <PhUsersBold />, 10.6k <CarbonColumnDependency /> | 1800 <IcOutlineCommit />, 133 <PhUsersBold />, 6.7k <CarbonColumnDependency />
| DX **bad** | DX **better** | DX *best* |
| Tailwind JIT: postcss 插件，它启动文件系统观察器来扫描源代码，以便按需生成 CSS | WindiCSS: 独立的编译器，0依赖，可以在任何地方工作。 构建工具、框架插件丰富 | UnoCSS: Atomic CSS 引擎,灵活性和性能最好，有TailwindCSS, WindiCSS, Bootstrap超集。
| <TablerBusinessplan />: Refactoring UI, tailwindUI, headlessUI, heroicons | Poor | Poor

---
layout: 'center'
class: 'text-center'
---

# 

<div grid="~ place-items-center h-full" text="6xl blue-500">
 Live Code
</div>