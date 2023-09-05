**Entidades (Entities) na Modelagem Tática**

- **Possuem identidade:** Entidades têm uma identidade única que as diferencia de outras entidades no mesmo tipo. Essa identidade geralmente é representada por um identificador único, como um ID, que não muda durante toda a vida da entidade.
- **Deve ser exclusiva para o objeto mapeado:** A identidade da entidade deve ser única dentro do contexto do domínio em que ela está sendo utilizada. Isso significa que não deve haver duas entidades com a mesma identidade.
- **Possui estados e comportamentos:** Entidades têm estados que refletem suas características e propriedades no contexto do domínio. Além disso, elas podem ter comportamentos que permitem que elas executem ações específicas.
- **Possui lógica de negócios, mas não faz persistência:** Entidades encapsulam lógica de negócios relacionada a elas mesmas, mas não são responsáveis por realizar operações de persistência no banco de dados. Isso é geralmente realizado por Repositórios ou outras camadas de infraestrutura.

As Entidades desempenham um papel fundamental na representação de conceitos significativos do domínio e ajudam a manter a integridade dos dados e a expressão da lógica de negócios de maneira eficaz dentro de um sistema baseado em DDD (Domain-Driven Design).

```typescript
class Produto {
  private readonly id: string;
  private nome: string;
  private preco: number;

  constructor(id: string, nome: string, preco: number) {
    this.id = id;
    this.nome = nome;
    this.preco = preco;
  }

  // Define um método para calcular o preço total com base na quantidade
  calcularPrecoTotal(quantidade: number): number {
    if (quantidade <= 0) {
      throw new Error("A quantidade deve ser maior que zero.");
    }
    return this.preco * quantidade;
  }

  // Getter para obter o ID da entidade
  getId(): string {
    return this.id;
  }

  // Getter para obter o nome do produto
  getNome(): string {
    return this.nome;
  }

  // Getter para obter o preço do produto
  getPreco(): number {
    return this.preco;
  }

  // Setter para atualizar o nome do produto
  setNome(novoNome: string): void {
    this.nome = novoNome;
  }

  // Setter para atualizar o preço do produto
  setPreco(novoPreco: number): void {
    if (novoPreco < 0) {
      throw new Error("O preço não pode ser negativo.");
    }
    this.preco = novoPreco;
  }
}

// Exemplo de uso da entidade Produto
const produto1 = new Produto("1", "Camiseta", 29.99);

// Obtendo informações sobre o produto
console.log("ID:", produto1.getId());
console.log("Nome:", produto1.getNome());
console.log("Preço:", produto1.getPreco());

// Atualizando o nome e o preço do produto
produto1.setNome("Camiseta Nova");
produto1.setPreco(34.99);

console.log("Nome atualizado:", produto1.getNome());
console.log("Preço atualizado:", produto1.getPreco());

// Calculando o preço total com base na quantidade
const quantidade = 3;
const precoTotal = produto1.calcularPrecoTotal(quantidade);
console.log(`Preço total para ${quantidade} unidades: R$ ${precoTotal}`);
```

---
[[29 - Modelagem Tática - Agregações]] - #ddd #domínios-ricos  #modelagem-tatica 