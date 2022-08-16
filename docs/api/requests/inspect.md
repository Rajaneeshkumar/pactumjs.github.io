---
tags:
  - debug
---

# inspect

Prints request & response details to the console.

::: tip
- Use it for debugging purpose.
- By default, request and response are printed to the terminal when a test case fails.
:::

## Syntax

```js
inspect()
inspect('path')
```

## Usage

### ✅  Correct Usage

```js
await spec()
  .get('/api/users/1')
  .inspect();
```

```js
await spec()
  .get('/api/users/1')
  .inspect('name')
  .inspect('age');
```