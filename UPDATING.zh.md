##更新

TypeDoc 使用 TypeScript 编译器的内部 API 方法 - 因此您需要为每个不同的 TypeScript 编译器版本重新编译它。如果您的项目不依赖于最新 TypeScript 编译器的功能,那么您可以使用不以其为目标的 TypeDoc 版本。

但是,如果您需要最新版本，且尚未发布,那么这些是您应该遵循的步骤来构建自己的版本。

```bash
#  如果您还没有TypeDoc的副本，请查看它
git clone https://github.com/TypeStrong/typedoc typedoc
cd typedoc

#  更改项目使用的TypeScript版本
editor package.json

npm install -g grunt-cli #  如果没有，请全局安装grunt的CLI
npm install #  安装TypeDoc的依赖项

#  签出您要定位的TypeScript版本
git clone https://github.com/Microsoft/TypeScript typescript
cd typescript
git checkout v1.8.10 #  签出正确的版本（在package.json中设置）
npm install -g jake #  如果你没有jake构建工具，请在全局安装它
npm install #  安装TypeScript的构建依赖项
jake local #  构建TypeScript
cd ../

#  为TypeScript版本设置TypeDoc
grunt ts:typescript #  编译internal-API typescript定义文件
grunt string-replace:typescript #  格式化内部API打字稿文件

#  构建并运行自动化TypeDoc测试
grunt build_and_test

#  进行目视检查以确保正确生成模块
ls test/render/specs/modules
```

完成此操作后,您应该有了个人 TypeScript 版本提供的 TypeDoc 功能版。如果您愿意,请使用更新的项目打开 Pull Request,以便其他人可以从更新中受益。

要在项目中使用您的 TypeDoc 版本,请在您的`package.json`指向在您的 GitHub 项目中使用的 TypeDoc 路径。

```json
{
  "dependencies": {
    "typedoc": "mygithubuser/typedoc#v1.8.10"
  }
}
```
