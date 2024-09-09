### 1. HTML
#### 1.1 简述一下http和https
- http是超文本传输协议，信息是明文传输，https加了SSL协议，可进行加密传输、身份认证，比http协议更安全
- http和https使用的是完全不同的连接方式，用的端口也不一样，前者是80，后者是443
- https协议需要ca申请证书，一般免费证书较少，因而需要一定费用

#### 1.2 HTML5增加了哪些属性和标签，还有哪些api
- 新增语义化标签：header、footer、nav、article、section、asicde
- 新增表单属性：min、max、step、placeholder、autofocus、required、pattern、multiple
- 新增数据存储localstorage sessionstorage
- 新增音频视频
- 新增画布canvas

#### 1.3 对HTML语义化标签的理解
- 用合适的标签和属性组合文档结构，增强代码可读性
- css不能正常加载时，仍然能够保证基本的文档结构
- 有利于后期维护
- 有利于团队合作
- 有利于SEO
- 有利于用户体验

#### 1.4 常见布局方式
- 固定布局、响应式布局、弹性布局、自适应布局、流式布局

#### 1.5 两边固定中间自适应怎么实现
- flex布局：使用display: flex，左右两栏设置固定宽度，中间栏设置flex: 1，让它自动填充剩余空间
- 自身浮动法：左栏左浮动，右栏右浮动，中间栏放在最后，不设置浮动属性，它会自动填充剩余空间
- 绝对定位法：左右栏使用position: absolute固定在页面两侧，中间栏通过设置margin-left和margin-right来自适应布局
- margin负值法：两边固定宽度的元素使用float浮动，中间元素设置width: 100%，通过左右栏的负margin值让中间元素自适应剩余空间

#### 1.6 页面导入样式时，使用link和@import有什么区别
- link标签用在html中，支持并行加载，性能更好；@import用于在CSS中，加载可能会延迟

#### 1.7 title与h1的区别，b与strong的区别，i与em的区别
- title定义了网页标题，显示在浏览器标签上，h1表示页面的主要标题，显示在网页内容上。对于SEO来说，title比h1更重要
- b和strong都用来加粗文本，strong表示标签内字符比较重要，用以强调
- i和em都用来倾斜文本，em表示标签内字符比较重要，用以强调

#### 1.8 img标签的title和alt有什么区别
- title：鼠标移入到图片显示的值
- alt：图片无法加载时显示的值。为了增加SEO效果，要加入alt属性来描述图片内容或关键词

#### 1.9 href和src的区别
- href不会直接下载资源，而是创建一个通道，当用户点击链接时，浏览器会导航到指定的URL
- src浏览器会下载资源并将其嵌入到当前文档中，替代当前元素

#### 1.10 一个完整的http请求都发生了些什么事情？
- 整个过程就像你在浏览器中输入网站地址，浏览器发出请求到服务器，服务器处理请求并返回网页内容，最后浏览器展示网页给你。

#### 1.11 TCP三次握手和TCP四次挥手
```
三次握手（建立连接）
第一次握手：你（客户端）要和对方（服务器）打招呼，告诉对方你想要开始聊天。你发出一个“你好，我想连接”的信号。
第二次握手：对方（服务器）收到你的打招呼信号后，回应你一个“你好，我愿意聊天，但我们需要确认一下。” 它会发回一个包含两个信号的回应：一个是确认你的“你好”，另一个是它自己的“我也想聊”的信号。
第三次握手：你收到对方的回应后，再发一个确认信号，告诉对方“好的，我收到了你的回应，我们可以开始聊天了。”这样，双方都确认了连接可以建立了。

四次挥手（断开连接）
第一次挥手：你（客户端）决定不再聊天了，发出一个“我想断开连接”的信号。
第二次挥手：对方（服务器）收到你的断开信号后，回复一个“收到，我明白了。” 它发回一个确认的信号，但它自己可能还在处理一些事情，所以它会继续与你保持连接一段时间。
第三次挥手：对方（服务器）完成了所有的处理，准备好断开连接了，它发出一个“我也要断开了”的信号。
第四次挥手：你（客户端）收到对方的断开信号后，再发一个确认信号，告诉对方“好的，我已经收到了。” 这样，双方就完全断开了连接。
```

### 2. CSS
#### 2.1 盒子模型
- 标准盒子模型：margin、border、padding、content `box-sizing: content-box;`
- IE盒子模型：margin、content( border + padding + content ) `box-sizing: border-box;`

