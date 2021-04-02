### 一、基本认识

#### 1. 官网

- 中文官网：`https://react.docschina.org/`
- 英文官网：`https://reactjs.org/`

#### 2. 介绍描述

1. 用于构建用户界面的`JavaScript`库
2. 主要用于构建`UI`，很多人认为`React`是`MVC`中的`V`（视图）
3. 起源于`Facebook`的内部项目，用来架设`Instagram`的网站，并于**2013年5月**开源
4. 拥有较高的性能，代码逻辑简单

#### 3. React特点

- 声明式设计：`React`采用声明范式，可以轻松描述应用
- 高效：`React`通过对`DOM`的模拟，最大限度的减少与`DOM`的交互
- 灵活：`React`可以与已知的库和框架很好的配合
- `JSX`：`JSX`是`JavaScript`的语法扩展，`React`开发不一定使用`JSX`，但是建议使用它
- 组件：通过`React`构建组件，使得代码更加容易得到复用，能够很好的应用在大项目开发中
- 单向响应的数据流：`React`实现了单向响应的数据流，从而减少了重复代码，这也是它为什么比传统数据绑定更简单

#### 4.  React高效的原因

1. 虚拟`DOM`，不总是直接操作`DOM`
2. `DOM Diff`算法，最小化页面重绘

### 二、基本使用

#### 1.  React开发环境搭建

- `react.js`：核心文件
- `react-dom.js`：渲染页面中的`DOM`，当前文件依赖于`react`核心文件
- `babel.js`：`ES6`转换成`ES5`，`JSX`语法转换成`JavaScript`，浏览器代码兼容

#### 2. 创建虚拟DOM的方式

`JS`（不推荐使用）

```javascript
<script>
  // 创建虚拟DOM
  const element = React.createElement('h1', { id: 'title' }, 'Create Virtual DOM By JS');
  // 渲染虚拟DOM到页面
  ReactDOM.render(element, document.getElementById('app'));
</script>
```

`JSX`

```javascript
<script type="text/babel">
  // 创建虚拟DOM
  const element = <h1>Create Virtual DOM By JSX</h1>
  // 渲染虚拟DOM到页面
  ReactDOM.render(element, document.getElementById('app'));
</script>
```

#### 3. 虚拟DOM

- 本质上虚拟`DOM`是`Object`类型的对象
- 虚拟`DOM`比较轻量,真实`DOM`比较笨重,因为虚拟`DOM`是`React`内部在使用,无需真实`DOM`上那么多的属性
- 虚拟`DOM`最终会被`React`转化为真实`DOM`,呈现在页面上

### 三、`React JSX`

#### 1. `JSX`

- 全称:`JavaScript XML`
- `React`定义的一种类似于`XML`的`JS`扩展语法:`JS + XML`
- 本质是`React.createElement(component, props, ...children)`方法的语法糖
- 作用：用来简化创建虚拟`DOM`
  - 写法: `const element = <h1>Hello, JSX</h1>`
  - 注意1: 它不是字符串,也不是`HTML/XML`标签
  - 注意2: 它最终产生的就是一个`JS`对象

- 标签名任意:`HTML`标签或其他标签

#### 2. 语法规则

- 定义虚拟`DOM`时,不要写引号
- 标签中混入`JS`表达式时需要使用大括号
- 样式的类名指定使用`className`
- 内联样式，使用`style={{ key: value }}`的形式书写
- 只能有一个根标签
- 标签必须闭合
- 标签首字母
  - 若小写字母开头，则将该标签转为`html`中同名元素，若`html`中无同名元素，则会报错
  - 若大写字母开头，`React`就去渲染对应的组件，若组件没有定义，则报错