**cURL (Client for URLs):**
O cURL é uma ferramenta de linha de comando utilizada para obter ou enviar arquivos utilizando a sintaxe de URL. Ela permite a interação com servidores web através de requisições HTTP e é uma ferramenta versátil para testar APIs, baixar arquivos e realizar diversas operações na web diretamente da linha de comando.

**Instalação:**
Para instalar o cURL, você pode utilizar os seguintes comandos de acordo com o sistema operacional:
- Linux: `sudo apt-get install curl`
- Mac: `brew install curl`
- Windows: Você pode obter o cURL através do [Cygwin](https://www.cygwin.com/) ou usar uma ferramenta online como [Onlinecurl](http://onlinecurl.com/).

**Utilizando o cURL:**
Uma requisição cURL é formada pelo comando `curl`, seguido pela URL que você deseja acessar e um conjunto de opções que permitem personalizar a requisição que será enviada.

**Algumas Opções (Flags) do cURL:**
- **-H (Header):** Usada para adicionar ou substituir campos de cabeçalho HTTP na requisição.
    - Exemplo: `-H "Content-Type: application/json"`
- **-d (Data):** Utilizada para enviar dados para o servidor, especialmente em requisições POST.
    - Exemplo: `-d '{"name": "Luther Azi"}'`
- **-i, -include:** Mostra tanto o corpo da resposta do servidor quanto o cabeçalho (HEADER).
- **-I, -head:** Faz uma requisição do tipo HEAD, trazendo apenas o cabeçalho do documento sem o corpo.
- **-X, -request:** Especifica o verbo HTTP a ser utilizado na requisição. Padrão é GET, mas você pode usar POST, PUT, PATCH ou DELETE.

O cURL é uma ferramenta poderosa para interagir com serviços web diretamente da linha de comando, facilitando testes, depuração e experimentação sem a necessidade de uma interface gráfica. Suas opções permitem ajustar várias características das requisições, o que o torna uma ferramenta versátil para diversos cenários de desenvolvimento e administração de sistemas.

---

**Fake Online REST API for Testing and Prototyping**:
https://jsonplaceholder.typicode.com/
**Documentação:** 
https://curl.haxx.se/

---
[[7 - Analisando uma resposta HTTP]] - #rest #restful #api #curl 