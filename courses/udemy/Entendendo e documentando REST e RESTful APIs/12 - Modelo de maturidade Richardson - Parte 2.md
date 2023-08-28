1. **Nível 1: Recursos**
    - A API começa a estruturar suas operações em torno de recursos.
    - As operações ainda são definidas por métodos HTTP, porém aplicados diretamente aos recursos.

```text
GET /cliente/1       # Obter informações do cliente 1
POST /produto        # Criar um novo produto
PUT /pedido/123      # Atualizar o pedido 123
DELETE /cliente/5    # Remover o cliente 5
```

1. **Nível 2: Verbos HTTP**
    - O foco está em adotar os verbos HTTP de maneira mais convencional para operações.
    - A semântica dos verbos ajuda a entender a natureza da operação sem examinar a URL completa.

```text
GET /cliente/1       # Obter informações do cliente 1
POST /produto        # Criar um novo produto
PUT /pedido/123      # Atualizar o pedido 123
DELETE /cliente/5    # Remover o cliente 5

```

**Códigos de Status HTTP**:
https://developer.mozilla.org/en-US/docs/Web/HTTP/Status

---
[[13 - Modelo de maturidade Richardson - Parte 3]] - #rest #restful #api