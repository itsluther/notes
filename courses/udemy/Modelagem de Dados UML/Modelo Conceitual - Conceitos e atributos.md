## Modelo Conceitual
O modelo conceitual é uma representação que descreve a estrutura das informações que um sistema irá gerenciar. Ele serve como um modelo de domínio no nível de análise, concentrando-se no escopo do problema em vez da solução. O modelo conceitual é independente de paradigmas e tecnologias, sendo uma representação abstrata das entidades e suas relações dentro do domínio do problema.

![[Pasted image 20220823221836.png]]

![[Pasted image 20220823222005.png]]
### Conceitos e Atributos
#### Conceitos
Um conceito é qualquer entidade que possua significado dentro do contexto do sistema e necessite de armazenamento de dados. Exemplos de conceitos incluem cliente, pedido, produto e fornecedor. Um conceito deve ser uma unidade coesa, ou seja, ele deve representar uma única ideia ou entidade, sem misturar informações de diferentes coisas distintas.
#### Atributos
Atributos são informações alfanuméricas simples associadas a cada conceito. Eles descrevem características específicas do conceito e permitem detalhar suas propriedades. Por exemplo, para o conceito de "Produto", os atributos podem ser "descrição" e "preço". É importante observar as seguintes características dos atributos:

- **Não pode ser multivalorado:** Um atributo não pode ter múltiplos valores para o mesmo conceito. Por exemplo, em vez de ter uma lista de telefones para um cliente, é preferível ter um único valor de telefone.
- **Não pode ser composto:** Um atributo não deve ser composto por múltiplas partes. Por exemplo, em vez de ter um único atributo "endereço" com várias informações, é melhor dividir essas informações em atributos separados, como "logradouro", "número", "complemento", etc.

![[Pasted image 20220823223157.png]]
![[Pasted image 20220823223213.png]]

#### Representação em Diagrama de Classes UML
A representação de conceitos e atributos pode ser realizada usando um diagrama de classes UML. Nesse diagrama, os conceitos são representados como classes e os atributos como propriedades dessas classes. A notação comum é: `nome_do_atributo : tipo`. Além disso, é possível indicar atributos identificadores, valores iniciais e atributos derivados.
## Resumo

- O modelo conceitual é uma representação que descreve a estrutura das informações do sistema, sendo independente de tecnologia e focado no escopo do problema.
- Conceitos são entidades significativas que requerem armazenamento de dados e devem ser unidades coesas.
- Atributos são informações alfanuméricas ligadas a conceitos e não podem ser multivalorados ou compostos.
- A representação de conceitos e atributos pode ser feita em diagramas de classes UML, indicando nomes, tipos, atributos identificadores, valores iniciais e atributos derivados.

![[Pasted image 20220823223518.png]]

---
 #modelagem-de-dados-uml  #modelo-conceitual