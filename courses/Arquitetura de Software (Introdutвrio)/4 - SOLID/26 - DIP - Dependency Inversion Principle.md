O Dependency Inversion Principle (Princípio da Inversão de Dependência) é um dos cinco princípios SOLID de design de software. Esse princípio afirma que módulos de alto nível não devem depender diretamente de módulos de baixo nível. Em vez disso, ambos devem depender de abstrações.

Isso significa que, em vez de escrever código que depende diretamente de classes concretas, você deve depender de interfaces ou classes abstratas. Essas abstrações definem o contrato que as classes concretas devem seguir. Dessa forma, se você precisar substituir uma classe concreta por outra, não precisará fazer alterações significativas em seu código de alto nível.

Além disso, o Dependency Inversion Principle também sugere que as abstrações devem ser definidas pelos módulos de alto nível, em vez de pelos módulos de baixo nível. Isso permite que os módulos de alto nível especifiquem o que precisam, em vez de dependerem de como os módulos de baixo nível são implementados.

Seguindo o Dependency Inversion Principle, você pode tornar seu código mais modular, flexível e fácil de manter. Ele também promove a reutilização de código, já que as abstrações podem ser usadas por vários módulos de alto nível.

---
Aqui está um exemplo em TypeScript que usa o Dependency Inversion Principle para separar as responsabilidades de um módulo de alto nível `UserService` e um módulo de baixo nível `UserRepository`:

```typescript
// Abstração
interface UserRepository {
  save(user: User): void;
  getById(id: string): User | undefined;
}

// Implementação concreta
class InMemoryUserRepository implements UserRepository {
  private users: Record<string, User> = {};

  save(user: User) {
    this.users[user.id] = user;
  }

  getById(id: string) {
    return this.users[id];
  }
}

// Módulo de alto nível que usa a abstração
class UserService {
  private userRepository: UserRepository;

  constructor(userRepository: UserRepository) {
    this.userRepository = userRepository;
  }

  createUser(user: User) {
    this.userRepository.save(user);
    // Código para enviar um e-mail de confirmação de conta, etc.
  }

  getUserById(id: string) {
    const user = this.userRepository.getById(id);
    if (!user) {
      throw new Error(`User not found for id ${id}`);
    }
    return user;
  }
}

// Exemplo de uso
const userRepository = new InMemoryUserRepository();
const userService = new UserService(userRepository);

// Cria um novo usuário e o salva no repositório
const newUser = new User("1", "John Doe");
userService.createUser(newUser);

// Obtém um usuário existente pelo ID
const existingUser = userService.getUserById("1");
console.log(existingUser);
```

Neste exemplo, o módulo de alto nível `UserService` depende apenas da abstração `UserRepository`, que define os métodos necessários para salvar e recuperar usuários. A implementação concreta `InMemoryUserRepository` é responsável por armazenar os usuários em memória e implementar os métodos da interface `UserRepository`.

Isso permite que o `UserService` possa usar diferentes implementações de repositório, como um repositório que se comunica com um banco de dados ou um serviço de armazenamento em nuvem, sem precisar ser modificado. Além disso, a implementação concreta do repositório é responsável por lidar com os detalhes específicos de armazenamento e recuperação de usuários.

---
Próxima anotação: [[27 - Dependency Injection]]
#arquitetura-de-software #solid 