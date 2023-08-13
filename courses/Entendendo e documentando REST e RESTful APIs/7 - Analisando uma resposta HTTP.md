- O que o cURL mostra como resposta de uma requisição HTTP pode ser dividido em 4 partes:
	-  **Start-Line**(Linha de início / Obrigatória)
	- **Header Fields** (Cabeçalho de Campos / Poder ter 0 ou mais)
	- **Empty Line** (Linha em branco / Obrigatória)
	- **Message-Body** (Corpo da mensagem / Opcional)
---
- **Start-Line**
	- A Start-Line pode ser dividida em duas partes, **Request-Line** e **Status-Line**, em que, na imagem, *HTTP/1.1* é a **Request-Line** que indica a versão do HTTP que foi usada, e o *200 OK* que é a **Status-Line** representando que houve uma resposta.
		`HTTP/1.1 200 OK`
- **Header Fields**
	- Os Header Fields representam os metadados da requisição e resposta HTTP. Eles contém informações sobre como a transferência dos dados deve ser manipulada.
		`Content-Type; Content-Length; X-Powered-By`
	- **Content-Type**: Informa como a representação é serializada:
		`application/json`
	- **Content-Length**: Informa o tamanho do corpo da mensagem e é indicado em octetos.
	- **X-Powered-By**: Header Fields não oficiais, por convenção começam com um **X**. No entanto essa prática está em desuso, pois existem diversos **Header Fields** oficiais e devemos tentar usá-los antes de criar algum. Mesmo assim, ao se criar um novo Header, atualmente, indica-se não começar mais com o **X**.
		https://developer.mozilla.org/en-US/docs/web/HTTP/Headers
		http://stackoverflow.com/questions/3561381/custom-http-headers-naming-conventions
	- **Empty Line**: A linha em branco serve apenas para delimitar o fim dos **Header Fields** e o início do corpo da mensagem.
	- **Message-Body**: O corpo da mensagem contém os dados que foram enviados do servidor em resposta à requisição feita.
---
Próxima anotação: [[8 - Métodos HTTP - Parte 1]]

---
#rest #restful #api #curl #http