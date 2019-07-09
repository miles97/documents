## [ryf学ES6](https://github.com/ruanyf/es6tutorial/blob/gh-pages/docs/array.md)

1. 复制对象数组

ES5使用concat()方法复制数组对象，ES6直接使用...[]拓展运算符

```js
const a1 = [1, 2];
// 写法一
const a2 = [...a1];
// 写法二
const [...a2] = a1;
```

2.  !!双叹号表示  `arrgument ? true : false`

3. 表示none or have

4. 关于非循环渲染列表的最佳实践之一（idea from college）
```javascipt
setAll(type){
	let tempObj = {
		1:()=>{
			this.first = {id:0,name:'全部'};
			this.besure();
		},
		2:()=>{
			this.besure();
		},
		3:()=>{
			this.besure();
		}
	}
	tempObj[type]();
```

5. 数组的完全填充内容
将一个数组的内容全部变成false，index为0的为true

Array.from( isArrayLike, ()=>{})有个问题。即是会影响原来的数组

isArrayLike.fill(false),直接完成需求。每次都会重新填充，后面可以加上两个参数， 

fill方法还可以接受第二个和第三个参数，用于指定填充的起始位置和结束位置。
['a', 'b', 'c'].fill(7, 1, 2)
// ['a', 7, 'c']
上面代码表示，fill方法从 1 号位开始，向原数组填充 7，到 2 号位之前结束。

6. 新建一个空数组or NaN数组 or Null数组 Or undefined数组 or nothing数值
undefined

```Array.from({ length: 3 });```

null||NaN||undefined
```Array.from({ length: 2 }, () => null)```

空的数组
```
Array(length);
Array(12).fill(false);
//[false, false, false, false, false, false, false, false, false, false, false, false]
``` 
