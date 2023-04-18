

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


**泛型**

泛型（Generics）是指在定义函数、接口或类的时候，不预先指定具体的类型，而在使用的时候再指定类型的一种特性

泛型约束
可以对泛型进行约束，只允许这个函数传入那些包含 length 属性的变量。这就是泛型约束

```js
interface Lengthwise {
    length: number;
}

function loggingIdentity<T extends Lengthwise>(arg: T): T {
    console.log(arg.length);
    return arg;
}
```

<br>

**用接口定义函数的形状**
我们也可以使用接口的方式来定义一个函数需要符合的形状：

```js
interface SearchFunc {
    (source: string, subString: string): boolean;
}

let mySearch: SearchFunc;
mySearch = function(source: string, subString: string) {
    return source.search(subString) !== -1;
}
```
采用函数表达式|接口定义函数的方式时，对等号左侧进行类型限制，可以保证以后对函数名赋值时保证参数个数、参数类型、返回值类型不变。




<br>

**参考**
[TypeScript入门教程](http://ts.xcatliu.com/)