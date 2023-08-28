Apesar de Roy Fielding deixar bem claro que para uma **API** ser considerada **RESTful**, ela deve obrigatoriamente aderir a todas as **constraints** definidas em seu trabalho. No entanto, na prática, muitas vezes é necessário adotar uma abordagem mais simplificada.

**Proposta de Leonard Richardson: Os 4 Níveis da API REST**
Para simplificar a implementação da abordagem REST, Leonard Richardson propôs um modelo dividido em 4 níveis de maturidade. Os níveis 0, 1 e 2 são mais familiares e relativamente mais simples de implementar, embora seja importante destacar que eles não são considerados completamente RESTful.

**Níveis de Maturidade Richardson:**
1. **Nível 0: POX (Plain Old XML/JSON)**
    - Muitas APIs adotam essa abordagem, embora seja o nível mais distante dos princípios fundamentais do REST.
    - As mensagens são serializadas em formatos como XML, JSON, etc.
    - Vale ressaltar que o formato da mensagem não define se o sistema é ou não RESTful.

```text
POST /salvarCliente <- Utilização de um verbo como recurso.
<Cliente>
  <Nome>Manoel da Silva</Nome>
  <!-- ... -->
</Cliente>
```

- Comparativo entre RPC (POX), RESTful e Verbos HTTP:

|Verbo HTTP|URI|Ação|
|---|---|---|
|GET|/buscarCliente/1|Visualizar|
|POST|/salvarCliente|Criar|
|POST|/alterarCliente|Alterar|
|GET/POST|/deletarCliente/1|Remover|

|Verbo HTTP|URI|Ação|
|---|---|---|
|GET|/cliente/1|Visualizar|
|POST|/cliente|Criar|
|PUT|/cliente/1|Alterar|
|DELETE|/cliente/1|Remover|

---
[[12 - Modelo de maturidade Richardson - Parte 2]] - #rest #restful #api