#### 2.2 重绘和重排(回流)
- 重绘：对元素的样式进行修改，比如color和background-color，浏览器不需要重新计算几何属性，直接绘制该元素的新样式，那么就只触发了重绘
- 重排：当一个元素自身的宽高、位置、显隐或元素内部的文字结构发生变化，导致需要重新构建页面，这个过程就是重排(也叫回流)。产生回流一定会造成重绘，但是重绘不一定会造成回流

#### 2.3 CSS选择器优先级
- !important > 内联样式(行间样式) > id选择器 > 类选择器 > 标签选择器 > 通配( * )

#### 2.4 实现元素的垂直居中
- 定位 + transform  `position: absolute; left: 50%; top: 50%; transform: translate(-50%, -50%);`
- 定位 + margin `position: absolute; left: 0; right: 0; top: 0; bottom: 0; margin: auto;`
- flex布局  `display: flex; align-items: center; justify-content: center;`

#### 2.5 什么是BFC
- BFC也就是块格式化上下文，是一个独立的容器，容器里的子元素不会影响到外面的元素
- 触发BFC：
  - float属性为left、right
  - position属性为absolute、fixed
  - display属性为inline-block、flex、grid、table-cell、table-caption
  - overflow属性为hidden、auto、scroll

#### 2.6 清除浮动有哪些方式(浮动塌陷)
- 元素浮动以后，脱离正常文档流，导致父元素无法被撑开(高度易陷)，且会影响后续正常布局
- 清浮动方法：
  - 给浮动元素的父元素添加一个伪元素	`.clearfix::after { content: ''; clear: both; display: table; }`
  - 触发BFC
  - 给浮动标签的父标签固定高度(不够灵活)

#### 2.7 margin塌陷
- 在两个盒子嵌套的时候，父盒子和子盒子同时设置margin的时候会出现实际的magin取的是两个margin的最大值
- 解决方法：
  - 给父元素添加一个伪元素	`.clearfix::after { content: ''; clear: both; display: table; }`
  - 触发BFC
  - 给父级设置边框或内边距

#### 2.8 隐藏元素的方法
- display: none;(不占位)	 visibility: hidden; (占位) 	opacity: 0; (占位)  position 移到外部，z-index 

### 3. JS
#### 3.1 JS数据类型
- 基本类型：String、Number、Boolean、Undefined、Null、Symbol
- 引用类型：Object、Function、Array
- 判断方式：
  - typeof()	只能判断基本数据  `console.log(typeof [1, 2, 3] ) // object`
  - instanceof()	只能判断引用数据类型  `console.log('abc'instanceof String) // false`
  - constructor `console.log(('abc').constructor=== String) // object`
  - `console.log(Object.prototype.toString.call('Hello')); // [object String]`

#### 3.2 闭包
- 函数嵌套函数，内部函数被外部函数返回并保存下来时，就会产生闭包  `function fn(a){ return function(){console.log(a)} }	var fo = fn('abcd')	fo()`
- 特点：可以重复利用变量，并且这个变量一直保存在内存中，不会被垃圾回收机制回收，不会污染全局
- 缺点：闭包较多的时候，会消耗内存，导致页面的性能下降
- 解决办法：把调用内部函数对象的变量设置为null

#### 3.3 内存泄漏
- 内存泄露是指程序由于某些原因未能及时释放不再需要的内存，导致内存使用不断增加，从而影响性能和用户体验
- 常见原因：一些未清除的定时器；过度的闭包；一些未声明直接赋值的变量

#### 3.4 什么是作用域，什么是作用域链？
- 作用域：作用域就像一个独立的空间，你只能在这个空间里使用里面的变量，这些变量在外部空间没办法使用
- 作用域链：作用域链就像是你在一个空间里找不到某个变量时，你就顺着作用域链一级一级往上找，先从你所在的作用域开始，然后去父作用域，再到更高的父作用域，一直到全局作用域

#### 3.5 什么是原型，什么是原型链？
- 原型：每个JS对象都有一个原型对象，它可以直接使用这个原型对象里的属性和方法
- 原型链：原型链是由多个原型对象构成的。当你在对象中找不到某个属性或方法时，JS会沿着原型链一个一个地往上查找，直到找到那个属性或方法，或者到达链的末尾

