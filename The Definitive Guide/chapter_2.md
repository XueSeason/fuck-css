# 结构和层叠

## 特殊性

选择器的特殊性由选择器本身的组件决定

- 内联样式 1 0 0 0
- id 选择器 0 1 0 0
- class 和属性选择器 0 0 1 0
- 元素选择器和伪元素选择器 0 0 0 1
- 通配选择器 0 0 0 0

**!import** 发生特殊性冲突，需要与非重要声明分开考虑。

## 继承

继承没有特殊性，浏览器样式表权重可能会更高。

## 层叠

1. 按权重和来源排序
1. 按特殊性排序
1. 按顺序排序
