- Uma classe deve ter ***um, e apenas um***, motivo para ser modificada.
- O princípio de Single Responsibility (SRP) do SOLID afirma que uma classe deve ter apenas uma única responsabilidade. Em outras palavras, uma classe deve ter apenas um motivo para ser alterada. Isso significa que a classe deve ter uma única tarefa ou funcionalidade que ela é responsável por executar.
- Ao seguir o princípio SRP, você pode escrever código mais modular e coeso, onde cada classe é responsável por uma única tarefa e não tem dependências desnecessárias. Isso torna o código mais fácil de entender, modificar e testar, além de reduzir a probabilidade de erros ou bugs.

```typescript
// A responsabilidade de UserRepository é de realizar tratamentos do user dentro do banco de dados
class UserRepository {
  private db: Database;

  constructor(db: Database) {
    this.db = db;
  }

  public saveUser(user: User): void {
    this.db.save(user);
  }

  public getUserById(id: number): User {
    return this.db.find(id);
  }
}

// A responsabilidade de UserController é de fazer a regra de negócio, chamando o UserRepository, caso necessário.
class UserController {
  private userRepository: UserRepository;

  constructor(userRepository: UserRepository) {
    this.userRepository = userRepository;
  }

  public saveUser(user: User): void {
    this.userRepository.saveUser(user);
  }

  public getUserById(id: number): User {
    return this.userRepository.getUserById(id);
  }
}

// A responsabilidade de User é da construção do usuário e de obter as propriedades desse objeto criado
class User {
  private id: number;
  private name: string;
  private email: string;

  constructor(id: number, name: string, email: string) {
    this.id = id;
    this.name = name;
    this.email = email;
  }

  public getId(): number {
    return this.id;
  }

  public getName(): string {
    return this.name;
  }

  public getEmail(): string {
    return this.email;
  }
}
```

- Nesse exemplo, a classe `UserRepository` é responsável por interagir com o banco de dados para salvar e buscar usuários. A classe `UserController`, por sua vez, utiliza a classe `UserRepository` para salvar e buscar usuários e é responsável por lidar com a lógica da aplicação em torno dos usuários (por exemplo, validação de entrada, autorização, etc.). A classe `User` é uma simples classe de dados que contém as propriedades de um usuário.
- Dessa forma, cada classe tem uma única responsabilidade: `UserRepository` gerencia a persistência de usuários no banco de dados, `UserController` gerencia a lógica da aplicação relacionada aos usuários e `User` representa apenas a entidade de usuário.
---
Próxima anotação: [[23 - OCP - Open-Closed Principle]]
#arquitetura-de-software #solid 