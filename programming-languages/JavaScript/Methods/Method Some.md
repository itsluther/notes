# some()
O método `some` funciona verificando se _pelo menos um_ dos elementos de um array passam em um teste. Ele retorna um booleano: `true` se pelo menos um valor atende ao critério e `false` caso contrário.

Por exemplo, o código a seguir verifica se qualquer elemento no array `numbers` é menor que 10:

```js
const numbers = [10, 50, 8, 220, 110, 11];

numbers.some(function(currentValue) {
  return currentValue < 10;
});
```

O método `some` retorna `true`.

---
#javascript #programação_funcional #javascript_methods 