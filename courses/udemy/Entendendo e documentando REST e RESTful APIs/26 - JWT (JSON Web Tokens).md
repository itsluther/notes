O JSON Web Token (JWT) é um padrão aberto que fornece uma maneira compacta e segura de transmitir informações entre partes, como um objeto JSON. É frequentemente usado para autenticação e troca de informações entre um servidor e um cliente ou entre serviços. O JWT é uma alternativa popular para a autenticação baseada em sessão, pois é stateless e permite a criação de tokens de acesso que podem ser facilmente verificados.

**Estrutura do JWT**
Um JWT consiste em três partes separadas por pontos (`.`):
1. **Header**: Contém informações sobre o tipo do token (JWT) e o algoritmo de assinatura usado. Geralmente, é um objeto JSON que parece o seguinte:

```json
{
	"alg": "HS256",
	"typ": "JWT"
}
```


2. **Payload (Claims)**: Contém as informações que você deseja transmitir. São declarações sobre uma entidade (geralmente um usuário) e metadados. Exemplos de claims incluem informações como ID do usuário, tempo de expiração do token, etc.

```json
{
  "sub": "1234567890",
  "name": "John Doe",
  "iat": 1516239022
}
```

3. **Signature**: A assinatura é usada para verificar se o remetente do JWT é confiável e se o conteúdo não foi alterado ao longo do caminho. A assinatura é calculada usando o header codificado, o payload codificado, uma chave secreta e o algoritmo especificado no header. A estrutura da assinatura pode ser algo como:

```bash
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

**Vantagens do JWT**

- **Compacto**: O JWT é fácil de ser transmitido como parte de uma URL, parâmetros de consulta ou cabeçalho HTTP.
- **Autocontido**: As informações do JWT são autocontidas, o que significa que você pode confiar nas informações do token sem consultar o banco de dados.
- **Stateless**: Como todas as informações necessárias estão no token, o servidor não precisa manter um estado, tornando-o stateless e escalável.
- **Segurança**: O JWT pode ser assinado digitalmente usando algoritmos criptográficos, garantindo a integridade dos dados e a autenticidade do remetente.

O JWT é amplamente utilizado em sistemas de autenticação, APIs RESTful e aplicações web que exigem troca segura de informações entre diferentes partes. Ele oferece uma solução conveniente e segura para transmitir informações autenticadas de maneira eficiente.

---
#rest #restful #api #autenticação #JWT