---
name: useMemo
route: /usememo
---

# useMemo 🎒

> 笔记：

- `useMemo`返回一个 [memoized](https://en.wikipedia.org/wiki/Memoization) 的值。
- [查看文档](https://zh-hans.reactjs.org/docs/hooks-reference.html#usememo)。

## 入门示例

<Editor noInline code={Starter} />

上面的例子，与[useCallback](/usecallback)类似。

这里唯一的区别是`someValue`是一个对象，而不是一个字符串。由于这个原因，`Instructions`尽管使用了`React.memo`，组件仍会重新渲染。

为什么？

对象是通过引用，进行比较，并且`<App />`重新渲染的话，引用`someValue`随时改变。

有解决方案吗

## 基本用法

对象，`someValue`可以通过`useMemo`，变为记忆化。这可以防止，不必要的重新渲染。

<Editor noInline code={Basic} />
