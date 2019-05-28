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

5. 对于计算机内容运用的问题