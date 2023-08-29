**Modelos do Domínio:**

- Na "Camada de Domínio", os modelos representam o núcleo da lógica de negócios e os conceitos essenciais do problema que o software resolve.
- Os modelos do domínio podem ser expressos de diferentes maneiras:
    - **Entidade baseada em OOP:** São objetos que encapsulam tanto o estado quanto o comportamento relacionado a um conceito no domínio. Eles geralmente seguem princípios de Programação Orientada a Objetos (OOP).
    - **Modelo Funcional:** Uma abordagem que enfatiza funções puras, imutabilidade e a manipulação de estados de forma declarativa.

**Guia para Classes de Entidades:**

- As classes de entidades são componentes fundamentais da "Camada de Domínio".
- São construídas de acordo com as convenções do DDD, envolvendo:
    - **Factories:** Métodos ou classes responsáveis por criar instâncias de entidades de maneira consistente.
    - **Value Types:** Objetos imutáveis que representam valores no domínio.
    - **Private Setters:** Atributos internos geralmente devem ser modificados apenas por métodos internos da própria classe.
- Essas classes unem dados e comportamento, incorporando as regras e operações essenciais do domínio.

**Modelo Anêmico:**

- O modelo anêmico é uma abordagem onde as classes de entidades contêm principalmente propriedades que representam os dados do modelo.
- Os comportamentos e regras são implementados em serviços de domínio, que operam sobre essas classes.
- Essa abordagem pode ser útil em cenários mais simples ou quando a complexidade da lógica de negócios não justifica a criação de métodos diretamente nas entidades.

**Serviços de Domínio:**

- Serviços de domínio são utilizados quando partes do domínio não se encaixam bem em entidades existentes.
- Eles agrupam comportamentos diversos e frequentemente trabalham com diversas entidades em conjunto.
- Esses serviços são responsáveis pela implementação de processos que:
    - Exigem acesso à persistência para ler e gravar dados.
    - Precisam interagir com serviços externos, como sistemas de pagamento ou APIs.

A "Camada de Domínio" é onde a complexidade do negócio é capturada e onde as regras de negócios são expressas de maneira mais direta. Ela desempenha um papel crucial na manutenção da integridade e coerência das operações essenciais da aplicação.

---
[[25 - Domain Model - Camada de infraestrutura]] - #domínios-ricos  #ddd #padrões-arquiteturais 