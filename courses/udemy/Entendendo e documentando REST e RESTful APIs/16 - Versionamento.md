- **Versionamento** não faz parte das **constraints REST**, nem também do **Modelo de Maturidade Richardson**, mas é indispensável para criar APIs que sofrem mudanças ao longo do tempo.
- **Formas de versionar APIs:**
	- **Subdomínio**: api1.example.com/users
	- **URL**: example.com/v1/users
	- **URL com parâmetros**: example.com/users?v=1
	- **HTTP Header customizado**: `X-API-Version: 1`
	- **Accept Header com Media Type customizado**: `Accept: application/vnd.myapi.v2+json`
	- **Accept Header com opção de versão**: `Accept: application/vnd.myapi+json;version=2.0`
- Atualmente, **uma das mais usadas**, é o versionamento através de **URL**, por ser de fácil implementação, evitar erros por parte de programadores novatos, e permitir compartilhar URLs facilmente.
---
Próxima anotação: [[17 - Caching]]

---
#rest #restful #api