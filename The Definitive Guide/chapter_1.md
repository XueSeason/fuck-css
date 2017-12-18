# 第二章

## 规则结构

CSS 每个规则都有两个基础模块：

1. 选择器 (selector)
1. 声明块 (declaration block)

## 元素选择器

文档的元素就是最基本的选择器

```css
html { color: black; }
h1 { color: red; }
p { color: gray; }
```

选择器分组，可以将多个选择器分组在一起

```css
html h1 p { color: black; }
```

## 通配选择器

作用于文档所有元素

```css
* { color: red; }
```

## 类选择器

要应用样式而不具体涉及元素，最常用的方法是使用类选择器。直接引用元素 class 属性的值，通过**点号(.)**标记。

```css
.info { color: blue; }
button.info { background-color: blue; }
```

多类选择器

```css
button.info.help { background: red; }
```

## ID 选择器

类似于类选择器，点号被 `#` 符号代替，且 ID 在页面中应该是唯一的。

```css
#app { color: red; }
```

## 属性选择器

```html
<p class="urgent warning">Hello World</p>
```

```css
p[class] { color: red; }
/* 根据部分属性值选择 */
p[class~="warning"] { font-weight: bold; }
/* 子串匹配属性选择器 */
p[class^="urgent"] /* class 属性为 urgent 开头 */
p[class$="warning"] /* class 属性为 warning 结尾 */
p[class*="urgent"] /* class 属性包含 urgent 字符串 */
```

特定属性选择类型

```html
<h1 lang="en">Hello</h1>
<h1 lang="en-US">Hello</h1>
```

```css
/* 所有 lang 属性为 en 或者 en- 开头的元素 */
*[lang|="en"] { color: "white" }
```

## 层级关系

```css
/* 选择子元素 */
h1 > strong { color: red; }
/* 选择相邻兄弟元素 */
h1 + p { margint-top: 0; } /* h1 和 p 同级，而且 p 位于 h1 之后 */
```

## 伪类选择器

```css
/* 必须拥有 href 属性的超链接 */
a:link { color: blue; }
a:visited { color: red; }
a:hover { color: yellow; }
a:active { color: white; }
```

伪类顺序：

link-visited-focus-hover-active

## 伪元素选择器

```css
p::first-letter { color: red; }
h2::first-letter { font-size: 200%; }
```
