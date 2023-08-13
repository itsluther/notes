## Propósito

O **Singleton** é um padrão de projeto criacional que permite a você garantir que uma classe tenha apenas uma instância, enquanto provê um ponto de acesso global para essa instância. Em outras palavras, o Singleton restringe a criação de objetos de uma determinada classe a um único objeto que pode ser acessado de qualquer lugar dentro do programa.

---
## Problema

O padrão Singleton resolve dois problemas de uma só vez, violando o _princípio de responsabilidade única_:

1. **Garantir que uma classe tenha apenas uma única instância**. Por que alguém iria querer controlar quantas instâncias uma classe tem? A razão mais comum para isso é para controlar o acesso a algum recurso compartilhado—por exemplo, uma base de dados ou um arquivo.
    Funciona assim: imagine que você criou um objeto, mas depois de um tempo você decidiu criar um novo. Ao invés de receber um objeto fresco, você obterá um que já foi criado.
    Observe que esse comportamento é impossível implementar com um construtor regular uma vez que uma chamada do construtor **deve** sempre retornar um novo objeto por design.
2. **Fornece um ponto de acesso global para aquela instância**. Se lembra daquelas variáveis globais que você (tá bom, eu) usou para guardar alguns objetos essenciais? Embora sejam muito úteis, elas também são muito inseguras uma vez que qualquer código pode potencialmente sobrescrever os conteúdos daquelas variáveis e quebrar a aplicação.
    Assim como uma variável global, o padrão Singleton permite que você acesse algum objeto de qualquer lugar no programa. Contudo, ele também protege aquela instância de ser sobrescrita por outro código.
    Há outro lado para esse problema: você não quer que o código que resolve o problema #1 fique espalhado por todo seu programa. É muito melhor tê-lo dentro de uma classe, especialmente se o resto do seu código já depende dela.   

Hoje em dia, o padrão Singleton se tornou tão popular que as pessoas podem chamar algo de _singleton_ mesmo se ele resolve apenas um dos problemas listados.

---
## Solução

Todas as implementações do Singleton tem esses dois passos em comum:

- Fazer o construtor padrão privado, para prevenir que outros objetos usem o operador `new` com a classe singleton.
- Criar um método estático de criação que age como um construtor. Esse método chama o construtor privado por debaixo dos panos para criar um objeto e o salva em um campo estático. Todas as chamadas seguintes para esse método retornam o objeto em cache.

Se o seu código tem acesso à classe singleton, então ele será capaz de chamar o método estático da singleton. Então sempre que aquele método é chamado, o mesmo objeto é retornado.

---
## Como implementar
1. Adicione um campo privado estático na classe para o armazenamento da instância singleton.
2. Declare um método de criação público estático para obter a instância singleton.
3. Implemente a “inicialização preguiçosa” dentro do método estático. Ela deve criar um novo objeto na sua primeira chamada e colocá-lo no campo estático. O método deve sempre retornar aquela instância em todas as chamadas subsequentes.
4. Faça o construtor da classe ser privado. O método estático da classe vai ainda ser capaz de chamar o construtor, mas não os demais objetos.
5. Vá para o código cliente e substitua todas as chamadas diretas para o construtor do singleton com chamadas para seu método de criação estático.

---
```typescript
class Singleton {
  private static instance: Singleton;
  private data: string;

  private constructor() {
    this.data = "Initial data";
  }

  public static getInstance(): Singleton {
    if (!Singleton.instance) {
      Singleton.instance = new Singleton();
    }
    return Singleton.instance;
  }

  public setData(newData: string): void {
    this.data = newData;
  }

  public getData(): string {
    return this.data;
  }
}

// Uso do Singleton
const instance1 = Singleton.getInstance();
const instance2 = Singleton.getInstance();

console.log(instance1 === instance2); // true, as duas variáveis referenciam a mesma instância

instance1.setData("New data");

console.log(instance1.getData()); // "New data"
console.log(instance2.getData()); // "New data", pois ambos apontam para a mesma instância
```

```typescript
enum LogLevel {
  DEBUG = "DEBUG",
  INFO = "INFO",
  WARNING = "WARNING",
  ERROR = "ERROR",
}

interface LogEntry {
  timestamp: Date;
  level: LogLevel;
  message: string;
}

class Logger {
  private static instance: Logger;
  private logs: LogEntry[];

  private constructor() {
    this.logs = [];
  }

  public static getInstance(): Logger {
    if (!Logger.instance) {
      Logger.instance = new Logger();
    }
    return Logger.instance;
  }

  public log(level: LogLevel, message: string): void {
    const timestamp = new Date();
    const logEntry: LogEntry = {
      timestamp,
      level,
      message,
    };
    this.logs.push(logEntry);
    this.displayLog(logEntry);
    this.writeToFile(logEntry);
  }

  private displayLog(logEntry: LogEntry): void {
    console.log(`[${logEntry.timestamp.toISOString()}] [${logEntry.level}] ${logEntry.message}`);
  }

  private writeToFile(logEntry: LogEntry): void {
    // Lógica para gravar o log em um arquivo
    // Implementação omitida neste exemplo
  }

  public getLogs(): LogEntry[] {
    return this.logs;
  }
}

// Uso do Logger
const logger = Logger.getInstance();
logger.log(LogLevel.INFO, "Mensagem de informação");
logger.log(LogLevel.ERROR, "Erro encontrado");

const logs = logger.getLogs();
console.log(logs);
```

**Em Python**
```python
class Singleton:
    __instance = None

    def __init__(self):
        if Singleton.__instance is not None:
            raise Exception("Esta classe é um Singleton. Use o método getInstance() para obter uma instância.")
        Singleton.__instance = self

    @staticmethod
    def getInstance():
        if Singleton.__instance is None:
            Singleton()
        return Singleton.__instance


# Uso do Singleton
instance1 = Singleton.getInstance()
instance2 = Singleton.getInstance()

print(instance1 is instance2)  # True, as duas variáveis referenciam a mesma instância
```

---
Próxima anotação: [[42 - Structural Pattern  - Adapter]]
#arquitetura-de-software #design-patterns