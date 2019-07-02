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

2.  !!双叹号表示  arrgument ? true : false

3. || 表示none or have