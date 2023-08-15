Um estilo arquitetural é uma *abordagem* de como *projetar* e entregar uma aplicação.

Trata-se de como *organizar* os *componentes* responsáveis de uma arquitetura, como eles irão *interagir* entre si e quais *aspectos tecnológicos* irão atender.

#### Arquitetura Monolítica
Uma arquitetura monolítica é uma abordagem de design em que toda a aplicação é desenvolvida como um único e grande bloco. Todos os componentes são interligados e funcionam como uma unidade coesa. Geralmente, essa arquitetura é mais simples de ser desenvolvida e testada, pois não envolve complexidades de comunicação entre diferentes serviços. No entanto, à medida que a aplicação cresce, a manutenção e a escalabilidade podem se tornar desafiadoras.

#### Arquitetura em Camadas
A arquitetura em camadas é uma abordagem que organiza os componentes da aplicação em camadas distintas, onde cada camada possui uma responsabilidade específica. As camadas são construídas de forma hierárquica, onde uma camada superior se comunica com a camada imediatamente abaixo dela. Isso ajuda a separar preocupações e facilita a manutenção e escalabilidade da aplicação. Geralmente, as camadas incluem a apresentação (interface do usuário), lógica de negócios e acesso a dados.

#### Arquitetura REST
A arquitetura REST (Representational State Transfer) é um estilo arquitetural baseado em padrões da web. Ela utiliza o protocolo HTTP para comunicação e é amplamente usada para projetar serviços web que podem ser acessados por diferentes clientes. Os recursos são expostos como URLs, e as operações são executadas por meio dos métodos HTTP, como GET, POST, PUT e DELETE. A arquitetura REST enfatiza a escalabilidade, a simplicidade e a independência de plataforma.

#### Arquitetura de Microservices
A arquitetura de Microservices é uma abordagem em que a aplicação é dividida em pequenos serviços independentes e autônomos, cada um responsável por uma funcionalidade específica. Cada serviço opera como uma entidade separada, podendo ser desenvolvido, implantado e dimensionado independentemente dos outros. Isso permite maior flexibilidade, escalabilidade e facilita a implementação contínua (continuous deployment). No entanto, também introduz desafios em termos de gerenciamento de comunicação e consistência entre os serviços.

#### SOA vs Microservices
Service-Oriented Architecture (SOA) e Microservices são duas abordagens diferentes para o design de sistemas distribuídos. SOA é um estilo arquitetural que enfatiza a criação de serviços reutilizáveis e altamente modulares que podem ser compartilhados por diferentes aplicações. Por outro lado, Microservices se concentra na construção de serviços independentes e autônomos que operam como unidades individuais. Embora ambos busquem promover a reutilização e a flexibilidade, o foco e a granularidade diferem entre as duas abordagens.

#### Outros estilos:

- **Plugin Architecture**
    - A arquitetura de Plugin é uma abordagem que permite estender a funcionalidade de um sistema por meio de módulos de plug-in. Esses módulos podem ser adicionados ou removidos para adicionar ou modificar recursos do sistema sem alterar o núcleo da aplicação. Isso facilita a personalização e a expansibilidade do software de forma modular.
- **Client-Server Architecture**    
    - A arquitetura Cliente-Servidor é um estilo em que a aplicação é dividida em duas partes principais: o cliente, que é responsável pela interação com o usuário e a apresentação de dados, e o servidor, que gerencia as operações de negócios e o armazenamento de dados. Essa arquitetura permite uma distribuição clara de responsabilidades e facilita a escalabilidade, pois várias instâncias de clientes podem se conectar a um servidor central.
- **Pipes and Filters Architecture**
    - A arquitetura Pipes and Filters é uma abordagem que organiza o processamento de dados em uma sequência de etapas, onde cada etapa representa um filtro que manipula os dados de entrada e os encaminha para a próxima etapa por meio de pipes (canais). Essa arquitetura é comumente usada em sistemas de processamento em lotes, onde cada filtro realiza uma tarefa específica e independente, resultando em um processamento modular e flexível dos dados.

---
Próxima anotação: [[46 - Padrões Arquiteturais]]
#arquitetura-de-software #estilos-arquiteturais