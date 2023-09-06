**Repositórios no Domain Model:**

- Um repositório no Domain Model é uma classe responsável por _persistir_ entidades e agregações.
- É um dos tipos de classes mais comuns no serviço de domínio.
- Seu principal propósito é cuidar da persistência dos agregados.
- Geralmente, segue o princípio de "um repositório por agregação", o que significa que cada agregação possui seu próprio repositório.

**Relação com Acesso a Dados:**

- Os repositórios têm uma dependência direta com o meio de acesso a dados.
- São responsáveis por lidar com comandos SQL, connection strings e outros aspectos de acesso a banco de dados.

**Variedade de Implementações:**

- Não há uma única forma "correta" de escrever um repositório. Existem várias abordagens possíveis:
    - O repositório pode ser genérico ou especializado, dependendo das necessidades do domínio.
    - Pode conectar diretamente ao banco de dados e trabalhar com ADO (ActiveX Data Objects).
    - Pode utilizar um ORM (Object-Relational Mapping).
    - Pode até mesmo consultar serviços externos, se necessário.
- O principal foco do repositório é retornar dados e fazê-lo de forma eficaz e precisa.

---
[[32 - Modelagem Tática - Eventos de Domínio]] - #ddd #domínios-ricos #modelagem-tatica 