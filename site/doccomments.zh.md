---
layout: 'guide'
title: 'DocComments'
menuOrder: 4
---
# Document your code

TypeDoc运行TypeScript编译器,并从生成的编译器符号中提取类型信息.因此,您不必在注释中包含其他元数据,将自动检测TypeScript特定元素,如类,枚举或属性类型以及访问修饰符.

所有评论都被解析为降价.TypeDoc使用Marked(<https://github.com/chjj/marked>markdown解析器和HighlightJS(<https://github.com/isagalaev/highlight.js>)突出显示降价部分内的代码块.此外,您可以使用双方括号链接到其他类,成员或函数.

## JavaDoc tags

文档生成器当前了解以下javadoc标记:

### `@param <param name>`

记录后续方法的参数

### `@return(s)`

记录后续方法的返回

### `@event`

记录后续方法触发的事件

### `@hidden and @ignore`

保持后续代码不被记录.

* * *

所有其他标记将呈现为定义列表,因此它们不会丢失.

## Function signatures

在编写功能签名的文档时,您不必重复自己.TypeDoc会自动将函数实现的注释和标记复制到其签名中.当然,如果你愿意,你仍然可以覆盖它们.

```typescript
/**
 * @param text  Comment for parameter ´text´.
 */
function doSomething(target:any, text:string):number;

/**
 * @param value  Comment for parameter ´value´.
 * @returns      Comment for special return value.
 */
function doSomething(target:any, value:number):number;

/**
 * Comment for method ´doSomething´.
 * @param target  Comment for parameter ´target´.
 * @returns       Comment for return value.
 */
function doSomething(target:any, arg:any):number {
    return 0;
}
```

## Modules

模块可以像TypeScript中的任何其他元素一样进行注释.由于模块可以在多个文件中定义,因此TypeDoc默认选择最长的注释.有人可能会使用特殊情况覆盖此行为`@preferred`评论标签.

```typescript
/**
 * Actual module comment.
 * @preferred
 */
module MyModule { }
```

```typescript
/**
 * Dismissed module comment.
 * This is the longer comment but will be dismissed in favor of the preferred comment.
 */
module MyModule { }
```

## Dynamic modules

文件中的第一个doc注释用作动态模块的doc注释.但是,您必须确保第一个声明也具有doc注释.

```typescript
/**
 * This is a doc comment for a dynamic module.
 */

/**
 * This is a doc comment for "someVar".
 */
var someVar:string = "value";
```