#### 3.6 数组去重方法
- 使用Set：`const uniqueArray = [...new Set(array)];`
- 使用Array.from与Set：`const uniqueArray = Array.from(new Set(array));`
- 使用filter和indexOf：`const uniqueArray = array.filter((item, index) => array.indexOf(item) === index); // 如果当前元素的索引位置与它在数组中第一次出现的位置一致，说明这是第一次出现，保留这个元素`	

#### 3.7 对象合并方法
- Object.assign：`const merged = Object.assign({}, obj1, obj2);`
- 使用扩展运算符：`const merged = { ...obj1, ...obj2 };`

#### 3.8 var、let、const
- var声明的变量不存在块级作用域，在全局范围内都有效，let、const声明的变量有块级作用域，只在它所在的代码块有效
- var声明的变量存在变量提升，let、const不存在
- var、let声明的变量可以重新赋值，const不可以
- var可以多次声明同一个变量，let、const不可以

#### 3.9 深拷贝
- JSON.parse(JSON.stringify(object))
- 扩展运算符。缺点：这个方法只能实现第一层，当有多层的时候还是浅拷贝
- 利用递归函数实现

#### 3.10 localStorage、sessionStorage、cookie
- 都是浏览器用于存储数据的机制
- localStorage：用于在客户端永久存储数据，数据在浏览器关闭后依然存在
- sessionStorage：存储数据在浏览器关闭后会被清除
- cookie：用于存储少量数据(最大4KB)，数据可以设置过期时间，通常用于认证信息等

#### 3.11 call、apply、bind
- 都用于改变函数的this指向
- call、apply都是立即执行，bind返回的是一个函数，需要被调用才能执行
- call、bind接受参数列表，apply接受参数数组

#### 3.12 get和post的区别
- get一般是获取数据，post一般是提交数据
- get参数会放在url上，所以安全性比较差，post是放在body中
- get请求时会被缓存，post请求不会被缓存

#### 3.13 箭头函数与普通函数的区别
- 普通函数是谁调用这个函数，this指向谁；箭头函数是在哪里定义函数，this指向谁，而且this不可修改
- 箭头函数不能new
- 箭头函数没有prototype
- 箭头函数没有arguments

#### 3.14 事件代理(事件委托)
- 利用事件冒泡机制来实现，将子元素的事件绑定到了父元素的身上。当子元素触发事件时，会冒泡到父元素，由父元素处理事件。提高了性能

#### 3.15 防抖和节流
- 都是应对页面中频繁触发事件的优化方案
- 防抖：事件触发后，如果在指定时间内又触发了相同事件，则重新开始计时。典型场景：搜索框搜索输入
- 节流：在设定的时间间隔内即使事件被频繁触发，也只执行一次函数。典型场景：高频点击事件、滚动事件、窗口大小调整

#### 3.16 图片懒加载
- 优先加载可视区的内容，其他部分等进入了可视区再加载，提高性能，减轻服务器压力
- 原理：在图片没有进入可视区域时，先不给<img>的src赋值，这样浏览器就不会发送请求，等到图片进入可视区域再给src赋值

#### 3.17 怎么解决异步回调地狱
- Promise.then()
- 使用async/await(Promise的语法糖)

#### 3.18 JS中的常用的继承方式
- 原型链继承、借用构造函数继承、组合式继承、ES6的class类继承

#### 3.19 class和普通构造函数的区别
- 普通构造函数：定义类时需要手动在prototype上添加方法，这些方法默认是可以被列举出来的，管理起来相对复杂一些
- class：ES6引入的语法，可以直接在类内部定义方法，这些方法默认不会被列举出来，更容易管理

#### 3.20 服务端渲染和客户端渲染的区别
- 服务端渲染：就像餐厅里厨师在厨房里准备好整份饭菜，然后直接端到你面前。服务器把完整的网页准备好，发给你的浏览器，所以你一打开网页就能看到内容，加载速度快，但每次你刷新或访问新页面时，服务器都会重新准备内容
- 客户端渲染：就像你在餐厅点了个半成品，厨房给你的是一堆原料，你需要自己动手做成美食。浏览器先加载一个空的网页，然后用JS在浏览器里填充内容，这样页面的互动会更流畅，但初次打开网页时可能需要等一会儿，因为浏览器要先执行JS脚本

