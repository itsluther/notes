O design pattern Factory Method é um padrão de criação que fornece uma interface para criar objetos, mas permite que as subclasses decidam qual classe concreta instanciar. Ele aborda o problema de criar objetos sem especificar explicitamente as classes exatas das instâncias que serão criadas.

1. Definição da interface: Primeiro, você define uma interface ou classe abstrata que representa o produto a ser criado. Essa interface declara o método factoryMethod, que será implementado pelas subclasses.
2. Classes concretas: Em seguida, você implementa classes concretas que implementam a interface ou herdam da classe abstrata. Cada uma dessas classes concretas representa um tipo específico de produto que pode ser criado.
3. Classe criadora abstrata: A classe criadora abstrata contém o método factoryMethod. Esse método retorna um objeto do tipo da interface definida no passo 1. A classe criadora também pode conter outros métodos relacionados ao processo de criação dos objetos.
4. Classes criadoras concretas: As classes criadoras concretas estendem a classe criadora abstrata e implementam o método factoryMethod. Cada classe criadora concreta decide qual classe concreta de produto será instanciada e retornada pelo factoryMethod.
5. Utilização: Em seu código, em vez de instanciar objetos diretamente usando a palavra-chave "new", você chama o método factoryMethod da classe criadora. A classe criadora decide qual classe concreta de produto deve ser criada e retorna o objeto desejado.

Dessa forma, o padrão Factory Method encapsula a lógica de criação de objetos em uma classe separada, fornecendo flexibilidade para adicionar novos tipos de produtos sem modificar o código existente que depende desses produtos.

---
```typescript
// Passo 1: Definição da interface de notificação
interface Notification {
  send(message: string): void;
}

// Passo 2: Classes concretas de notificações
class EmailNotification implements Notification {
  send(message: string): void {
    console.log(`Enviando e-mail: ${message}`);
    // Lógica de envio de e-mail
  }
}

class SMSNotification implements Notification {
  send(message: string): void {
    console.log(`Enviando SMS: ${message}`);
    // Lógica de envio de SMS
  }
}

class PushNotification implements Notification {
  send(message: string): void {
    console.log(`Enviando notificação push: ${message}`);
    // Lógica de envio de notificação push
  }
}

// Passo 3: Classe criadora abstrata
abstract class NotificationCreator {
  abstract createNotification(): Notification;

  sendNotification(message: string): void {
    const notification = this.createNotification();
    notification.send(message);
  }
}

// Passo 4: Classes criadoras concretas
class EmailNotificationCreator extends NotificationCreator {
  createNotification(): Notification {
    return new EmailNotification();
  }
}

class SMSNotificationCreator extends NotificationCreator {
  createNotification(): Notification {
    return new SMSNotification();
  }
}

class PushNotificationCreator extends NotificationCreator {
  createNotification(): Notification {
    return new PushNotification();
  }
}

// Utilização do padrão Factory Method
const emailCreator: NotificationCreator = new EmailNotificationCreator();
emailCreator.sendNotification('Olá, este é um e-mail!'); // Enviando e-mail: Olá, este é um e-mail!

const smsCreator: NotificationCreator = new SMSNotificationCreator();
smsCreator.sendNotification('Olá, esta é uma mensagem SMS!'); // Enviando SMS: Olá, esta é uma mensagem SMS!

const pushCreator: NotificationCreator = new PushNotificationCreator();
pushCreator.sendNotification('Olá, esta é uma notificação push!'); // Enviando notificação push: Olá, esta é uma notificação push!
```

---
Próxima anotação: [[41 - Creational Pattern - Singleton]]
#arquitetura-de-software #design-patterns