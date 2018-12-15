## 更新

TypeDoc使用TypeScript编译器的内部API方法 - 因此您需要为每个不同的TypeScript编译器版本重新编译它.如果您的项目不依赖于最新TypeScript编译器的功能,那么您可以使用不以其为目标的TypeDoc版本.

但是,如果您需要最新版本且尚未发布,那么这些是您应该遵循的步骤来构建自己的版本.

```bash
# Checkout a copy of TypeDoc if you don't have one already
git clone https://github.com/TypeStrong/typedoc typedoc
cd typedoc

# Change the version of TypeScript used by the project
editor package.json

npm install -g grunt-cli # install grunt's CLI globally if you don't have it
npm install # install TypeDoc's dependencies

# Checkout the version of TypeScript you are targetting
git clone https://github.com/Microsoft/TypeScript typescript
cd typescript
git checkout v1.8.10 # checkout the correct version (as set in package.json)
npm install -g jake # install the jake build tool globally if you don't have it
npm install # install TypeScript's build dependencies
jake local # build TypeScript
cd ../

# Setup TypeDoc for your TypeScript version
grunt ts:typescript # compile the internal-API typescript definition files
grunt string-replace:typescript # format the internal-API typescript files

# Build and run the automated TypeDoc tests
grunt build_and_test 

# Do a visual inspection to make sure that modules were generated correctly
ls test/render/specs/modules
```

完成此操作后,您应该为您的TypeScript版本提供TypeDoc的功能版本.如果您愿意,请使用更新的项目打开Pull Request,以便其他人可以从更新中受益.

要在项目中使用您的TypeDoc版本,请指向您的`package.json`使用您的GitHub项目路径在其中归档.

```json
{
    "dependencies": {
        "typedoc": "mygithubuser/typedoc#v1.8.10"
    }
}
```
