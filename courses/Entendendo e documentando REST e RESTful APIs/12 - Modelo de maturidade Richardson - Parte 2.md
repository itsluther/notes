## Nível 1 - Recursos
- No nível 1, passamos a usar recursos como forma de modelar e organizar a API. Neste nível não precisaremos conhecer a funcionalidade de cada método e sim apenas o recurso ao qual temos acesso.
```
POST /cliente

<Cliente>
	<Nome>Luther Azi</nome>
...
</Cliente>
```
| Verbo HTTP | URI | Ação |
| --- | --- | --- |
| GET | /cliente/1 | Visualizar |
| POST | /cliente | Criar |
| PUT | /cliente/1 | Alterar |
| DELETE | /cliente/1 | Remover |

- Modelando corretamente os recursos, preicamos usar os métodos HTTP da forma certa, para que a gente possa criar todas as interações necessárias sob um recurso.
- No nível 1 dizemos que agora temos recursos!
---
## Nível 2 - Verbos HTTP
- Nesse nível, o HTTP deixa de exercer um papel apenas de transporte e passa a exercer um papel semântico na API, ou seja, seus verbos passam a ser utilizados com o propósito no qual foram criados.
- A utilização do métodos mais conhecidos (GET, POST, PUT e DELETE), bem como a tratativa correta dos códigos de resposta, permitem a modelagem e interação com os recursos presentes em uma API.

```
--Enviando--
POST /cliente

<Cliente>
	<Nome>Luther Azi</Nome>
...
</Cliente>
```

```
--Recebendo--
201 Created
Location: /cliente/1
```

- É importante notar 2 aspectos nessa resposta: O primeiro é a utilização correta da resposta "201 Created". Como foi solicitado a criação de um recurso, nada mais adequado que uam resposta que informe que o recurso foi criado com sucesso.
- Além disso, um importante aspecto é a presença do header "**Location**". Esse header informa em qual endereço o recurso criado se encontra disponível.
- No nível 2 dizemos que agora usamos os verbos HTTP de forma correta!
---
- **Códigos de Status HTTP**
	https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
---
Próxima anotação: [[13 - Modelo de maturidade Richardson - Parte 3]]

---
#rest #restful #api