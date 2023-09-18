A arquitetura CQRS, ou Command Query Responsibility Segregation, é um padrão arquitetural que separa as operações de leitura (queries) das operações de escrita (comandos) em um sistema. Essa separação é implementada por meio de dois componentes principais: o Command Stack (Pilha de Comandos) e o Query Stack (Pilha de Consultas).

**Command Stack (Pilha de Comandos):**

1. O Command Stack lida com as operações de escrita e atualização de dados no sistema.
2. Ele consiste em controladores, serviços, validações e manipuladores de comandos que recebem solicitações de alteração de estado do sistema.
3. Os comandos representam as intenções do usuário ou de outras partes do sistema de realizar uma ação, como criar um novo registro, atualizar um existente ou excluir um registro.
4. Os comandos são processados de forma assíncrona e podem envolver validações complexas e lógica de negócios antes de serem executados.
5. Após a execução bem-sucedida de um comando, eventos são gerados para indicar que uma mudança de estado ocorreu. Esses eventos são armazenados em um log de eventos (Event Store) e podem ser usados para criar uma representação consistente do estado atual do sistema.
    

**Query Stack (Pilha de Consultas):**

1. O Query Stack lida com as operações de leitura de dados no sistema.
2. Ele consiste em componentes como consultas, manipuladores de consultas e modelos de leitura que são projetados para atender a consultas de forma eficiente.
3. As consultas representam as solicitações de leitura de informações do sistema, como recuperar dados de um usuário, listar produtos disponíveis ou buscar informações de relatórios.
4. O Query Stack consulta a fonte de leitura, que geralmente é um banco de dados otimizado para leituras rápidas e não contém a mesma complexidade de validação e lógica de negócios encontrada no Command Stack.
5. Os dados lidos são retornados ao usuário ou ao componente que fez a solicitação de consulta.

**Vantagens da Arquitetura CQRS:**

- **Escalabilidade:** A separação de leituras e gravações permite dimensionar independentemente cada parte do sistema. O Query Stack pode ser dimensionado para atender a cargas pesadas de leitura, enquanto o Command Stack pode ser dimensionado para suportar operações de escrita intensivas.
- **Modelagem de Dados Flexível:** O Command Stack permite a implementação de modelos de dados complexos e validações, enquanto o Query Stack pode ser otimizado para consultas específicas.
- **Melhor Desempenho:** A separação de responsabilidades facilita a otimização de cada pilha para seu propósito específico, resultando em consultas mais rápidas e operações de gravação mais eficientes.
    

Em resumo, o uso de Command Stack e Query Stack na arquitetura CQRS é uma abordagem eficaz para melhorar o desempenho, escalabilidade e flexibilidade de sistemas distribuídos e complexos, permitindo que operações de leitura e gravação sejam tratadas de forma independente e otimizada.

---

![[Pasted image 20230914082029.png]]

---
