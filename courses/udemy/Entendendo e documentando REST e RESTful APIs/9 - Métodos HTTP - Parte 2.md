Além dos métodos GET, POST, PUT e DELETE, existem outros métodos HTTP que desempenham funções específicas em uma comunicação entre cliente e servidor.

- **HEAD:**
    - O método **HEAD** é semelhante ao método GET, mas o servidor não retorna o corpo da resposta. É usado para obter informações sobre o recurso sem transferir os dados do corpo.

```bash
curl -I -v http://example.com/users
```

- **PATCH:**
    - O método **PATCH** permite fazer modificações parciais em um recurso, alterando apenas alguns dados específicos, em vez de substituir o recurso inteiro.
    - Enquanto o método PUT substitui o recurso por completo, o método PATCH permite alterações parciais.

```bash
curl -X PATCH http://www.example.com/users/1 \
-H "Content-Type: application/json" \
-d '{"age": 26}'
```

- **OPTIONS:**
    - O método **OPTIONS** permite ao cliente perguntar ao servidor quais requisitos são necessários para um recurso específico.
    - É usado para descobrir quais métodos podem ser aplicados a um recurso ou quais URLs são permitidas para a comunicação com um recurso.
    - O cabeçalho HTTP **Access-Control-Allow-Methods** é usado em conjunto com o método OPTIONS para permitir métodos específicos em uma solicitação CORS. Saiba mais em [MDN Web Docs - Access-Control-Allow-Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS#Access-Control-Allow-Methods) e [OPTIONS Method](http://zacstewart.com/2012/04/14/http-options-method.html).
- **TRACE:**
    - O método **TRACE** ecoa a requisição recebida de volta para o cliente, permitindo que o cliente veja quais mudanças ou adições foram feitas por servidores intermediários.
    - No entanto, o método TRACE pode ser uma vulnerabilidade de segurança em algumas situações. Saiba mais em [CGISecurity - TRACE Vulnerability](http://www.cgisecurity.com/questions/httptracer.shtml).
- **CONNECT:**
    - O método **CONNECT** converte uma requisição de conexão em um túnel TCP/IP transparente, geralmente usado para estabelecer uma comunicação criptografada via SSL (HTTPS) através de um proxy HTTP não criptografado.

Cada um desses métodos HTTP tem uma finalidade específica e contribui para a versatilidade e funcionalidade das APIs e sistemas baseados em HTTP.

---
[[10 - Safe Methods e Métodos Idempotentes]] - #rest #restful #api #curl #http