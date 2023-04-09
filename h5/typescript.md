

#### 概念
TypeScript is JavaScript with syntax for types
TypeScript是带有类型语法的JavaScript

- **编译时类型检查**
<br>  

- **自动补全**
<br>

- **支持jsx**

<br>

#### tsconfig.json

TypeScript配置文件

<br>

#### type 和 interface

- type是类型别名
- interface是对对象形状的定义

相同点

- 类型别名和接口都可以用来描述对象或函数
- 类型别名和接口都支持扩展

不同点

- 类型别名可以用在基本类型、联合类型或元组类型，而接口不行
- 同名接口会自动合并，而类型别名不会

<br>

**元组**
个数和类型确定的数组，不同类型
```js
let tom: [string, number] = ['Tom', 25];
```

<br>

**联合类型**
联合类型（Union Types）表示取值可以为多种类型中的一种

```js
let myFavoriteNumber: string | number;
myFavoriteNumber = 'seven';
myFavoriteNumber = 7;
```

<br>


**参考**
[TypeScript入门教程](http://ts.xcatliu.com/)