---
title: antd Botton组件 httpType属性。
date: 2021/07/26
---

## button type属性

* submit 该按钮是提交按钮（除了 Internet Explorer，该值是其他浏览器的默认值）

* button 该按钮是可点击的按钮（Internet Explorer 的默认值）

* reset 该按钮是重置按钮（清除表单数据）

### 总结：

其他浏览器（除IE浏览器）中，如果button没有设置type属性，默认值为type="submit"，会进行跳转页面和提交数据的操作，假如想进行使用ajax表单提交而且不进行跳转，必须设置成type="button"

IE浏览器button默认type属性是type="button"

end～