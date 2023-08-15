- O princípio da herança é um conceito central no paradigma de Orientação a Objetos, que permite a criação de novas classes a partir de classes existentes, herdando seus atributos e comportamentos. Isso significa que uma classe pode ser definida como uma extensão ou especialização de outra classe, aproveitando sua estrutura e funcionalidades, mas adicionando ou modificando seus próprios elementos. A herança é uma forma poderosa de reutilização de código, permitindo que os desenvolvedores criem classes mais específicas e complexas a partir de classes mais genéricas e simples.

```typescript
class Animal {
	name: string;
	
	constructor(name: string) { 
		this.name = name;
	} 
	
	move(distanceInMeters: number = 0) { 
		console.log(`${this.name} moved ${distanceInMeters}m.`); 
	} 
}

class Dog extends Animal {
	bark() {
		console.log('Woof! Woof!');
	}
}

const dog = new Dog('Fido');
dog.bark();
dog.move(10);
```
---
Próxima anotação: [[15 - Abstração]]
#arquitetura-de-software #poo 