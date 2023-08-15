1. **Significados Diferentes para Termos:** No DDD, é comum que os termos utilizados no desenvolvimento de software tenham significados específicos para cada contexto delimitado. Isso evita ambiguidades e garante que as equipes de desenvolvimento e os especialistas do domínio estejam alinhados quanto ao entendimento dos termos usados. É importante definir explicitamente o significado dos termos em cada contexto.
2. **Representações Diferentes:** Um mesmo termo pode representar conceitos diferentes em contextos distintos. Por exemplo, o termo "cliente" pode ter diferentes significados no contexto de uma loja virtual e no contexto do departamento de atendimento ao cliente. O DDD enfatiza a criação de modelos específicos para cada contexto, permitindo que essas diferentes representações sejam expressas de maneira clara.
3. **Dependências com Sistemas Externos:** É comum que uma aplicação dependa de sistemas externos, como serviços de terceiros ou integrações com outras empresas. No DDD, é importante identificar essas dependências e definir interfaces claras entre os contextos para minimizar o acoplamento. Isso preserva a integridade do modelo dentro de cada contexto, mesmo quando há interações com sistemas externos.
4. **Dependências com Código Legado:** Muitos sistemas têm código legado que pode ser difícil de refatorar. O DDD reconhece essa realidade e sugere a criação de "Camadas de Integração" para lidar com a comunicação entre o código legado e os novos contextos mais bem definidos. Isso permite que o modelo seja introduzido gradualmente sem perturbar a funcionalidade existente.
5. **Separação de Áreas Funcionais:** O DDD incentiva a modelagem de domínios complexos dividindo-os em contextos delimitados menores. Cada contexto representa uma área funcional específica da aplicação. Isso ajuda a gerenciar a complexidade, facilita a manutenção e permite que as equipes se concentrem em partes específicas do domínio, mantendo a coesão e a integridade do modelo.

**Visão dos Contextos Delimitados:**

A Visão dos Contextos Delimitados é um conceito central no DDD. Ela se concentra em dividir o domínio complexo de um software em contextos delimitados menores e mais gerenciáveis. Isso é feito para:

1. **Compreender o Domínio:** Ao dividir o domínio em contextos mais específicos, é mais fácil compreender e modelar cada parte individualmente. Isso permite que as equipes se tornem especialistas em seus contextos específicos.
2. **Evitar Conflitos:** Quando diferentes equipes trabalham em diferentes contextos, as chances de conflitos e ambiguidades são reduzidas. Cada equipe é responsável por seu próprio contexto e pode tomar decisões de design que se adequem melhor às necessidades daquela área funcional.
3. **Flexibilidade e Escalabilidade:** Contextos delimitados facilitam a evolução e a escalabilidade da aplicação. Mudanças em um contexto específico têm menos probabilidade de afetar outros contextos, tornando as mudanças mais controladas e menos arriscadas.
4. **Organização Física da Empresa:** A estrutura de contextos delimitados pode espelhar a estrutura organizacional da empresa, permitindo que as equipes de desenvolvimento correspondam mais diretamente às unidades de negócios ou departamentos.
5. **Composição da Aplicação:** A aplicação é composta pela interação entre diferentes contextos. Cada contexto é responsável por sua própria lógica e estado, e a comunicação entre contextos é gerenciada por meio de interfaces bem definidas.

Em resumo, a integridade do modelo no DDD é mantida através da criação de contextos delimitados que encapsulam partes específicas do domínio. Cada contexto tem seu próprio modelo que reflete a realidade daquela área funcional, e a comunicação entre contextos é cuidadosamente projetada para preservar a clareza e a coesão do domínio global da aplicação.

---
Próxima anotação: [[14 - Tipos de relacionamento entre contextos]]
#domínios-ricos #ddd #modelagem-estrategica 