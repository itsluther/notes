## HATEOAS (Hypermedia as the Engine of Application State)
- Em seu blog pessoal, Fielding deixa muito claro que APIs que não utilizam HATEOAS não podem ser consideradas RESTful, mesmo assim, você vai encontrar muitos conteúdos sobre REST que nem ao menos cita essa característica.
- Apesar de aparentemente ser algo não muito familiar, HATEOAS é um conceito presente no dia a dia de todos os usuários da Web. Ele tem como elemento principal uma representação **hypermedia**, que permite um documento descrever seu estado atual e quais os seus relacionamentos com outros futuros estados.

```
GET /cliente/1
HTTP/1.1 200 OK

<Cliente>
	<Id>1</Id>
	<Nome>Manoel da Silva</Nome>
	<link rel="deletar" href="/cliente/1" />
	<link rel="notificar" href="/cliente/1/notificacao" />
</Cliente>
```

- No exemplo, o cliente da API deverá entender o significado dos relacionamentos "deletar" e "notificar" para que ele consiga de fato consumir de forma adequada esses links.
- No nível 3 dizemos que temos controles de hipermídia!
---
- **RESUMO**
	- Nível 0 - Você não sabe nem mesmo usar o HTTP corretamente.
	- Nível 1 - Agora você tem recursos.
	- Nível 2 - Agora você sabe usar os verbos HTTP corretamente.
	- Nível 3 - Agora você usa controles de hipermídia.

---
Próxima anotação: [[14 - Media Types]]

---
#rest #restful #api