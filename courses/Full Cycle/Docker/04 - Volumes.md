Em Docker, um volume é um mecanismo utilizado para persistir dados gerados ou consumidos por um contêiner. Ele fornece um meio de armazenamento flexível e independente do ciclo de vida do contêiner em si. Um volume pode ser considerado como um diretório montado em um ou mais contêineres, que pode ser usado para armazenar dados e compartilhá-los entre contêineres.

Os volumes são úteis em várias situações. Aqui estão alguns motivos pelos quais você pode querer usar volumes em Docker:

1. **Persistência de dados**: Ao usar um volume, você pode armazenar dados gerados ou consumidos por um contêiner, como bancos de dados, arquivos de log ou uploads de usuários. Dessa forma, mesmo que você pare ou remova o contêiner, os dados serão mantidos no volume e podem ser facilmente acessados novamente quando você iniciar um novo contêiner.    
2. **Compartilhamento de dados**: Os volumes podem ser compartilhados entre vários contêineres. Isso é útil quando você precisa que vários contêineres acessem os mesmos dados. Por exemplo, se você tem um contêiner de aplicação e um contêiner de banco de dados, pode usar um volume compartilhado para permitir que ambos acessem os arquivos de banco de dados.
3. **Backup e restauração**: Com volumes, é mais fácil fazer backup dos dados gerados pelos contêineres e restaurá-los posteriormente, se necessário. Você pode simplesmente copiar os dados do volume para um local seguro e, em caso de perda ou falha, restaurar esses dados em um novo contêiner.

**Volumes gerenciados pelo Docker**:

1. Crie um volume usando o comando `docker volume create <nome-do-volume>`.
2. Execute um contêiner usando o volume criado com o comando `docker run -v <nome-do-volume>:<caminho-no-contêiner> <imagem-do-contêiner>`. Isso montará o volume no contêiner no caminho especificado.
3. Os dados gravados no caminho especificado dentro do contêiner serão salvos no volume.

**Volumes montados manualmente**:

1. Crie uma pasta no host onde deseja armazenar os dados do volume.
2. Execute um contêiner usando o comando `docker run -v <caminho-no-host>:<caminho-no-contêiner> <imagem-do-contêiner>`. Isso montará a pasta do host no contêiner no caminho especificado.
3. Os dados gravados no caminho dentro do contêiner serão armazenados na pasta do host.


---
#docker #full-cycle 