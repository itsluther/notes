- Os objetivos do caching HTTP são **eliminar o envio de requisições o máximo possível**, e caso uma requisição precise ser feita, **reduzir os dados de resposta.**
- O primeiro objetivo pode ser alcançado usando-se um mecanismo de expiração conhecido como **Cache-Control**, e o segundo é através do mecanismo de validação **ETag** ou **Last-Modifed**.
	- Mínimo de requisições: **Cache-Control**
	- Mínimo de dados nas respostas: **ETag**
- **Prevenindo Requisições Inteiras**
	- A maneira mais rápida de fazer uma requisição HTTP é não enviá-la inteiramente.
	- O header **Cache-Control** pode ser usado para definir uma política de cache para um recurso.
		- `Cache-Control: max-age=3600`
		- `Cache-Control: no-cache`
		- `Cache-Control: private, max-age=86400`
	- **max-age**: Especifica em segundos quanto tempo o recurso pode ser cacheado. É interessante notar que esse cache também pode ser feito por intermediários, não só o browser em si.
	- **private/public**: Define quem pode fazer o cache.
		- **Public** significa que qualquer um pode fazer o ache.
		- **Private** por sua vez indica que o cache só pode ser feito pelo browser, ou seja, os intermediários como os CDNs não podem fazer cache.
	- **no-cache/no-store**:
		- **no-store** informa a resposta não deve ser armazenada seja no browser ou em seus intermediários.
		- **no-cache** significa que a resposta pode ser cacheada mas não pode ser recusada sem antes checar o servidor. Ela pode ser combinada com um **ETag**.
	- https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control
---
Próxima anotação: [[19 - ETag]]

---
#rest #restful #api #cache