#### 3.21 宏任务和微任务都有哪些
- 宏任务：就像你安排了几个大任务，比如做饭、洗衣服、整理房间，每个任务都要做完后才能开始下一个。比如`<script>`标签里的脚本、定时器(`setTimeout`和`setInterval`)都算宏任务
- 微任务：是小任务，通常是你完成大任务后要做的额外工作，比如整理桌子上的小物件。微任务包括`promise.then`，`process.nextTick`。每次一个宏任务做完后，所有的微任务都会被处理完，然后才会开始下一个宏任务

#### 3.22 延迟JS加载的方式
- `<script defer src="script.js"></script>`
- `<script async src="script.js"></script>`

### 4. VUE
#### 4.1 MVVM和MVC
- MVC
  - Model：处理数据和逻辑
  - View：显示数据，不负责逻辑
  - Controller：处理用户输入，更新数据和视图
- MVVM
  - Model：处理数据和逻辑
  - View：通过数据绑定与ViewModel互动
  - ViewModel：管理数据和操作，但不直接操作DOM
- 区别：
  - MVC中使用Controller处理输入和更新，数据和视图的同步需要手动管理
  - MVVM中使用ViewModel处理输入和数据更新，自动同步数据和视图。更适合动态更新的数据驱动应用

#### 4.2 MVVM框架和jQuery框架有什么区别
- MVVM：专注于处理数据的变化，比如添加、删除、更新数据，能自动把数据和网页上的内容同步起来，适合做复杂的单页应用（SPA）
- jQuery：擅长操作网页上的元素，比如改变样式、动画效果等，需要手动去更新页面上的内容，适合做简单的页面交互和快速搭建原型

#### 4.3 SPA单页面应用和传统页面跳转有什么区别？
- 单页面应用：一个系统只加载一次资源，之后的操作交互、数据交互是通过路由、ajax来进行，页面并没有刷新
- SPA跳转是一个页面进行切换，传统页面跳转就是跳转不同的html 
- SPA对于SEO不是特别好，只能收录一个，传统的页面对于SEO比较好，多个html文件收录

#### 4.4 Vue的双向绑定原理
- 通过Object.defineProperty劫持数据发生的改变，如果数据发生改变了，触发update方法进行更新节点内容，从而实现了数据双向绑定。

#### 4.5 Vue优缺点
- Vue的两个核心系统：数据驱动、组件系统
- 优点：MVVM、数据驱动、组件化、轻量、简洁、高效、快速、模块友好。
- 缺点：1.不支持低版本的浏览器，最低只支持到IE9；2.不利于SEO优化；3.第一次加载首页耗时相对较长

#### 4.6 Vue的生命周期
- `beforeCreate、created、beforeMount、mounted、beforeUpdate、updated、beforeDestroy、destroyed`
- 一旦进入到页面或组件，会执行`beforeCreate、created、beforeMount、mounted`
- 父组件引入子组件，那么生命周期执行的顺序是`父：beforeCreate、created、beforeMount，子：beforeCreate、created、beforeMount、mount、mounteed，父：mounted`
- 如果加入了keep-alive(缓存组件)会多两个生命周期`activated、deactivated`，第一次进入组件会执行`beforeCreate、created、beforeMount、mounted、activated`，第二次或第N次进入组件会执行`activated`

#### 4.7 导航守卫有哪些
- 全局守卫：`beforeEach、beforeResolve、afterEach`
- 路由独享守卫：`beforeEnter`
- 组件内守卫：`beforeRouteEnter、beforeRouteUpdate、beforeRouteLeave`
 
#### 4.8 组件传值
- 父传子：父组件通过`props`向子组件传递数据
- 子传父：子组件通过`$emit`方法向父组件发送事件。子组件触发事件时，可以附带数据，父组件通过监听事件来获取数据
- 组件之间：vuex、eventbus、本地存储

#### 4.9 Vue-router的模式
- hash模式：带 # ，hash虽然出现在URL中，但不会被包含在HTTP请求中，对后端完全没有影响，因此即使没有做到对路由的全覆盖，也不会返回404错误
- history模式：一旦刷新的话，有可能会404，因为没有当前的真正路径，需要后端配合将不存在的路径重定向到入口文件

#### 4.10 v-if和v-for的优先级
- Vue2中：v-for的优先级比v-if高，Vue3中：v-if的优先级比v-for高
- v-if和v-for不要写在同一个节点上，v-if要写在父节点上

#### 4.11 Vue检测不到数组的改变怎么解决
- `vm.arr.splice(index, 1, newValue)`
- `vm.$set(vm.arr, index, newValue)`
- `Vue.set(vm.arr, index, newValue)`

