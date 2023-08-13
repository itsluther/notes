- Os mecanismos padrões de autenticação com HTTP são definidos como **Basic** e **Digest** (resumida).
- Esses dois mecanismos foram projetados seguindo as constraints REST, ou seja, eles são stateless
- Nesses dois mecanismos o conjunto usuário/senha é incluído em cada requisição
	- **Codificado em *Base64*** para autenticação **Basic**
	- **Codificado em *hash MD5*** para a autenticação **Digest**
- A definição do funcionamento da autenticação em HTTP pode ser encontrada em:
	- https://tools.ietf.org/html/rfc2617
- A documentação informa que para uma autenticação o cliente deve enviar o header **Authorization** no seguinte formato:
	- `Authorization: auth-scheme hashed-credentials`
- **Autenticação Basic**
	- `Authorization: Basic am9objpwYXNz`
	- Para fazer uma requisição de autenticação básica HTTP via cURL teríamos:
		- `curl -u user:pass http://example.com`
- **Autenticação Digest**
	- `Authorization: Digest 2ac75c760bd3ea55c5ce4c83a6bad1d7`
	- Para fazer uma requisição autenticação HTTP do tipo Digest, teríamos
		- `curl --digest -u user:pass http://example.com`
- Em retorno à requisição feita com o header Authorization, caso as credenciais não sejam autorizadas, o servidor deve retornar o status code **401 Unauthorized** e setar o header **WWW-Authenticate** com o **tipo de autenticação** que deve ser usado e **qual o domínio** (realm).
	- `WWW-Authenticate: Basic realm="Perfil"`
- A diretiva de domínio "**realm**" é opcional e indica a proteção de um determinado espaço, pois uma mesma aplicação pode-se ter diferentes áreas protegidas usando diferente esquemas de autenticação.
---
Próxima anotação: [[24 - Autenticação baseada em Token]]

---
#rest #restful #api #autenticação