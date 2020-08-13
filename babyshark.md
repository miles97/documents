## uniapp开发小结

* 使用前端的split进行模糊匹配搜索

使用@input="confirm" 首先监听输入内容
```js
let value = e.detail.value
this.keyword = value
this.haveValue = true
let self = this;
	if(value){
		let attr = [];
		let obj= {};
		for(let item in self.thatOptions){
			if(self.thatOptions[item].city.indexOf(value)> -1){
				obj = {
					city: self.thatOptions[item].city,
					id: self.thatOptions[item].id,
					code: self.thatOptions[item].code
				}
				attr.push(obj)
			}
			
		}
		self.searchList = attr;
	}else{
		self.searchList = self.thatOptions
	}
	var search = this.search;
```

* 兼容性问题排查

使用window.alert()，通过本地代理localhost跑的本地ip以及端口在其他移动设备上调试。

* 

## typescript使用小结分享

## 微信小程序脱坑实践

通过不友好的调试器以及不友好的代码，决定还是远离微信小程序比较好，调试器占用内存已经够跑若干个VS以及webstorm

## 生产力相关优化

编辑器效率低下，考虑使用vscode集成相关应用

使用mac编程后注意事项以及行为养成习惯

## 生产力相关优化
