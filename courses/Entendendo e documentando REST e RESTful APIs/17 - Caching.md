- **Caching** é extremamente importante, não só para os usuários, mas também para reduzir o custo de rodar aplicações.
- Na **computação**, qualquer valor que é **difícil** e computacionalmente custoso de obter deve ser cacheado.
- As únicas coisas que não devem ser cacheadas são as que mudam com muita frequência.
- Uma vez feito o cache, como saber que ele está desatualizado?
	- Esse processo chama-se **cache invalidation** e não é algo simples de se fazer.
	- Para nossa sorte o HTTP já conta com tudo que precisamos para fazer cache do lado do cliente.
- **Pontos-chave sobre Caching**
	- Cache pode salvar uma enorme quantidade de tempo.
	- A medida em que diminuímos o tempo de requisição, suas aplicações precisarão de menos poder para rodar e isso implica em gastar menos com servidores.
	- Cache permite uma aplicação escalar mais facilmente, especialmente se a maioria das requisições retornam dados.
	- Infelizmente nem tudo pode ser cacheado. Alguns dados real-time precisam ser buscados todas as vezes. O restante pode ser cacheado por um período de tempo, seja alguns segundos ou um dia, dependendo da frequência em que os dados mudam.
https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching
---
Próxima anotação: [[18 - Cache no Cliente]]

---
#rest #restful #api #cache