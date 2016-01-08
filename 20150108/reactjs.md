
- [React.jsとは](#introduction)
- [Hello World](#hello_world)
- [Component](#component)
- [StateとProps](#state_props)
- [ComponentのLifecycle](#component_lifecycle)
- [Libraries](#liberaries)
- [その他のフレームワーク](#other_framework)


<a id="introduction">

# React.jsとは

- Facebook製
- コンポーネント志向
- 仮想DOM
- JSX
- 2way bindingではない

### トレンド

![image](https://cloud.githubusercontent.com/assets/1647252/12188691/114f7ece-b5fb-11e5-930c-da529cbfc2bf.png)


<a id="hello_world">

# Hello World


```html
<body>
  <div id="app"></div>
</body>
```

##### with jsx
- https://jsfiddle.net/hidechae/z7hqj0k2/

```javascript
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

```javascript
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

```javascript
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

es6とは

- https://babeljs.io/docs/learn-es2015/
- 追加機能
  - クラス (`class`, `extends`, `super`)
  - アロー関数 (`(x, y) => { ... }`)
  - ブロックスコープの変数 (`let`)、定数 (`const`)
  - テンプレートリテラル (`${x} + ${y} = ${x + y}`)
  - etc...


<a id="component">

# Component

基本的にComponentの組み合わせでアプリケーションを作っていく

## render

- renderではcomponentを1つだけ返す

```javascript
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

- `{ }` で囲ってJavscriptのコードを呼び出す

```javascript
render() {
  return (
    <div>Hello {this.props.name}</div>
  );
}
```

- 閉じタグが無いタグは `/>` で終わらないといけない

```javascript
render() {
  return (
    <input type='text' />
  );
}
```

<a id="state_props">

# StateとProps

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

```javascript
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



## Component間でやり取りする

simpleな例

- https://jsfiddle.net/hidechae/k9ghevzd/

ちょっと複雑な例

- https://jsfiddle.net/hidechae/p7kyjtwx/

<a id="component_lifecycle">

# ComponentのLifecycle

### componentWillMount()
- ComponentがDOMツリーに追加される前に呼ばれる
- Constructorみたいに初期化処理に使う

### componentDidMount()
- componentがDOMツリーに追加された後に呼ばれる

### componentWillReceiveProps(nextProps)
- Propsが更新されるときに呼ばれる
- Propsの値に応じて変数の値を変えたい場合などに使う

### shouldComponentUpdate()
- Componentがrenderされる前に呼ばれる
- boolを返し、falseを返すとrenderされない

### componentWillUpdate(nextProps, nextState)
- Componentが更新される前に呼ばれる

### componentDidUpdate(prevProps, prevState)
- Componentが更新された後に呼ばれる

### componentWillUnmount()
- ComponentがDOMから削除されるときに呼ばれる
- destructorみたいにクリーンアップ系の処理をする


<a id="liberaries">

# Libraries

- react router
  - https://github.com/rackt/react-router
- redux
  - https://github.com/rackt/redux
- react bootstrap
  - https://react-bootstrap.github.io/
- others
  - http://react-components.com/


<a id="other_framework">

# その他のフレームワーク

- Angular.js
  - v1: https://angularjs.org/
  - v2: https://angular.io/
- Vue.js
  - http://jp.vuejs.org/
- Mithril.js
  - http://mithril.js.org/
- Riot.js
  - http://riotjs.com/ja/
