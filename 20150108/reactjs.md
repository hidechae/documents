React.js入門

# Hello World


```
# html
<body>
  <div id="app"></div>
</body>
```

##### with jsx
- https://jsfiddle.net/hidechae/z7hqj0k2/

```
var Hello = React.createClass({
  render: function() {
    return (
      <div>Hello {this.props.name}</div>
    );
  }
});

ReactDOM.render(
  <Hello name="World" />,
  document.getElementById('app')
);
```

##### without jsx
- https://jsfiddle.net/hidechae/zfv1f458/

```
var Hello = React.createClass({
  render: function() {
    return React.DOM.div({className: 'container'}, 'Hello ' + this.props.name);
  }
})

ReactDOM.render(
  React.createFactory(Hello)({name: 'World'}),
  document.getElementById("app")
);
```

##### with jsx + es6
- https://jsfiddle.net/hidechae/2Lyaaatm/

es6: https://babeljs.io/docs/learn-es2015/

```
class Hello extends React.Component {
  render() {
    return (
      <div>Hello {this.props.name}</div>
    );
  }
}

React.render(
  <Hello name="World"/ >,
  document.getElementById('app')
);
```


# Component

基本的にComponentの組み合わせでアプリケーションを作っていく

## render

- renderではcomponentを1つだけ返す

```
// NG
render() {
  return (
    <div>item1</div>
    <div>item2</div>
  )
}

// OK
render () {
  return (
    <div>
      <div>item1</div>
      <div>item2</div>
    </div>
  )
}
```

# StateとProps

https://jsfiddle.net/hidechae/k9ghevzd/

## State

- component内変数
- 変更されると再renderingされる
- ユーザのアクションやAjax処理などで動的に値が変化する場合に使う

## Prop

- componentの引数
- component間でやりとりする場合に使う

### PropTypes

- 型チェックできる
- エラーじゃなくてwarnが出る

https://facebook.github.io/react/docs/reusable-components.html

```
React.createClass({
  propTypes: {
    optionalArray:  React.PropTypes.array,
    optionalBool:   React.PropTypes.bool,
    optionalFunc:   React.PropTypes.func,
    optionalNumber: React.PropTypes.number,
    optionalObject: React.PropTypes.object,
    optionalString: React.PropTypes.string
  }
})
```

# Component間でやり取りする
https://jsfiddle.net/hidechae/p7kyjtwx/


## Lifecycle

- componentDidMount


# Libraries

- react router
  - https://github.com/rackt/react-router
- redux
  - https://github.com/rackt/redux
- react bootstrap
  - https://react-bootstrap.github.io/
- others
  - http://react-components.com/


# その他のフレームワーク

- Angular.js
- Mithril.js
- Vue.js
- Riot.js
