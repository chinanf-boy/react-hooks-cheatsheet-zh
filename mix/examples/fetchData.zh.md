---
name: 获取数据
menu: 示例
route: examples/fetching-data
order: 1
---

`import Editor from "../../components/Editor" import { fetchOnMount, fetchOnUserEvent, fetchOnUserEventAndLoading } from "../../components/examples/fetchData"`

# 获取数据 🏃

> 在 Suspense 发布之前，获取的数据，证明是钩子的一个很好练习。享受以下示例

## 获取 mount 上的数据

<Editor code={ fetchOnMount } />

## 用户事件触发，响应中获取数据

<Editor code={ fetchOnUserEvent } />

## 显示加载指示器

<Editor code={ fetchOnUserEventAndLoading } />
