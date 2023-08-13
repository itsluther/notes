A afirmação "DDD não é uma arquitetura de camadas" refere-se ao fato de que Domain-Driven Design (DDD) não é uma estrutura arquitetural baseada em camadas tradicionais, como a arquitetura em três camadas (apresentação, lógica de negócio e armazenamento de dados) ou em camadas mais complexas, como a arquitetura hexagonal (portas e adaptadores). Em vez disso, DDD é uma abordagem para o design de software que se concentra na compreensão profunda do domínio da aplicação e na modelagem desse domínio de forma a capturar as regras de negócio complexas e os conceitos essenciais.

Algumas das principais características do DDD incluem:

1. **Modelo de Domínio Rico:** DDD incentiva a criação de um modelo de domínio rico e expressivo que reflete com precisão as regras, entidades, agregados e relacionamentos do negócio. Isso permite uma comunicação mais eficaz entre desenvolvedores e especialistas no domínio.
2. **Separação de Responsabilidades:** Embora DDD não seja uma arquitetura em camadas, ele enfatiza a separação de responsabilidades dentro do código, mas não necessariamente seguindo uma divisão estrita em camadas.
3. **Agregados e Agregados Raiz:** DDD introduz o conceito de agregados, que são grupos de entidades relacionadas que são tratadas como uma única unidade coesa. Cada agregado tem uma entidade raiz, que é a principal entidade de acesso ao agregado.
4. **Contextos Delimitados:** DDD sugere dividir um sistema em diversos "Contextos Delimitados", cada um com seu próprio modelo de domínio. Isso permite a modelagem detalhada em áreas específicas do negócio.
5. **Padrões Estratégicos:** DDD fornece padrões estratégicos para lidar com questões como modelagem de agregados, gerenciamento de repositórios, comunicação entre contextos, entre outros.

Portanto, enquanto DDD não é uma arquitetura de camadas clássica, ele pode ser utilizado em conjunto com diferentes estilos arquiteturais, incluindo arquiteturas em camadas, arquitetura hexagonal, microservices, etc., para criar sistemas mais eficazes e bem projetados, com foco na modelagem do domínio e na colaboração entre as equipes técnicas e os especialistas do domínio.

---

O DDD é uma *abordagem* de *modelagem* de software com foco na *complexidade* da aplicação.
Através do *conhecimento do domínio* é possível facilitar a *implementação* de complexas regras / processos de *negócio*.

- Domain-Driven Design é sobre **design**.
- Design guiado pelo **conhecimento** do **domínio**.

*Toda arquitetura é design, mas nem todo design é arquitetura. - Grady Booch*

---
Próxima anotação: [[02 - Quando eu devo implementar o DDD]]

#domínios-ricos #ddd 