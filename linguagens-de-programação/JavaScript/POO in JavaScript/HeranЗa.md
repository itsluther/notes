# Herança
- Pais e filhos;
- Objetos podem herdar, ou estender, características bases;
- Uma cópia de atributos e métidos de outra classe.

```js
class Veiculo {
	rodas = 4;

	mover(direcao){};
	virar(direcao){};
}

class Moto extends Veiculo {
	constructor() {
		super(); // puxar atributos e métodos do pai
		this.rodas = 2;
	}
}
```

### Saiba
- Um objeto pode estender de outro objeto que pode estender de outro objeto;
- Fácil reutilização de código.
---
#javascript #poo