O polimorfismo é um princípio da orientação a objetos que se refere à capacidade de objetos de diferentes classes serem tratados como se fossem da mesma classe. Em outras palavras, objetos polimórficos podem assumir diferentes formas (ou comportamentos) em diferentes contextos. O polimorfismo é importante porque permite que o código seja mais flexível e adaptável a diferentes situações, tornando-o mais fácil de manter e estender.

Existem dois tipos principais de polimorfismo: o polimorfismo de subtipo, que se refere à capacidade de objetos de uma classe filha serem tratados como objetos de uma classe pai; e o polimorfismo paramétrico (ou genérico), que se refere à capacidade de classes e métodos serem genéricos o suficiente para trabalhar com tipos diferentes sem precisar serem modificados.

Em TypeScript, um exemplo de polimorfismo de subtipo ocorre quando uma classe filha sobrescreve um método da classe pai e, em seguida, um objeto da classe filha é tratado como um objeto da classe pai. Isso significa que o objeto da classe filha pode ser usado em qualquer lugar onde um objeto da classe pai seja esperado.

```typescript
class Animal {
  speak() {
    console.log('O animal faz um som');
  }
}

class Dog extends Animal {
  speak() {
    console.log('O cachorro late');
  }
}

const animal: Animal = new Dog();
animal.speak(); // O cachorro late
```

Neste exemplo, a classe `Animal` tem um método `speak` que imprime "O animal faz um som". A classe `Dog` estende a classe `Animal` e sobrescreve o método `speak` para imprimir "O cachorro late". Em seguida, um objeto da classe `Dog` é criado e atribuído a uma variável do tipo `Animal`. Quando o método `speak` é chamado no objeto `animal`, o método sobrescrito na classe `Dog` é executado e imprime "O cachorro late". Isso mostra como o objeto da classe filha pode ser tratado como um objeto da classe pai e como o polimorfismo permite que diferentes objetos tenham comportamentos diferentes em diferentes contextos.

Um exemplo de polimorfismo paramétrico em TypeScript é o uso de tipos genéricos em uma classe ou método. Isso permite que a classe ou método trabalhe com tipos diferentes sem precisar serem modificados para cada tipo específico.

```typescript
class Box<T> {
  value: T;
  constructor(value: T) {
    this.value = value;
  }
}

const box1 = new Box<string>('Olá');
const box2 = new Box<number>(42);

console.log(box1.value); // Olá
console.log(box2.value); // 42
```

Neste exemplo, a classe `Box` é genérica e pode ser usada com qualquer tipo `T`. A classe tem um atributo `value` do tipo `T` e um construtor que recebe um valor do tipo `T`. Em seguida, dois objetos da classe `Box` são criados, um com o tipo `string` e outro com o tipo `number`. O valor de cada objeto é impresso no console, mostrando como a classe `Box` pode ser usada com tipos diferentes sem precisar ser modificada para cada tipo específico.

---
Próxima anotação: [[16 - Polimorfismo]]
#arquitetura-de-software #poo 