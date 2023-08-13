- O browser, por padrão, usa o **método HTTP e a URI** como chave para registrar respostas cacheadas, ou seja, mesmo que tenhamos várias representações diferentes, por se tratar do mesmo verbo HTTP e mesma URI, o browser ficará confuso de qual resposta deve fazer cache.
	- `curl http://mysite.com/users -H "Accept: application/json"`
- Para resolver esse problema existe o header `Vary`, que permite indicarmos outros itens para a composição da chave do cache.
	- `curl http://mysite.com/users -H "Accept: application/json"`
```curl
HTTP/1.1 200 OK
Vary: Accept
Cache-Control: max-age=86400
Content-Type: application/json
Content-Length: 128
```
- Assim, nossa chave atual será: `GET/users application/json`
- Isso permitirá que o browser faça o cache de todas as representações.
- A header Vary também pode informar mais de uma chave, por exemplo:
```curl
curl http:mysite.com/users \
	-H "Accept: application/json" \
	-H "Accept-Language: br" \
	-H "Accept-Encoding: gzip" \
```

```curl
HTTP/1.1 200 OK
Vary: Accept, Accept-Language, Accept-Enconding
Cache-Control: max-age=86400
Content-Type: application/xml
Content-Language: br
Content-Encoding: gzip
Content-Length: 1024
```
- Nesse caso, a chave seria; `GET/users application/xml:br:gzip`
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Vary
---
Próxima anotação: [[21 - Autenticação]]

---
#rest #restful #api #cache