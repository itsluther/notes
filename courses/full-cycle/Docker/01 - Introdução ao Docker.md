## O que são e como funcionam os containers?

Os containers são processos e subprocessos isolados que emulam um sistema operacional. Eles são criados utilizando recursos como namespaces, cgroups e file system overlays para fornecer isolamento e gerenciamento eficiente de recursos.

**Namespaces** são mecanismos que permitem isolar processos e recursos dentro de um container. Existem vários tipos de namespaces que o Docker utiliza para fornecer isolamento, tais como:

- **PID Namespace**: Isola os processos dentro do container, de modo que cada container tenha sua própria árvore de processos.
- **User Namespace**: Isola a identidade e permissões dos usuários dentro do container, permitindo que um usuário dentro do container tenha privilégios diferentes do mesmo usuário fora do container.
- **Network Namespace**: Isola a pilha de rede do container, fornecendo interfaces de rede virtuais e endereços IP exclusivos para cada container.
- **File System Namespace**: Isola o sistema de arquivos do container, fornecendo uma visão própria do sistema de arquivos para cada container.

CGroups (ou Control Groups) são mecanismos utilizados para controlar e limitar o consumo de recursos pelos processos dentro de um container. Com o uso de cgroups, é possível reservar quantidades específicas de CPU, memória, I/O de disco e outros recursos para os processos dentro do container, garantindo que eles não interfiram nos recursos do restante do sistema.

O **File System Overlay** (OFS) é um recurso importante no Docker. Ele permite trabalhar com camadas (layers) de forma individualizada e eficiente. Cada imagem do Docker é composta por camadas, e o OFS trabalha com a diferença entre essas camadas, sem alterar as dependências existentes. Dentro de um container, a imagem é considerada imutável, mas é possível criar uma camada de leitura e escrita (read/write) que permite fazer alterações no comportamento do container. Essas alterações podem ser posteriormente "commitadas" para criar uma nova versão da imagem.

## Imagens

As imagens no Docker são criadas a partir de camadas, onde cada camada representa um conjunto de dependências encadeadas em uma árvore. Cada camada é construída a partir de instruções definidas em um arquivo chamado **Dockerfile**, que é um arquivo declarativo utilizado para construir imagens. O Dockerfile descreve os passos necessários para criar uma imagem, incluindo a instalação de dependências, a cópia de arquivos e a definição de configurações.
As imagens são armazenadas em um **Image Registry**, que é um repositório centralizado para armazenar e distribuir imagens do Docker. O Docker Hub é um exemplo de Image Registry público, onde é possível encontrar uma ampla variedade de imagens prontas para uso. No entanto, também é possível criar e usar Image Registries privados para armazenar imagens personalizadas.

## Como o Docker funciona?

O Docker funciona através da interação entre vários componentes. O coração do sistema é o **Docker Host**, que é responsável por executar e gerenciar os containers. O Docker Host executa um processo chamado **daemon** que disponibiliza uma API para que outros componentes possam interagir com ele. Essa API é geralmente consumida através da linha de comando do Docker (CLI).

Além disso, o Docker Host possui algumas funcionalidades importantes:

- **Cache**: O Docker Host possui um sistema de cache que armazena as camadas de imagens e outras informações relevantes. Isso permite que, ao criar ou executar um container, o Docker possa aproveitar as camadas de imagens já presentes no cache, evitando a necessidade de transferir novamente essas camadas pela rede.
- **Gerenciador de Volumes**: O Docker Host possui um sistema de gerenciamento de volumes, que permite criar volumes compartilhados entre o host e os containers. Esses volumes são diretórios no sistema operacional do host que são montados dentro dos containers, permitindo que os arquivos usados dentro do container sejam salvos diretamente no sistema operacional hospedeiro.
- **Network**: O Docker Host possui um sistema de gerenciamento de rede que permite a comunicação entre os containers. Ele fornece interfaces de rede virtuais para os containers e permite a configuração de regras de firewall e encaminhamento de portas para facilitar a comunicação entre os containers e o mundo externo.

Ao utilizar o Docker, os usuários interagem com o Docker Host através do CLI ou outras ferramentas de gerenciamento, que enviam comandos e solicitações para o daemon do Docker Host. O daemon, por sua vez, executa as ações solicitadas, como criar, executar ou parar containers, construir imagens, gerenciar volumes e redes, entre outras operações.

Essa interação entre os componentes do Docker e o isolamento proporcionado pelos namespaces, cgroups e file system overlays permitem que os containers sejam executados de forma eficiente, portátil e isolada, tornando o Docker uma ferramenta poderosa para o desenvolvimento e implantação de aplicações.

#full-cycle #docker