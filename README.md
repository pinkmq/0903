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
