O **ETag**, abreviação de **Entity Tag**, é um mecanismo essencial para assegurar a validação e identificar versões específicas de respostas em uma API RESTful.

**Como Funciona:**
1. Um cliente faz uma requisição a um recurso, como `/users/jackson`, e o servidor responde incluindo um token de ETag na resposta, como `ETag: "12345"`.
2. Posteriormente, o cliente envia uma nova requisição para o mesmo recurso e inclui o token ETag anterior no cabeçalho `If-None-Match`.
3. O servidor, ao receber a requisição, compara o valor do cabeçalho `If-None-Match` com o ETag atual do recurso. Se forem idênticos, indica que o recurso não foi alterado desde a última requisição e responde com um código **304 Not Modified**. Caso contrário, retorna um código **200 OK** com a representação atualizada.

**Exemplo de Uso:**
- Primeira Requisição:

```bash
Requisição: curl https://example.com/users/jackson

HTTP/1.1 200 OK
Content-Length: 2048
ETag: "12345"

[DATA]
```

- Segunda Requisição com ETag:

```bash
Requisição: curl http://example.com/users/jackson -H 'If-None-Match: "12345"'

HTTP/1.1 304 Not Modified
ETag: "12345"

```

**Vantagens e Considerações:**
- O ETag é um token de validação que pode ser representado por um hash, composto por letras e números.
- O uso de hash como ETag pode ser custoso em termos de computação, especialmente se o recurso for atualizado frequentemente.
- Alternativamente, a data da última atualização (timestamp) do recurso pode ser usada como ETag.
- Para essa abordagem, as headers `Last-Modified` e `If-Modified-Since` são usadas, seguindo a mesma lógica do ETag.

O **ETag** oferece uma maneira eficaz de controlar a validação e versões de recursos em uma API RESTful, permitindo que os clientes economizem largura de banda ao evitar requisições desnecessárias e garantindo que sempre recebam os dados mais recentes quando necessário.

Fonte: [Conditional requests](https://developer.mozilla.org/en-US/docs/Web/HTTP/Conditional_requests)

---
[[20 - Cache com diferentes tipos de representações]] - #rest #restful #api #cache