---
layout: 'guide'
title: 'DocComments'
menuOrder: 4
---

# Document your code

文档化你的代码

TypeDoc 运行 TypeScript 编译器,并从生成的编译器符号中，提取类型信息。因此,您不必在注释中包含其他元数据，就可以自动检测 TypeScript 特定元素,如类，枚举 或属性类型，以及访问修饰符。

所有注释都被解析为 markdown。TypeDoc 使用 Marked(<https://github.com/chjj/marked>作为 markdown 解析器和 HighlightJS(<https://github.com/isagalaev/highlight.js>)突出显示 markdown 部分内的代码块。此外,您可以使用双方括号链接到其他类,成员或函数。

## JavaDoc tags

文档生成器当前了解以下 javadoc 标记:

### `@param <param name>`

记录后续方法的参数

### `@return(s)`

记录后续方法的返回

### `@event`

记录后续方法触发的事件

### `@hidden and @ignore`

保持后续代码不被记录.

---

所有其他标记将呈现为定义的列表,因此它们不会丢失。

## Function signatures

> 函数签名

在编写函数签名的文档时,您不必重复自己。TypeDoc 会自动将函数实现的注释和标记复制到其签名中。当然,如果你愿意,你仍然可以覆盖它们.

```typescript
/**
 * @param text   参数 ´text´ 的注释.
 */
function doSomething(target: any, text: string): number;

/**
 * @param value   参数 ´value´ 的注释.
 * @returns       指定 return值 的注释.
 */
function doSomething(target: any, value: number): number;

/**
 *  ´doSomething´方法 注释.
 * @param target   参数 ´target´的注释.
 * @returns        指定 return值 的注释.
 */
function doSomething(target: any, arg: any): number {
  return 0;
}
```

## Modules

> 模块

模块可以像 TypeScript 中的任何其他元素一样进行注释。由于模块可以在多个文件中定义,因此 TypeDoc 默认选择最长的注释。有人可能想使用`@preferred`注释标签，覆盖此行为.

```typescript
/**
 * 真正的模块注释.
 * @preferred
 */
namespace MyModule {

}
```

```typescript
/**
 * 此模块注释 不再考虑(因为它不够长).
 * 这才是 长长的注释，但 仍会被 `@preferred`注释标签所覆盖.
 */
namespace MyModule {

}
```

## Dynamic modules

> 动态模块

文件中的第一个 doc 注释用作动态模块的 doc 注释。但是,您必须确保第一个声明也具有 doc 注释.

```typescript
/**
 * 一个动态模块的 doc 注释
 */

/**
 *   "someVar" 的 doc 注释.
 */
var someVar: string = 'value';
```
