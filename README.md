# react-note
react笔记
1. 跟路由不变，查询参数改变，也会触发componentWillReceiveProps
2. 不要在componentWillReceiveProps执行dispatch来触发action， 因为props改变又会触发componentWillReceiveProps，会进入死循环

## react 生命周期
![生命周期](https://images2017.cnblogs.com/blog/1106982/201708/1106982-20170811224737742-1564011484.jpg)

* componentWillReceiveProps(nextProps)
> props发生变化时，会执行，根据属性变化，可以用this.setState更新组件的状态
> 旧的属性还是通过this.props获取
- 父组件更新状态，无论有没有给子组件传参，都会触发子组件componentWillReceiveProps -> shouldComponentUpdate ->(true) ->  componentWillUpdate -> render -> componentDidUpdate
- 父组件更新状态，父组件生命周期过长，shouldComponentUpdate ->(true) ->  componentWillUpdate -> render -> componentDidUpdate
  
* this.setState
this.setState({})，参数是空对象，也会执行render从新渲染