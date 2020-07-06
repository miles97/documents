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

7. 与非逻辑运算符与if之间的关系
```
&& || 
以及用二者来代替if的逻辑关系    

表达式&&结果 ||另一个结果   ==  if(表达式){结果}else{另一个结果}

```

8. [ES6语法规范相关](https://github.com/ruanyf/es6tutorial/blob/gh-pages/docs/style.md)

使用const 以及 let 代替var ，并使用解构赋值的思想来对于一些变量的声明进行简化
或者直接 安装 Airbnb 语法规则，以及 import、a11y、react 插件。

$ npm i -g eslint-config-airbnb
$ npm i -g eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react
在项目的根目录下新建一个.eslintrc文件，配置 ESLint。

{
  "extends": "eslint-config-airbnb"
}
现在就可以检查，当前项目的代码是否符合预设的规则

9.数组去重方法
new set()
