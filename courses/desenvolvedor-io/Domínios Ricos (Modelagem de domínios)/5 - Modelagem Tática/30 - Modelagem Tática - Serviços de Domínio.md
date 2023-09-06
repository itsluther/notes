**Serviços de domínio**

- Implementam lógica de negócios que não pertencem a um agregado em particular e trabalham com múltiplas entidades.
- Coordenam a atividade dos agregados e repositórios com o propósito de implementar a ação de negócio.
- Podem consumir serviços da infraestrutura, como enviar um e-mail eventos ou mensagens.

As ações realizadas pelos serviços de domínio estão previstas nos _requisitos_ e são permitidas e aprovadas pelos _domain experts_. Os nomes utilizados nos serviços de domínio fazem parte da _linguagem ubíqua_.

**Exemplo de Serviço de Domínio**

_Determinar se um cliente atingiu o status "platinum":_ O cliente precisa ter atingido mais de R$ 5000,00 em compras.

1. É necessário consultar _pedidos_ e _produtos_ para determinar a soma.
2. Não é _responsabilidade_ da agregação acessar dados diretamente.
3. Os valores são definidos nas novas instâncias das entidades.
4. É uma _regra_ de negócios que abrange agregados diferentes (cross-aggregate).
5. Restrito ao _processo de negócio_.

_Alugando uma sala de reunião:_ Alugar uma sala requer _validação_ da disponibilidade da sala e _processamento_ do pagamento.

- Reserva: Domain Service
	1. Valida a disponibilidade da sala
	2. Realiza a transação com o mecanismo
- Reserva: Agregação
	1. Sala e objetos filhos
	2. O repositório da agregação realiza a ação.

---
[[31 - Modelagem Tática - Repositories]] - #ddd #domínios-ricos #modelagem-tatica 