#### 4.12 computed、watch、methods
- computed：计算属性，可以监听某些数据的变化，并且有缓存。只有监听的数据发生变化才会重新进行计算。如果一进入页面调用，就会触发
- methods：可以放入函数，没有缓存。如果一进入页面调用，就会触发
- watch：监听属性，当数据发生改变时，才会触发。可以得到现在的值和过去的值

#### 4.13 vue.$nextTick()
- 当DOM更新完毕执行内部代码

#### 4.14 props和data优先级
- props > methods > data > computed > watch

#### 4.15 Vuex
- Vuex用来集中管理应用里的所有状态数据
- State：是数据仓库，所有组件都能从这里取数据
- Getters：是用来从数据仓库里提取和计算信息的工具
- Mutations：是用来直接更改数据仓库内容的方法
- Actions：是处理异步操作的地方，然后调用mutations来更新仓库里的数据
- Modules：如果数据和方法太多，可以把它们分成几个小模块，每个模块自己管理自己的数据和方法，适合大型应用
- 持久化存储：Vuex里的数据只保存在内存中，当页面刷新时，数据会丢失。为了保存数据，可以用localStorage、cookies，或使用vuex-persistedstate插件来解决这个问题

#### 4.16 什么是虚拟DOM
- 虚拟DOM就像是在内存中搞了一个虚拟的网页副本，当我们做一些页面更新时，框架会先在这个虚拟副本上进行更改，然后再把需要变化的应用到真正的网页上。这样做能让页面更新变得更快，更流畅。就像先在草稿纸上画图，再把有改动的地方放到正式图上

#### 4.17 Vue跨域问题怎么处理
- 在vue.config.js中配置代理
  ```
  module.exports = {
    devServer: {
      proxy: {
        '/api': {
          target: 'http://localhost:3000',  // 后端 API 的地址
          changeOrigin: true,
          pathRewrite: { '^/api': '' }  // 如果后端不需要 '/api' 前缀
        }
      }
    }
  };
  ```

### 5. VUE 3
#### 5.1 Vue3和Vue2的区别
- 双向绑定方法不同
  - Vue2：`Object.defineProperty()` 后添加的属性是劫持不到的
  - Vue3：`new Proxy()` 即使后添加的也可以劫持到，还不需要循环。Vue3中没有$set，new Proxy不需要
- Vue2中组件只能有一个根节点，Vue3引入了Fragment，允许组件有多个根节点
- Vue2使用选项式API，Vue3使用组合式API，代码更整洁
- Teleport组件允许将子组件渲染到DOM中的任何位置
- 更好的TypeScript支持
- 使用了更小的包体积和更高效的运行时性能

#### 5.2 Vue3中响应式系统的实现方式与Vue2有什么不同？
- Proxy可以拦截和监控对对象属性的访问和修改，因此它能够处理Vue2无法高效处理的一些场景，如数组的直接修改、对嵌套对象的深层次监听等

#### 5.3 Vue3的生命周期钩子有哪些变化？
- Vue3继续支持Vue2的生命周期钩子，但将`beforeDestroy`和`destroyed`改名为`beforeUnmount`和`unmounted`
- 在组合式API中，生命周期钩子被函数化，可以在setup()函数中使用
- 对应关系：
  - `beforeCreate -> setup()`
  - `created -> setup()`
  - `beforeMount -> onBeforeMount`
  - `mounted -> onMounted`
  - `beforeUpdate -> onBeforeUpdate`
  - `updated -> onUpdated`
  - `beforeDestroy -> onBeforeUnmount`
  - `destroyed -> onUnmounted`

#### 5.4 Composition API的新特性是什么？
- Composition API主要包含了`ref，reactive，setup，computed，watch`等新的函数和特性。

#### 5.5 Composition API如何使用响应式数据？
- 可以通过reactive或ref函数来创建响应式数据，reactive适用于对象，ref适用于基本类型和单一值。

#### 5.6 Composition API如何实现props的响应式？
- 使用defineProps函数来定义响应式的props

#### 5.7 Vue3中的Teleport是什么？
- Teleport就像是一个传送门，可以把组件的内容从页面的一个地方移动到另一个地方显示。适合用来处理Modal、弹窗等，不用担心布局和层级问题

