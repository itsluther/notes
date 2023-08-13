- Open-Closed Principle é um dos princípios do SOLID, um conjunto de diretrizes que visam melhorar a qualidade do software.
- O Open-Closed Principle (Princípio Aberto-Fechado) afirma que as entidades de software (classes, módulos, funções etc.) devem ser abertas para extensão, mas fechadas para modificação. Isso significa que uma entidade de software deve ser fácil de estender, permitindo a adição de novas funcionalidades sem alterar o código existente, mas deve ser difícil de modificar, evitando que mudanças em uma parte do código afetem outras partes do sistema.
- Um exemplo de como o Open-Closed Principle pode ser aplicado é através do uso de interfaces em vez de classes concretas. Uma interface define um conjunto de comportamentos que uma classe pode implementar, permitindo que novas classes possam ser criadas e adicionadas ao sistema sem modificar o código existente. Dessa forma, a funcionalidade do sistema pode ser estendida sem alterar o comportamento das classes existentes.
- Outra maneira de aplicar o Open-Closed Principle é através do uso de padrões de projeto como o padrão Strategy. Esse padrão permite que um objeto altere seu comportamento dinamicamente, escolhendo uma estratégia de entre várias opções disponíveis. Dessa forma, o comportamento do objeto pode ser estendido sem modificar o código existente.
- Em resumo, o Open-Closed Principle incentiva a criação de um software que seja fácil de estender e difícil de modificar, o que ajuda a garantir que o código seja mais robusto e menos propenso a erros.
---
- Suponha que temos uma classe chamada `PaymentProcessor` que é responsável por processar pagamentos. Atualmente, essa classe processa apenas pagamentos com cartão de crédito. No entanto, queremos que a classe seja facilmente extensível para processar outros tipos de pagamentos, como PayPal, boleto bancário, entre outros.
- Para aplicar o Open-Closed Principle, vamos criar uma interface `PaymentProvider` que define um método `processPayment()` e, em seguida, modificar a classe `PaymentProcessor` para aceitar qualquer objeto que implemente essa interface:

```typescript
interface PaymentProvider {
  processPayment(amount: number): void;
}

class PaymentProcessor {
  constructor(private paymentProvider: PaymentProvider) {}

  public processPayment(amount: number): void {
    this.paymentProvider.processPayment(amount);
  }
}
```

- Agora, podemos criar uma nova classe que implementa a interface `PaymentProvider` para lidar com pagamentos com PayPal:

```typescript
class PayPalPaymentProvider implements PaymentProvider {
  public processPayment(amount: number): void {
    // Lógica para processar pagamentos com PayPal
  }
}
```

- E, em seguida, podemos instanciar a classe `PaymentProcessor` passando uma instância da classe `PayPalPaymentProvider`:

```typescript
const paymentProcessor = new PaymentProcessor(new PayPalPaymentProvider());
paymentProcessor.processPayment(100);
```

- Com isso, podemos facilmente adicionar novos provedores de pagamento, sem modificar a classe `PaymentProcessor`. Por exemplo, podemos criar uma nova classe `BoletoPaymentProvider` e passá-la para a classe `PaymentProcessor`:

```typescript
class BoletoPaymentProvider implements PaymentProvider {
  public processPayment(amount: number): void {
    // Lógica para processar pagamentos com boleto bancário
  }
}

const paymentProcessor = new PaymentProcessor(new BoletoPaymentProvider());
paymentProcessor.processPayment(100);
```

- Assim, estamos seguindo o princípio Open-Closed, pois a classe `PaymentProcessor` está aberta para extensão (podemos adicionar novos provedores de pagamento sem modificar o código existente), mas fechada para modificação (não precisamos alterar o código da classe `PaymentProcessor` para adicionar novos provedores de pagamento).
---
Próxima anotação: [[24 ]]
#arquitetura-de-software #solid 