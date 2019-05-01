---
name: useEffect
route: /useeffect
---

# useEffect 🦋

> 笔记：

- `useEffect`接受一个函数，它可能有副作用代码。
- [查看文档](https://zh-hans.reactjs.org/docs/hooks-reference.html#useeffect)。

> 作用函数指的是，传递给`useEffect`的第一个参数：函数类型。

## Effect 基本作用

<Editor code={BasicEffect}/>

## 清理 Effect

一段时间后，要清理 Effect 是很常见。要实现这一点，`useEffect` 函数需返回一个清除函数。下面是一个`addEventListener`例子。

<Editor code={EffectCleanup}/>

## 多重效果

多个`useEffect`调用可在组件函数中发生，如下所示：

<Editor code={MultipleEffects}/>

> 其实 `useEffect`的调用是可以跳过的，即不一定会在每个渲染上调用。这是通过将第二个数组参数，传递给作用函数来完成的。

## 跳过 Effects（数组依赖）

在下面的例子中，`useEffect`被传递了具有一个值的数组，`[randomNumber]`，因此，作用函数将在 mount（阶段）上，**和**每当生成新的随机数`randomNumber`时，调用。

单击“生成随机数”按钮，以查看此内容。

<Editor code={ArrayDep}/>

## 跳过效果（空数组依赖）

在这个例子中，`useEffect`被传递了一个空数组，`[]`。因此，只在 mount（阶段），调用作用函数。

单击按钮，您会看到，并没有调用作用函数。

<Editor code={ArrayDepMount}/>

## 跳过效果（无数组依赖）

如果没有数组依赖关系，作用函数将在每次渲染后，运行。

```js
useEffect(() => {
  console.log('This will be logged after every render!');
});
```
