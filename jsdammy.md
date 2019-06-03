### JS问题一览

1. 基本都是数组处理以及对象访问，渲染，转换字符串，对象，数组等

2. 目前的问题是关于当数组的key为数值时的特殊访问，a.['key']，采用这种方式进行访问

3. 然后对于json内获取的数值的数据格式存在一些疑惑，以及对于自己push({[item.id]:item.name})，诸如此类的自定义数组的数据格式问题

4. 最佳实践的输入控制以及表单数值控制和监听等问题


```java
通过input原生的@input.native.capture="checkPrice"  check事件，然后通过判断e.target.value的值进行使用
checkPrice(e) {
    if(e.target.value <= 1000){
            e.target.value = commonObj.checkNum(e.target.value);
    }else{
        e.target.value = 1000
        Toast('请输入1-1000数字')
    }

},

完成对于输入控制区间的简单判断
```

5. 对于原生HTML5,css媒体查询,PC特性的问题[onclick]

6. 移动端300ms延迟的处理方式(faseclick的基本用法)，以及产生的原生和不同浏览器厂商的处理方式

7. 移动端分辨率适配解决方案flexible

8. 公用样式里面需要定义，清空基本样式的margin,padding等属性问题

```javascript
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, font, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td {
  margin: 0;
  padding: 0;
  border: 0;
  outline: 0;
  font-size: 100%;
  vertical-align: baseline;
  background: transparent;
}
```

9. 监听数组，对象，方法等不同监听方法之间的差别[vue监听watch](https://blog.csdn.net/guanguan0_0/article/details/80355029)

10. 自定义输入控制检测的部分问题

11. this.$emit向父组件传递自定义函数

12. 关于数组和数组之间的问题  [77654, __ob__: Observer] 和 [77654]  ,在页面内的watch属性设置相应字段的监听vans

13. 默认填充的问题