#### 5.8 Vue3中的Fragment是什么？
- Fragment允许组件有多个根节点。在Vue2中组件只能有一个根节点， Vue3中组件可以有多个根节点

#### 5.9 Vue3中Suspense是什么？
- Suspense就像是一个加载提示器，帮助你处理异步组件的加载过程。用它包裹异步组件时，可以设置一个占位符或加载动画，这样在等待组件加载完成时，用户看到的不会是空白的页面或卡顿，而是一个友好的提示，直到内容准备好

#### 5.10 Vue3中的watch和watchEffect有何不同？
- 都是用来监视数据变化的工具
- 区别：
  - watch：你得告诉它具体要监视哪些数据，只有这些数据变了，它才会执行回调函数。初始化的时候不会执行回调，只在数据变化时执行
  - watchEffect：它会自动追踪回调函数中用到的所有响应式数据，并在这些数据变化时执行回调。初始化时会立即执行一次回调

#### 5.11 Vue3中的provide和inject是什么？
- provide和inject可以在组件树的不同层级之间轻松传递数据，不需要逐层通过props传递

### 6. 小程序
#### 6.1 小程序的生命周期函数有哪些？
- 应用生命周期
  - onLaunch：当小程序初始化完成时触发，全局只触发一次
  - onShow：当小程序启动或从后台进入前台显示时触发
  - onHide：当小程序从前台进入后台时触发
  - onError：当小程序发生错误时触发
  - onPageNotFound：当页面不存在时触发
- 页面生命周期
  - onLoad：页面加载时触发
  - onReady：页面初次渲染完成时触发
  - onShow：页面显示时触发
  - onHide：页面隐藏时触发
  - onUnload：页面卸载时触发
  - onPullDownRefresh：用户下拉刷新时触发
  - onReachBottom：页面滚动到底部时触发
  - onShareAppMessage：点击分享按钮时触发

#### 6.2 如何在小程序中实现页面跳转？
- wx.navigateTo：保留当前页面，跳转到应用内的某个页面，但不能跳转到tabBar页面
- wx.redirectTo：关闭当前页面，跳转到应用内的某个页面
- wx.switchTab：跳转到 tabBar 页面，并关闭其他所有非tabBar页面
- wx.navigateBack：关闭当前页面，返回上一页面或多级页面，可通过`getCurrentPages()`获取当前页面栈
- wx.reLaunch：关闭所有页面，跳转到应用内的某个页面

#### 6.3 如何处理小程序中的授权和用户登录？
- 用户首次进入小程序时，小程序可以调用wx.getUserProfile获取用户信息，并展示授权弹窗
- 用户同意授权后，小程序可以通过wx.login获取用户的登录凭证code
- 然后通过后台接口将code换取用户的openid、unionid、session_key，并进行登录状态的维护

#### 6.4 小程序的openid和unionid
- openid：在不同小程序拥有不同的openid
- unionid：在微信体系下的unionid是相同的

#### 6.5 什么是小程序的自定义组件？如何定义和使用它们？
- 定义组件：在*.js中定义逻辑、属性和方法；在*.json中配置组件；在*.wxml和*.wxss中设置结构和样式
- 使用组件：在页面的json文件中引入组件，然后在wxml中使用组件标签

#### 6.6 小程序如何与后台通信？
- 通过微信提供的wx.request方法来实现。这个方法支持发送GET或POST请求，并可以携带参数。在请求成功后，后台返回的数据可以通过success回调函数来处理。

#### 6.7 小程序的页面间数据传递有哪些方式？
- 绑定事件传参：`data-name="John"  console.log(e.currentTarget.dataset.name);`
- 页面传参：`wx.navigateTo`问号传参，在目标页面通过onLoad函数的options参数获取传递的数据 `onLoad: function(options) { console.log(options.[key名]); }`
- globalData：
  ```
  // 在当前页面中设置全局数据
  const app = getApp();
  app.globalData = {
    name: 'John',
  };
  目标页面：
  const app = getApp();
  console.log(app.globalData.name); // 输出: John
  ```
- 本地存储：`wx.setStorageSync() wx.getStorageSync()`
- 自定义事件

#### 6.8 小程序的页面有哪些文件组成？各自的作用是什么？
- .json：页面配置文件，用于配置页面的窗口表现、导航栏等。
- .wxml：页面结构文件，用于描述页面的结构和内容。
- .wxss：样式文件，用于控制页面的样式和布局。
- .js：逻辑文件，用于处理页面的交互逻辑、数据处理等。

