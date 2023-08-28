2. **Nível 3: HATEOAS (Hypermedia as the Engine of Application State)**
    - A API fornece links hipermídia nas respostas, permitindo a navegação dinâmica pelos recursos.
    - Isso torna a API mais flexível e autoexplicativa, reduzindo a necessidade de documentação externa.

```json
{
  "id": 1,
  "nome": "João",
  "_links": {
    "self": {
      "href": "/cliente/1"
    },
    "pedidos": {
      "href": "/cliente/1/pedidos"
    }
  }
}

```

Em resumo, o Modelo de Maturidade Richardson oferece uma estrutura para avaliar o nível de aderência de uma API aos princípios RESTful. Cada nível representa um passo progressivo em direção à utilização plena dos recursos HTTP e à incorporação do HATEOAS para construir APIs altamente flexíveis e autoexplicativas.

- Nível 0 - Você não sabe nem mesmo usar o HTTP corretamente.
- Nível 1 - Agora você tem recursos.
- Nível 2 - Agora você sabe usar os verbos HTTP corretamente.
- Nível 3 - Agora você usa controles de hipermídia.

---
[[14 - Media Types]] - #rest #restful #api