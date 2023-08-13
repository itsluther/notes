Dependency Injection (DI) é um padrão de projeto utilizado na programação orientada a objetos para gerenciar as dependências entre objetos. O objetivo do DI é tornar o código mais modular, reutilizável, fácil de testar e mais fácil de manter.
Em vez de criar objetos diretamente dentro de uma classe, a DI envolve a criação de um objeto externamente e fornecendo-o para a classe como uma dependência. Isso significa que a classe não precisa saber como criar a dependência, ela simplesmente a recebe pronta para uso.

Existem três formas comuns de implementar a DI:
1.  Construtor de injeção de dependência: a dependência é passada para a classe através do construtor. Isso significa que a classe é instanciada com todas as dependências necessárias.
    
2.  Injeção de dependência de método: a dependência é passada para a classe através de um método específico. Isso significa que a classe é instanciada sem todas as dependências necessárias, mas pode recebê-las posteriormente.
    
3.  Injeção de dependência de propriedade: a dependência é definida como uma propriedade da classe e é definida posteriormente.
    
A DI é uma técnica poderosa que pode melhorar a qualidade do código e facilitar a manutenção de grandes sistemas. No entanto, pode ser complexa de implementar e gerenciar corretamente, especialmente em sistemas complexos. Por isso, existem diversas ferramentas e bibliotecas que auxiliam na implementação da DI, como o Spring Framework para Java, o Angular para JavaScript e o ASP.NET Core para .NET.

---
Suponha que você esteja desenvolvendo uma aplicação de comércio eletrônico em TypeScript, e você tem uma classe `ProductService` que é responsável por lidar com todas as operações relacionadas a produtos, como buscar produtos do banco de dados, adicionar novos produtos, atualizar informações de produtos existentes, etc. Para isso, a classe `ProductService` depende de um objeto `DatabaseConnection` que gerencia a conexão com o banco de dados.
Em vez de instanciar a classe `DatabaseConnection` diretamente dentro da classe `ProductService`, você pode utilizar a DI para passar a dependência de `DatabaseConnection` para `ProductService`. Aqui está como você pode fazer isso:

```typescript
class DatabaseConnection {
  // implementação da conexão com o banco de dados
}

class ProductService {
  private dbConnection: DatabaseConnection;

  constructor(dbConnection: DatabaseConnection) {
    this.dbConnection = dbConnection;
  }

  // métodos da classe ProductService que utilizam a conexão com o banco de dados
  // ...
}

// criando uma instância de DatabaseConnection
const dbConnection = new DatabaseConnection();

// criando uma instância de ProductService e passando a dependência de DatabaseConnection
const productService = new ProductService(dbConnection);
```

Nesse exemplo, a classe `ProductService` não precisa mais se preocupar em como criar uma instância de `DatabaseConnection`, pois essa dependência é passada para ela através do construtor. Além disso, se você precisar alterar a implementação da classe `DatabaseConnection`, você só precisa fazer isso em um lugar, em vez de ter que modificar todos os lugares em que a classe é instanciada diretamente.

A DI pode parecer um pouco complexa no início, mas é uma técnica muito útil que pode melhorar a organização e a manutenção do seu código.

---
Próxima anotação: [[28 - Life Cycle]]
#arquitetura-de-software #dependecy-injection