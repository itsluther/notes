As portas no Docker desempenham um papel fundamental na comunicação entre os contêineres Docker e o mundo externo. Quando um contêiner Docker é executado, ele pode expor portas específicas para permitir que os serviços dentro do contêiner sejam acessíveis a partir do host ou de outros contêineres.

O Docker usa o conceito de mapeamento de portas para expor serviços em contêineres para o host ou outros contêineres. Isso permite que os aplicativos dentro do contêiner sejam acessíveis por meio de endereços IP e portas específicas.
Os contêineres têm seu próprio espaço de endereço IP isolado. Por padrão, os contêineres executam em uma rede isolada, e suas portas não são acessíveis diretamente do host ou de outros contêineres.

Para expor um serviço dentro de um contêiner, é necessário mapear uma porta do contêiner para uma porta no host. Isso é feito durante o processo de execução do contêiner usando a opção -p ou --publish.

O mapeamento de porta é definido no formato `hostPort:containerPort`, onde `hostPort` é a porta do host que será vinculada à porta `containerPort` no contêiner. Por exemplo, -p 8080:80 mapeia a porta 80 do contêiner para a porta 8080 do host.

É possível mapear várias portas do contêiner para diferentes portas do host, permitindo que vários serviços sejam expostos.

Além do mapeamento de porta para o host, também é possível vincular portas entre contêineres Docker. Isso permite que os contêineres se comuniquem entre si por meio de suas portas expostas.

As portas expostas em um contêiner podem ser consultadas usando o comando docker port <container_name_or_id>. Ele exibirá o mapeamento das portas do contêiner para as portas do host.

Lembre-se de que as portas no Docker são importantes para permitir a comunicação entre contêineres e o mundo externo. Elas desempenham um papel crucial na construção de aplicativos em contêineres e garantem que os serviços sejam acessíveis de forma adequada.

---
#full-cycle #docker