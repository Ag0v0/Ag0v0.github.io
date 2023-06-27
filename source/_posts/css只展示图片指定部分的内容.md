---
title: css只展示图片指定部分的内容
date: 2023-06-26 10:20:05
categories:
  - 前端
tags:
  - css
  - 图片
---

## css 只展示图片指定部分的内容

##### 1、使用 `background-position `属性

可以使用 CSS 的 `background` 属性将图片设置为元素的背景，并使用 `background-position` 属性来控制要显示的部分。

下面是一个示例 CSS 代码块，展示了如何将图片的左上角部分设置为元素的背景，然后将其向右下方移动 50 像素：

```css
div {
  width: 200px;
  height: 200px;
  background-image: url("your-image.jpg");
  background-repeat: no-repeat;
  background-position: 50px 50px;
}
```

这将创建一个宽度为 200 像素、高度为 200 像素的 `div` 元素，并将其背景设置为 `your-image.jpg`。`background-repeat` 属性设置为 `no-repeat` 表示图片不应该被重复显示。最后，`background-position` 属性将图片向右下方移动了 50 像素。你可以根据需要调整 `background-position` 属性的值来控制要显示的部分。

##### 2、使用 `clip` 属性

通过设置四个参数来裁剪元素的显示区域，从而控制要显示的部分。

下面是一个示例 CSS 代码块，展示了如何将图片的左上角部分设置为元素的显示区域，然后将其移动到页面的左上角：

```css
img {
  position: absolute;
  clip: rect(0px, 50px, 50px, 0px);
  top: 0;
  left: 0;
}
```

这将创建一个 img 元素，并将其设置为绝对定位。clip 属性的参数使用 rect 函数来设置，其中第一个参数是裁剪区域的顶部位置，第二个参数是右侧位置，第三个参数是底部位置，第四个参数是左侧位置。在这个示例中，我们将裁剪区域设置为图片的左上角部分，因此其顶部位置为 0 像素，右侧位置为 50 像素，底部位置为 50 像素，左侧位置为 0 像素。top 和 left 属性将图片移动到页面的左上角。

你可以根据需要调整 clip 属性的值来控制要显示的部分。注意，clip 属性只适用于绝对定位的元素。

##### 3、使用 `object-position` 属性

下面是一个示例 CSS 代码块，展示了如何将图片的左上角部分设置为 `img` 元素的显示区域：

```css
img {
  width: 200px;
  height: 200px;
  object-fit: none;
  object-position: 0px 0px;
}
```

这将创建一个宽度为 200 像素、高度为 200 像素的 `img` 元素，并将其 `object-fit` 属性设置为 `none`，以防止图片被缩放。`object-position` 属性将图片的左上角设置为 `img` 元素的显示区域，从而只显示图片的左上角部分。

你可以根据需要调整 `object-position` 属性的值来控制要显示的部分。
