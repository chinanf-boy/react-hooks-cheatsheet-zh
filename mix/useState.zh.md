---
name: useState
route: /usestate
---

# useState🦄

> 笔记：

-   `useState`允许您在组件函数中，使用本地状态(state)。
-   查看[文档](https://zh-hans.reactjs.org/docs/hooks-reference.html#usestate)。

## 声明状态变量

声明状态变量简单，只要调用`useState`时，带有些初始状态值。

<Editor code={DeclareStateVar}/>

## 更新状态变量

更新状态变量简单，`useState`函数返回了，更新函数`updaterFn`(如下)。

```js
const [stateValue, updaterFn] = useState(initialStateValue);
```

<Editor code={UpdateStateVar} />

## 多个状态变量

可以在组件函数中，使用和更新多个状态变量，如下所示：

<Editor code={MultipleStateVars} />

## 使用对象状态变量

除字符串和数字，您还可以使用对象(Object)类型，作为传递给`useState`的初始值。

> 注意：你必须将整个对象，传递给`useState`的更新函数，因为（存储的）对象是会被替换， **不会** 合并。

<Editor code={StateObject} />

```js
// 🐢 setState (Object 合并) vs useState (Object 替换)
// 假设，初始化状态是 {name: "Ohans"}

setState({ age: 'unknown' })
// 新状态 (Object) 会是
// {name: "Ohans", age: "unknown"}

useStateUpdater({ age: 'unknown' })
// 新状态 (Object) 会是
// {age: "unknown"} - 初始化状态被替换

```

## 从函数初始化状态

除了，传递初始状态值，`state`也可以通过函数，进行初始化，如下所示：

<Editor code={StateFromFn} />

## 函数化 setState

从调用`useState`返回的更新函数`updateValue`，也可以采用旧派'setState'，相同的函数化定义。

```js
const [value, updateValue] = useState(0);
// 两种形式，都可行 👇

updateValue(1);
updateValue(previousValue => previousValue + 1);
```

当状态的更新，取决于某个先前的状态值时，这是理想的形式。

<Editor code={CounterFnSetState} />
