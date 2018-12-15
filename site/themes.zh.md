---
layout: 'guide'
title: 'Themes'
menuOrder: 3
---
# Themes

主题允许您更改生成的文档的外观.您可以使用其中一个包含的主题,根据需要进行修改或创建完全自定义主题.该`--theme`参数允许您在创建文档时选择主题:

```bash
$ typedoc --theme <default|minimal|path/to/theme>
```

您必须提供有效主题目录的路径或内置主题的名称.如果你不提供`--theme`参数,主题`default`将会被使用.

## Built-in themes

TypeDoc附带两个主题,因此您可以立即开始创建文档:

-   `default`- 这是TypeDoc使用的标准主题.它旨在用于大中型项目.它为项目中的每个模块,类,接口和枚举创建一个单独的html文件.它支持按不同标准过滤显示的成员,它包括一个简单的搜索.

-   `minimal`- 此主题旨在用于较小的项目.它非常便携,因为它将整个文档呈现为一个大的html文件,包括样式表或图像等所有必需的资源.与默认主题一样,它支持按不同标准过滤显示的成员.

## Custom themes

在TypeDoc中创建自定义主题非常简单.基本上你创建一个目录并覆盖它的组件`default`你想要改变的主题.所有主题都扩展了默认主题,因此您只需更改不符合您需求的部分.

这是主题的基本目录结构,只有assets目录是必需的:

```
+ my-theme             // Root directory of your theme
  + assets             // Static assets like *.css or *.js files
  + layouts            // Optional. Layout templates
    - default.hbs      // Optional. Default layout template
  + partials           // Optional. Partials to be used by Handlebar
  + templates          // Optional. Page templates
    - index.hbs        // Optional. Home page template
    - reflection.hbs   // Optional. Definition page template
  - theme.js           // Optional. JavaScript class of the theme
```
