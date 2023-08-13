Ciclo de vida se refere ao tempo em que um objeto é criado, usado e, eventualmente, destruído. A gestão adequada do ciclo de vida de objetos é importante para garantir que os recursos sejam utilizados de forma eficiente e para evitar vazamentos de memória.

Existem diferentes tipos de ciclos de vida que podem ser gerenciados, dependendo do contexto de uso do objeto. Aqui estão alguns exemplos de tipos de ciclo de vida comuns:

1.  Ciclo de vida de um objeto de escopo de requisição: Nesse ciclo de vida, um objeto é criado no início de uma requisição e destruído quando a requisição é concluída. Isso é comum em aplicações web que usam frameworks como o Angular ou o React. Por exemplo:

```typescript
class RequestScopedObject {
  constructor() {
    console.log('Objeto criado!');
  }

  doSomething() {
    console.log('Fazendo algo...');
  }

  destroy() {
    console.log('Objeto destruído!');
  }
}

// Exemplo de uso em um serviço Angular
@Injectable({ providedIn: 'root' })
class MyService {
  private requestScopedObject: RequestScopedObject;

  constructor() {
    this.requestScopedObject = new RequestScopedObject();
  }

  doSomething() {
    this.requestScopedObject.doSomething();
  }

  ngOnDestroy() {
    this.requestScopedObject.destroy();
  }
}
```

2.  Ciclo de vida de um objeto de escopo de sessão: Nesse ciclo de vida, um objeto é criado quando a sessão do usuário é iniciada e destruído quando a sessão é encerrada. Isso é comum em aplicações web que precisam manter informações de sessão, como autenticação ou preferências do usuário. Por exemplo:

```typescript
class SessionScopedObject {
  constructor() {
    console.log('Objeto criado!');
  }

  doSomething() {
    console.log('Fazendo algo...');
  }

  destroy() {
    console.log('Objeto destruído!');
  }
}

// Exemplo de uso em um serviço Angular
@Injectable({ providedIn: 'root' })
class MyService {
  private sessionScopedObject: SessionScopedObject;

  constructor() {
    this.sessionScopedObject = new SessionScopedObject();
  }

  doSomething() {
    this.sessionScopedObject.doSomething();
  }

  ngOnDestroy() {
    this.sessionScopedObject.destroy();
  }
}
```

3.  Ciclo de vida de um objeto de escopo de aplicação: Nesse ciclo de vida, um objeto é criado quando a aplicação é iniciada e destruído quando a aplicação é encerrada. Isso é comum em aplicações que precisam manter informações globais que são usadas por vários componentes ou serviços. Por exemplo:

```typescript
class ApplicationScopedObject {
  constructor() {
    console.log('Objeto criado!');
  }

  doSomething() {
    console.log('Fazendo algo...');
  }

  destroy() {
    console.log('Objeto destruído!');
  }
}

// Exemplo de uso em um serviço Angular
@Injectable({ providedIn: 'root' })
class MyService {
  private applicationScopedObject: ApplicationScopedObject;

  constructor() {
    this.applicationScopedObject = new ApplicationScopedObject();
  }

  doSomething() {
    this.applicationScopedObject.doSomething

```

---
Próxima anotação: [[29 - Registro de generics]]
#arquitetura-de-software #dependecy-injection