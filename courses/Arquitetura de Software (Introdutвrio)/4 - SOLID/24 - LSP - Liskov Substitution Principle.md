>*"Se nada como um pato, voa como um pato, porém precisa de baterias, provavelmente você possui um problema de abstração"*

- O Princípio da Substituição de Liskov (Liskov Substitution Principle, LSP) é um dos cinco princípios SOLID da programação orientada a objetos (POO). Ele foi introduzido por Barbara Liskov em 1987 e estabelece que, se uma classe A é um subtipo de uma classe B, então os objetos do tipo B podem ser substituídos pelos objetos do tipo A sem alterar a corretude do programa.
- Em outras palavras, se um programa é projetado para trabalhar com objetos do tipo B, ele também deve funcionar corretamente com objetos do tipo A, sem a necessidade de modificar o código do programa. Isso implica que as classes derivadas devem ser substituíveis pelas classes base em qualquer contexto sem afetar a integridade do sistema.
- Para garantir que o princípio de Liskov seja respeitado, as classes derivadas devem seguir algumas regras, como:
	- Os métodos da classe derivada devem aceitar os mesmos parâmetros (ou subtipos dos mesmos parâmetros) que os métodos da classe base;
	- Os métodos da classe derivada devem retornar o mesmo tipo (ou um subtipo do mesmo tipo) que os métodos da classe base;
	- A classe derivada não deve lançar exceções que não sejam lançadas pela classe base.
- Ao seguir essas regras, podemos garantir que a substituição de um objeto da classe base por um objeto de uma classe derivada não altere o comportamento do programa.
- Em resumo, o LSP é um princípio importante na programação orientada a objetos, pois permite que o código seja mais flexível e reutilizável, facilitando a manutenção e evolução do sistema.
---
- Vamos supor que temos uma classe base chamada `Animal`, que possui um método `mover()`. Além disso, temos duas classes derivadas, `Cachorro` e `Gato`, que também implementam o método `mover()`. Veja como o Princípio da Substituição de Liskov poderia ser aplicado em TypeScript:

```typescript
class Animal {
  mover() {
    console.log('O animal se moveu.');
  }
}

class Cachorro extends Animal {
  mover() {
    console.log('O cachorro correu.');
  }
}

class Gato extends Animal {
  mover() {
    console.log('O gato pulou.');
  }
}
```

- Nesse exemplo, a classe `Cachorro` e `Gato` são subtipos de `Animal`, pois herdam dela e implementam seu método `mover()`. Assim, podemos utilizar objetos das classes `Cachorro` e `Gato` em qualquer lugar em que um objeto da classe `Animal` é esperado, sem afetar o comportamento do programa.
- Por exemplo, podemos criar um array de animais e adicionar objetos das classes `Cachorro` e `Gato`:

```typescript
const animais: Animal[] = [new Cachorro(), new Gato()];

for (const animal of animais) {
  animal.mover();
}
```

- Nesse caso, ao percorrer o array de animais, cada objeto chama seu próprio método `mover()`, que apresenta comportamentos diferentes. No entanto, o fato de utilizarmos objetos das classes derivadas em um array de objetos da classe base não afeta o funcionamento do programa.
---
Próxima anotação: [[25 - ISP - Interface Segregation Principle]]
#arquitetura-de-software #solid 