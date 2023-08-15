**Direção do Relacionamento:**

1. **Contextos Upstream Influenciam Contextos Downstream:**
    - Contextos "upstream" são aqueles que fornecem funcionalidades ou serviços utilizados por outros contextos.
    - Contextos "downstream" são aqueles que consomem os serviços ou funcionalidades fornecidos pelos contextos upstream.
    - As mudanças nos contextos upstream podem afetar os contextos downstream.
2. **Influências que Afetam Binário, Mudanças e Cronograma:**
    - Mudanças nos contextos upstream podem impactar o código-fonte, as mudanças planejadas e os cronogramas dos contextos downstream.
3. **Mudanças no Downstream não Afetam o Upstream:**
    - Contextos downstream não devem introduzir mudanças que afetem os contextos upstream, garantindo a independência dos contextos upstream.

**Tipos de Relacionamentos:**

- **Cliente-Fornecedor:**
    - Contextos "Customer" dependem de funcionalidades ou serviços fornecidos por contextos "Supplier".
    - Isso cria oportunidades para identificar preocupações e colaborativamente abordar soluções para atender às necessidades do cliente.
- **Parceiros:**
    - Dois contextos têm dependências mútuas, o que significa que eles colaboram e dependem um do outro.
- **Conformista (com Camada Anti-Corrupção):**
    - Contextos downstream dependem de contextos upstream, mas não há negociação direta entre eles.
    - Uma camada anti-corrupção atua como intermediária para traduzir as informações do contexto upstream para um formato adequado ao contexto downstream.
- **Shared Kernel:**
    - Dois ou mais contextos compartilham um modelo de dados comum.
    - Mudanças no modelo compartilhado requerem consulta e cooperação entre os times dependentes.
- **Anti-Corruption Layer:**
    - Uma camada adicional entre contextos upstream e downstream, que fornece uma interface fixa e independente.
    - Protege o contexto downstream de influências indesejadas do contexto upstream.

**Núcleo Compartilhado:**
- Classes base e interfaces são compartilhadas entre múltiplos contextos.
- Isso cria um forte acoplamento entre os contextos que compartilham esse núcleo.

Ao entender esses diferentes tipos de relacionamentos e suas implicações, as equipes de desenvolvimento podem projetar e implementar sistemas de software de forma mais coesa, evitando dependências excessivas, conflitos e problemas de integração. O DDD fornece uma estrutura conceitual valiosa para guiar a colaboração entre diferentes contextos e garantir a integridade do modelo em um domínio complexo.

---
Próxima anotação: [[15 - A evolução dos estilos arquiteturais]]
#domínios-ricos #ddd #modelagem-estrategica 