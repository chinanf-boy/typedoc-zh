---
layout: 'guide'
title: 'Installation'
menuOrder: 1
---

# Installation

> 安装

<ul class="toc">
<li><a href="#command-line-interface">命令行 接口 </a></li>
<li><a href="#task-runners">任务 运行器</a></li>
</ul>

## Command line interface

> 命令行接口

### Requirements

> 要求

TypeDoc 要求在系统上安装 Node.js。如果你还没有这么做,去他们的站点,按照他们的安装说明:

<http://nodejs.org/>

安装 TypeDoc 非常简单,因为它可以作为 Node 包使用。使用`npm`确保所有相关依赖项都正确设置。你只需要决定是用全局安装还是本地安装。

### Global installation

> 全局安装

如果您想直接使用 TypeDoc,这是安装它的首选方法:

```bash
$ npm install --global typedoc
```

与 TypeScript 编译器一样,TypeDoc 附带了一个二进制文件，如果将 TypeDoc 安装为全局模块,可以从任何地方调用它。可执行文件的名称是`typedoc`。 为了验证所有设置是否正确,可以不带参数地运行 TypeDoc。它应该输出一些帮助消息:

```bash
$ typedoc

Version 0.1.0
Syntax:   typedoc [options] [file ..]

Examples: typedoc --out ../doc/ hello.ts
```

### Local installation

> 本地安装

如果希望将 TypeDoc 用作项目中的模块，例如将其与构建过程集成，那么也可以将其安装为本地模块。

```bash
$ npm install --save-dev typedoc
```

在模块中,可以通过 require 方式访问`typedoc`:

```js
var typedoc = require('typedoc');
var app = new typedoc.Application();
```

去我们的[api 文档](http://typedoc.org/api/)，了解更多关于公开 api 的信息。

## Task runners

> 任务 运行器

一些优秀的人员已经创建了插件,以便您可以使用您喜欢的任务运行器运行 TypeDoc。Grunt 和 Gulp 都有可用的插件,可以使用`npm`轻松安装这两个插件。 这两个插件接受与 cli 应用程序相同的选项,请参见[usage](./usage.zh.md).

### Grunt

<dl class="specs">
    <dt>名称</dt><dd>grunt-typedoc</dd>
    <dt>站点</dt><dd>https://www.npmjs.org/package/grunt-typedoc/</dd>
    <dt>作者</dt><dd>[Bart van der Schoor](https://github.com/Bartvds)</dd>
</dl>

可以使用以下命令安装插件:

```bash
$ npm install --save-dev grunt-typedoc
```

使用配置更新以下代码片段,并将其添加到`gruntfile.js`文件:

```js
grunt.loadNpmTasks('grunt-typedoc');
grunt.initConfig({
  typedoc: {
    build: {
      options: {
        module: 'commonjs',
        target: 'es5',
        out: 'docs/',
        name: 'My project title'
      },
      src: 'src/**/*'
    }
  }
});
```

### Gulp

<dl class="specs">
    <dt>名称</dt><dd>gulp-typedoc</dd>
    <dt>站点</dt><dd>https://www.npmjs.org/package/gulp-typedoc/</dd>
    <dt>作者</dt><dd>[Rogier Schouten](https://github.com/rogierschouten)</dd>
</dl>

可以使用以下命令安装插件:

```bash
$ npm install --save-dev gulp-typedoc
```

使用配置更新以下代码片段,并将其添加到`gulpfile.js`文件:

```js
var typedoc = require('gulp-typedoc');
gulp.task('typedoc', function() {
  return gulp.src(['src/**/*.ts']).pipe(
    typedoc({
      module: 'commonjs',
      target: 'es5',
      out: 'docs/',
      name: 'My project title'
    })
  );
});
```
