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
lineNumbers: false
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
---

# 前端概览

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

---
layout: image-right
image: https://images.unsplash.com/photo-1591267990439-bc68529677c3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1706&q=80/1920x1080
---

# 目录

1. 前端定义

2. 做什么

3. 怎么做

4. 软技能

5. 技术栈

6. 学习资料

7. 未来

---

# 前端定义

<br>

- 软件程序或网站的前端是一切与用户交互的媒介

- 创建流畅或无阻塞的用户体验的应用

- 应用程序或页面布局

<!-- 软件程序或网站的前端是一切与用户交互的媒介。 从用户的角度来看，前端与用户界面是同义词。 从开发人员的角度来看，前端是界面设计、代码驱动界面功能。 相反，后端包括发生在幕后的功能和数据处理。

前端开发的主要目标之一是创建流畅或无阻塞的用户体验的应用。 换句话说，应用程序或网站的前端应该直观且易用。 虽然这听起来像是一个简单的目标，但它可能会非常复杂，因为并非所有用户或设备都是相同的。 例如，为移动设备开发的应用程序需要与桌面应用程序截然不同的前端。 网站必须在多种设备和屏幕尺寸上运行良好，这也是现代 Web 开发通常涉及响应式设计的原因。


前端所涉及的主要内容：

应用程序或页面布局
图形
音视频元素
文字内容
用户界面元素（按钮、链接、工具栏、导航栏等）
输入区域（对话框）、表单域、文本区域等）
用户流（一个界面如何通向下一个界面）
用户偏好、主题和自定义


用户输入内容通过前端接收并在程序或网站的后端进行处理。 后端代码读取和写入数据并通过前端将输出发送给用户。 由于应用程序或网站的后端和前端协同工作，因此软件工作通常需要前端和后端开发。  -->

---

# 做什么

- 使用 HTML, CSS, JavaScript 将设计变为现实，开发和维护用户界面

- 持续优化用户体验，统一的交互体验

- 网站响应式设计，考虑不同尺寸窗口页面展示效果，用户操作反馈等

- 管理自己软件开发工作流程

- 遵循最佳实践，如代码语义化，SEO，A11y等

- 修复错误并测试可用性，保证交付质量

<!--
设计变为现实：如Web网页，APP等交互界面

管理自己软件开发工作流程：软件开发过程中，经常会有中断，会议等穿插进来，会干扰开发节奏，我们应该培养自己的开发节奏，尽可能减少中断带来的影响。

遵循最佳实践：一般是一些经验提炼，规范定义。比如语义化，可以提高网站SEO的打分，代码可读性高。A11y是无障碍访问的简写，为有访问网站障碍的用户考虑，利于屏幕阅读器理解区分。

交付质量：是开发者的名片，交付前应该仔细自测，如果测试同事写了测试用例，最好能够自己跑一遍测试用例，保证模块高质量交付。

 -->

---

# 怎么做

- HTML(超文本标记语言): 开发网站所需的基本构建块，一种允许您在不同于常规文本的数字文档中做笔记的语言

- CSS(层叠样式表): 用于创建您使用 HTML 创建的页面的布局、颜色、样式等的语言

- JavaScript: 确定页面将做什么的开发人员的编程语言

- Framework: 用于一致、高效和准确地开发软件的平台

- UI(用户界面): 应用程序的图形布局

- UX(用户体验): 用户如何与应用程序交互

- 版本控制: 跟踪和控制源代码更改的过程

--- 

# 软技能

仅凭技术能力不足以胜任前端角色。 任何软件开发工作都必须具备数学、分析、创造力、设计和解决问题的能力。 在数字优先或纯数字环境中，软技能更为重要。

- 时间管理

- 沟通

- 项目管理

- 创造力

- 解决问题的能力

<!-- 
时间管理：需要做任务拆分，任务估时，任务完成时间等，还需要处理中断事件带来的时间消耗，如穿插着做核酸，开会，节日活动等事件。

沟通：与同事沟通应注意双方理解、认知的不同，领域的不同，尽量调整语言来达成共识，如跟项目经理的沟通、UI、后端、测试同事的沟通，都应该尽量减少自己专业词汇的出现

创造力：条条大路通罗马。一个需求的实现，可能会有多种方法，应该在平衡时间和进度之前找的平衡点，努力探寻最适合的方式来实现

解决问题的能力：多培养学习的方法，学习如何学习，如何解决问题。应该减少互相之前的依赖。随着网页、浏览器的发展，项目需求复杂度也会越来越高，新技术不断涌现，可能很多问题别人也没遇到过。一些建议：1. 阅读英文文档；2. 擅用搜索引擎，如Bing，Google，DuckDuckGo等；3. 学习到的知识，分享给他人，教会别人

 -->

---

# 技术栈

- Language: [<logos-ecma />ES6 +](https://www.ecma-international.org/publications-and-standards/standards/ecma-262/), [<VscodeIconsFileTypeTypescriptOfficial />TypeScript](https://www.typescriptlang.org/)

- Framework: [<VscodeIconsFileTypeVue />Vuejs 2](https://v2.vuejs.org/), [<LogosNuxtIcon />Nuxt 3](https://v3.nuxtjs.org/)

- Build: [<LogosWebpack />Webpack 4](https://v4.webpack.js.org/concepts/), [<LogosVitejs />Vite 2](https://vitejs.dev/), [<LogosRollupjs />Rollup](https://rollupjs.org/), [<LogosEsbuild />esbuild](https://esbuild.github.io/) 

- UI: [<LogosElement />ElementUI](https://element.eleme.cn/#/zh-CN/component/installation), [<PrimePrime class="text-blue-500 text-xl" />PrimeVue](https://www.primefaces.org/primevue/)

- CSS: [<FileIconsWindi class="text-blue-400" />WindiCSS](https://windicss.org/), [<LogosUnocss />UnoCSS](https://uno.antfu.me/), [<LogosTailwindcssIcon />TailwindCSS 2](https://v2.tailwindcss.com/)

- Charts: [<SimpleIconsApacheecharts class="text-red-600" />ECharts](https://echarts.apache.org/), [<LogosHighcharts />Highcharts](https://www.highcharts.com/)

- Utils: [<LogosLodash />Lodash](https://lodash.com/), [Date-fns](https://date-fns.org/), [AntV X6](https://antv-x6.gitee.io/zh), [<IconParkOutlineEarth class="text-green-600" />ArcGIS](https://developers.arcgis.com/)

---

# 学习资料

- [MDN](https://developer.mozilla.org/en-US/docs/Learn/Front-end_web_developer)<uim-rocket v-motion-fade class="text-xl text-green-500 mx-2" />

- [JavaScript.INFO](https://javascript.info/)

- [Javascript Tutorial](https://www.javascripttutorial.net/)

- [FreeCodeCamp](https://www.freecodecamp.org/)

- [W3schools](https://www.w3schools.com/)

- [CSS Tricks](https://css-tricks.com/)

- [CodePen](https://codepen.io/trending)

- [Vue2 Style Guide](https://v2.vuejs.org/v2/style-guide/)

- [以太坊](https://ethereum.org/)

---

# 未来

- WebGL: GIS, BIM etc

- DAPPS

- AI based web

- voice commands

- smart recommendation algorithms

- automated coding

- AR/VR
