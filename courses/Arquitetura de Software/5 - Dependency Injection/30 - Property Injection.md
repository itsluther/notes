Property injection é uma técnica de injeção de dependência em que as dependências são injetadas em propriedades públicas de um objeto após a sua instanciação. Em outras palavras, em vez de injetar dependências por meio do construtor, as dependências são injetadas diretamente em propriedades públicas do objeto.
Embora a property injection possa parecer uma alternativa mais simples à constructor injection, ela tem suas desvantagens. Uma das principais desvantagens é que as dependências injetadas em propriedades públicas podem ser alteradas a qualquer momento após a instanciação do objeto, o que pode levar a comportamentos inesperados e dificultar a manutenção do código.
Em TypeScript, a property injection pode ser implementada usando o decorator `@inject` da biblioteca InversifyJS, que é uma biblioteca popular de injeção de dependência para TypeScript. O decorator `@inject` é usado para marcar as propriedades públicas que devem ser injetadas com dependências.
Por exemplo, considere o seguinte serviço `UserService` que depende de um repositório `UserRepository`:

```typescript
import { inject, injectable } from 'inversify';
import { TYPES } from './types';
import { UserRepository } from './userRepository';

@injectable()
export class UserService {
  @inject(TYPES.UserRepository)
  public userRepository!: UserRepository;

  public getUsers(): User[] {
    return this.userRepository.getAll();
  }

  public getUserById(id: number): User {
    return this.userRepository.getById(id);
  }
}
```

Observe que a propriedade `userRepository` é marcada com o decorator `@inject(TYPES.UserRepository)`. Isso indica ao contêiner de injeção de dependência que o `UserRepository` deve ser injetado nessa propriedade.
Para usar a property injection em uma aplicação, é necessário criar uma instância do contêiner de injeção de dependência e registrar os tipos que serão injetados. Por exemplo:

```typescript
import { Container } from 'inversify';
import { TYPES } from './types';
import { UserRepository } from './userRepository';
import { UserService } from './userService';

const container = new Container();
container.bind<UserRepository>(TYPES.UserRepository).to(UserRepository);
container.bind<UserService>(TYPES.UserService).to(UserService);

const userService = container.get<UserService>(TYPES.UserService);
```

Neste exemplo, estamos criando uma instância do contêiner de injeção de dependência e registrando os tipos `UserRepository` e `UserService`. Em seguida, usamos o método `get` do contêiner para obter uma instância do serviço `UserService`. Observe que não é necessário passar a dependência `UserRepository` no construtor, já que ela será injetada automaticamente na propriedade `userRepository` usando a property injection.
Em resumo, a property injection é uma técnica de injeção de dependência que injeta dependências em propriedades públicas de um objeto após a sua instanciação. Embora possa ser útil em alguns casos, a constructor injection é geralmente considerada uma técnica mais robusta e fácil de manter em projetos maiores.

---
Próxima anotação: [[31 - Service Locator Pattern]]
#arquitetura-de-software #dependecy-injection