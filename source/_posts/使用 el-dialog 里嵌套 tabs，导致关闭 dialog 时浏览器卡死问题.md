---
title: 使用 el-dialog 里嵌套 tabs，导致关闭 dialog 时浏览器卡死问题
date: 2023-06-26 10:04:42
categories:
  - 前端
tags:
  - Element-ui
  - el-dialog
---

## 使用 el-dialog 里嵌套 tabs，导致关闭 dialog 时浏览器卡死问题

_解决办法：_

- 给 tab 添加 v-if ，判断条件与 dialog 的 visible 属性值一致

```xml
<el-dialog :visible.sync="linkSelecterShow">
  <el-tabs v-model="activeName" v-if="linkSelecterShow">
    <el-tab-pane label="用户管理" name="first">用户管理</el-tab-pane>
    <el-tab-pane label="配置管理" name="second">配置管理</el-tab-pane>
    <el-tab-pane label="角色管理" name="third">角色管理</el-tab-pane>
    <el-tab-pane label="定时任务补偿" name="fourth">定时任务补偿</el-tab-pane>
  </el-tabs>
</el-dialog>
```
