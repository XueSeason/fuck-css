# 文本属性

## 缩进文本

```css
p { text-indent: 1em; }
/* 相对于父元素的宽度计算 */
p { text-indent: 10%; }
```

text-indent 可以继承。

## 水平对齐

text-align

## 垂直对齐

### 行高

`line-height` 属性是**文本行基线之间的距离**，line-height 的值减去**字体大小**就是行间距。

line-height 可以被继承。

### 垂直对齐文本

`vertical-align` 用于行内元素和替换元素，且不能被继承。

#### 基线对齐

```css
p { vertical-align: baseline; }
```

默认对齐方式。

#### 上标和下标

```css
.up { vertical-align: super; }
.down { vertical-align: sub; }
```

配合 `font-size` 可以达到展示构造数学公式的效果。

#### 底端对齐

```css
.feeder { vertical-align: bottom; }
```

同样的还有 `top`, `text-top` 以及 `text-bottom`

#### 居中对齐

```css
img { vertical-align: middle; }
```

多用于图片。

### 字间距和字母间距

```css
p { word-spacing: 1em; }
span { letter-spacing: 1em; }
```

默认为 normal，绝对长度为 0。

### 文本转换

```css
/* 其他值 lowercase capitalize none */
span { text-transform: uppercase; }
```

### 文本装饰

```css
/* underline overline line-through blink inherit */
span { text-decoration: none; }
```
