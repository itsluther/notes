- Existem **9 métodos** os quais podemos utilizar para a criação de uma API RESTful. Esse conjunto de métodos possui a semântica de operações possíveis de serem efetuadas sob um determinado **recurso**.
- Na especificação original do **HTTP** existiam apenas 3 métodos (GET, POST, HEAD). Na revisão 1.1 foram adicionados mais 5 verbos (OPTIONS, PUT, DELETE, TRACE e CONNECT). A *RFC 5789* estendeu o HTTP com um novo método PATCH.
---
- **GET** - Read
	- O método GET é utilizado quando existe a necessidade de se obter um recurso. Ele é considerado **idempotente** (Que tem a propriedade de poder ser aplicado mais do que uma vez sem que o resultado se altere), ou seja, independente da quantidade de vezes que é executado sob um recurso, o resultado sempre será o mesmo.
	- Exemplos:
		`curl www.exemplo.com/clients/1`
		`curl -X GET www.exemplo.com/cliente/1`
- **POST** - Create
	- Utilizado para a criação de um recurso a partir do uso de uma representação.
	- Exemplos:
```curl
curl -X POST www.exemplo.com/cliente \
-H "Content-Type: application/json" \
-d '{"nome": "João"}'
```
- **PUT** - Update
	- O método PUT é utilizado como forma de atualizar/criar um determinado recurso.
	- Exemplos:
```curl
curl -X PUT www.exemplo.com/cliente/1 \
-H "Content-Type: application/json" \
-d '{"nome": "João da Silva"}'
```
- **DELETE** - Delete
	- O delete tem como finalidade a remoção de um determinado recurso.
	- Exemplos:
		`curl -X DELETE www.exemplo.com/cliente/1`
---
Próxima anotação: [[9 - Métodos HTTP - Parte 2]]

---
#rest #restful #api #curl #http 