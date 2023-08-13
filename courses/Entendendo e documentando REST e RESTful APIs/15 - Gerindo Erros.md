- Naturalmente, quando fazemos **requisições RESTful**, receberemos como **retorno** um possível **erro**, seja por falha no **formato da requisição**, seja por **causas internas referentes ao servidor**.
- Isso não significa que o **retorno** apresentado seja uma **mensagem clara**, que não deixa **dúvidas sobre o que aconteceu** de fato.
- Pois bem, o intuito da **gerência de erros** em APIs Restful é **informar** ao requisitante, uma **mensagem que retrate o que de fato ocorreu**. Mais do que isso, um **status code** que não seja genérico e sim, útil.
- **Classes dos HTTP Status Code**
	- Existem 5 classes de HTTP Status Code:
		- **1xx Informacional**: Códigos começados com **1** são conhecidos como códigos informacionais. A maioria deles não são usados nos dias atuais.
		- **2xx Success**: Esses códigos indicam que houve sucesso no intercâmbio entre o servidor e o cliente.
		- **3xx Redirection**: Os códigos **3xx** indicam que o cliente deve fazer uma ação adicional antes da requisição estar completa.
		- **4xx Client Error**: Nesse caso, o código indica que existe algo errado com a requisição do cliente.
		- **5xx Server Error**: O cliente enviou uma requisição válida, mas o servidor não foi capaz de processá-la com sucesso.
	https://httpstatuses.com/
---
Próxima anotação: [[16 - Versionamento]]

---
#rest #restful #api