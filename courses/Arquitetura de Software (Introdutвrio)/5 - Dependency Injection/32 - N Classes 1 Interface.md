O padrão N Classes 1 Interface é uma abordagem para organizar e gerenciar a complexidade de um sistema em que há várias classes que implementam funcionalidades semelhantes. Em vez de ter uma única classe monolítica que execute todas as funcionalidades, o sistema é dividido em várias classes menores, cada uma responsável por uma parte específica da funcionalidade. Em seguida, uma interface é criada para definir um conjunto de métodos comuns que todas as classes devem implementar.

O benefício de usar o padrão N Classes 1 Interface é que ele permite uma maior flexibilidade e manutenção do sistema. Cada classe é responsável por uma tarefa específica, o que torna mais fácil entender e modificar o comportamento do sistema. Além disso, a interface comum fornece um meio para as classes se comunicarem e trabalharem juntas de forma consistente.

Em TypeScript, podemos implementar o padrão N Classes 1 Interface da seguinte forma:

```typescript
interface IShape {
  calculateArea(): number;
}

class Rectangle implements IShape {
  constructor(private width: number, private height: number) {}

  calculateArea(): number {
    return this.width * this.height;
  }
}

class Circle implements IShape {
  constructor(private radius: number) {}

  calculateArea(): number {
    return Math.PI * Math.pow(this.radius, 2);
  }
}
```

Neste exemplo, estamos usando uma interface `IShape` para definir um conjunto comum de métodos que todas as classes que implementam formas geométricas devem ter. Em seguida, estamos implementando duas classes que implementam esta interface, `Rectangle` e `Circle`. Cada uma dessas classes é responsável por calcular a área de uma forma geométrica específica (um retângulo e um círculo, respectivamente).

Observe que a interface `IShape` fornece um conjunto comum de métodos que ambas as classes implementam. Isso significa que podemos escrever código genérico que lida com objetos do tipo `IShape`, sem se preocupar com a implementação específica de cada forma geométrica.

```typescript
function calculateTotalArea(shapes: IShape[]): number {
  let totalArea = 0;
  for (let shape of shapes) {
    totalArea += shape.calculateArea();
  }
  return totalArea;
}

const shapes: IShape[] = [new Rectangle(5, 10), new Circle(7)];

console.log(calculateTotalArea(shapes)); // Saída: 260.681... 
```

Neste exemplo, estamos passando um array de objetos `IShape` para a função `calculateTotalArea`. A função itera sobre cada objeto `IShape` no array e chama o método `calculateArea` correspondente para calcular a área de cada forma geométrica. Observe que a função não precisa saber como cada forma geométrica é implementada, apenas precisa saber que todas elas implementam a interface `IShape`.

---
Próxima anotação: [[33 - O que é um código limpo]]
#arquitetura-de-software #dependecy-injection