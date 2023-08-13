https://refactoring.guru/pt-br/design-patterns/abstract-factory
---

![[Pasted image 20230412211448.png]]

---
- O Abstract Factory é um padrão de criação que fornece uma interface para criar famílias de objetos relacionados ou dependentes sem especificar suas classes concretas. Isso significa que o padrão Abstract Factory é uma maneira de encapsular um conjunto de fábricas concretas que têm uma relação lógica entre si.
- Por exemplo, imagine que você esteja desenvolvendo um jogo de computador com diferentes raças de personagens. Cada raça tem seu próprio conjunto de personagens, armas, veículos e outros itens. Usando o padrão Abstract Factory, você pode criar uma interface para cada tipo de fábrica de personagens (por exemplo, fábrica de elfos, fábrica de orcs, etc.) e fornecer métodos para criar personagens, armas, veículos e outros itens específicos para cada raça.
- A principal vantagem do padrão Abstract Factory é que ele permite que você altere as fábricas concretas que são usadas em tempo de execução, sem afetar o restante do código. Isso significa que você pode facilmente mudar a aparência e comportamento do seu jogo, simplesmente mudando as fábricas que são usadas para criar os objetos.
- Outra vantagem do padrão Abstract Factory é que ele ajuda a garantir que o código do seu jogo seja altamente coeso e modular. Cada fábrica concreta é responsável por criar objetos que fazem parte de uma família lógica, tornando mais fácil adicionar ou remover funcionalidades do seu jogo sem afetar outras partes do código.
- No entanto, uma desvantagem do padrão Abstract Factory é que ele pode tornar o código mais complexo, pois exige a criação de várias classes adicionais. Além disso, o padrão Abstract Factory pode ser menos útil em projetos com poucas famílias de objetos relacionados ou dependentes.

```typescript
// interface para a fábrica abstrata de personagens
interface CharacterFactory {
  createWarrior(): Warrior;
  createMage(): Mage;
}

// classe abstrata para guerreiros
abstract class Warrior {
  abstract attack(): void;
}

// classe abstrata para magos
abstract class Mage {
  abstract castSpell(): void;
}

// classe concreta para guerreiros de humanos
class HumanWarrior extends Warrior {
  attack() {
    console.log("Human warrior attacks with sword!");
  }
}

// classe concreta para magos de humanos
class HumanMage extends Mage {
  castSpell() {
    console.log("Human mage casts fireball!");
  }
}

// classe concreta para guerreiros de elfos
class ElfWarrior extends Warrior {
  attack() {
    console.log("Elf warrior attacks with bow and arrows!");
  }
}

// classe concreta para magos de elfos
class ElfMage extends Mage {
  castSpell() {
    console.log("Elf mage casts ice spell!");
  }
}

// fábrica concreta para personagens humanos
class HumanFactory implements CharacterFactory {
  createWarrior() {
    return new HumanWarrior();
  }
  createMage() {
    return new HumanMage();
  }
}

// fábrica concreta para personagens elfos
class ElfFactory implements CharacterFactory {
  createWarrior() {
    return new ElfWarrior();
  }
  createMage() {
    return new ElfMage();
  }
}

// exemplo de uso
const humanFactory = new HumanFactory();
const humanWarrior = humanFactory.createWarrior();
const humanMage = humanFactory.createMage();
humanWarrior.attack(); // Human warrior attacks with sword!
humanMage.castSpell(); // Human mage casts fireball!

const elfFactory = new ElfFactory();
const elfWarrior = elfFactory.createWarrior();
const elfMage = elfFactory.createMage();
elfWarrior.attack(); // Elf warrior attacks with bow and arrows!
elfMage.castSpell(); // Elf mage casts ice spell!
```

---
- O padrão Abstract Factory é especialmente útil quando você tem um contexto que envolve a criação de vários objetos similares ou relacionados.
- **Por exemplo**, imagine que você está desenvolvendo um sistema de processamento de pagamentos que precisa lidar com diferentes tipos de transações financeiras, como transferências bancárias, pagamentos com cartão de crédito, pagamentos com boleto bancário, entre outros. Cada tipo de transação tem suas próprias regras e configurações específicas.
- Nesse caso, você pode usar o padrão Abstract Factory para criar uma fábrica abstrata para cada tipo de transação. Cada fábrica concreta seria responsável por criar objetos de um tipo específico de transação dentro do sistema.
- Dessa forma, o padrão Abstract Factory ajuda a encapsular a lógica de criação de objetos relacionados em uma classe separada, o que pode facilitar a manutenção e a extensão do sistema ao longo do tempo. Além disso, o padrão permite que você altere as classes concretas que são usadas pelo sistema sem precisar modificar o código em vários lugares diferentes, o que pode tornar o código mais flexível e menos propenso a erros.
---
Próxima anotação: [[40 - Creational Pattern - Factory Method]]
#arquitetura-de-software #design-patterns