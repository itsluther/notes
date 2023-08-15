- **ETag** vem de **Entity Tag** e destina-se a assegurar um token de validação identificando uma versão específica de uma resposta.
- Exemplo:
	- Em um primeiro momento um cliente faz a requisição de um recurso `/users/jackson`, na resposta o servidor inclui o token atual ("12345") na header ETag.
	- Em um segundo momento o cliente envia uma nova requisição para `/users/jackson` e inclui o token ETag recebido no header `If-None-Match`.
	- Quando a requisição é recebida pelo servidor, ele checa o valor do header **If-None-Match** e compara com o ETag atual.
	- Se forem iguais, não houve mudança e ele pode retornar um status code **304 Not Modifed**, do contrário pode retornar um **202 OK** com a nova representação.
```curl
--Primeiro momento--
Requisição: curl https://example.com/users/jackson

HTTP/1.1 200 OK
Content-Length: 2048
ETag: "12345"

[DATA]
```

```curl
--Segundo momento--
Requisição: curl http://example.com/users/jackson -H 'If-None-Match: "12345"'

HTTP/1.1 304 Not Modifed
ETag: "12345"
```

- É importante lembrar que o token ETag pode ter uma representação de letras e números, como por exemplo um **HASH**.
- Por oturo lado, um hash ao ser calculado tem um custo computacional considerável, então, caso o recurso seja atualizado diversas vezes, talvez ele não seja a melhor solução.
- Contrapondo ao hash, é possível usar a **data da última atualização (timestamp)** do recurso para verificar se o mesmo encontra-se desatualizado.
- Para esses casos o melhor é usar a header `Last-Modified` associado à header `If-Modifed-Since`, seguindo a mesma lógica do ETag
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Conditional_requests
---
Próxima anotação: [[20 - Cache com diferentes tipos de representação]]

---
#rest #restful #api #cache