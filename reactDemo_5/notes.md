## React Props

### 默认Props
```html
        <div id="demo">
    
        </div>
```
```js
        class SayHi extends React.Component{
            render() {
                return (
                    <p>Say Hi, {this.props.name}</p>
                );
            }
        }

        SayHi.defaultProps = {
            name: 'Alan'
        };

        const element = <SayHi/>;

        ReactDOM.render(
            element,
            document.getElementById("demo")
        )
```
可以通过组件类的defaultProps中属性为props设置默认值

### State和Props
