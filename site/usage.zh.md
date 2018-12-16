---
layout: 'guide'
title: 'Usage'
menuOrder: 2
---

# Usage

> 用法

## Arguments

> 参数

TypeDoc 接受 TypeScript 编译器接受的大多数命令行参数。在没有标志的情况下，传入的所有参数都将被解析为输入文件。TypeDoc 还接受目录作为输入文件。

要为整个项目创建文档,只需键入:

```bash
$ typedoc --out path/to/documentation/ path/to/typescript/project/
```

### out

```bash
$ typedoc --out <path/to/documentation/>
```

指定，文档应写入的位置.

### name

```bash
$ typedoc --name <Documentation title>
```

设置将在模板标题中，使用的项目的名称.

### readme

```bash
$ typedoc --readme <path/to/readme|none>
```

应在索引页面上显示的 readme 文件的路径。传递 none 以禁用索引页面，并在 全局 页面上启动文档.

### module

```bash
$ typedoc --module <commonjs or amd>
```

指定模块代码生成:"commonjs"或"amd"

### target

```bash
$ typedoc --target <ES3 or ES5>
```

指定 ECMAScript 目标版本:"ES3"(默认值)或"ES5"

### exclude

```bash
$ typedoc --exclude <pattern>
```

当路径作为源提供时,按给定模式排除文件。

### theme

```bash
$ typedoc --theme <path/to/theme>
```

指定应使用的主题的路径

### includeDeclarations

```bash
$ typedoc --includeDeclarations
```

打开 `.d.ts` 声明文件的解析.

### externalPattern

```bash
$ typedoc --externalPattern <pattern>
```

为应该被视为外部的文件，定义模式.

### excludeExternals

```bash
$ typedoc --excludeExternals
```

防止外部解析的 TypeScript 文件被文档化.

### gaID

```bash
$ typedoc --gaID
```

设置 Google Analytics 跟踪 ID ，并激活跟踪代码.

### gaSite

```bash
$ typedoc --gaSite <site>
```

设置 Google Analytics 的网站名称。默认为`auto`.

### hideGenerator

```bash
$ typedoc --hideGenerator
```

不要在页面末尾打印 TypeDoc 链接.

### verbose

```bash
$ typedoc --verbose
```

在 TypeDoc 运行时，打印更多信息.
