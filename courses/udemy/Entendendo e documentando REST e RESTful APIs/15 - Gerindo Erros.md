Ao realizar **requisições RESTful**, é natural que possamos receber erros como **resposta**. Esses erros podem ocorrer devido a problemas no **formato da requisição** ou a **questões internas no servidor**. No entanto, receber uma mensagem de erro não garante que a mensagem seja clara e informativa sobre o que exatamente aconteceu.

O objetivo da **gerência de erros** em APIs RESTful é proporcionar ao solicitante uma mensagem que descreva claramente o ocorrido. Além disso, um **código de status** apropriado também é fundamental, evitando códigos genéricos e priorizando informações úteis.

**Classes dos HTTP Status Code:**
Os códigos de status HTTP são agrupados em cinco classes distintas:
1. **1xx - Informacional**: Códigos que começam com **1** são classificados como códigos informacionais. A maioria deles não é amplamente usada nos dias atuais.
2. **2xx - Sucesso**: Códigos nesta faixa indicam que a comunicação entre o servidor e o cliente ocorreu com sucesso.
3. **3xx - Redirecionamento**: Códigos **3xx** indicam que o cliente deve executar uma ação adicional antes que a requisição possa ser concluída.
4. **4xx - Erro do Cliente**: Códigos nesta categoria apontam que há um problema com a requisição feita pelo cliente. Exemplos incluem solicitações inválidas, autenticação falha ou recursos não encontrados.
5. **5xx - Erro do Servidor**: Quando o servidor não consegue processar com sucesso uma requisição válida do cliente, são utilizados códigos **5xx**. Isso ocorre quando há problemas internos no servidor.

[Lista completa de códigos de status HTTP](https://httpstatuses.com/)

Em resumo, a gerência de erros em APIs RESTful visa fornecer mensagens de erro claras e significativas, juntamente com códigos de status apropriados, para facilitar a compreensão dos problemas pelos solicitantes e permitir uma comunicação eficaz entre o cliente e o servidor.

---
[[16 - Versionamento]] - #rest #restful #api