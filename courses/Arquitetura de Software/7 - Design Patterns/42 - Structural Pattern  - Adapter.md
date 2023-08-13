O padrão de design Adapter, também conhecido como Wrapper, é um padrão estrutural que permite a colaboração entre classes ou objetos com interfaces incompatíveis. Ele atua como um intermediário entre dois componentes, permitindo que eles interajam mesmo que suas interfaces sejam diferentes.
A ideia principal por trás do Adapter é fornecer uma camada de tradução entre duas interfaces incompatíveis, de modo que uma classe ou objeto possa ser usado por outro sem a necessidade de modificar seu código original. Isso é especialmente útil quando você tem um código legado ou de terceiros que não pode ser facilmente modificado para se adequar à interface necessária.

Vantagens do uso do padrão Adapter:
1. Reutilização de código: O Adapter permite que você reutilize classes ou objetos existentes, mesmo que suas interfaces sejam diferentes, evitando a duplicação de código e promovendo a modularidade.
2. Integração fácil: O Adapter facilita a integração de componentes que, de outra forma, não poderiam trabalhar juntos devido às suas interfaces incompatíveis.
3. Manutenção simplificada: Ao usar o Adapter, você pode isolar as mudanças necessárias para adaptar uma interface, mantendo o restante do código inalterado. Isso simplifica a manutenção e reduz o impacto de possíveis alterações.

---

### Como implementar

Você pode criar um _adaptador_. Ele é um objeto especial que converte a interface de um objeto para que outro objeto possa entendê-lo.

Um adaptador encobre um dos objetos para esconder a complexidade da conversão acontecendo nos bastidores. O objeto encobrido nem fica ciente do adaptador. Por exemplo, você pode encobrir um objeto que opera em metros e quilômetros com um adaptador que converte todos os dados para unidades imperiais tais como pés e milhas.

Adaptadores podem não só converter dados em vários formatos, mas também podem ajudar objetos com diferentes interfaces a colaborar. Veja aqui como funciona:

1. O adaptador obtém uma interface, compatível com um dos objetos existentes.
2. Usando essa interface, o objeto existente pode chamar os métodos do adaptador com segurança.
3. Ao receber a chamada, o adaptador passa o pedido para o segundo objeto, mas em um formato e ordem que o segundo objeto espera.

Algumas vezes é possível criar um adaptador de duas vias que pode converter as chamadas em ambas as direções.

---

### Exemplo com Axios usando TypeScript

Primeiro, vamos definir nossa interface personalizada `HttpClient` que terá os métodos comuns para fazer solicitações HTTP:

```typescript
interface HttpClient {
  get(url: string): Promise<any>;
  post(url: string, data: any): Promise<any>;
  // Adicione outros métodos conforme necessário (PUT, DELETE, etc.)
}
```

A seguir, criaremos o adaptador `AxiosAdapter` que implementará a interface `HttpClient` usando o Axios:

```ts
import axios, { AxiosResponse } from 'axios';

class AxiosAdapter implements HttpClient {
  async get(url: string): Promise<any> {
    const response: AxiosResponse<any> = await axios.get(url);
    return response.data;
  }

  async post(url: string, data: any): Promise<any> {
    const response: AxiosResponse<any> = await axios.post(url, data);
    return response.data;
  }
}
```

A classe `AxiosAdapter` implementa os métodos da interface `HttpClient` e usa o Axios para fazer as solicitações HTTP correspondentes. A resposta do Axios é então retornada ao cliente.

Agora podemos usar o adaptador em nosso código cliente. Veja um exemplo de como utilizá-lo:

```ts
const httpClient: HttpClient = new AxiosAdapter();

async function makeRequest() {
  try {
    const response = await httpClient.get('https://api.example.com/data');
    console.log('Response:', response);
  } catch (error) {
    console.error('Error:', error);
  }
}

makeRequest();
```

Neste exemplo, estamos criando uma instância do `AxiosAdapter` e atribuindo-a à variável `httpClient`, que é do tipo `HttpClient`. Em seguida, fazemos uma chamada assíncrona para o método `get` usando o `httpClient` para fazer a solicitação HTTP.

Ao usar o padrão Adapter com o Axios, você pode substituir facilmente a implementação do adaptador se desejar usar uma biblioteca diferente para fazer solicitações HTTP, mas ainda assim manter a mesma interface `HttpClient`.

---

### Exemplo genérico em Python

```Python
class Target:
    """
    The Target defines the domain-specific interface used by the client code.
    """

    def request(self) -> str:
        return "Target: The default target's behavior."

class Adaptee:
    """
    The Adaptee contains some useful behavior, but its interface is incompatible
    with the existing client code. The Adaptee needs some adaptation before the
    client code can use it.
    """

    def specific_request(self) -> str:
        return ".eetpadA eht fo roivaheb laicepS"

class Adapter(Target, Adaptee):
    """
    The Adapter makes the Adaptee's interface compatible with the Target's
    interface via multiple inheritance.
    """

    def request(self) -> str:
        return f"Adapter: (TRANSLATED) {self.specific_request()[::-1]}"

def client_code(target: "Target") -> None:
    """
    The client code supports all classes that follow the Target interface.
    """

    print(target.request(), end="")

if __name__ == "__main__":
    print("Client: I can work just fine with the Target objects:")
    target = Target()
    client_code(target)
    print("\n")

    adaptee = Adaptee()
    print("Client: The Adaptee class has a weird interface. "
          "See, I don't understand it:")
    print(f"Adaptee: {adaptee.specific_request()}", end="\n\n")

    print("Client: But I can work with it via the Adapter:")
    adapter = Adapter()
    client_code(adapter)
```

---
Próxima anotação: [[43 - Structural Pattern  - Facade]]
#arquitetura-de-software #design-patterns