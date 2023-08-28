**Autenticação Stateless com OAuth**
A autenticação stateless é um paradigma em que as aplicações web não armazenam informações de estado no servidor entre as requisições, o que melhora a escalabilidade e a simplicidade das interações entre o cliente e o servidor. O protocolo OAuth é uma implementação popular desse conceito, permitindo que os usuários concedam acesso a recursos sem compartilhar suas credenciais originais.

**OAuth: Conceito e Funcionamento**
OAuth (Open Authorization) é um protocolo de autorização que permite que um aplicativo acesse os recursos de um usuário em um serviço sem a necessidade de compartilhar as credenciais do usuário. Ele permite que os usuários autorizem terceiros a agir em seu nome, geralmente por um período limitado, sem a exposição direta de suas senhas.

O processo de autenticação OAuth envolve as seguintes partes:
1. **Cliente**: A aplicação que deseja acessar os recursos do usuário. Pode ser um aplicativo móvel, site ou serviço.
2. **Servidor de Autorização**: Responsável por verificar a identidade do usuário e fornecer tokens de acesso. Ele interage com o usuário para obter sua permissão e gera tokens de acesso para a aplicação cliente.
3. **Proprietário do Recurso (Usuário)**: O dono dos recursos protegidos (por exemplo, conta de usuário, perfil, fotos etc.) que autoriza o cliente a acessar esses recursos.
4. **Servidor de Recursos**: O servidor que hospeda os recursos protegidos que o cliente deseja acessar em nome do usuário. Ele valida os tokens de acesso e fornece os recursos se a autorização for bem-sucedida.

**Fluxo do Protocolo OAuth**
1. O cliente solicita autorização ao usuário, redirecionando-o para o servidor de autorização. Isso pode ser feito por meio de uma página de login do provedor de autenticação (por exemplo, Google, Facebook).
2. O usuário fornece suas credenciais ao servidor de autorização e concede permissão ao cliente.
3. O servidor de autorização gera um token de acesso e redireciona o usuário de volta ao cliente com esse token.
4. O cliente inclui o token de acesso no cabeçalho **Authorization** de suas requisições para o servidor de recursos.
5. O servidor de recursos verifica o token e fornece os recursos solicitados se o token for válido.

**Vantagens do OAuth Stateless**
- **Segurança**: O usuário não compartilha suas credenciais com o cliente, reduzindo o risco de exposição indevida.
- **Conveniência**: O usuário não precisa criar uma nova conta ou compartilhar senhas com aplicativos terceiros.
- **Escalabilidade**: A ausência de estado no servidor simplifica a arquitetura e facilita a escalabilidade.
- **Controle de Permissões**: O usuário tem controle sobre quais permissões conceder a um aplicativo, podendo revogá-las a qualquer momento.

Em resumo, o OAuth oferece uma abordagem stateless para autenticação e autorização, permitindo que aplicativos acessem os recursos de um usuário de forma segura e controlada, sem a necessidade de compartilhar credenciais originais. Isso torna a experiência do usuário mais conveniente e reduz os riscos associados à exposição de senhas.

![[Pasted image 20230226193659.png]]


**Leituras Extras**:
- https://scotch.io/tutorials/the-ins-and-outs-of-token-based-authentication
- http://www.kaleidos.net/blog/295/stateless-authentication-with-api-rest

---
[[26 - JWT (JSON Web Tokens)]] - #rest #restful #api #autenticação #OAuth