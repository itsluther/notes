- **Media Type** é uma string que define qual o formato do dado e como ele deve ser lido pela máquina. Isso permite um computador diferenciar entre JSON e XML, por exemplo.
- Exemplos:
	- `application/json`
	- `application/xml`
	- `multipart/form-data`
	- `text/html`
- Um media type é composto por duas partes separada por uma barra. A primeira parte refere-se ao tipo e a segunda ao subtipo. Também é possível especificar alguns parâmetros adicionais, como por exemplo: `charset=UTF-8`
- A primeira parte contém um tipo registrado de alto nível, que pode ser:
	- application
	- audio
	- example
	- image
	- message
	- model
	- multipart
	- text
	- video
http://www.iana.org/assignments/media-types/media-types.xhtml
- **Accept**
	- Para informar o media type, usamos o header field **Accept** no momento da requisição
		- `curl mockbin.org/request -H "Accept: application/json"`
		- `curl mockbin.org/request -H "Accept: application/xml"`
	- O header field **Accept** não se limita apenas a um valor, pode-se também encadear outros tipos em uma mesma requisição, bastando para isso separá-las por vírgula.
		- `curl mockbin.org/request - H "Accept: application/json;q=0.5, application/yaml;q=0.1"`
	- O parâmetro **q** define **quality factor**, que informa a ordem preferida de retorno da requisição. Esse parâmetro deve estar no intervalo de 0 a 1, sendo 1 o de maior prioridade.
- **Content-Type Vs Accept**
	- É comum a confusão entre os campos **Content-Type** e o **Accept**, mas devemos saber que o Content-Type é o campo que identifica o conteúdo da requisição, ou seja, em uma requisição **POST**, o formato dos dados enviados deve ser indicado no **Content-Type**, já o **Accept**, informa o tipo de retorno do servidor.

---
Próxima anotação: [[15 - Gerindo Erros]]

---
#rest #restful #api