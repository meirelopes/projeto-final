# cidade-segura API 

A **Cidade Segura API** é uma aplicação REST projetada para melhorar a segurança nas cidades. Esta API permite aos usuários postar informações sobre locais considerados perigosos em uma determinada cidade, bem como pesquisar esses locais com base em bairros e cidades específicas.


<p align="center">
     <a alt="Java">
        <img src="https://img.shields.io/badge/Java-v11-blue.svg" />
    </a>
    <a alt="Spring Boot">
        <img src="https://img.shields.io/badge/Spring%20Boot-v2.7.15-brightgreen.svg" />
    </a>
    <a alt="PostgreSQL">
        <img src="https://img.shields.io/badge/PostgreSQL-v42.6.0-blue.svg" />
    </a>
</p>

- [Principais Tecnologias](#principais-tecnologias)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Detalhes do Projeto](#detalhes-do-projeto)
- [Documentação](#documentação)
- [Postman](#postman)
- [Sugestões](#sugestões)
- [Autores](#autores)

## Principais Tecnologias:

- **Java 11**

- **Spring Boot 2.7.15**: Spring Boot, reponsável por aumentar a produtividade do desenvolvedor com sua configuração automática disponível em  [Spring Initializr](https://start.spring.io/)
  
- **Spring Data JPA**: Abstração da camada de acesso ao banco de dados, reduzindo o código padrão.
  
- **ModelMapper**: Simplifica a transferência de dados entre diferentes modelos de objetos, tornando a tarefa de conversão de dados mais eficiente e intuitiva.
  
- **Spring Security com Token JWT**: Implementamos o Spring Security para garantir a segurança de nossa aplicação. Utilizamos tokens JWT (JSON Web Tokens) para autenticação de usuários. Essa abordagem de autenticação baseada em tokens é segura e escalável, permitindo que os usuários façam login com segurança em nossa aplicação.
  
- **Hibernate Validator**: Implementação da especificação Bean Validation, que permite validar objetos com facilidade em diferentes camadas da aplicação. 
  
## Estrutura do Projeto:

O projeto está estruturado em diversos conjuntos de pacotes, cada um com uma finalidade específica:

### Pacote API

Esse pacote é responsável por tratar da camada de controle da aplicação, como a interação com o consumidor da API, processar solicitações HTTP e coordenar a execução das operações do sistema. Contém os seguintes sub pacotes:

- `controller`: este pacote contém nossos controladores Rest. Aqui, expomos nossos endpoints, seguindo o estilo arquitetural REST. DTOs são utilizados nesta camada para definir as interfaces de consumo de forma adequada, evitando a exposição de atributos desnecessários do modelo.

- `apiexceptionhandler`: um manipulador de exceções global para lidar com as exceções do Spring.
  
- `mapper`: composto de dois sub pacotes: `assembler` responsábel por desempenhar um papel crucial na transformação de objetos de modelo em DTOs (Data Transfer Objects) e `disassembler` responsável pela transformação dos DTOs em objetos de modelo.

  
### Pacote Config

O pacote core é um componente fundamental da aplicação, onde são mantidas as classes de configuração que afetam o comportamento e o funcionamento geral do sistema.

- `ModelMapperConfig`: contém as configurações da biblioteca modelmapper.
  
- `WebSecurityConfig`: contém as configurações de segurança da aplicaç]ao.

### Pacote Domain

- `exception`: define as exceções personalizadas.

- `dto`: neste pacote, são definidos os Data Transfer Objects (DTOs), que servem como estruturas de dados simples para a transferência de informações entre diferentes partes da aplicação. São compostos por dois sub-pacotes:

     - `request`: responsáel por abrigar os dto's de entrada das entidades. 
  
     - `response`: responsável por conter as classes dto's de saída da aplicação.
    
- `model`: onde nossas entidades são definidas, usando anotações JPA (Jacarta) para ORM com nosso banco de dados SQL.
  
- `repository`: neste pacote, tratamos do acesso a dados usando interfaces fornecidas pelo Spring Data JPA.
  
- `service`: onde reside nossa lógica de negócios. Aqui validamos nossos dados, tratamos de exceções de negócios e gerenciamos o acesso ao nosso banco de dados SQL por meio de repositórios.
  
### Pacote security

Esse pacote é responsável por tratar da camada de segurança da aplicação, contendo as classes necessárias para sua implementação.

### `Application.java`
Classe principal para executar nosso projeto. Ele inicializa nosso aplicativo Spring e conecta todos os componentes.


### Pacote test

- `apitest`: contém as classes responsáveis pelos testes de API. É utilizado o banco de dados PostgreSQL para a execução dos testes.
  
- `integracaotest`: contém as classes responsáveis pelos testes de integração.  É utilizado o banco de dados PostgreSQL para a execução dos testes.

- `mockmvc`: contém as classes de testes utilizando o @WebMvcTest para testar a classe controller.

- `util`: Contém as classes utilitárias, que são projetadas para fornecer funcionalidades comuns ou auxiliares que podem ser usadas em toda a aplicação. 

  
## Detalhes do Projeto:

O projeto inclui operações básicas de CRUD seguindo o uso de códigos de status HTTP apropriados. O tratamento de exceções é gerenciado globalmente com um `@ControllerAdvice` para garantir o tratamento consistente de exceções em todo o aplicativo.

O projeto utiliza o banco de dados postgreSQL para ambiente de desenvolvimento.

## Documentação

A documentação da API foi descrita obedecendo a especificação OpenAPI e pode ser encontrada na UI do Swagger. Para visualizá-lo, visite: Swagger UI.: [Swagger UI](http://localhost:8080/swagger-ui.html).

## Postman

Foi utilizado o Postman para  testar as solicitações HTTP, como GET, POST, PUT, DELETE e outros. 
O arquivo da Collection gerenciamento-de-estoque pode ser acessado por meio do link: [gerenciamento-de-estoque](https://github.com/meirelopes/estoque-de-produtos/blob/main/estoque/gerenciamento-de-estoque.postman_collection.json)

## Sugestões

Se você encontrar algum problema ou tiver sugestões de melhorias, não hesite em nos contactar por meio dos e-mails a seguir:
- jucemeire.lopes@zup.com.br
- mateus.damasceno@zup.com.br
- nicoly.vitorio@zup.com.br

## Autores
<table>
  <tr>
    <td align="center"><a href="https://github.com/meirelopes"><img src="https://avatars.githubusercontent.com/u/105396487?v=4" width="100px;" alt=""/><br/><strong>Jucemeire Lopes</strong></a><br/><a href="https://www.linkedin.com/in/jucemeirelopes/">LinkedIn</a></td>
    <td align="center"><a href="https://github.com/mateus-damasceno-zup"><img src="https://avatars.githubusercontent.com/u/105396487?v=4" width="100px;" alt=""/><br/><strong>Mateus Damasceno</strong></a><br/><a href="https://www.linkedin.com/in/jucemeirelopes/">LinkedIn</a></td>
    <td align="center"><a href="https://github.com/NicolyZup"><img src="https://avatars.githubusercontent.com/u/133882322?v=4" width="100px;" alt=""/><br/><strong>Nicoly Barros</strong></a><br/><a href="https://www.linkedin.com/in/nicoly-barros-henrique-vitorio/">LinkedIn</a></td>
       
  </tr>
</table>
</table>




