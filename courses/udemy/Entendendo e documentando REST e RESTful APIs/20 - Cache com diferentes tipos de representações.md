**Cache com Diferentes Tipos de Representações**
Quando lidamos com diferentes representações de recursos em uma API RESTful, como JSON, XML ou outros formatos, o navegador normalmente usa o **método HTTP e a URI** como chave para armazenar respostas cacheadas. No entanto, isso pode gerar conflitos entre as diferentes representações, já que o navegador se baseia apenas nesses critérios para determinar o cache.

**O Problema:**
Considere o seguinte exemplo:

```bash
curl http://mysite.com/users -H "Accept: application/json"
```

O browser cacheia a resposta com base na chave `GET/users`. Se quisermos buscar uma representação diferente do recurso, como XML, o browser usará a mesma chave e obterá a representação anterior, levando a confusões.

**Solução: Header Vary**
Para resolver essa questão, usamos o header `Vary`, que permite especificar quais outros itens devem ser considerados na composição da chave do cache. Por exemplo:

```bash
HTTP/1.1 200 OK
Vary: Accept
Cache-Control: max-age=86400
Content-Type: application/json
Content-Length: 128
```

Agora, a chave do cache inclui também a informação do cabeçalho `Accept`, resultando em `GET/users application/json`. Dessa forma, o browser pode armazenar e buscar diferentes representações adequadamente.

**Múltiplas Chaves com o Header Vary:**
Além disso, o header Vary pode conter mais de uma chave, como no exemplo a seguir:

```bash
curl http:mysite.com/users \
	-H "Accept: application/json" \
	-H "Accept-Language: br" \
	-H "Accept-Encoding: gzip"
```

```bash
HTTP/1.1 200 OK
Vary: Accept, Accept-Language, Accept-Encoding
Cache-Control: max-age=86400
Content-Type: application/xml
Content-Language: br
Content-Encoding: gzip
Content-Length: 1024
```

Nesse caso, a chave se torna `GET/users application/xml:br:gzip`, permitindo ao browser armazenar diversas representações baseadas nas diferentes combinações de valores.

O uso inteligente do header **Vary** garante que o cache funcione corretamente para diferentes representações, evitando conflitos e proporcionando uma melhor experiência para os usuários.

Fonte: [Vary - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Vary)

---
[[21 - Autenticação]] - #rest #restful #api #cache