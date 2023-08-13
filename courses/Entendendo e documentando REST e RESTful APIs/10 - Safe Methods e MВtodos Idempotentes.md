- **Safe Methods**
	- São métodos que são considerados "**salvos**". Eles não fazem nenhum efeito de qualquer um dos lados (cliente/servidor).
	- Você pode até implementar algo para quando um safe method for chamado, como por exemplo atualizar o contador de um usuário, mas, o cliente não pode ser o responsável por essa alteração.
	- Os Safe Methods são:
		- GET
		- HEAD
- **Métodos Idempotentes**
	- *Idempotência* é uma propriedade de algumas operações matemáticas e da ciência da computação, que quando "rodadas" múltiplas vezes o resultado não será alterado depois da primeira vez.
	- O impacto de enviar 10 requisições HTTP para um método idempotente será o mesmo de se enviar apenas uma única requisição.
	- Os métodos idempotentes são:
		- GET
		- HEAD
		- PUT
		- DELETE
		- OPTIONS
		- TRACE
---
Próxima anotação: [[11 - Modelo de maturidade Richardson - Parte 1]]

---
#rest #restful #api #curl #http