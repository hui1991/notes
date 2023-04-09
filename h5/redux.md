
**redux概念**
redux A Predictable State Container for JS Apps
js项目里一个可预测的状态容器

- store 全局数据中心
- action  描述state发生了什么变化
- reducer 修改state(纯函数)

**特点**

- Predictable 可预测
- Centralized 集中化
- Debuggable  可测试
- Flexible    灵活的

**三大原则**
- 单一数据源
  整个应用的state被存在一棵object tree中 而这个object tree被存在唯一的store中
<br>

- state是只读的
  唯一改变state的方式就是触发action，action是一个描述已发生事件的普通对象
<br>

- 使用纯函数来执行修改

**单向数据流**
![](images/2023-04-03-15-56-26.png)  


**数据流**
![](images/2023-04-03-15-58-35.gif)

**异步数据流**
![](images/2023-04-03-15-58-36.gif)


**Middleware**

中间件就是一个函数，对store.dispatch方法进行了改造，在发出 Action 和执行 Reducer 这两步之间，添加了其他功能，处理异步等功能

**React-Redux**
Redux 的作者封装了一个 React 专用的库 React-Redux
React-Redux 将所有组件分成两大类：UI 组件（presentational component）和容器组件（container component）

UI组件
- 只负责 UI 的呈现，不带有任何业务逻辑
- 没有状态（即不使用this.state这个变量）
- 所有数据都由参数（this.props）提供
- 不使用任何 Redux 的 API

容器组件
- 负责管理数据和业务逻辑，不负责 UI 的呈现
- 带有内部状态
- 使用 Redux 的 API

**hook**

- useSelector
  从 redux 提取 state
  ```js
  import React from 'react'
  import { useSelector } from 'react-redux'

  export const CounterComponent = () => {
    const counter = useSelector((state) => state.counter)
    return <div>{counter}</div>
  }
  ```

- useDispatch
  这个 hook 返回一个对 Redux store 中的 dispatch 函数的引用。你可以按需使用它来 dispatch action
  ```js
  import React from 'react'
  import { useDispatch } from 'react-redux'

  export const CounterComponent = ({ value }) => {
    const dispatch = useDispatch()

    return (
      <div>
        <span>{value}</span>
        <button onClick={() => dispatch({ type: 'increment-counter' })}>
          Increment counter
        </button>
      </div>
    )
  }
  ```

- useStore
  这个 hook 返回一个 Redux store 引用，该 store 与传递给 Provider 组件的 store 相同。

  ```js
  import React from 'react'
  import { useStore } from 'react-redux'

  export const CounterComponent = ({ value }) => {
    const store = useStore()

    // 仅仅是示例！不要在实际的应用中这么做。
    // 当 store state 变更时，组件不会自动更新
    return <div>{store.getState()}</div>
  }
  ```

<br>

**参考**

[redux中间件与异步操作](http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_two_async_operations.html)
      




