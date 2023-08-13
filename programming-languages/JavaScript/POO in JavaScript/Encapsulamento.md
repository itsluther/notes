# Encapsulamento
`Você pode dirigir um carro, mas não precisa conhecer como ele foi construído.`
- Colocar numa cápsula;
- Agrupamento de funções e variáveis;
- Esconder detalhes de implementação;
- Camada de segurança para os atributos e métodos.

# Encapsulamento no código JavaScript
```js
// Estrutural
let altura = 50;
let largura = 60;

function calcularArea() {
	return altura * largura;
}

let area = calcularArea();
```

```js
// Orientado a Objetos
class Poligono {
	constructor(altura, largura) {
		this.altura = altura;
		this.largura = largura;
	}

	get area() {
		return this.#calcularArea();
	}

	// necessário colocar # antes do nome da função para torná-la anônima
	#calcularArea() {
		return this.altura * this.largura;
	}
}

let poligono = new Poligono(50, 50);
console.log(poligono.area());
console.log(#calcularArea()); // Não existe, pois ela está escondida e não pode ser usada fora do escopo do classe.
```
---
#javascript #poo 