---
layout: 'guide'
title: 'Installation'
menuOrder: 1
---
# Installation

<ul class="toc">
<li><a href="#command-line-interface">Command line interface</a></li>
<li><a href="#task-runners">Task runners</a></li>
</ul>

## Command line interface

### Requirements

TypeDoc要求在系统上安装Node.js.如果你还没有这么做,去他们的站点,按照他们的安装说明:

<http://nodejs.org/>

安装TypeDoc非常简单,因为它可以作为节点包使用.使用`npm`确保所有相关依赖项都正确设置.只需要决定是否需要全局设置或本地设置.

### Global installation

如果您想直接使用TypeDoc,这是安装它的首选方法:

```bash
$ npm install --global typedoc
```

与TypeScript编译器一样,TypeDoc附带了一个二进制文件,如果将TypeDoc安装为全局模块,可以从任何地方调用它.可执行文件的名称是`typedoc`. 为了验证所有设置是否正确,可以不带参数地运行TypeDoc.它应该输出一些帮助消息:

```bash
$ typedoc

Version 0.1.0
Syntax:   typedoc [options] [file ..]

Examples: typedoc --out ../doc/ hello.ts
```

### Local installation

如果希望将TypeDoc用作项目中的模块,例如将其与构建过程集成,那么也可以将其安装为本地模块.

```bash
$ npm install --save-dev typedoc
```

在模块中,可以通过以下方式访问它`typedoc`:

```js
var typedoc = require('typedoc');
var app = new typedoc.Application();
```

去我们的[api documentation](/api/)了解更多关于公开的api的信息.

## Task runners

一些优秀的人员已经创建了插件,以便您可以使用您喜欢的任务运行器运行TypeDoc.Grunt和Gulp都有可用的插件,可以使用以下方法轻松安装这两个插件`npm`. 这两个插件接受与cli应用程序相同的选项,请参见[usage](/guides/usage.html).

### Grunt

<dl class="specs">
    <dt>Name</dt><dd>grunt-typedoc</dd>
    <dt>Website</dt><dd>https://www.npmjs.org/package/grunt-typedoc/</dd>
    <dt>Author</dt><dd>[Bart van der Schoor](https://github.com/Bartvds)</dd>
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
    <dt>Name</dt><dd>gulp-typedoc</dd>
    <dt>Website</dt><dd>https://www.npmjs.org/package/gulp-typedoc/</dd>
    <dt>Author</dt><dd>[Rogier Schouten](https://github.com/rogierschouten)</dd>
</dl>

可以使用以下命令安装插件:

```bash
$ npm install --save-dev gulp-typedoc
```

使用配置更新以下代码片段,并将其添加到`gulpfile.js`文件:

```js
var typedoc = require("gulp-typedoc");
gulp.task("typedoc", function() {
    return gulp
        .src(["src/**/*.ts"])
        .pipe(typedoc({
            module: "commonjs",
            target: "es5",
            out: "docs/",
            name: "My project title"
        }))
    ;
});
```
