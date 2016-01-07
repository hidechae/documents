React.js入門

# Hello World

```
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

- renderではcomponentを1つ返す

# Libraries

- react router
  - https://github.com/rackt/react-router
- redux
  - https://github.com/rackt/redux
- react bootstrap
  - https://react-bootstrap.github.io/
- others
  - http://react-components.com/


# Other frameworks

- Angular.js
- Mithril.js
- Vue.js
- Riot.js
