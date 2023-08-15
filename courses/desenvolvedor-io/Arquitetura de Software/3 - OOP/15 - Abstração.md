O princípio de Abstração no paradigma de Orientação a Objetos se refere à capacidade de abstrair, ou seja, extrair as características essenciais de um objeto e representá-las em uma classe abstrata. Isso envolve a identificação de atributos e comportamentos comuns entre diferentes objetos e a criação de uma classe genérica que encapsula essas características. A abstração permite que os desenvolvedores se concentrem nas características importantes de um objeto, ignorando detalhes irrelevantes, e fornece uma base sólida para a hierarquia de classes e a reutilização de código. Além disso, a abstração permite que os objetos sejam tratados como entidades independentes com suas próprias operações e propriedades, facilitando a compreensão e o desenvolvimento de programas orientados a objetos.

```typescript
abstract class Shape {
  abstract area(): number;
}

class Circle extends Shape {
  radius: number;
  
  constructor(radius: number) {
    super();
    this.radius = radius;
  }
  
  area() {
    return Math.PI * this.radius * this.radius;
  }
}

class Rectangle extends Shape {
  width: number;
  height: number;
  
  constructor(width: number, height: number) {
    super();
    this.width = width;
    this.height = height;
  }
  
  area() {
    return this.width * this.height;
  }
}

const circle = new Circle(5);
console.log('Circle area:', circle.area());

const rectangle = new Rectangle(3, 4);
console.log('Rectangle area:', rectangle.area());
```

---
Próxima anotação: [[16 - Polimorfismo]]
#arquitetura-de-software #poo 