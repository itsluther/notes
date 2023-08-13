- **HEAD**
	- O método **HEAD** é muito parecido com o método **GET**, a única diferença é que o servidor não retornará o "**body**" depois de receber a requisição:
		- Exemplos:
			`curl -I -v http://example.com/users`
- **PATCH**
	- O método **PATCH** faz "modificações parciais nos recursos", ou seja, fazer a alteração de valores específicos de um recurso, ao invés de enviar todos os dados novamente.
	- Enquanto método **PUT** só permite "substituição" inteira do recurso, o **PATCH** permite modificações parciais.
		- Exemplos:
```curl
curl -X PATCH http://www.example.com/users/1 \
-H "Content-Type: application/json" \
-d '{"age": 26}'
```
- **OPTIONS**
	- O método **OPTIONS** é a forma que o cliente possui de perguntar ao servidor quais os requisitos para um determinado recurso.
	- Por exemplo, o **OPTIONS** pode ser usado para saber quais métodos podem ser aplicados a um determinado recurso, ou qual a URL permitida para se comunicar com um determinado recurso.
	- *Access-Control-Allow-Methods*
		https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS#Access-Control-Allow-Methods
	- *OPTIONS Method*
		http://zacstewart.com/2012/04/14/http-options-method.html
- **TRACE**
	- Ecoa de volta a requisição recebida para que o cliente veja se houveram mudanças e adições feitas por servidores intermediários.
	- *TRACE Vulnerabilidade*
		http://www.cgisecurity.com/questions/httptracer.shtml
- **CONNECT**
	- Converte a requisição de conexão para um túnel TCP/IP transparente, usualmente para facilitar comunicação criptografada com SSL (HTTPS) através de um proxy HTTP não criptografado.
---
Próxima anotação: [[10 - Safe Methods e Métodos Idempotentes]]

---
#rest #restful #api #curl #http