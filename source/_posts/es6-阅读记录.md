---
title: es6 阅读记录。
date: 2021/11/17
cover: https://img2.huashi6.com/images/resource/2015/11/07/53h430426p0.jpg
categories:
- 开发
tags:
- javascript
- es6
---


## 变量解构赋值
### 默认值生效的条件是，对象的属性值严格等于undefined。

```javascript
let {x = 3} = {x: undefined};
x // 3

let {x = 3} = {x: null};
x // null
```
上面代码中，属性`x`等于`null`，因为`null`与`undefined`不严格相等，所以是个有效的赋值，导致默认值`3`不会生效。

### 用途

#### 不使用第三个变量交换两个变量的值
```javascript
let x = 1;
let y = 2;

[x, y] = [y, x];
```

## Object.getOwnPropertyDescriptors()
### 为了解决Object.assign() 无法拷贝set或者get，Object.getOwnPropertyDescriptors() 配合 Object.defineProperties() 就可以实现set和get的拷贝。
```javascript
const target = {};
const source = {
  set foo(value) {
    console.log(value);
  }
};
Object.defineProperties(
  target,
  Object.getOwnPropertyDescriptors(source)
);
// { get: undefined,
//   set: [Function: set foo],
//   enumerable: true,
//   configurable: true }
```

### Object.assign()无法拷贝原型，Object.create() 和 getOwnPropertyDescriptors() 配合可以实现原型拷贝。
```javascript
const obj = {
    a:1,
    b:2
}
const obj1 = {
  x:0
}
obj.__proto__ = obj1 // 或者Object.setPrototypeOf(obj,obj1)
const clone = Object.create(Object.getPrototypeOf(obj), Object.getOwnPropertyDescriptors(obj));
// a: 1
// b: 2
//         [[Prototype]]: Object
//          x: 0
```

end～