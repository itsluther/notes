A aridade de uma função é o número de argumentos que ela toma. Realizar currying em uma função significa transformar uma função de aridade N em N funções de aridade 1.

Em outras palavras, a função é reestruturada para que ela receba apenas um argumento e retorne outra função que recebe o próximo argumento e assim por diante.

Exemplo:

```js
function unCurried(x, y) {
  return x + y;
}

function curried(x) {
  return function(y) {
    return x + y;
  }
}

const curried = x => y => x + y

curried(1)(2)
```

`curried(1)(2)` retornaria `3`.

Isso é útil em seu programa quando você não pode fornecer todos os argumentos para uma função de uma só vez. Você pode salvar cada chamada de função em uma variável, que será uma referência à função retornada que recebe o próximo argumento quando ele estiver disponível. Um exemplo usando a função do exemplo acima:

```js
const funcForY = curried(1);
console.log(funcForY(2)); // 3
```

Da mesma forma, aplicação parcial pode ser descrita como a aplicação de alguns argumentos a uma função e o retorno de outra função à qual é aplicada a mais argumentos. Exemplo:

```js
function impartial(x, y, z) {
  return x + y + z;
}

const partialFn = impartial.bind(this, 1, 2);
partialFn(10); // 13
```

---
#javascript 