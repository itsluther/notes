- Design Patterns são padrões de código para solução de problemas conhecidos.
- O objetivo é não reinventar a roda e aplicar uma solução com um bom design de código.
- O conceito de padrões foi introduzido por 4 desenvolvedores intitulados "Gang of Four" (GoF) e hoje conta com 23 padrões fundamentais.
- Atualmente existem mais de 80 padrões conhecidos que são em geral variações dos 23 patterns do GoF.

![[Pasted image 20230412210421.png]]

- Os padrões do GoF estão divididos em 3 famílias:
	- Creational Patterns (Criacional)
		- Fornecem meios de criação de um objeto e de como ele será instanciado.
	- Structural Patterns (Estrutural)
		- Tratam da composição de objetos por heranças e interfaces para diferentes funcionalidades.
	- Behavioral Patterns (Comportamental)
		- Tratam de interações e comunicação entre os objetos além da divisão de responsabilidades.
---
Design Patterns, ou Padrões de Projeto em português, são soluções genéricas para problemas recorrentes que surgem durante o desenvolvimento de software. Eles foram primeiramente formalizados no livro "Design Patterns: Elements of Reusable Object-Oriented Software", escrito por Erich Gamma, Richard Helm, Ralph Johnson e John Vlissides, também conhecido como o "Gang of Four" (GoF), em 1994.

Os padrões de projeto são geralmente categorizados em três grupos principais: padrões de criação, padrões de estrutura e padrões comportamentais.

Os padrões de criação ajudam a lidar com a criação de objetos, como o Singleton, que garante que uma única instância de uma classe seja criada e usada por toda a aplicação, e o Factory Method, que define uma interface para criar objetos, mas permite que as subclasses decidam quais classes instanciar.

Os padrões de estrutura lidam com a composição de classes e objetos, como o Adapter, que converte a interface de uma classe em outra que o cliente espera, e o Composite, que permite que objetos sejam compostos em estruturas de árvore para representar hierarquias todo-parte.

Os padrões comportamentais lidam com a comunicação entre objetos, como o Observer, que define uma dependência um-para-muitos entre objetos de modo que quando um objeto muda de estado, todos os seus dependentes são notificados e atualizados automaticamente, e o Strategy, que define uma família de algoritmos, encapsula cada um deles e os torna intercambiáveis dentro de uma família.

Ao utilizar padrões de projeto, os desenvolvedores podem resolver problemas comuns de maneira eficiente, reduzindo o tempo e esforço necessários para criar soluções personalizadas para cada caso. Além disso, o uso consistente de padrões de projeto pode melhorar a legibilidade, manutenibilidade e escalabilidade do código.

---
Próxima anotação: [[39 - Creational Pattern - Abstract Factory]]
#arquitetura-de-software #design-patterns