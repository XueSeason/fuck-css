# CSS 和文档

CSS 优点

1. 丰富的样式
1. 易于使用
1. 在多个页面上使用样式
1. 层叠
1. 缩减文件大小

## 元素

- 替换元素，元素内容不是由文档内容直接表示，例如 img 元素。
- 非替换元素，大多数 HTML 元素都是非替换元素。

- 块级元素，默认填充父元素的内容区，旁边不能有其他元素。替换元素可以是块级元素，不过通常都不是。
- 行内元素，在文本行内生成元素框，不会打断这行文本。

## 引入 CSS

### 外部引入

```html
<head>
  <link rel="stylesheet" href="style.css" type="text/css" media="all">
</head>
```

link 必须放在 head 元素中

1. rel 代表关系 **relation**
1. href 是样式表的 URL
1. type 总是 **text/css** 这个值描述了 link 加载数据的类型
1. media 属性，这里使用 all，说明样式表应用于所有表现媒体。其他常用的还有 print 和 screen，前者用于打印机和打印预览，后者用于 Web 浏览器。

定义候选样式表，需要将 rel 设置为 **alternate styleshett**，浏览器会使用 link 元素的 **title** 属性生成候选样式列表。如果没有 title，默认将作为永久样式表，始终用于文档的显示。

```html
<link rel="alternate stylesheet" title="Default" type="text/css" href="style.css">
<link rel="alternate stylesheet" title="Big Text" type="text/css" href="bigtext.css">
```

候选样式表需要浏览器的支持，可以选择指定加载相关 CSS。Chrome 至今没有支持。

### Style 元素

使用 style 元素包含样式表，style 一定要使用 type 属性，对于 css 正确的 type 属性值为 **text/css**，这点与 link 相似。

```html
<style type="text/css">
.h1 { color: red; }
</style>
```

style 也可以指定 media 属性，与 link 的 media 属性值相同。

我们将 style 元素内的样式称之为**文档样式表**或者**嵌套样式表**

#### @import 指令

```css
@import url(style.css);
```

与 link 类似，@import 告诉 Web 浏览器加载一个外部样式表，并作用于文档显示。

区别在于命令的具体语法和位置，同时 link 是可以并行加载，@import 则是顺序加载。

可以限制导入的样式表用于指定媒体：

```css
@import url(style.css) all;
@import url(style1.css) screen;
@import url(style2.css) print;
```

还要注意的是，@import 指令必须出现在样式表的首部，否则兼容浏览器会将其忽略。

#### 向后可访问性

对于无法识别 `<style>` 和 `</style>` 的浏览器，会忽略其元素。但是标记中声明不一定会被忽略，对于浏览器，这些看上去就像正常的文本，所以样式声明会出现在页面的最上面。

所以一般如下进行注释标记：

```html
<style type="text/css">
<!--
.h1 { color: red; }
-->
</style>
```

### 内联样式

在 HTML 元素中通过 style 属性来设置内联样式。内联 style 属性只能放在一个声明块，不能放整个样式表。所以不能在 style 属性中使用 @import 指令。

样式放在 style 属性中会抵消 CSS 一些重要的优点，内联样式并不比 font 强多少，所以不推荐使用。