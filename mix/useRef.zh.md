---
name: useRef
route: /useRef
---

# useRef 🌂

> 笔记

- 返回一个`ref`对象。
- 值可以从访问对象的`.current`属性中访问。
- `.current`属性可以初始化，为初始值，例如`useRef(initialValue)`
- 该对象在组件的整个生命周期内，保持不变。
- [查看文档](https://zh-hans.reactjs.org/docs/hooks-reference.html#useref)。

## 访问 DOM

`<Editor code={AccessDOM} />`

## 像变量一样的实例（通用容器）

除了，持有 DOM refs 之外，`ref`对象可以持有任何值。

`<Editor code={HoldStringVal} />`

您可以更整洁地达到同一效果，存储从一个`setInterval`，返回的值。

```js
function TimerWithRefID() {
  const setIntervalRef = useRef();

  useEffect(() => {
    const intervalID = setInterval(() => {
      // 每 100ms 完成一些东西
    }, 100);

    // 这就是， interval ID 被保存在 ref 对象的位置。
    setIntervalRef.current = intervalID;
    return () => {
      clearInterval(setIntervalRef.current);
    };
  });
}
```
