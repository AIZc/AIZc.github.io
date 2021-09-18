---
title: antd Select组件的Option组件的设置key不生效问题。
date: 2021/08/02
cover: https://img2.huashi6.com/images/resource/2015/11/07/53h430426p0.jpg
categories: 
- 开发
tags:
- react
- antd
---

## 使用map遍历生成Option时，给每一个option组件设置key为什么会报不唯一错误？

* 同时给option设置了value，value为覆盖key的值，value可能重复了。
* value 不应该重复，会导致 select 无法判断选中项。

### 逻辑总结：

* 只有 key，就用 key。
* 只有 value，就用 value。
* 两者都有，用 value。

end～