---
layout: 'guide'
title: 'Themes'
menuOrder: 3
---

# Themes

> 主题们

主题允许您更改生成的文档的外观。您可以使用其中一个已包含的主题,根据需要进行修改或创建完全自定义主题。该`--theme`参数允许您在创建文档时选择主题:

```bash
$ typedoc --theme <default|minimal|path/to/theme>
```

您必须提供有效主题目录的路径或内置主题的名称。如果你不提供`--theme`参数,主题`default`将会被使用。

## Built-in themes

> 内置 主题

TypeDoc 附带两个主题,因此您可以立即开始创建文档:

- `default`- 这是 TypeDoc 使用的标准主题。它旨在用于大中型项目。它为项目中的每个模块,类,接口和枚举创建一个单独的 html 文件。它支持按不同标准过滤显示的成员,它包括一个简单的搜索.

- `minimal`- 此主题旨在用于较小的项目。它非常便携,因为它将整个文档呈现为一个大的 html 文件,包括样式表或图像等所有必需的资源。与默认主题一样,它也支持按不同标准过滤显示的成员。

## Custom themes

> 自定义 主题

在 TypeDoc 中创建自定义主题非常简单。基本上你创建一个目录。并覆盖`default`组件主题中你想要改变。所有主题都是扩展了默认主题,因此您只需更改不符合您需求的部分。

这是主题的基本目录结构,只有 assets 目录是必需的:

```
+ my-theme             // 主题的根目录
  + assets             // 静态资产，如 *.css或 *.js文件
  + layouts            // 可选的。 布局模板
    - default.hbs      // 可选的。 默认布局模板
  + partials           // 可选的。 Handlebar使用的部分
  + templates          // 可选的。 页面模板
    - index.hbs        // 可选的。 主页模板
    - reflection.hbs   // 可选的。 定义页面模板
  - theme.js           // 可选的。 主题的JavaScript类
```
