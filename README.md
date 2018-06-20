# react-note
react笔记
1. 跟路由不变，查询参数改变，也会触发componentWillReceiveProps
2. 不要在componentWillReceiveProps执行dispatch来触发action， 因为props改变又会触发componentWillReceiveProps，会进入死循环
  