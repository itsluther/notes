**Direção do relacionamento**
1. **Contextos Upstream** influenciam **Contextos Downstream**
2. Essas influências afetam: binário (código fonte), mudanças, cronograma.
3. Mudanças no **Downstream** não podem influenciar no **Upstream**.

**Relacionamentos**
- Cliente-Fornecedor
	- Contextos Customer dependem de Contextos Supplier.
	- Oportunidades de levantar preocupações e abordar alguma solução.
- Parceiros
	- Dependência mútua entre dois contextos.
- Conformista (com camada anti-corrupção):
	- Contextos downstream dependem de contextos upstream.
	- Nenhuma negociação é permitida.
- Shared Kernel:
	- Um modelo compartilhado não pode ser alterado sem consultar os times que dependem dele.
- Anti-Corruption Layer:
	- Camada adicional dando ao contexto Downstream uma interface fixa independente do que acontece com contexto upstream.

**Núcleo compartilhado**: Classes base e interfaces.
- Forte acoplamento com todos os contextos.

---
