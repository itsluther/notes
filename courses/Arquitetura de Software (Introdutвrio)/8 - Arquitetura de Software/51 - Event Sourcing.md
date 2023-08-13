"Nós podemos buscar o estado de uma aplicação para encontrar o estado atual do mundo, e isso responde muitas perguntas. Entretanto há momentos que nós não só queremos ver onde nós estamos, mas também queremos saber como chegamos lá." - Martin Fowler

"Event Sourcing assegura que todas as mudanças feitas no estado de uma aplicação são armazenadas como uma sequência de eventos. Não só podemos buscar esses eventos, mas também podemos usar este log de eventos para reconstruir estados passados e ajustar automaticamente o estado atual com mudanças retroativas." - Martin Fowler

O Event Sourcing é um padrão de arquitetura de software que se tornou popular nos últimos anos, especialmente em sistemas distribuídos e aplicativos baseados em eventos. Ele oferece uma abordagem diferente para o armazenamento e gerenciamento do estado da aplicação em comparação com o modelo tradicional de banco de dados.

Aqui estão algumas anotações sobre o Event Sourcing:

1. Conceito básico:
    - O Event Sourcing é uma técnica que consiste em armazenar o estado de um aplicativo como uma sequência imutável de eventos que representam mudanças no estado ao longo do tempo.
    - Em vez de armazenar apenas o estado atual da aplicação, cada ação ou comando que modifica o estado resulta na geração de um evento.
    - Os eventos são armazenados em uma ordem cronológica, permitindo que o estado atual seja reconstruído através da reprodução sequencial dos eventos.
2. Eventos:
    - Um evento é uma representação imutável e autocontida de uma mudança de estado em um sistema.
    - Cada evento deve conter informações suficientes para descrever a mudança ocorrida e ser capaz de reconstruir o estado em que o sistema se encontrava após a ocorrência do evento.
3. Armazenamento de Eventos:
    - Os eventos são armazenados em um log de eventos (event log) persistente, geralmente em uma ordem estritamente sequencial, permitindo que novos eventos sejam adicionados no final do log.
    - O log de eventos pode ser implementado em um banco de dados especializado para tal finalidade ou em sistemas de mensageria.
4. Reconstrução do Estado:
    - Para determinar o estado atual do aplicativo em um determinado momento, todos os eventos desde o início do tempo até o momento desejado são aplicados sequencialmente.
    - Esse processo de aplicar eventos para reconstruir o estado é conhecido como "replay" e é uma operação relativamente rápida e eficiente.
5. Modelagem de Domínio:
    - O Event Sourcing facilita a modelagem do domínio da aplicação, permitindo que os desenvolvedores se concentrem nos eventos relevantes e na lógica de negócios, ao invés de se preocuparem com a camada de persistência.
6. Cenários de uso:
    - Event Sourcing é especialmente útil em sistemas colaborativos ou que precisam manter um histórico detalhado de todas as alterações.
    - Também é adequado para sistemas complexos onde a auditoria é essencial ou para aplicações com requisitos de compliance.
7. Considerações:
    - Event Sourcing implica um modelo de consistência eventual (eventual consistency), o que significa que, em sistemas distribuídos, pode haver atrasos na propagação dos eventos e, consequentemente, na atualização do estado.
8. Event Store e CQRS:
    - Em sistemas que adotam Event Sourcing, muitas vezes é utilizado o padrão CQRS (Command Query Responsibility Segregation), onde a escrita e a leitura de dados são tratadas de forma separada para melhorar o desempenho e a escalabilidade.
    - O "Event Store" é o componente responsável por armazenar e recuperar os eventos no padrão CQRS.

O Event Sourcing oferece uma abordagem interessante para a construção de sistemas que requerem rastreamento detalhado de mudanças e históricos confiáveis. No entanto, é importante notar que sua implementação também traz complexidades adicionais e pode não ser adequada para todos os tipos de aplicativos. Portanto, a decisão de adotar o Event Sourcing deve ser avaliada de acordo com as necessidades específicas do projeto em questão.

---

![[Pasted image 20230725205436.png]]

---
Próxima anotação: [[52 - Domain-Driven Design]]
#arquitetura-de-software #padrões-arquiteturais