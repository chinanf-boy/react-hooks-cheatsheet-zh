---
name: useLayoutEffect
route: /uselayoutEffect
---

# useLayoutEffect

> 笔记：

- `useLayoutEffect`的函数签名，与`useEffect`相当接近。
- `useLayoutEffect`和`useEffect`两者的区别，请接着往下看。
- 查看[文档](https://zh-hans.reactjs.org/docs/hooks-reference.html#uselayouteffect)

```js
useLayoutEffect(() => {
  //do something
}, [arrayDep]);
```

## 与 useEffect 相似的用法

<Editor code={ArrayDep} />

## useLayoutEffect vs useEffect

传递给`useEffect`的函数，会在浏览器布局和绘制后，才会起火。
即在 `render` 已经提交到页面之后。

对于大多数，不应阻止浏览器更新页面的副作用来说，这是可以的。

有些情况下，你可能不想用`useEffect`提供的行为。例如，如果需要对 网页 DOM 进行视觉更改的副作用。为了防止用户，看到更改的闪烁，可以使用`useLayoutEffect`.

> 传递给`useLayoutEffect`的函数，将在浏览器更新屏幕之前运行。
