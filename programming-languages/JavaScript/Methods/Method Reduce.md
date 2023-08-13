# Array.prototype.reduce() ou reduce()
`Array.prototype.reduce()`, ou simplesmente `reduce()`, realiza as operações mais gerais de todas as operações de array em JavaScript. Você pode resolver quase qualquer problema de processamento de array usando o método `reduce`.

O método `reduce` permite formas mais gerais de processamento de array, e é possível mostrar que tanto o `filter` quanto o `map` podem ser derivados como aplicações especiais de `reduce`. O método `reduce` percorre cada elemento de um array e retorna um valor (uma string, um número, um objeto ou array). Isso pode ser feito através de uma função de callback que é chamada para cada elemento.

A função de callback recebe quatro argumentos. O primeiro argumento é conhecido como o acumulador, ao qual é atribuído o resultado da função de callback na iteração anterior. O segundo é o elemento a ser processado. O terceiro é o índice do elemento e o quarto é o array do qual `reduce` foi chamado.

Além da função de callback, `reduce` tem um parâmetro adicional que recebe um valor inicial para o acumulador. Se o segundo parâmetro não for usado, então a primeira iteração é ignorada e ao acumulador é atribuído o primeiro elemento do array na segunda iteração.

Veja abaixo um exemplo usando `reduce` no array `users` para retornar a soma de todas as idades de todos os usuários. O exemplo usa apenas os dois primeiros argumentos pela simplicidade.

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const sumOfAges = users.reduce((sum, user) => sum + user.age, 0);
console.log(sumOfAges);
```

O console mostra o valor `64`.

No próximo exemplo abaixo, veja como um objeto pode ser retornado contendo os nomes dos usuários como chaves e suas idades como valores.

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const usersObj = users.reduce((obj, user) => {
  obj[user.name] = user.age;
  return obj;
}, {});
console.log(usersObj);
```

O console mostra o valor `{ John: 34, Amy: 20, camperCat: 10 }`.

---
#javascript #programação_funcional #javascript_methods
