Na construção de uma API RESTful, existem 9 métodos HTTP que podem ser utilizados para executar operações em recursos. Cada método possui uma semântica específica e representa uma operação sobre o recurso.

**Origem e Evolução dos Métodos HTTP:**

- Na especificação original do HTTP, existiam apenas 3 métodos (GET, POST, HEAD).
- Na revisão 1.1, mais 5 verbos foram adicionados (OPTIONS, PUT, DELETE, TRACE e CONNECT).
- A RFC 5789 estendeu o HTTP com um novo método chamado PATCH.

**Métodos HTTP e Suas Semânticas:**

- **GET** - Ler (Read):
    - Utilizado para obter informações de um recurso.
    - É considerado idempotente, ou seja, o resultado é sempre o mesmo independentemente do número de requisições.

```bash
www.exemplo.com/clients/1 curl -X GET www.exemplo.com/cliente/1`
```

- **POST** - Criar (Create):
    - Utilizado para criar um novo recurso a partir dos dados fornecidos na requisição.

```bash
curl -X POST www.exemplo.com/cliente \ -H "Content-Type: application/json" \ -d '{"nome": "João"}'
```

- **PUT** - Atualizar (Update):
    - Utilizado para atualizar ou criar um recurso com os dados fornecidos.        


```bash
curl -X PUT www.exemplo.com/cliente/1 \
-H "Content-Type: application/json" \
-d '{"nome": "João da Silva"}'
```

- **DELETE** - Excluir (Delete):
    - Utilizado para remover um recurso.
```bash
curl -X DELETE www.exemplo.com/cliente/1
```

Os métodos HTTP em uma API RESTful possuem significados bem definidos, tornando a comunicação entre o cliente e o servidor padronizada e sem ambiguidades. Cada método é aplicado de acordo com o objetivo e a natureza da operação que se deseja realizar em um recurso específico.

---
[[9 - Métodos HTTP - Parte 2]] - #rest #restful #api #curl #http 