---
title: TypeScript 笔记
date: 2021-10-26 08:41:06
categories: Web
tags: TypeScript
---

## 泛型

< 任意字符 >，一般使用 T 来表示。

如下代码使用了泛型，函数的形参 `first` 和 `second` 分别指定为 T 和 P，譬如可以在调用方法时，指定 `T` 和 `P` 分别为 `string` 和 `number` 类型。

```typescript
function join<T, P>(first: T, second: P) {
	return `${first}${second}`
}
const num = join<string, number>("1", 2) //12
```

### 约束泛型类型

```typescript
function join<T extends number>{
}
```

