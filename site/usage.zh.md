---
layout: 'guide'
title: 'Usage'
menuOrder: 2
---
# Usage

## Arguments

TypeDoc接受TypeScript编译器接受的大多数命令行参数.在没有标志的情况下传入的所有参数都将被解析为输入文件.TypeDoc接受目录作为输入文件,它会.

要为整个项目创建文档,只需键入:

```bash
$ typedoc --out path/to/documentation/ path/to/typescript/project/
```

### out

```bash
$ typedoc --out <path/to/documentation/>
```

指定文档应写入的位置.

### name

```bash
$ typedoc --name <Documentation title>
```

设置将在模板标题中使用的项目的名称.

### readme

```bash
$ typedoc --readme <path/to/readme|none>
```

应在索引页面上显示的自述文件的路径.传递none以禁用索引页面并在globals页面上启动文档.

### module

```bash
$ typedoc --module <commonjs or amd>
```

指定模块代码生成:"commonjs"或"amd"

### target

```bash
$ typedoc --target <ES3 or ES5>
```

指定ECMAScript目标版本:"ES3"(默认值)或"ES5"

### exclude

```bash
$ typedoc --exclude <pattern>
```

当路径作为源提供时,按给定模式排除文件

### theme

```bash
$ typedoc --theme <path/to/theme>
```

指定应使用的主题的路径

### includeDeclarations

```bash
$ typedoc --includeDeclarations
```

打开.d.ts声明文件的解析.

### externalPattern

```bash
$ typedoc --externalPattern <pattern>
```

为应该被视为外部的文件定义模式.

### excludeExternals

```bash
$ typedoc --excludeExternals
```

防止记录外部解析的TypeScript文件.

### gaID

```bash
$ typedoc --gaID
```

设置Google Analytics跟踪ID并激活跟踪代码.

### gaSite

```bash
$ typedoc --gaSite <site>
```

设置Google Analytics的网站名称.默认为`auto`.

### hideGenerator

```bash
$ typedoc --hideGenerator
```

不要在页面末尾打印TypeDoc链接.

### verbose

```bash
$ typedoc --verbose
```

在TypeDoc运行时打印更多信息.
