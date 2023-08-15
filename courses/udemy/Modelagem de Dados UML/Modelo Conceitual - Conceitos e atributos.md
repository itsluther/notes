# Modelo Conceitual
- **Definição 1**: é um modelo que descreve a estrutura das informações que o sistema vai gerenciar (Wazlawick);
- **Definição 2**: é o *Modelo de Domínio* em nível de *Análise*:
	- Pertence ao escopo do problema e não ao escopo da solução;
	- Independente de paradigma;
	- Independente de tecnologia.

```
Modelo de domínio:
	- Modelo que descreve as entidades do domínio, bem como as interrelações entre elas.
```

![[Pasted image 20220823221836.png]]

---
![[Pasted image 20220823222005.png]]

## Conceitos
- Um conceito pode ser qualquer entidade que tenha um **significado** para o sistema e que tenha uma necessidade de **armazenamento de dados**.
	- Exemplos: cliente, pedido, produto, fornecedor, etc.
- Um conceito deve ser uma **unidade coesa**.
	- **Observação**: *Não se deve misturar informações de várias coisas distintas em um mesmo conceito.*
## Atributos
- Informações alfanuméricas simples, como números, textos, datas, etc. contidas em cada conceito.
	- Produto: descrição, preço
	- Cliente: nome, email, telefone, CPF, dataNascimento
- Notas (1FN):
	- *Não pode ser multivalorado*
		- **RUIM**: telefones("3763-3938", "3762-2233", 3769-1451)
		- **BOM**: telefone : "3762-1433"
	- *Não pode ser composto*
		- **RUIM**: endereço ("Rua Floriano Peixoto, n250, apto 302, Bairro...")
		- **BOM**: logradouro, numero, complemento, bairro, cep

![[Pasted image 20220823223157.png]]
![[Pasted image 20220823223213.png]]

---
# Resumo da aula
- **O que é modelo conceitual**
	- Modelo que descreve a estrutura das informações gerenciadas pelo sistema;
	- Modelo de domínio em nível de análise;
	- Pertence ao escopo do problema.
- **Conceitos**
	- Algo que tenha significado para o negócio e necessidade de armazenamento;
	- Unidade coesa do negócio.
- **Atributos**
	- Informações alfanuméricas simples;
	- Não pode ser multivalorado (1FN);
	- Não pode ser composto (1FN).
- **Representação de conceitos e atributos com diagrama de classes UML**
	- nome : tipo
	- Atributo identificador
	- Valor inicial
	- Atributo derivado
![[Pasted image 20220823223518.png]]

---
 #modelagem-de-dados-uml  #modelo-conceitual