A autenticação baseada em token é um método amplamente utilizado em aplicações web para controlar o acesso a recursos protegidos. Nesse método, o usuário fornece suas credenciais (normalmente email/senha) para o servidor, que então gera um token de autenticação. Esse token é então incluído no cabeçalho **Authorization** de cada requisição subsequente.

**Processo de Autenticação:**
1. O cliente envia as credenciais para o servidor através de uma requisição, geralmente em formato JSON.

```bash
curl http://example.com/login -i -d '{"email": "email@email.com", "password": "password123"}'
```

2. O servidor processa as credenciais, autentica o usuário e gera um token de acesso.

```bash
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 51
Connection: keep-alive
Server: thin

{
    "access_token": "6afc7fdb1231asda"
}
```

1. O cliente armazena o token e inclui-o no cabeçalho **Authorization** de cada requisição subsequente.

```bash
curl -i -H 'Authorization: Token 6afc7fdb1231asda' http://localhost:3000
```

Embora seja uma solução popular, é importante notar que a autenticação baseada em token não é completamente stateless, pois o servidor precisa armazenar os tokens emitidos para cada usuário. Isso introduz um elemento de "estado" no servidor.

Algumas desvantagens da abordagem stateful incluem a necessidade de replicação dos dados armazenados à medida que a aplicação escala e a gestão dos tokens à medida que o número de clientes aumenta. Também é importante considerar questões de segurança, como a proteção dos tokens armazenados no servidor e a validação adequada dos tokens em cada requisição.

Apesar dessas considerações, a autenticação baseada em token ainda é uma escolha comum para a maioria das Web APIs, devido à sua praticidade e eficiência em controlar o acesso a recursos protegidos.

---
[[25 - Stateless Authentication (com OAuth)]] - #rest #restful #api #autenticação