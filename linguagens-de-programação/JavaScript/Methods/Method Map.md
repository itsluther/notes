# Array.prototype.map() ou map()
O método `map` percorre cada item de um array e retorna um novo array cujos elementos são os resultados da chamada da função de callback para cada item. Isso tudo acontece sem modificar o array original.

A função de callback é chamada com três argumentos. O primeiro argumento é o elemento que está a ser processado. O segundo é o índice deste elemento e o terceiro é o array do qual `map` foi chamado.

Abaixo você vê um exemplo do `map` sendo usado do array `users` para retornar um novo array apenas com os nomes dos usuários. O exemplo usa apenas o primeiro argumento da função de callback por simplicidade.

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const names = users.map(user => user.name);
console.log(names);
```

O console mostraria o valor `[ 'John', 'Amy', 'camperCat' ]`.

---
#javascript #programação_funcional #javascript_methods 