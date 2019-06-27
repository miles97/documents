
## React begin again

1. 关于函数和class的问题[暂不研究hook]
在render内的标签称之为class

```js
    render(){
        return(
            <View style={styles.item}>
                <Icon name="ios-menu" size={px2dp(25)} color="#ccc"/>
                <Text style={{fontSize: theme.actionBar.fontSize, color: '#000', marginLeft: px2dp(20)}}>{this.props.name}</Text>
                <View style={{flex: 1, flexDirection: 'row', justifyContent: 'flex-end'}}>
                    <Switch
                        onValueChange={this._onValueChange.bind(this)}
                        value={this.state.isSwitchOn}/>
                </View>
            </View>
        );
    }
```
而作为函数，不需要this指向
```js
function Example() {
	const [count, setCount] = useState(0);
	return (
		<div>
			<p>You clicked {count} times</p>
			<button onClick={() => setCount(count + 1)}>
			Click me
			</button>
		</div>
			);
		}
```

2. 在：key需要使用的时候
```
不仅仅是这些框架用遍历的key值不建议index
key值在没有删除插入操作时只要是唯一值也无所谓
但是如果有删除插入的操作，后一位会继承删掉的index
所以这时的key写不如不写，本来key是为了让遍历性能优化的操作，这种可能重复或者改变的key值不仅不会优化还会影响性能
所以怎么写呢？
可以试试这样 ${Date.now()}  ${Math.floor(Math.random()*10000)}
可以试试 symbol()
```