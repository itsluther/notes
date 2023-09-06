**Eventos de Domínio:**

- Você já considerou a utilização de _eventos_ em sua camada de domínio?
- Embora não sejam obrigatórios, os eventos podem ser poderosos para expressar comportamentos do mundo real de forma eficaz.

**Exemplo de Utilização:**

**Venda**:

1. Pedido iniciado.
2. Processo de checkout.
3. Pagamento aprovado.
4. Envio de e-mail / SMS.
    - Nesse caso, é apropriado disparar um evento para concluir determinada tarefa baseada em ações que vão além da responsabilidade do domínio. A responsabilidade pelo envio pertence à camada de Infraestrutura.

**Exemplo de Código Monolítico:**

```typescript
// Add any tasks to the method that processed the order
function Checkout(cart: ShoppingCart): void {
	// Proceed through the necessary steps
	...
	if (success) {
		// Execute task
	}
}
```

- Disparar um evento de domínio para ações relevantes.
- Não é necessário ter todo o código em um único lugar.
- Disparar o evento sem precisar conhecer em detalhes o que ele faz.
- A capacidade de manipular o mesmo evento em diversos lugares facilita a manutenção e a escalabilidade.

**Exemplo de Disparo de Evento:**

```typescript
function Checkout(cart: ShoppingCart): void {
	// Proceed through the necessary steps
	...
	if (success) {
		// Execute Task(s)
		Bus.RaiseEvent(new GoldMemberStatusReached(customer));
	}
}
```

---
[[33 - Modelagem Tática na prática]] - #ddd #domínios-ricos #modelagem-tatica 