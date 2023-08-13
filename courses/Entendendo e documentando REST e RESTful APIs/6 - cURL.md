- A command line tool for getting or sending files using URL syntax.
- **Instalação**
	- `sudo apt-get install curl` (Linux)
	- `brew install curl` (Mac)
	- https://www.cywin.com/ (Windows)
	- http://onlinecurl.com/ (Online)
- Uma requisição cURL é composta da palavra **curl**, da **URL** a qual você quer acessar, e um conjunto de opções que permitem você modificar qualquer coisa na requisição que será enviada.
- **Algumas opções (flags)**
	- **-H**: H é um atalho para **H**eader. Essa opções permite adicionar ou substituir campos de cabeçalho HTTP.
		- Exemplo: `-H "Content-Type: application/json"`
	- **-d**: É um atalho para *data*. É esta opção que vamos usar quando queremos enviar dados para o servidor.
		- Exemplo: `-d '{"name": "Luther Azi"}'`
	- **-i, -include**: Quando usamos esta opção, o cURL não mostrará apenas o corpo da resposta enviada do servidor, mas também o cabeçalho/HEADER.
	- **-I, -head**: Esta opção diz ao cURL para fazer uma requisição do tipo **HEAD** que irá trazer apenas o cabeçalho do documento sem o corpo.
	- **-X, -request**: Esta opção especifica qual o verbo HTTP que queremos usar. O padrão é o GET, mas nós podemos usar também o **POST, PUT, PATCH** ou **DELETE**.
---
- **Fake Online REST API for Testing and Prototyping**
	- https://jsonplaceholder.typicode.com/
---
- **Documentação:** https://curl.haxx.se/
---
Próxima anotação: [[7 - Analisando uma resposta HTTP]]

---
#rest #restful #api #curl 