# 字体

## 字体系列

```html
<div style="font-family: serif;">click me! - 中文 - Serif</div>
<div style="font-family: sans-serif;">click me! - 中文 - Sans-serif</div>
<div style="font-family: monospace;">click me! - 中文 - Monospace</div>
<div style="font-family: cursive;">click me! - 中文 - Cursive</div>
<div style="font-family: fantasy;">click me! - 中文 - Fanstasy</div>
<div style="font-family: 'Times New Roman', Times, serif">click me! - 中文</div>
```

## 字体加粗

```css
/* 也是可以使用具体数值 100 200 ... 900 */
b { font-weight: bold; }
```

假设常规文本用 Times 显示，实际上使用同一种字体的两种变形来显示效果：**Times** 和 **TimesBold**。

**bolder** 和 **lighter** 能够让字体更粗或者更细。最高上限为 900 最低下限为 100。

## 字体大小

指定字体大小其实是指定字体 em 框的大小，不同字体的 em 框由字体设计者决定。数值 1em 等于数值 100%。

## 字体风格

```css
p { font-style: normal; }
/* 斜体 */
em { font-style: italic; }
/* 倾斜 */
i { font-style: oblique; }
```

italic 和 oblique 两者有时候区分度不大，需要字体和浏览器的支持。

## 字体变形

```css
/* 将小写字母转换为小型大写字母 */
h1 { font-variant: small-caps; }
span { font-variant: normal; }
```

## 字体简写

font 前三个值可以采取任意顺序(font-style, font-weight, font-variant)，也可以不写，但是 **font-size** 和 **font-family** 必须在结尾，而且顺序固定(font-size 在前，font-family 在后)。

如果引入行高，需要紧随 **font-size** 之后，并且通过 / 分隔。
