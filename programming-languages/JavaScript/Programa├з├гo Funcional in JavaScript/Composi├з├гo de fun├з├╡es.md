# Composição de funções
- Um *encadeamento* de funções;
- Uma função que retorna um dado e vai para outra função, que retorna um dado e vai pra outra função, que retorna...

```js
const people = ['Rafa', 'Diego', 'Dani', 'Rod'];
const upperCasePeopleThatStartsWithD = people
										.filter(person => person.startsWith('D'))
										.map(dPerson => dPerson.toUpperCase());
```
---
#javascript #programação_funcional 