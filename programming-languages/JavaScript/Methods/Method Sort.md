# Sort()
O método `sort` consegue ordenar os elementos de um array de acordo com uma função de callback.

Por exemplo:

```js
function ascendingOrder(arr) {
  return arr.sort(function(a, b) {
    return a - b;
  });
}

ascendingOrder([1, 5, 2, 3, 4]);
```

O código acima retorna `[1, 2, 3, 4, 5]`.

```js
function reverseAlpha(arr) {
  return arr.sort(function(a, b) {
    return a === b ? 0 : a < b ? 1 : -1;
  });
}

reverseAlpha(['l', 'h', 'z', 'b', 's']);
```

Este retorna o valor `['z', 's', 'l', 'h', 'b']`.

O método de ordenação padrão do JavaScript é por valores de ponto Unicode, o que pode nos dar resultados inesperados. Por isso você é encorajado a providenciar uma função de callback para especificar como a ordenação deve ocorrer. Quando tal função callback (comumente chamada de `compareFunction`, ou função de comparação) é providenciada, os elementos do array são ordenados de acordo com o valor de retorno dela: se `compareFunction(a,b)` retornar um valor menor que 0 para dois elementos `a` e `b`, então `a` virá antes de `b`. Se `compareFunction(a,b)` retornar um valor maior que 0 para dois elementos `a` e `b`, então `b` virá antes de `a`. Finalmente, se `compareFunction(a,b)` retornar 0, então `a` e `b` não trocarão de lugar entre si.

```js
// Retorne o array em ordem alfabética
function alphabeticalOrder(arr) {
  return arr.sort((a, b) => a === b ? 0 : a < b ? -1 : 1);
}

alphabeticalOrder(["a", "d", "c", "a", "z", "g"]);
```

Um efeito colateral do método `sort` é que ele altera a ordem dos elementos no array original. Em outras palavras, o array sofre uma mutação. Uma forma de evitar isto é primeiro concatenar um array vazio ao array a ordenar (não esqueça que `slice` e `concat` retornam um novo array) e, então, executar o método `sort` no novo array.

```js
const globalArray = [5, 6, 3, 2, 9];
function nonMutatingSort(arr) {
  const newArr = arr
    .slice()
	.sort((a, b) => a === b ? 0 : a < b ? -1 : 1);

  return newArr;
}

nonMutatingSort(globalArray);
```
---
#javascript #programação_funcional #javascript_methods 