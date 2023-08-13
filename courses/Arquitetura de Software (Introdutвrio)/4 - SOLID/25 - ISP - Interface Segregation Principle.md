O Princípio da Segregação de Interfaces (ISP, do inglês Interface Segregation Principle) é um dos cinco princípios do SOLID, um conjunto de diretrizes para desenvolvimento de software orientado a objetos.
O ISP afirma que uma classe não deve ser forçada a implementar interfaces que não utiliza. Em outras palavras, é melhor ter interfaces menores e mais específicas, ao invés de interfaces maiores e genéricas.
Isso promove uma maior coesão entre as classes, o que significa que cada classe tem uma responsabilidade bem definida e limitada. Isso também ajuda a reduzir o acoplamento entre as classes, o que significa que as mudanças em uma classe não afetam outras classes que não dependem dela.
Ao seguir o ISP, os desenvolvedores podem criar sistemas mais flexíveis e fáceis de manter, pois as mudanças em uma parte do sistema terão um impacto mínimo em outras partes do sistema. Isso também pode ajudar a melhorar o desempenho e a escalabilidade do sistema, pois as interfaces menores e mais específicas são mais fáceis de implementar e testar.

---
Suponha que estamos construindo um sistema de gerenciamento de loja online em que temos duas classes principais, `CarrinhoDeCompras` e `Pagamento`. A classe `CarrinhoDeCompras` lida com a adição e remoção de itens no carrinho, enquanto a classe `Pagamento` lida com o processamento de pagamentos.

Para seguir o ISP, podemos criar duas interfaces separadas, uma para lidar com as operações de carrinho de compras e outra para lidar com as operações de pagamento:

```typescript
interface CarrinhoDeCompras {
  adicionarItem(item: Item): void;
  removerItem(item: Item): void;
  calcularTotal(): number;
}

interface Pagamento {
  processarPagamento(): void;
  atualizarStatusDePagamento(): void;
}
```

Observe que as duas interfaces são pequenas e específicas, cada uma contendo apenas os métodos necessários para cada uma das responsabilidades.

Agora podemos criar as classes que implementam as interfaces. A classe `CarrinhoDeCompras` implementa apenas a interface `CarrinhoDeCompras`, enquanto a classe `Pagamento` implementa apenas a interface `Pagamento`.

```typescript
class MeuCarrinhoDeCompras implements CarrinhoDeCompras {
  private itens: Item[] = [];

  adicionarItem(item: Item) {
    this.itens.push(item);
  }

  removerItem(item: Item) {
    const index = this.itens.indexOf(item);
    if (index >= 0) {
      this.itens.splice(index, 1);
    }
  }

  calcularTotal() {
    let total = 0;
    for (const item of this.itens) {
      total += item.preco;
    }
    return total;
  }
}

class MeuPagamento implements Pagamento {
  processarPagamento() {
    console.log("Processando pagamento...");
  }

  atualizarStatusDePagamento() {
    console.log("Atualizando status de pagamento...");
  }
}
```

Dessa forma, cada classe implementa apenas os métodos que são relevantes para sua responsabilidade específica. Ao separar as interfaces e implementá-las em classes separadas, seguindo o Princípio da Segregação de Interfaces, temos um sistema mais modular, flexível e fácil de manter.

---
Próxima anotação [[26 - DIP - Dependency Inversion Principle ]]
#arquitetura-de-software #solid 