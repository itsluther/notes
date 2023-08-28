# First Class function
- Podem estar em qualquer lugar, inclusive, como parâmetro de outras funções;
- A função poderá ser entendida como uma variável.

```js
const sayMyName = () => console.log('Luther');
const runFunction = fn => fn();

runFunction(sayMyName);
runFunction(() => console.log('discover'));

console.log(runFunction(Math.random));
```
---
#javascript #programação_funcional 