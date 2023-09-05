![[Pasted image 20230904080125.png]]

**E o que seria um Domain Module?**

Um Domain Module é uma coleção organizada de Aggregates, Entities e Value Objects que encapsulam um subconjunto específico do domínio de um sistema. Esse módulo é projetado para representar e gerenciar um aspecto particular do negócio, garantindo que as regras e conceitos relacionados a esse domínio específico sejam adequadamente encapsulados e isolados do restante do sistema. Isso promove a modularização, reutilização e manutenção eficiente do código, facilitando a compreensão e a evolução do sistema de software. Cada Domain Module deve ser coeso, focado em um contexto de negócios específico e seguir os princípios de DDD (Domain-Driven Design) para criar um modelo de domínio rico e representativo desse contexto.

**Camada de Domínio**

- Domain Models
    - Aggregates
        - Raízes de agregação que encapsulam entidades e objetos de valor relacionados.
    - Entities
        - Objetos de domínio com identidades distintas e mutáveis.
    - Value Types
        - Objetos imutáveis que representam valores importantes para o domínio.
    - Factories
        - Responsáveis por criar instâncias complexas de objetos de domínio.
- Domain Services
    - Componentes que realizam operações específicas no domínio, muitas vezes envolvendo múltiplos agregados.
    - Responsáveis por comportamentos que não se encaixam naturalmente em entidades ou objetos de valor.
    - Repositories
        - Abstrações que permitem recuperar e persistir objetos de domínio.
    - External services
        - Integrações com serviços externos necessários para o funcionamento do domínio.

**Clareando os equívocos**

- Modelos de domínio
    - Mapear o contexto é fundamental para identificar os conceitos e limites do domínio.
    - Modelar os objetos de domínio conforme identificados na UL (Linguagem Ubíqua), garantindo que o código reflita a linguagem do negócio.
- Database Agnostic
    - O modelo deve ser agnóstico ao banco de dados, ou seja, não deve depender de detalhes de implementação de um sistema de armazenamento específico.
    - O modelo deve ser fácil de persistir, mas a preocupação principal deve ser manter a semântica do domínio e não apenas a persistência.
    - Persistir não deve ser a única preocupação; a manutenção do alinhamento com os processos de negócio do domínio é crucial.
- Ubiquitous Language
    - Entender a linguagem é essencial para compreender o negócio e traduzi-lo para o código de forma precisa.
    - Manter a linguagem do negócio alinhada com o código ajuda a evitar ambiguidades e garantir que todos os envolvidos compartilhem uma compreensão comum.

---
[[27 - Modelagem Tática - Value Objects]] - #ddd #domínios-ricos  #modelagem-tatica