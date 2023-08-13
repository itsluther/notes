# Abstração
`Template ou identidade de uma classe que será construída no futuro.`
- Atributos e métodos podem ser criados na classe de Abstração (Superclasse), mas a *implementação dos métodos e atributos*, só poderá ser feita na classe que irá herdar essa *Abstração*.

```js
// definir
class Parafuso { // Superclasse - Abstrata
	constructor() {
		if (this.constructor === Parafuso) {
			throw new Error("Classe abstrata não pode ser instânciada.")
		}
	}

	get tipo() {
		throw new Error('Método "get tipo()" precisa ser implementado."')
	}
}

class Fenda extends Parafuso {
	constructor() { super() }
	get tipo() {
		return 'fenda'
	}
}

class Allen extends Parafuso {}
```
---
#javascript #poo