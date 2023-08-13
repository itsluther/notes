- O encapsulamento em Orientação a objetos é um conceito que consiste em esconder o estado interno de um objeto e permitir o acesso a ele somente por meio de métodos definidos na classe desse objeto. Isso garante que o objeto mantenha seu estado consistente e que seu uso seja controlado, evitando erros e aumentando a segurança e a confiabilidade do programa.
```typescript
class Pessoa {
  private nome: string;
  protected idade: number;

  constructor(nome: string, idade: number) {
    this.nome = nome;
    this.idade = idade;
  }

  public getNome(): string {
    return this.nome;
  }

  public setNome(nome: string): void {
    this.nome = nome;
  }

  public getIdade(): number {
    return this.idade;
  }

  public setIdade(idade: number): void {
    this.idade = idade;
  }
}

let pessoa = new Pessoa("João", 25);
console.log(pessoa.getNome()); // "João"
pessoa.setNome("Maria");
console.log(pessoa.getNome()); // "Maria"
console.log(pessoa.idade); // ERRO: a propriedade 'idade' é protegida e só pode ser acessada dentro da classe 'Pessoa' e suas subclasses
```
- Neste exemplo, a classe `Pessoa` tem dois atributos, `nome` e `idade`, onde `nome` é privado e `idade` é protegido. Os métodos `getNome()` e `setNome()` permitem obter e definir o nome da pessoa, enquanto os métodos `getIdade()` e `setIdade()` permitem obter e definir a idade da pessoa. Observe que a propriedade `idade` é protegida e só pode ser acessada dentro da classe `Pessoa` e suas subclasses. Isso garante que o estado interno da classe seja mantido e controlado.
---
Próxima anotação: [[21 - Princípios SOLID]]
#arquitetura-de-software #poo