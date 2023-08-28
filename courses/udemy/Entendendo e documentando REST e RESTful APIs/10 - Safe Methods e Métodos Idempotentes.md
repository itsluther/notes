Ao projetar e trabalhar com APIs RESTful, é importante compreender os conceitos de métodos seguros (Safe Methods) e métodos idempotentes, pois eles influenciam o comportamento e a semântica das operações que podem ser realizadas nos recursos.

**Safe Methods (Métodos Seguros):**
- São métodos considerados "seguros" porque não causam alterações nos recursos.
- Qualquer implementação específica pode ter efeitos secundários (como atualizar contadores), mas o cliente não deve depender disso.
- Métodos Safe:
    - GET: Obtém informações do servidor.
    - HEAD: Obtém informações do servidor sem o corpo da resposta.

**Métodos Idempotentes:**
- A idempotência é uma propriedade matemática e de ciência da computação que descreve operações em que aplicar a operação múltiplas vezes resulta no mesmo estado do que se aplicada apenas uma vez.
- Ao aplicar um método idempotente várias vezes, o resultado será o mesmo que aplicá-lo apenas uma vez.
- Métodos Idempotentes:
    - GET: Obtém informações do servidor.
    - HEAD: Obtém informações do servidor sem o corpo da resposta.
    - PUT: Atualiza ou cria um recurso.
    - DELETE: Remove um recurso.
    - OPTIONS: Obtém informações sobre os métodos suportados em um recurso.
    - TRACE: Permite ao cliente ver a transformação da requisição através de servidores intermediários.

Compreender a distinção entre métodos seguros, métodos idempotentes e outros métodos HTTP é crucial para a construção de APIs RESTful que se comportam de maneira previsível e que seguem as diretrizes e as boas práticas do protocolo HTTP. Isso ajuda a garantir a consistência e a confiabilidade das operações realizadas na aplicação.

---
[[11 - Modelo de maturidade Richardson - Parte 1]] - #rest #restful #api #curl #http