# Classes
As classes na orientação a objetos funcionam como um molde para os objetos. Os objetos são criados a partir de uma classe e muitos deles podem ser feitos da mesma classe.

- Exemplo: Máquina de biscoito
	- Instâncias

# Classes em JavaScript
- Syntactical sugar
	- Significa que é uma maneira diferente de escrever os objetos como prototype
- Prototype
	- Todo objeto criado no JavaScript é um prototype;
	- Todo objeto prototype herda uma cadeia de outras funcionalidades.

```js
// Definir classe
class Pessoa {
	constructor(nome) {
		this.id = ~~(Math.random() * 100000);
		this.nome = nome;
	}

	dizerNome() {
		console.log(this.nome);
	}
}

const pessoa = new Pessoa('Luther');
console.log(pessoa);
```
---
#javascript #poo