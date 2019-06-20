### JS问题一览

1. 基本都是数组处理以及对象访问，渲染，转换字符串，对象，数组等

2. 目前的问题是关于当数组的key为数值时的特殊访问，a.['key']，采用这种方式进行访问

3. 然后对于json内获取的数值的数据格式存在一些疑惑，以及对于自己push({[item.id]:item.name})，诸如此类的自定义数组的数据格式问题

4. 最佳实践的输入控制以及表单数值控制和监听等问题


```js
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

```js
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

13. 默认填充的问题,区分数组，对象，以及字符串。vans



14. for循环拼接对象

```js
 let newObj = {};
    arr2.forEach((item, index) => {
        for (var k in item) {
            newObj[k] = item[k]
        }
    })
```
这样，这个newObj直接变成了包含所有合集的对象


15. 当问题是条件不渲染还是直接{{item.key}}展示出来的问题

```
<!--                        <ul v-for="(item,key) in defaultData.defeatInfo" :key="item.id">-->
<!--                            <li :style="isDefeat" style="color: #000;" v-if="key !== 'defeatReasonNum' && key !=='sellToFriendNum' && key !== 'darkCarNum'-->
<!--                                    && key !== 'accidentCarNum' && key !== 'tooHighNum'">-->
<!--                                <span>{{item}}</span>-->
<!--                            </li>-->
<!--                        </ul>-->
```
对于后端而言，不是很友好而且不符合未来的拓展要求，所以还是需要手动控制

```
                            <div v-if="defaultData.totalInfo.newCarExchangeRate">
                                <span>{{item.exchangeNum}}</span>
                                <span>{{item.newCarSaleNum}}</span>
                                <span>{{item.newCarExchangeRate}} <b v-if="item.newCarExchangeRate !=='-'">%</b> </span>
                                <span>{{item.monthTargetNum}}</span>
                                <span>{{item.monthNewCarExchangeRate}} <b
                                        v-if="item.monthNewCarExchangeRate !=='-'">%</b> </span>
                            </div>
```


16. 解决一个index操作的数组并且对应操作数据

最开始采用操作index的方法，对照一个数组然后操作一个修改的数组，但是随着数组长度的变化，index的指向是错误的，如果通过逻辑判断的话几乎需要很大的工作量才能涵盖完全的形式，所以经过了很久的判断之后使用index对应的itemName，然后遍历新数组的item，如果数组内存在相应的元素，才开始操作。
同理，只有有相应的元素时，才开始操作对应的数据。

```js
      if (!this.isClickOn[index]) {     //删除item
          group.forEach(function (item, index, arr) {
              if (item == itemName) {
                  arr.splice(index, 1);
              }
          });

          //before
          //if(index<group.length){.........}
          //let arr1 =  group.splice(index, 1)
          //然后控制很多index的情况以及判断ele

      }
      if (this.isClickOn[index]) {      //添加item
          let arr1 = group.splice(index, 0, itemName)
      }
```

17. mint-ui组件问题 上拉刷新，下拉加载的问题  除了minheight或者height之外，还需要的即是

```js
overflow-y: auto;
-webkit-overflow-scrolling: touch;
```

18. 写一个组件包含的简单问题 props,this.$emit("getPayTypeStr", this.payTypeStr),watch.

19. 清空数据操作
```js
this.$refs.input.emptySearchVal();//ref='input'  清空该值
this.$set(this.price, 'maxPrice', newValue);// //
```

20. ES6    ??? arr.findIndex((ele)=>(ele.value == value)) > -1  ??? 作为条件

21. 代码库以及封装的模块组件库  供未来使用   除了.vue  .js的一些正则校验，输入控制，图片，媒体处理，ajax请求封装，等等

22. 对于生命周期，以及一些简单的问题处理。还有业务逻辑的完善 

23. 字符串拼接ES6 
```js
`&type=${this.type}&outType=${this.outType}&orderId=${
  this.orderId
}&memberSid=${this.userSid}&outId=${this.evaluateInfo.clueId}`;
```
24. 关于页面的fixed问题  直接通过滑动部分的div 设置overflow auto ，而不是设置position fixed IOS兼容性问题  fixed页面抖动问题，对于scroll||touch的支持问题，index的问题（暂时未知）

25. 对于图表类的页面，style内联样式容易滥用，同时需要注意权重分配的问题，否则容易导致页面不一致的问题

26. 对于wrap-content最好的解决方案仍然还是使用块级样式包裹，然后通过调整完成.

27. 
