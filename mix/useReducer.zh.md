---
name: useReducer
route: /usereducer
---

# useReducer 🦖

> 笔记：

- `useReducer` 可以用作 `useState` 的替代方法。
- 适用场景：`state` 逻辑较复杂且包含多个子值，或者下一个 `state` 依赖于之前的 `state` 等
- 根据您的用例，您可能会发现 `useReducer` 非常好测试
- [查看文档](https://zh-hans.reactjs.org/docs/hooks-reference.html#usereducer)

## 基本用法

与`useState`不同，`useReducer`调用是一个`reducer`和`initialState`，如下图所示。这个`useReducer`调用返回 State 属性和`dispatch`功能。

<Editor noInline code={BasicExample}/>

## 惰性初始化状态

`useReducer`有第三个参数，是个函数。可以用来初始化状态，并且从该函数返回的任何内容，都将作为状态对象。此函数的调用可用`initialState`作为参数 —— `useReducer`的第二个参数。

<Editor noInline code={InitLazy}/>

## 模仿`this.setState`的行为

`useReducer`使用一个`reducer`，这不是 redux 严格的语法，例如传递给 `reducer` 的第二个参数，`action`不必有`type`属性。这种宽松条件，能做些有趣的操作，例如，重命名第二个参数，并执行以下操作：

<Editor noInline code={ImitateSetState}/>

<!-- todo: usecase where no re-renders when
useReducer returns the same state object -->
