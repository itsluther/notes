O registro de tipos genéricos (ou generics) em um contêiner de injeção de dependência permite que tipos genéricos sejam injetados em componentes e serviços de uma aplicação. Isso é importante porque os tipos genéricos são usados em muitas bibliotecas e estruturas de dados em TypeScript, e é importante ter uma maneira de injetá-los em outros componentes e serviços que os utilizam.
O registro de tipos genéricos geralmente é feito através de uma interface genérica que define o contrato que os tipos devem cumprir. Por exemplo, um contrato genérico pode ser definido como:

```typescript
interface IRepository<T> {
  getById(id: number): T;
  getAll(): T[];
}
```

Neste exemplo, a interface `IRepository` define um contrato genérico que pode ser usado para injetar diferentes tipos de repositórios em serviços ou componentes. Qualquer classe que implemente esta interface pode ser registrada no contêiner de injeção de dependência como um tipo genérico.
O registro de tipos genéricos é semelhante ao registro de tipos não genéricos. Em geral, o processo envolve a criação de uma instância do contêiner de injeção de dependência e, em seguida, a chamada do método `register` ou `registerSingleton` para registrar o tipo genérico. Por exemplo:

```typescript
import { Container } from 'inversify';

interface IRepository<T> {
  getById(id: number): T;
  getAll(): T[];
}

class Repository<T> implements IRepository<T> {
  getById(id: number): T {
    // implementação aqui
  }

  getAll(): T[] {
    // implementação aqui
  }
}

const container = new Container();

container.bind<IRepository<User>>(TYPES.UserRepository).to(Repository<User>);
container.bind<IRepository<Order>>(TYPES.OrderRepository).to(Repository<Order>);
```

Neste exemplo, estamos registrando um repositório genérico `Repository<T>` para ser usado em diferentes serviços ou componentes da nossa aplicação. O método `bind` é usado para registrar o tipo genérico no contêiner de injeção de dependência. Observe que estamos usando um identificador (`TYPES.UserRepository` e `TYPES.OrderRepository`) para registrar diferentes tipos de repositórios genéricos.
Após o registro dos tipos genéricos, eles podem ser injetados em componentes ou serviços que os usam. Isso é feito adicionando um parâmetro ao construtor do componente ou serviço que corresponde ao tipo genérico registrado. Por exemplo:

```typescript
import { injectable, inject } from 'inversify';

@injectable()
class UserService {
  constructor(@inject(TYPES.UserRepository) private userRepository: IRepository<User>) {}

  getUsers(): User[] {
    return this.userRepository.getAll();
  }

  getUserById(id: number): User {
    return this.userRepository.getById(id);
  }
}
```

Neste exemplo, estamos injetando o tipo genérico `IRepository<User>` no serviço `UserService`. Observe que estamos usando o identificador `TYPES.UserRepository` para indicar o tipo de repositório que deve ser injetado. O contêiner de injeção de dependência cuidará de instanciar a classe `Repository<User>` e injetá-la no construtor do serviço `UserService`.

---
Próxima anotação: [[30 - Property Injection]]
#arquitetura-de-software #dependecy-injection