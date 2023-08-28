O **Media Type** é uma string que determina o formato dos dados e a maneira como eles devem ser interpretados por máquinas. Essa especificação permite que um computador distinga entre diferentes tipos de dados, como JSON e XML.

**Exemplos de Media Types:**
- `application/json`
- `application/xml`
- `multipart/form-data`
- `text/html`

O Media Type é composto por duas partes separadas por uma barra. A primeira parte é o tipo e a segunda é o subtipo. Além disso, é possível incluir parâmetros adicionais, como por exemplo: `charset=UTF-8`.

A primeira parte do Media Type contém um tipo registrado de alto nível, que pode ser:

- application
- audio
- example
- image
- message
- model
- multipart
- text
- video [Lista de Tipos Registrados](http://www.iana.org/assignments/media-types/media-types.xhtml)

**Definindo o Media Type com o Header Accept:**
O header field **Accept** é usado para informar o Media Type durante a requisição. Por exemplo:
- `curl mockbin.org/request -H "Accept: application/json"`
- `curl mockbin.org/request -H "Accept: application/xml"`

O header field **Accept** não está limitado a apenas um valor; você pode encadear vários tipos em uma única requisição, separando-os por vírgula:
- `curl mockbin.org/request -H "Accept: application/json;q=0.5, application/yaml;q=0.1"`

O parâmetro **q** (quality factor) define a ordem de preferência para o retorno da requisição. Esse parâmetro varia de 0 a 1, onde 1 indica a maior prioridade.

**Diferença entre Content-Type e Accept:**
É comum haver confusão entre os campos **Content-Type** e **Accept**, mas é importante entender a distinção. O **Content-Type** identifica o formato dos dados na requisição. Por exemplo, em uma requisição **POST**, o formato dos dados enviados é indicado pelo **Content-Type**. Por outro lado, o campo **Accept** informa o tipo de formato de retorno desejado do servidor.

Em resumo, os Media Types são essenciais para garantir que os dados sejam interpretados corretamente pelas máquinas, permitindo a comunicação eficaz entre sistemas com diferentes formatos de dados.

---
[[15 - Gerindo Erros]] - #rest #restful #api