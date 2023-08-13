- A autenticação baseada em token consiste em enviar o usuário/senha para o servidor e receber em troca um Token que será informado em cada requisição através da header Authorization.
```curl
curl http://example.com/login \
-i -d '{"email": "email@email.com", "password": "password123"}'
```

```HTTP Response
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 51
Connectionn: keep-alive
Server: thin

{
	"access_token": "6afc7fdb1231asda"
}
```

```curl
curl -i -H 'Authorization: Token 6afc7fdb1231asda' \
	http://localhost:3000
```
- Geralmente essa é a escolha para o uso em Web APIs, mas ela não é considerada stateless, pois o **servidor precisará armazenar o Token** e isso caracteriza "**manter o estado**".
- Qual o mal de uma conenxão **stateful**?
	- Será necessário replicar os dados armazenados na medida em que se escala.
	- Quando tiver muitos clientes você precisará gerir muitos tokens.
	- Se cada cliente armazenado tiver mais de um token isso pode dobrar facilmente.
---
Próxima anotação: [[25 - Stateless Authentication (com OAuth)]]

---
#rest #restful #api #autenticação