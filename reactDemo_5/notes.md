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
```html
        <div id="demo">
    
        </div>
```
```js
        class WebSite extends React.Component {
            constructor() {
                super();

                this.state = {
                    ip: returnCitySN.cip,
                    city: returnCitySN.cname
                }
            }
            render() {
                return(
                    <div>
                        <Ip ip={this.state.ip}/>
                        <City city={this.state.city}/>
                    </div>
                );
            }
        }

        class Ip extends React.Component {
            render() {
                return (
                    <p>{this.props.ip}</p>
                );
            }
        }

        class City extends React.Component {
            render() {
                return (
                    <p>{this.props.city}</p>
                );
            }
        }

        ReactDOM.render(
            <WebSite/>,
            document.getElementById("demo")
        )
```
上面的例子中，在父组件中设置state，通过在子组件上使用props将其传递到子组件上，在render函数中设置ip和city来获取父组件传过来的数据

### Props验证
```html
<div id="demo">

</div>
```
```js
    var name = 'Alan';
    var ip = returnCitySN.cip;

    class MyIp extends React.Component {
        render() {
            return (
                <p>{this.props.name} your ip is, {this.props.ip}</p>
            );
        }
    }

    MyIp.propTypes = {
        name: PropTypes.string,
        ip: PropTypes.string
    };

    ReactDOM.render(
        <MyIp name={name} ip={ip}/>,
        document.getElementById("demo")
    )
```
Props验证使用propTypes，propTypes可以保证我们的组件正确使用，React.PropTypes提供多种验证器来验证数据有效性。

