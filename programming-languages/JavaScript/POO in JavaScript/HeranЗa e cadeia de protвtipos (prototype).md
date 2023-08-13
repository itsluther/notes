# Herança e cadeia de protótipos (prototype chain)
JavaScript é um pouco confuso para desenvolvedores com experiência em linguagens baseadas em classes (como Java ou C++), porque é dinâmico e não dispõe de uma implementação de uma `class` (a palavra-chave `class` foi introduzida no ES2015, mas é syntax sugar, o JavaScript permanece baseado em `prototype`).

Quando se trata de herança, o JavaScript tem somente um construtor: objetos. Cada objeto tem um link interno para um outro objeto chamado `prototype`. Esse objeto `prototype` também tem um atributo `prototype`, e assim por diante até o que o valor `null` seja encontrado como sendo o seu `prototype`. `null` que, por definição, não tem `prototype`, e age como um link final nesta **cadeia de protótipos** (prototype chain).

Isto muitas vezes é considerado como um dos pontos fracos do JavaScript, mas o modelo de herança prototipal é de fato mais potente do que o modelo clássico. É, por exemplo, relativamente trivial construir um "modelo clássico" (como na implementaçao de `class`), enquanto o contrário é uma tarefa muito mais difícil.

## Herança com o encadeamento de protótipos

### Propriedades de heranças
Objetos em JavaScript são "sacos" dinâmicos de propriedades (a que se refere as próprias propriedades) e cada um tem um link para um objeto `prototype`. Eis o que acontece quando se tenta acessar uma propriedade:

```Javascript
// Vamos criar um objeto o da função f com suas próprias propriedades a e b:
let f = function () {
   this.a = 1;
   this.b = 2;
}
let o = new f(); // {a: 1, b: 2}

// adicionar propriedades no protótipo da função f
f.prototype.b = 3;
f.prototype.c = 4;

// não defina o protótipo f.prototype = {b: 3, c: 4}; isso vai quebrar a cadeia de protótipos
// o. [[Prototype]] possui propriedades bec.
// o. [[Prototype]]. [[Prototype]] é Object.prototype.
// Finalmente, o. [[Prototype]]. [[Prototype]]. [[Prototype]] é nulo.
// Este é o fim da cadeia de protótipos, como nulo,
// por definição, não possui [[Prototype]].
// Assim, a cadeia completa de protótipos se parece com:
// {a: 1, b: 2} ---> {b: 3, c: 4} ---> Object.prototype ---> null dfdf

console.log(o.a); // 1
// Existe uma propriedade 'a' no objeto o? Sim, e seu valor é 1.

console.log(o.b); // 2
// Existe uma propriedade própria 'b' em o? Sim, e seu valor é 2.
// O protótipo também tem uma propriedade 'b', mas não é visitado.
// Isso é chamado de sombreamento de propriedade(Property Shadowing)

console.log(o.c); // 4
// Existe uma propriedade própria 'c' em o? Não, verifique seu protótipo.
// Existe uma propriedade 'c' própria em o. [[Prototype]]? Sim, seu valor é 4.

console.log(o.d); // undefined
// Existe uma propriedade 'd' própria em o? Não, verifique seu prototype.
// Existe uma propriedade 'd' em o. [[Prototype]]? Não, verifique seu prototype.
// o. [[Prototype]]. [[Prototype]] é Object.prototype e não há propriedade 'd' por padrão, verifique seu prototype.
// o. [[Prototype]]. [[Prototype]]. [[Prototype]] é nulo, pare de pesquisar,
// nenhuma propriedade encontrada, retorne indefinido.
```
---
#javascript 