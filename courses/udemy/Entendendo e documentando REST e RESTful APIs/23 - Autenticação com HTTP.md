A autenticação é uma parte crítica da segurança em comunicações via HTTP, e dois mecanismos de autenticação padrão são **Basic** e **Digest**. Ambos foram projetados para operar no contexto das constraints REST, mantendo a natureza stateless das interações HTTP.

**Autenticação Basic:**
No esquema de autenticação **Basic**, as credenciais do usuário (nome de usuário e senha) são codificadas em formato **Base64** e incluídas no cabeçalho **Authorization** de cada requisição. A estrutura é a seguinte:

`Authorization: Basic base64-encoded-credentials`

Por exemplo, usando o cURL, uma requisição de autenticação básica seria:

`curl -u user:pass http://example.com`

Se as credenciais fornecidas não forem autorizadas, o servidor responde com um status code **401 Unauthorized** e inclui o header **WWW-Authenticate** para indicar o tipo de autenticação e o domínio protegido.

`HTTP/1.1 401 Unauthorized WWW-Authenticate: Basic realm="Perfil"`

**Autenticação Digest:**
No esquema de autenticação **Digest**, em vez de enviar as credenciais diretamente, o cliente envia um hash de desafio. O servidor responde com um desafio, o cliente cria um hash a partir das credenciais combinadas com o desafio e envia esse hash para o servidor. Isso evita que as credenciais sejam enviadas em texto claro.

`curl --digest -u user:pass http://example.com`

A resposta do servidor incluirá um **Nonce**, que é um valor único utilizado para proteger contra ataques de repetição. O cliente então cria um hash com base nas credenciais, no método HTTP, no URI e no nonce, e envia esse hash para o servidor.

Ambos os métodos têm vantagens e desvantagens, e a escolha entre eles depende dos requisitos de segurança e da compatibilidade com o servidor e cliente. Em geral, a autenticação Digest oferece maior segurança, mas também é mais complexa de implementar do que a autenticação Basic.

---
[[24 - Autenticação baseada em Token]] - #rest #restful #api #autenticação