**Definindo um Estilo Arquitetural:**

Antes de escolher um estilo arquitetural, é essencial entender as nuances do negócio e os requisitos do sistema. Aqui estão alguns passos para orientar essa definição:

**1. Entendimento do Negócio:** Primeiramente, é importante avaliar a necessidade de uma experiência do usuário (UX) na aplicação. Se a aplicação interage diretamente com os usuários, é crucial ter uma abordagem que atenda às suas expectativas e necessidades. Para isso, a definição de casos de uso (Use-Cases) é uma etapa fundamental. Eles identificam como os usuários interagem com a aplicação e ajudam a orientar o design e a lógica do sistema.

**2. Definindo o "Business" com Base nos Use-Cases:** Uma vez que os casos de uso são definidos, é necessário mapear a lógica de negócios com base neles. Isso envolve determinar como as ações dos usuários se traduzem em operações do sistema. Dependendo da complexidade do negócio, você pode escolher entre várias abordagens arquiteturais:

- **Transaction Script:** Adequado para cenários mais simples, onde a lógica de negócios é representada como um conjunto de scripts que manipulam transações.
- **Table Module:** Útil quando a lógica de negócios é focada em tabelas de banco de dados específicas, agrupando operações relacionadas em módulos.
- **Domain Model:** Indicado para domínios mais complexos, o modelo de domínio captura as regras de negócios e as entidades do sistema de forma mais abstrata e coesa.
- **CQRS (Command Query Responsibility Segregation):** Em sistemas complexos, essa abordagem separa as operações de leitura e escrita em modelos diferentes, otimizando o desempenho e a escalabilidade.
- **Event Sourcing:** Útil quando é crucial rastrear o histórico das alterações nos dados. O evento de cada alteração é registrado, permitindo reconstruir o estado atual.

**3. Escolhendo o Modelo de Persistência:** Uma vez definida a lógica de negócios, é importante escolher um modelo de persistência adequado para armazenar os dados do sistema. Aqui, pode-se considerar uma abordagem de persistência híbrida, combinando diferentes tecnologias de armazenamento:

- **Relacional (Banco de Gravação):** Bancos de dados relacionais são adequados para armazenar dados consistentes e altamente estruturados, especialmente para operações de gravação.
- **NoSQL (Banco de Leitura):** Bancos de dados NoSQL são ideais para cenários em que a escalabilidade e a recuperação rápida de dados são prioridades, sendo frequentemente utilizados para operações de leitura.
- **Memória/Cache:** A utilização de cache em memória é recomendada para acelerar o acesso a dados frequentemente usados, melhorando o desempenho geral do sistema.

Lembrando que a escolha do estilo arquitetural e do modelo de persistência deve ser guiada pelas características específicas do projeto, incluindo requisitos de desempenho, escalabilidade e complexidade do domínio.

![[Pasted image 20230828134155.png]]

---
[[17 - Transaction Script Pattern]] - #domínios-ricos #ddd #padrões-arquiteturais 