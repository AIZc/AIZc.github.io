---
title: es6-阅读记录-变量解构赋值。
date: 2021/08/22
cover: https://img2.huashi6.com/images/resource/2015/11/07/53h430426p0.jpg
categories:
- 开发
  tags:
- javascript
- es6
---

## 默认值生效的条件是，对象的属性值严格等于undefined。

```javascript
let {x = 3} = {x: undefined};
x // 3

let {x = 3} = {x: null};
x // null
```
上面代码中，属性`x`等于`null`，因为`null`与`undefined`不严格相等，所以是个有效的赋值，导致默认值`3`不会生效。

## 用途

### 不使用第三个变量交换两个变量的值
```javascript
let x = 1;
let y = 2;

[x, y] = [y, x];
```

end～