#### 6.9 如何在小程序中处理图片的预览和上传？
- 图片预览可以通过wx.previewImage方法实现，它接收一个对象作为参数，其中urls是预览的图片链接数组。
- 图片上传可以使用wx.chooseImage选择图片，再通过wx.uploadFile方法将图片上传到服务器。上传时可以携带额外的表单数据，上传成功后会返回图片的地址或其他信息。

#### 6.10 什么是小程序的模板（template）？如何使用它们？
- 小程序的模板（template）类似于组件，但它们只是静态的代码片段，可以在多个页面中复用。可以减少重复代码，提高开发效率。
- 使用模板时，首先需要在wxml文件中通过`<template>`标签定义模板，然后在需要的地方通过`<import>`引入模板，并使用`<template is="模板名" data="数据"/>`进行渲染。

#### 6.11 如何实现小程序的分享功能？
- 通过在页面的onShareAppMessage方法中进行配置。当用户点击右上角的“分享”按钮时，会触发该方法，开发者可以在此方法中返回自定义的分享内容，包括标题、路径和图片等。
- 分享时，也可以在onShareAppMessage的回调中携带参数，从而实现个性化的分享链接。

#### 6.12 如何实现小程序的下拉刷新？
- 在页面`.json`配置中设置`enablePullDownRefresh: true;`
- 在`Page`中定义`onPul1DownRefresh`钩子函数
- 当处理完数据刷新后，`wx.stopPullDownRefresh`停止下拉刷新

#### 6.13 小程序中如何实现数据的持久化？
- 本地缓存 `wx.setStorageSync、wx.getStorageSync、wx.setStorage、wx.getStorage、wx.clearStorageSync、wx.clearStorage`

#### 6.14 如何在小程序中实现一个自定义导航栏？
- 在app.json中的tabBar项添加`custom: true,`，同时其余tabBar相关配置也补充完整 
- 在代码根目录下添加`custom-tab-bar`文件，编写tabBar代码  `custom-tab-bar/index.js custom-tab-bar/index.json custom-tab-bar/index.wxml custom-tab-bar/index.wxss`

#### 6.15 小程序中的setData方法有什么作用？
- setData方法用于更新页面的数据并触发视图的重新渲染。
- 频繁调用setData可能会导致性能问题，应避免在短时间内多次调用。
- setData只能更新已经在data中定义过的属性，未定义的属性需要先在data中声明。
- 尽量只更新必要的数据，避免过多的无关数据引起不必要的渲染。

#### 6.16 什么是小程序的WXS？它与JS有何不同？
- WXS（WeiXin Script）是小程序中用于编写逻辑的一种脚本语言，具有更高的执行性能和独立的运行环境。
- 区别：
  - WXS不能操作DOM和BOM。
  - WXS文件是单独编译的，不能与页面的js文件共享数据。
  - WXS的执行环境与页面的JavaScript执行环境不同，它没有页面的上下文。

#### 6.17 小程序如何处理页面的滚动事件？
- 使用bindscroll绑定事件处理函数。可以在wxml文件中绑定scroll事件，例如`<scroll-view bindscroll="onScroll" />` 在js文件中，定义onScroll函数来处理滚动事件，如获取滚动位置、处理加载更多等。

#### 6.18 如何在小程序中实现分页加载？
- 使用wx.request发送请求，获取当前页的数据。
- 在请求成功后，将数据追加到已有数据中。
- 记录当前页码，当用户触发加载更多事件时（如滚到底部），更新页码并发送请求获取下一页数据。
- 需要注意处理加载状态、空数据等情况，避免重复加载。

#### 6.19 小程序中的组件如何实现通讯？
- 属性传递：父组件通过properties向子组件传递数据。
- 事件传递：子组件通过this.triggerEvent触发自定义事件，父组件通过事件绑定处理。
- 使用this.selectComponent：在父组件中通过this.selectComponent获取子组件实例，调用子组件的方法。

#### 6.20 小程序中如何实现用户权限管理？
- 使用wx.getSetting获取用户的授权状态。
- 使用wx.authorize请求用户授权特定权限。
- 根据用户授权状态，控制应用的功能访问，例如相册、位置、通讯录等。

#### 6.21 bindtap和catchtap的区别是什么
- 都是点击事件函数，bindtap不会组织冒泡，catchtap阻止冒泡
