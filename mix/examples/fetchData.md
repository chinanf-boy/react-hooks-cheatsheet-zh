---
name: fetching data
menu: Examples
route: examples/fetching-data
order: 1
---

`import Editor from "../../components/Editor" import { fetchOnMount, fetchOnUserEvent, fetchOnUserEventAndLoading } from "../../components/examples/fetchData"`

# Fetching Data 🏃

> Until Suspense is released, fetching data proves to be a good exercise for hooks practice.
> Enjoy the examples below

## Fetching data on mount

`<Editor code={ fetchOnMount } />`

## FetchData in response to user event

`<Editor code={ fetchOnUserEvent } />`

## Show Loading Indicator

`<Editor code={ fetchOnUserEventAndLoading } />`
