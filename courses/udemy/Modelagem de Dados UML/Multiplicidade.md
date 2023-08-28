## O que é Multiplicidade?
A multiplicidade em associações na modelagem de dados UML define quantos objetos de uma classe estão relacionados com objetos de outra classe por meio dessa associação. Ela descreve a quantidade de instâncias de uma classe que podem estar associadas a uma única instância da outra classe.
## Como Encontrar as Multiplicidades?
Para determinar as multiplicidades em associações, é necessário analisar o contexto do problema e as necessidades do sistema. Algumas perguntas que podem ajudar a identificar a multiplicidade incluem:

- **Quantos objetos de uma classe estão relacionados a um objeto da outra classe?**
- **Haverá sempre uma única instância associada ou pode haver várias?**
- **Um objeto da primeira classe pode estar relacionado a nenhum objeto da segunda classe?**
- **Um objeto da segunda classe pode estar relacionado a nenhum objeto da primeira classe?**

## Associações Comuns
Existem três tipos de associações comuns que podem ser representadas através da multiplicidade:
### Um para Muitos (1:N)
Neste tipo de associação, uma instância de uma classe está associada a várias instâncias de outra classe, mas cada instância desta última classe está associada a apenas uma instância da primeira classe.
### Um para Um (1:1)
A associação um-para-um indica que uma instância de uma classe está associada a uma única instância de outra classe, e vice-versa. É uma relação mais restrita e menos comum.
### Muitos para Muitos (N:N)
Nesta associação, várias instâncias de uma classe estão associadas a várias instâncias de outra classe. No entanto, a implementação direta de uma associação muitos-para-muitos geralmente requer a criação de uma terceira classe intermediária para representar essa associação, transformando-a em duas associações um-para-muitos.

## Resumo

- **Multiplicidade** em associações define quantos objetos de uma classe estão relacionados a objetos de outra classe.
- Para determinar as multiplicidades, considere o contexto do problema e as necessidades do sistema.
- **Associações Comuns** incluem:
    - Um para Muitos (1:N): uma instância está associada a várias instâncias da outra classe, mas cada instância desta última está associada a apenas uma instância da primeira.
    - Um para Um (1:1): cada instância de uma classe está associada a uma única instância de outra classe.
    - Muitos para Muitos (N:N): várias instâncias de uma classe estão associadas a várias instâncias de outra classe, frequentemente implementada com uma terceira classe intermediária.
---
#modelagem-de-dados-uml