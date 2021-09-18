---
title: lodash的debounce函数防抖在特殊情况下的使用。
date: 2021/09/18
cover: https://img2.huashi6.com/images/resource/2015/11/07/53h430426p0.jpg
categories:
- 开发
tags:
- lodash
- javascript
---

## 类方法下的使用

在类中声明一个方法叫myFA：
```javascript
class myClass extends Object {
  constructor(props) {
    super(props);
    this.myFA = debounce(this.myFA,500);
  };
  myFA = () => {
      console.log('myFA')
  }
  myFB = debounce(() => {
    console.log('myFB')
  },500)
}
```
在函数使用：
```javascript
const MyFunc = () => {
    // 省略
  const myFC = debounce(() => {
      console.log('myFC')
  },500)
    // 省略
};
```

### 总结：
由上面代码可见，类方法处理防抖有两种方式，其实两种方式原理一样，只是写法不同，函数处理防抖跟类的第二种写法大致相同。

end～