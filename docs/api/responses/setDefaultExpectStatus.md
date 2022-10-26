# setDefaultExpectStatus

set default expect response status code for all the response assertions.

## Syntax

```js
setDefaultExpectStatus(value)
```

::: tip
- Reference guide for HTTP status codes: [here](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status).
:::


## Usage

### ✅  Correct Usage

```js
response.setDefaultExpectStatus(200)
```

## Arguments

#### > value (number)

response status code.

## Examples

### Normal

```js
const { spec, response } = require('pactum');

response.setDefaultExpectStatus(200)

await spec()
  .get('https://randomuser.me/api');
```

## See Also

- [expectStatus](/api/assertions/expectStatus)
