A arquitetura Saga é um padrão arquitetural que tem como objetivo coordenar processos de longa duração em sistemas distribuídos ou complexos, onde uma ação ou evento em um domínio de negócios pode desencadear uma série de outras ações ou eventos em diferentes partes do sistema. Isso é particularmente útil em cenários de micro serviços e sistemas distribuídos, nos quais é essencial manter a consistência dos dados e garantir que as operações sejam executadas de maneira coordenada.

Um processo Saga é uma sequência de etapas ou ações que devem ser executadas em resposta a um evento ou comando. Cada etapa da Saga representa uma tarefa que pode ser executada em um serviço ou componente específico do sistema. À medida que cada etapa é executada com sucesso, a Saga avança para a próxima etapa. Se ocorrer algum erro durante uma etapa, a Saga pode desencadear etapas de compensação para reverter as operações já realizadas e manter a integridade do sistema.

**Exemplo em TypeScript de uma Classe Saga Simples:**

Aqui está um exemplo básico de uma classe Saga em TypeScript para ilustrar como você pode implementar um processo de Saga simples. Neste exemplo, vamos considerar uma Saga que lida com o processo de compra de um produto online, onde várias etapas são executadas, incluindo a reserva de estoque, o processamento do pagamento e o envio do pedido.

```typescript
class PurchaseSaga {
  async start() {
    try {
      // Etapa 1: Reservar o estoque do produto
      const stockReserved = await this.reserveStock();

      // Etapa 2: Processar o pagamento
      const paymentProcessed = await this.processPayment();

      // Etapa 3: Enviar o pedido
      const orderShipped = await this.shipOrder();

      // Se todas as etapas forem concluídas com sucesso, a Saga é bem-sucedida.
      if (stockReserved && paymentProcessed && orderShipped) {
        console.log("Compra concluída com sucesso!");
      } else {
        console.log("Erro na Saga: Algo deu errado.");
        // Aqui você pode implementar etapas de compensação se necessário.
      }
    } catch (error) {
      console.error("Erro na Saga:", error);
      // Aqui você pode implementar etapas de compensação se necessário.
    }
  }

  async reserveStock() {
    // Implemente a lógica para reservar o estoque aqui.
    // Retorne true se a reserva for bem-sucedida ou false se houver um erro.
  }

  async processPayment() {
    // Implemente a lógica para processar o pagamento aqui.
    // Retorne true se o pagamento for bem-sucedido ou false se houver um erro.
  }

  async shipOrder() {
    // Implemente a lógica para enviar o pedido aqui.
    // Retorne true se o envio for bem-sucedido ou false se houver um erro.
  }
}

// Uso da Saga
const purchaseSaga = new PurchaseSaga();
purchaseSaga.start();
```

Neste exemplo, a classe `PurchaseSaga` possui três etapas principais (reserva de estoque, processamento de pagamento e envio de pedido) e verifica se cada etapa é bem-sucedida antes de prosseguir para a próxima. Se ocorrer um erro em qualquer etapa, você pode implementar a lógica de compensação adequada para lidar com a reversão das operações já realizadas.

---

![[Pasted image 20230918072230.png]]

![[Pasted image 20230918073122.png]]

---
[[39 - CQRS Prática - Repositório GitHub]] - #ddd #domínios-ricos #cqrs