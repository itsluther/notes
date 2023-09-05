**O que são Agregações no contexto de Modelagem Tática em DDD?**

- Agregações são um conjunto de entidades que são usadas e referenciadas juntas, tratadas como uma única unidade quando o dado é alterado.
- Cada agregação possui uma raiz de agregação (Aggregate Root), que é a única entrada para a manipulação de entidades dentro da agregação.
- A raiz de agregação (Aggregate Root) é responsável por manter a integridade das classes filhas.

**Comportamento em uma Agregação:**

- O comportamento em uma agregação é definido por métodos que:
    - Validam o estado do objeto.
    - Invocam regras de negócio e alteram o estado do objeto.
    - Expressam processos de negócios que envolvem objetos na agregação.

**Fatores que afetam uma Agregação:**

- Limitação do acesso aos objetos filhos, garantindo que o acesso seja sempre feito por meio da raiz de agregação.
- Certificação de que o estado dos objetos filhos esteja sempre consistente.
- Os limites reais de uma agregação são determinados pelas regras de negócio específicas do domínio.

**Responsabilidades de uma Agregação:**

- Certificar sempre a consistência do estado dos objetos filhos.
- Cuidar da integridade de todos os objetos filhos, garantindo que eles sejam usados de maneira apropriada.
- Intermediar a adição, edição e exclusão dos objetos filhos, mantendo a coerência do estado da agregação.
- Garantir que o acesso aos objetos filhos seja sempre feito por meio de ações controladas pela raiz de agregação.
- Recomenda-se a utilização de um único repositório por agregação para gerenciar o acesso e a persistência dos objetos dentro da agregação.

Exemplo:

```typescript
class ItemPedido {
  constructor(public produto: string, public quantidade: number, public precoUnitario: number) {}
}

class Pedido {
  private itens: ItemPedido[] = [];

  constructor(public numeroPedido: string) {}

  adicionarItem(item: ItemPedido): void {
    this.itens.push(item);
  }

  removerItem(item: ItemPedido): void {
    const index = this.itens.indexOf(item);
    if (index !== -1) {
      this.itens.splice(index, 1);
    }
  }

  calcularTotal(): number {
    return this.itens.reduce((total, item) => total + item.quantidade * item.precoUnitario, 0);
  }

  listarItens(): ItemPedido[] {
    return this.itens;
  }
}

// Criando um pedido e adicionando itens
const pedido1 = new Pedido("P001");
const item1 = new ItemPedido("Produto A", 2, 10.0);
const item2 = new ItemPedido("Produto B", 1, 20.0);

pedido1.adicionarItem(item1);
pedido1.adicionarItem(item2);

console.log("Itens do Pedido P001:", pedido1.listarItens());
console.log("Total do Pedido P001:", pedido1.calcularTotal());

// Removendo um item do pedido
pedido1.removerItem(item1);

console.log("Itens do Pedido P001 após a remoção do Produto A:", pedido1.listarItens());
console.log("Total do Pedido P001 após a remoção do Produto A:", pedido1.calcularTotal());
```

---
[[30 - Modelagem Tática - Serviços de Domínio]] - #ddd #domínios-ricos #modelagem-tatica 