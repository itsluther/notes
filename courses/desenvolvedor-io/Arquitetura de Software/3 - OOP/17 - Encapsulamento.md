- O princípio de Encapsulamento da orientação a objetos é a ideia de que uma classe deve esconder seus detalhes de implementação e fornecer uma interface bem definida para interagir com seus objetos. Em outras palavras, é a capacidade de proteger as propriedades e métodos de uma classe de acesso externo não autorizado e permitir que eles sejam acessados ​​apenas por meio de métodos públicos ou interfaces definidas.
- O encapsulamento é importante porque ajuda a proteger os dados de uma classe, garantindo que eles não possam ser alterados diretamente de fora da classe. Em vez disso, o acesso aos dados é controlado por meio de métodos públicos que validam e manipulam os dados de maneira apropriada. Isso torna o código mais seguro, confiável e fácil de manter, pois os detalhes de implementação da classe são isolados do restante do sistema e podem ser modificados sem afetar outros componentes.

- Em TypeScript, há três tipos de modificadores de classe `public`, `private` e `protected`.
	1.  `public`: é o modificador de acesso padrão e permite que as propriedades e métodos da classe sejam acessados de qualquer lugar, tanto dentro da classe quanto fora dela.
	2.  `private`: é um modificador de acesso que restringe o acesso a propriedades e métodos da classe apenas dentro da própria classe. Isso significa que as propriedades e métodos privados não podem ser acessados ​​de fora da classe.
	3.  `protected`: é um modificador de acesso que permite que as propriedades e métodos da classe sejam acessados ​​dentro da própria classe e em suas classes derivadas (subclasses).  
- Esses modificadores de acesso ajudam a controlar a visibilidade e o acesso às propriedades e métodos de uma classe, garantindo a encapsulação e a segurança dos dados. O uso adequado dos modificadores de acesso também pode tornar o código mais fácil de entender e manter, pois limita a exposição dos detalhes de implementação da classe para o mundo externo.

- Em TypeScript, o encapsulamento pode ser alcançado usando modificadores de acesso (`public`, `private` e `protected`) para controlar a visibilidade dos membros de uma classe. Aqui está um exemplo simples de encapsulamento em TypeScript:
```typescript
class ContaBancaria {
  private saldo: number;

  constructor(saldoInicial: number) {
    this.saldo = saldoInicial;
  }

  public depositar(valor: number): void {
    this.saldo += valor;
  }

  public sacar(valor: number): boolean {
    if (valor > this.saldo) {
      return false;
    }
    this.saldo -= valor;
    return true;
  }

  public getSaldo(): number {
    return this.saldo;
  }
}
```
- Neste exemplo, a classe `ContaBancaria` encapsula o saldo da conta bancária usando o modificador `private`. Isso significa que o saldo não pode ser acessado diretamente de fora da classe. Em vez disso, a classe fornece métodos públicos (`depositar`, `sacar` e `getSaldo`) para interagir com o saldo de maneira controlada e validada.

- O método `depositar` adiciona um valor ao saldo, enquanto o método `sacar` verifica se o valor do saque é menor ou igual ao saldo e, se sim, subtrai o valor do saldo. O método `getSaldo` retorna o valor atual do saldo.

- Ao encapsular o saldo dentro da classe e controlar seu acesso por meio de métodos públicos, a classe `ContaBancaria` se torna mais segura e flexível. Os usuários da classe só podem acessar o saldo de maneira apropriada e validada, evitando erros e problemas de segurança.
---
Próxima anotação: [[17 - Encapsulamento]]
#arquitetura-de-software #poo #typescript 