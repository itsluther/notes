# Array.prototype.filter ou filter()
O `filter` chama uma função para cada elemento de um array e constrói um novo array contendo apenas os elementos para os quais a função retorna `true`. Em outras palavras, ele filtra o array de acordo com a função passada a ele. Ele o faz sem alterar o array original assim como `map`.

A função de callback toma três argumentos. O primeiro argumento é o elemento que está a ser processado. O segundo é o índice deste elemento e o terceiro é o array do qual `filter` foi chamado.

Abaixo você vê um exemplo do `filter` sendo usado do array `users` para retornar um novo array apenas com os usuários cuja idade é menor que 30. O exemplo usa apenas o primeiro argumento da função de callback por simplicidade.

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const usersUnder30 = users.filter(user => user.age < 30);
console.log(usersUnder30); 
```

O console mostraria o valor `[ { name: 'Amy', age: 20 }, { name: 'camperCat', age: 10 } ]`.

---
#javascript #programação_funcional #javascript_methods 