---
name: useContext
route: /usecontext
---

# useContext 👜

> 笔记：

- `useContext`为您节省了，必须依赖 Context consumer 的压力。
- 与`MyContext.Consumer`以及它公开的渲染 props API 相比，它具有更简单的 API。
- 查看[文档](https://zh-hans.reactjs.org/docs/hooks-reference.html#usecontext)

```js
// 之前:
const ThemeContext = React.createContext('dark');

function Button() {
  return (
    <ThemeContext.Consumer>
      {theme => <button className={theme}>Amazing button</button>}
    </ThemeContext.Consumer>
  );
}
```

这是一个`ThemeContext.Consumer`的在线例子：

<Editor noInline code={ContextConsumerExample}/>

```js
// 现在:
import {useContext} from 'react';

function ButtonHooks() {
  const theme = useContext(ThemeContext);
  return <button className={theme}>Amazing button</button>;
}
```

这是一个`useContext`在线例子：

<Editor noInline code={useContextDisplay}/>
