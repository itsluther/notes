# split()
O método `split` divide uma string em um array de strings. Ela recebe um delimitador, que pode ser um caractere ou uma expressão regular, como argumento para dividir a string. Por exemplo, se o delimitador for um espaço, você recebe um array de palavras. Se o delimitador for a string vazia, você recebe um array contendo os caracteres da string.

Abaixo há dois exemplos de uso de split, um separando uma string por espaços, e outro por dígitos usando uma expressão regular:

```js
const str = "Hello World";
const bySpace = str.split(" ");

const otherString = "How9are7you2today";
const byDigits = otherString.split(/\d/);
```

`bySpace` terá o valor `["Hello", "World"]` e `byDigits` terá o valor `["How", "are", "you", "today"]`.

Como strings são imutáveis, o método `split` facilita o trabalho com elas.

---
#javascript #programação_funcional #javascript_methods 