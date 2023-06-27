---
title: 处理canvas使用外部字体，外部字体加载不及时
date: 2023-06-26 10:04:42
categories:
  - 前端
tags:
  - canvas
---

## 处理 canvas 使用外部字体，外部字体加载不及时

```javascript
async mounted() {
    const font = new FontFace(
      "字体名称",
      `url(${require("字体路径")})`
    );
    await font.load();
    document.fonts.add(font);
    document.fonts.ready.then(() => {
      // 字体加载完成执行的代码
    });
  },
```
