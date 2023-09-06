**CQRS - Command Query Responsibility Segregation**

- Um **padrão arquitetural** onde o foco principal é **separar** os meios de **leitura** e **escrita** de dados. **Alterações** de dados são realizados via **Commands** e **Leituras** de dados são realizados via **Queries**.
- O objetivo do CQRS é prover **expressividade** para aplicação, pois todos os Commands representam uma **intenção de negócio**.
- CQRS promove a **consistência eventual**, que é quando possuímos um banco de **leitura** e outro de **escrita** com os **mesmos dados**, porém os dados não são consistidos exatamente no **mesmo momento**
- Muito aplicado em arquiteturas hexagonais, microservices ou em aplicações que possuem uma **alta demanda** de consumo de dados.

**Commands**: representam uma intenção de mudança no estado de uma entidade. São expressivos e representam uma única intenção de negócio, ex: `AumentarSalarioFuncionarioCommand`.

**Queries**: é a forma de obter dados de um banco ou origem de dados para atender as necessidades da aplicação.

![[Pasted image 20230906071558.png]]

**Por que CQRS?**

1. **Separação de preocupações:** O CQRS ajuda a separar claramente as preocupações relacionadas à escrita e leitura de dados. Isso torna o código mais modular e fácil de manter, pois você pode se concentrar em cada aspecto separadamente.
2. **Desempenho otimizado:** Ao usar modelos de leitura otimizados para consultas, você pode melhorar o desempenho das operações de leitura, uma vez que esses modelos podem ser projetados especificamente para atender às necessidades de consulta sem a complexidade dos modelos de gravação.
3. **Evolução independente:** Com o CQRS, você pode evoluir os modelos de leitura e gravação de forma independente. Isso significa que você pode fazer alterações em um modelo sem afetar necessariamente o outro, o que facilita a manutenção e a escalabilidade.
4. **Suporte a múltiplas fontes de dados:** O CQRS pode ser útil quando você precisa consolidar dados de várias fontes diferentes em um único ponto de consulta. Cada fonte de dados pode ser tratada como um modelo de leitura separado.
5. **Segurança e controle granular:** O CQRS permite um controle mais granular sobre as operações de leitura e gravação, o que pode ser útil em sistemas que requerem restrições de acesso específicas para diferentes partes dos dados.

![[Pasted image 20230906073225.png]]

---
[[35 - CQRS - Teorema CAP]] - #ddd #domínios-ricos #cqrs