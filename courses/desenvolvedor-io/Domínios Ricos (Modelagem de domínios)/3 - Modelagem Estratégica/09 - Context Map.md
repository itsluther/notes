No Domain-Driven Design, a modelagem estratégica é uma abordagem que visa criar uma representação clara e eficaz das relações e interações entre diferentes domínios dentro de um sistema complexo. A modelagem estratégica ajuda a equipe a compreender melhor a arquitetura, os limites dos diferentes domínios e como eles se relacionam entre si. Ela é especialmente útil quando se lida com sistemas grandes e complexos, nos quais a divisão clara entre diferentes áreas de funcionalidade é fundamental para o sucesso do projeto.

Um dos conceitos-chave na modelagem estratégica de DDD é o "Context Map" (Mapa de Contexto). O Context Map é uma ferramenta visual que ilustra as interações e limites entre diferentes contextos delimitados, também conhecidos como "bounded contexts". Cada bounded context representa uma parte do sistema com um significado específico e uma semântica bem definida. Essa delimitação ajuda a evitar a ambiguidade e a confusão entre as diferentes partes do sistema.

O Context Map é geralmente criado por meio de diagramas, nos quais são representados os bounded contexts e os tipos de relações que existem entre eles. Essas relações podem ser de diferentes tipos, como:

1. **Conformista (Conformist)**: Nesse tipo de relação, um bounded context se adapta às regras definidas por outro contexto. Pode envolver o compartilhamento de uma mesma base de dados ou a dependência direta de uma API.
2. **Compartilhado (Shared Kernel)**: Nesse caso, dois bounded contexts compartilham um núcleo comum, geralmente contendo componentes ou conceitos que são relevantes para ambos. Isso ajuda a evitar duplicações e inconsistências entre os contextos.
3. **Cliente-Fornecedor (Customer-Supplier)**: Nessa relação, um bounded context é considerado o "cliente" e depende de outro como seu "fornecedor". O fornecedor disponibiliza serviços ou informações que o cliente utiliza.
4. **Anticorrupção (Anticorruption Layer)**: Essa relação envolve a criação de uma camada intermediária que traduz as interações entre dois bounded contexts, protegendo um contexto de mudanças indesejadas provenientes de outro.
5. **Conformidade (Conformist)**: Nesse caso, um contexto se compromete a cumprir as regras definidas por outro contexto, garantindo que as interações entre eles ocorram de maneira harmoniosa.
6. **Open Host Service (OHS)**: Essa relação permite que um contexto forneça serviços abertos para serem utilizados por outros contextos, mas sem comprometer sua integridade interna.
    

O Context Map é uma ferramenta poderosa para a visualização e comunicação das complexas relações entre os bounded contexts dentro de um sistema. Ele ajuda as equipes a entenderem a arquitetura de alto nível, a colaborar de forma mais eficaz e a manter uma divisão clara das responsabilidades entre diferentes partes do sistema.

Lembrando que a modelagem estratégica e o uso de Context Maps são práticas que podem evoluir ao longo do tempo à medida que o entendimento do domínio aumenta e as necessidades do sistema se desenvolvem.

---
Próxima anotação: [[10 - Bounded Context]]
#domínios-ricos #ddd #modelagem-estrategica 