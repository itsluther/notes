**O que é REST (Representational State Transfer)?**
REST, ou Transferência de Estado Representacional, é um conceito introduzido e definido em uma tese de doutorado escrita por Roy Fielding em 2000. Fielding é um dos principais autores da especificação do protocolo HTTP. O objetivo central dessa tese foi formalizar um conjunto de melhores práticas chamadas de "constraints" (restrições).

**Constraints (Restrições) do REST:**
1. **Cliente-Servidor:**
    - Essa constraint envolve a separação de responsabilidades entre diferentes partes de um sistema.
    - Essa separação pode ser entre a interface do usuário e o back-end da aplicação.
    - Isso permite a evolução e a escalabilidade independentes das responsabilidades.
2. **Stateless (Sem Estado):**
    - Cada requisição feita ao servidor não deve depender de requisições anteriores ou futuras.
    - Todas as informações necessárias para tratar a requisição devem estar presentes nela mesma.
3. **Cache:**
    - Para melhorar a performance, o sistema REST deve permitir que suas respostas possam ser armazenadas em cache.
    - O cache é uma técnica que permite armazenar temporariamente dados frequentemente acessados para reduzir a latência e o tráfego de rede.
    - Saiba mais sobre cache em: [O que é cache?](https://br.godaddy.com/blog/o-que-e-cache/)
4. **Interface Uniforme:**
    - É necessário esforço para criar uma interface que siga padrões importantes.
    - Elementos-chave da interface são:
        - **Recursos:** Elementos de informação identificados por URIs.
        - **Mensagens autodescritivas:** Cada mensagem deve conter informações suficientes para entender como processá-la.
        - **Hypermedia:** A interface deve fornecer links para outras ações possíveis, permitindo a navegação eficiente.
5. **Sistemas de Camadas:**
    - Sistemas REST devem permitir a adição de intermediários transparentes para os clientes.
    - Isso permite escalabilidade em sistemas distribuídos, com intermediários como balanceadores de carga.
6. **Código Sob Demanda (Opcional):**
    - Essa constraint opcional visa aumentar a flexibilidade dos clientes, permitindo o download de código, como JavaScript, conforme necessário.
    - No entanto, essa prática pode reduzir a visibilidade e é considerada opcional.

O conceito REST e suas constraints definem um conjunto de diretrizes que visam criar sistemas de comunicação eficientes e escaláveis na web. Ao seguir essas restrições, os desenvolvedores podem criar APIs que são fáceis de entender, manter e integrar, resultando em sistemas mais confiáveis e interoperáveis.

---
Próxima anotação: [[4 - REST vs RESTful representações]]
#rest #restful #api