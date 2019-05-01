---
name: useCallback
route: /usecallback
---

# useCallback 👁

> 笔记：

- `useCallback`，返回一个[memoized](https://en.wikipedia.org/wiki/Memoization)的回调函数。
- 查看[文档](https://zh-hans.reactjs.org/docs/hooks-reference.html#usecallback)

## 入门示例

以下示例，是后面的解释和代码片段的基础。

<Editor noInline code={Starter} />

在上面的示例中，父组件`<Age />`，每当单击“变老”按钮时，都会更新（并重新渲染）。因此，`<Instructions />`子组件也重新渲染，因为`doSomething` prop，它传递了一个新的回调，带有一个新的`someValue`。

> 注意：即使是`Instructions`子组件，使用`React.memo`优化性能，它仍然是重新渲染的。

怎么解决这个问题？即防止`<Instructions />`不必要的重新渲染？

## useCallback 具有参考数组的函数

<Editor noInline code={ReferencedFn} />

## useCallback 的内联形态

`useCallback`也适用于内联函数。这是与内联版本的`useCallback`调用解决方案，与上面同一作用。

<Editor noInline code={InlineFn} />
