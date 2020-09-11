
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



3. 
