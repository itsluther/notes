No Docker, tanto o `ENTRYPOINT` quanto o `CMD` são usados para definir o comando que será executado quando um contêiner for iniciado. No entanto, eles têm diferenças significativas em como são tratados durante a execução do contêiner.

O `ENTRYPOINT` é usado para configurar um comando ou um executável que será executado como o principal processo dentro do contêiner. Ele define um comando fixo que é invocado quando o contêiner é iniciado e normalmente é usado para especificar a funcionalidade principal do contêiner. O `ENTRYPOINT` pode ser definido como uma matriz JSON ou como uma única string, onde cada elemento da matriz ou a própria string representa um argumento do comando. Se um `ENTRYPOINT` for especificado, ele não será substituído por comandos fornecidos na linha de comando ao iniciar o contêiner.

Por exemplo:

`ENTRYPOINT ["python", "app.py"]`

Já o `CMD` é usado para fornecer argumentos padrão para o comando especificado no `ENTRYPOINT` ou, se nenhum `ENTRYPOINT` for fornecido, será usado como o comando padrão a ser executado. O `CMD` é geralmente usado para definir argumentos variáveis que podem ser substituídos por meio da linha de comando ao iniciar o contêiner. Ele também pode ser substituído no arquivo `Dockerfile` usando o parâmetro `docker run` na linha de comando.

Por exemplo:

`CMD ["--mode=prod"]`

No comando `docker run`, você pode substituir o `CMD` especificado no `Dockerfile` com seus próprios argumentos, como:

`docker run myimage --mode=dev`

Se tanto o `ENTRYPOINT` quanto o `CMD` estiverem presentes no mesmo `Dockerfile`, o `CMD` será usado como os argumentos para o `ENTRYPOINT`.

Resumindo, o `ENTRYPOINT` define o comando principal do contêiner e o `CMD` fornece argumentos padrão para esse comando. O `ENTRYPOINT` é mais adequado quando você deseja especificar um comando fixo para o contêiner, enquanto o `CMD` é útil quando você deseja fornecer argumentos padrão que podem ser substituídos.

---
#full-cycle #docker 