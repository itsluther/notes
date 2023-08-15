## Propósito

O **Facade** é um padrão de projeto estrutural que fornece uma interface simplificada para uma biblioteca, um framework, ou qualquer conjunto complexo de classes.

## Problema

Imagine que você precisa fazer seu código funcionar com um amplo conjunto de objetos que pertencem a uma sofisticada biblioteca ou framework. Normalmente, você precisaria inicializar todos aqueles objetos, rastrear as dependências, executar métodos na ordem correta, e assim por diante.
Como resultado, a lógica de negócio de suas classes vai ficar firmemente acoplada aos detalhes de implementação das classes de terceiros, tornando difícil compreendê-lo e mantê-lo.

## Solução

Uma fachada é uma classe que fornece uma interface simples para um subsistema complexo que contém muitas partes que se movem. Uma fachada pode fornecer funcionalidades limitadas em comparação com trabalhar com os subsistemas diretamente. Contudo, ela inclui apenas aquelas funcionalidades que o cliente se importa.
Ter uma fachada é útil quando você precisa integrar sua aplicação com uma biblioteca sofisticada que tem dúzias de funcionalidades, mas você precisa de apenas um pouquinho delas.
Por exemplo, uma aplicação que carrega vídeos curtos engraçados com gatos para redes sociais poderia potencialmente usar uma biblioteca de conversão de vídeo profissional. Contudo, tudo que ela realmente precisa é uma classe com um único método `codificar(nomeDoArquivo, formato)`. Após criar tal classe e conectá-la com a biblioteca de conversão de vídeo, você terá sua primeira fachada.

## Aplicabilidade

Utilize o padrão Facade quando você precisa ter uma interface limitada mas simples para um subsistema complexo.
Com o passar do tempo, subsistemas ficam mais complexos. Até mesmo aplicar padrões de projeto tipicamente leva a criação de mais classes. Um subsistema pode tornar-se mais flexível e mais fácil de se reutilizar em vários contextos, mas a quantidade de códigos padrão e de configuração que ele necessita de um cliente cresce cada vez mais. O Facade tenta consertar esse problema fornecendo um atalho para as funcionalidades mais usadas do subsistema que corresponde aos requerimentos do cliente.
Utilize o Facade quando você quer estruturar um subsistema em camadas.
Crie fachadas para definir pontos de entrada para cada nível de um subsistema. Você pode reduzir o acoplamento entre múltiplos subsistemas fazendo com que eles se comuniquem apenas através de fachadas.
Por exemplo, vamos retornar ao nosso framework de conversão de vídeo. Ele pode ser quebrado em duas camadas: relacionados a vídeo e áudio. Para cada camada, você cria uma fachada e então faz as classes de cada camada se comunicarem entre si através daquelas fachadas. Essa abordagem se parece muito com o padrão [Mediator](https://refactoring.guru/pt-br/design-patterns/mediator).

##  Como implementar

1. Verifique se é possível providenciar uma interface mais simples que a que o subsistema já fornece. Você está no caminho certo se essa interface faz o código cliente independente de muitas classes do subsistema.
2. Declare e implemente essa interface em uma nova classe fachada. A fachada deve redirecionar as chamadas do código cliente para os objetos apropriados do subsistema. A fachada deve ser responsável por inicializar o subsistema e gerenciar seu ciclo de vida a menos que o código cliente já faça isso.
3. Para obter o benefício pleno do padrão, faça todo o código cliente se comunicar com o subsistema apenas através da fachada. Agora o código cliente fica protegido de qualquer mudança no código do subsistema. Por exemplo, quando um subsistema recebe um upgrade para uma nova versão, você só precisa modificar o código na fachada.
4. Se a fachada ficar [grande demais](https://refactoring.guru/pt-br/smells/large-class), considere extrair parte de seu comportamento para uma nova e refinada classe fachada.

##  Prós e contras

- Prós
	-  Você pode isolar seu código da complexidade de um subsistema.

- Contras
	-  Uma fachada pode se tornar [um objeto deus](https://refactoring.guru/pt-br/antipatterns/god-object) acoplado a todas as classes de uma aplicação.
 
---

## Exemplo em TypeScript

```typescript
// Subsistema 1
class OrderValidation {
  public validate(orderId: number): boolean {
    console.log(`Validating order: ${orderId}`);
    // Lógica de validação da ordem...
    return true;
  }
}

// Subsistema 2
class PaymentProcessing {
  public processPayment(orderId: number): void {
    console.log(`Processing payment for order: ${orderId}`);
    // Lógica de processamento do pagamento...
  }
}

// Subsistema 3
class Shipping {
  public shipOrder(orderId: number): void {
    console.log(`Shipping order: ${orderId}`);
    // Lógica de envio do pedido...
  }
}

// Facade
class OrderFacade {
  private orderValidation: OrderValidation;
  private paymentProcessing: PaymentProcessing;
  private shipping: Shipping;

  constructor() {
    this.orderValidation = new OrderValidation();
    this.paymentProcessing = new PaymentProcessing();
    this.shipping = new Shipping();
  }

  public processOrder(orderId: number): void {
    const isValid = this.orderValidation.validate(orderId);

    if (isValid) {
      this.paymentProcessing.processPayment(orderId);
      this.shipping.shipOrder(orderId);
      console.log('Order processed successfully!');
    } else {
      console.log('Order validation failed. Unable to process the order.');
    }
  }
}

// Cliente
const facade = new OrderFacade();
facade.processOrder(123);
```

Neste exemplo, temos três subsistemas representados pelas classes `OrderValidation`, `PaymentProcessing` e `Shipping`. Cada um desses subsistemas possui suas próprias responsabilidades, como validação de pedido, processamento de pagamento e envio de pedidos.
A classe `OrderFacade` atua como uma fachada que fornece uma interface simplificada para interagir com esses subsistemas. Ela encapsula a complexidade desses subsistemas e coordena as operações necessárias para processar um pedido.
No exemplo, o cliente cria uma instância da fachada `OrderFacade` e chama o método `processOrder` para processar um pedido específico. A fachada realiza a validação do pedido usando o subsistema `OrderValidation`, processa o pagamento usando o subsistema `PaymentProcessing` e envia o pedido usando o subsistema `Shipping`.
O uso da fachada simplifica a interação com os subsistemas subjacentes, ocultando sua complexidade e fornecendo uma interface única e fácil de usar.

---
Próxima anotação: [[44 - Structural Pattern  - Composite]]
#arquitetura-de-software #design-patterns