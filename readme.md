# TypeStrong/typedoc [![explain]][source] [![translate-svg]][translate-list]

<!-- [![size-img]][size] -->

[explain]: http://llever.com/explain.svg
[source]: https://github.com/chinanf-boy/Source-Explain
[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list
[size-img]: https://packagephobia.now.sh/badge?p=Name
[size]: https://packagephobia.now.sh/result?p=Name

「 TypeScript 项目的文档生成器 」

[中文](./readme.md) | [english](https://github.com/TypeStrong/typedoc)

---

## 校对 🀄️

<!-- doc-templite START generated -->
<!-- repo = 'TypeStrong/typedoc' -->
<!-- commit = 'e650aa7ec56f6b6ef5cbef2d3feddf6d7ee967bf' -->
<!-- time = '2018-12-11' -->

| 翻译的原文 | 与日期        | 最新更新 | 更多                       |
| ---------- | ------------- | -------- | -------------------------- |
| [commit]   | ⏰ 2018-12-11 | ![last]  | [中文翻译][translate-list] |

[last]: https://img.shields.io/github/last-commit/TypeStrong/typedoc.svg
[commit]: https://github.com/TypeStrong/typedoc/tree/e650aa7ec56f6b6ef5cbef2d3feddf6d7ee967bf

<!-- doc-templite END generated -->

### 贡献

欢迎 👏 勘误/校对/更新贡献 😊 [具体贡献请看](https://github.com/chinanf-boy/chinese-translate-list#贡献)

## 生活

[help me live , live need money 💰](https://github.com/chinanf-boy/live-need-money)

---

# TypeDoc

> TypeScript 项目的文档生成器.

[![Build Status](https://travis-ci.org/TypeStrong/typedoc.svg?branch=master)](https://travis-ci.org/TypeStrong/typedoc)
[![NPM Version](https://badge.fury.io/js/typedoc.svg)](http://badge.fury.io/js/typedoc)
[![Chat on Gitter](https://badges.gitter.im/TypeStrong/typedoc.svg)](https://gitter.im/TypeStrong/typedoc?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## 安装

TypeDoc 在 Node.js 上运行,可作为 NPM 包使用.您可以像往常一样在项目目录中安装 TypeDoc:

```bash
$ npm install typedoc --save-dev
```

与 TypeScript 编译器一样,TypeDoc 附带一个二进制文件,如果将 TypeDoc 安装为全局模块,则可以从任何位置调用该二进制文件.可执行文件的名称是`typedoc`.

```bash
$ npm install typedoc --global
$ typedoc
```

## 用法

### Shell

TypeDoc 接受 TypeScript 编译器接受的大多数命令行参数.一个主要区别是,可以将整个目录而不是单个文件传递给文档生成器.因此,要为整个项目创建文档,只需键入:

```bash
$ typedoc --out path/to/documentation/ path/to/typescript/project/
```

### 重要的提示

从版本 0.2 开始,TypeDoc 不再能够预测文件是应该被视为模块还是应该将项目编译成一个大的命名空间.你必须指定`mode`参数是为了改变 TypeDoc 的行为.

### 参数

- `--out <path/to/documentation/>`<br>指定文档应写入的位置.
- `--mode <file|modules>`<br>指定用于编译项目的输出模式.
- `--options`<br>指定应加载的 js 选项文件.如果未指定,TypeDoc 将在当前目录中查找"typedoc.js".
- `--json <path/to/output.json>`<br>指定描述项目写入的 json 文件的位置和文件名.指定时,不会生成任何文档.
- `--ignoreCompilerErrors`<br>即使编译器返回错误,TypeDoc 是否仍会生成文档页面?

#### 源文件处理

- `--exclude <pattern>`<br>当路径作为源提供时,按给定模式排除文件.支持标准迷你匹配模式(参见[#170](https://github.com/TypeStrong/typedoc/issues/170))
- `--includeDeclarations`<br>打开.d.ts 声明文件的解析.
- `--externalPattern <pattern>`<br>为应该被视为外部的文件定义模式.
- `--excludeExternals`<br>防止记录外部解析的 TypeScript 文件.
- `--excludePrivate`<br>防止私有成员包含在生成的文档中.
- `--excludeProtected`<br>防止受保护的成员包含在生成的文档中.

#### TypeScript 编译器

- `--module <commonjs, amd, system or umd>`<br>指定模块代码生成:"commonjs","amd","system"或"umd".
- `--target <ES3, ES5, or ES6>`<br>指定 ECMAScript 目标版本:"ES3"(默认),"ES5"或"ES6"
- `--tsconfig <path/to/tsconfig.json>`<br>指定应加载的 typescript 配置文件.如果未指定,TypeDoc 将在当前目录中查找"tsconfig.json".

#### 主题化

- `--theme <default|minimal|path/to/theme>`<br>指定应使用的主题的路径.
- `--name <Documentation title>`<br>设置将在模板标题中使用的项目的名称.
- `--readme <path/to/readme|none>`<br>应在索引页面上显示的自述文件的路径.通过`none`禁用索引页面并在 globals 页面上启动文档.
- `--plugin`<br>指定应加载的 npm 插件.省略加载所有已安装的插件,设置为"none"以不加载任何插件.
- `--hideGenerator`<br>不要在页面末尾打印 TypeDoc 链接.
- `--gaID`<br>设置 Google Analytics 跟踪 ID 并激活跟踪代码.
- `--gaSite <site>`<br>设置 Google Analytics 的网站名称.默认为`auto`
- `--entryPoint <fully.qualified.name>`<br>指定根符号的完全限定名称.默认为全局命名空间.
- `--gitRevision <revision|branch>`<br>使用指定的修订版或分支而不是最后一个修订版来链接到 GitHub 源文件.

#### 内容

- `--includes <path/to/includes>`<br>指定查找包含文档的位置.一个人可以使用<code>\[[包括:文件名]]</code>在评论中包括来自此位置的文档.

- `--media <path/to/media>`<br>指定应复制到输出目录的媒体文件的位置.要创建媒体文件的链接,请使用该模式<code>媒体:// FILENAME</code>在评论中.

#### 杂

- `--version`<br>显示 TypeDoc 的版本号.
- `--help`<br>显示所有 TypeDoc 选项.

### 的 WebPack

有一个插件可以运行 TypeDoc 与 Microsoft 创建的 Webpack.你可以在 NPM 上找到它:<br>
<https://www.npmjs.com/package/typedoc-webpack-plugin>

### 吞

有一个插件可以运行 TypeDoc 和 Gogp 由 Rogier Schouten 创建.你可以在 NPM 上找到它:<br>
<https://www.npmjs.com/package/gulp-typedoc/>

### 咕噜

有一个插件可以运行 TypeDoc 与由 Bart van der Schoor 创建的 Grunt.你可以在 NPM 上找到它:<br>
<https://www.npmjs.com/package/grunt-typedoc>

## 插件

- [External Module Name](https://github.com/christopherthielen/typedoc-plugin-external-module-name)- 设置 TypeDoc 外部模块的名称
- [Sourcefile URL](https://github.com/gdelmas/typedoc-plugin-sourcefile-url)- 设置自定义源文件 URL 链接
- [Internal/External Module](https://github.com/christopherthielen/typedoc-plugin-internal-external)- 明确将模块标记为`@internal`要么`@external`
- [Single Line Tags](https://github.com/christopherthielen/typedoc-plugin-single-line-tags)- 处理确定`@tags`作为单行
- [Localization](https://github.com/IgniteUI/typedoc-plugin-localization)- 生成不同语言的文档

可以在 NPM 上找到所有已发布的 Typedoc 插件的列表:<br>
<https://www.npmjs.com/search?q=keywords:typedocplugin>

## 高级指南和文档

访问我们的主页以获取高级指南和广泛的 API 文档:<br>
<http://typedoc.org>

## 特约

该项目由开发人员社区维护.欢迎并赞赏我们的贡献.你可以在 GitHub 上找到 TypeDoc;随意启动问题或创建拉取请求:<br>
<https://github.com/TypeStrong/typedoc>

有关更多信息,请阅读[contribution guide](https://github.com/TypeStrong/typedoc/blob/master/CONTRIBUTING.md).

## 执照

版权所有(c)2015[Sebastian Lenz](http://typedoc.org).<br>版权所有(c)2016-2018[TypeDoc Contributors](https://github.com/TypeStrong/typedoc/graphs/contributors).<br>根据 Apache License 2.0 许可.
