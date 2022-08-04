# desafio_Microsserviços
#### Exercício assunto Microsserviços.


A ideia é continuar trabalhando com o Total Shake, e vamos utilizar um tipo de arquitetura de microsserviços em que o Total Shake era um monolito e decidimos quebrar a aplicação em parte e transformá-la em microsserviço.

Para iniciar um projeto usando o Spring, vou usar o site padrão "start.spring.io", esse é o Spring Initializr que facilita para começarmos o projeto do zero.

Vamos escolher que é um projeto que vai utilizar o Maven, logo vamos selecionar a opção "Maven Project" em "Project" para controlar as dependências e como ferramenta de build.

Então vamos ter dois microsserviços: um de pedido e outro de
pagamento, cada um com seu banco de dados e vamos simular a nossa
aplicação na prática. Então façam um CRUD para cada um dos microsserviços, estruturando-os no padrão camada MVC. Crie os pacotes controller, model, repository, e service e dto. Utilize o padrão DTO (data transfer object) no projeto para expormos somente os atributos desejados na aplicação.

Crie as APIs dos microsserviços do zero, ou reaproveite o que for possível do material dos desafios anteriores refatorando quando necessário. Vamos usar as migrations para criar as tabelas no banco de dados para  o versionamento.

Adicione as dependências que vamos precisar para o projeto. Vamos usar estas, e mais as que o desafiado julgar necessárias: 

- Spring Web
- Spring Data JPA
- Dependência para o banco de dados para o banco de sua preferência
- Spring Boot DevTools
- Lombok
- Validation
- Flyway Migration
- Feign

## API Pedidos:

### Classe Pedido

- private Long id (Chave primária, autogerada);
- private LocalDateTime dataHora;
- private Status status;
- List<ItemDoPedido> itens.


### Enum Status

- REALIZADO;
- CANCELADO;
- PAGO;
- NAO_AUTORIZADO;
- CONFIRMADO;
- PRONTO;
- SAIU_PARA_ENTREGA;
- ENTREGUE.

### Classe Item do Pedido

- private Long id (Chave primária, autogerada);
- private Integer quantidade;
- private String descricao;
- private Pedido pedido.


## API Pagamentos:

### Classe Pagamento

- private Long id (Chave primária, autogerada);
- private BigDecimal valor;
- private String nome;
- private String numero;
- private String expiracao;
- private String codigo;
- private Status status;
- private Long pedidoId;
- private FormaDePagamento formaDePagamento; 

### Enum Status

- CRIADO;
- CONFIRMADO;
- CANCELADO;
  
### Enum FormaDePagamento

- PIX;
- DINHEIRO;
- CARTAO_DEBITO;
- CARTAO_CREDITO.  

### Conteúdo Auxiliar

Abaixo estão links de apoio que poderão auxiliar na resolução do desafio.

| Assunto | Link |
| ------ | ------ |
| Microsserviços | [https://www.opus-software.com.br/os-beneficios-da-arquitetura-de-micro-servicos/] |
| Spring Boot | [https://www.devmedia.com.br/primeiros-passos-com-o-spring-boot/33654#Spring] |
| Spring Boot | [https://www.youtube.com/watch?v=JLShKaS0XxY] |
| Spring Initializr | [https://start.spring.io/] |
| API RESTful | [https://mari-azevedo.medium.com/construindo-uma-api-restful-com-java-e-spring-framework-46b74371d107] |
| Boas práticas Rest | [https://www.youtube.com/watch?v=P-juXKmJy_g] |
| Migrations | [https://www.youtube.com/results?search_query=migration+java] |
| Discovery | [https://www.youtube.com/watch?v=Td_6NcZJ4WM] |
| Discovery | [https://4soft.co/tutorial-how-to-implement-service-discovery-with-eureka-java/] |
| Feign | [https://domineospring.wordpress.com/2017/06/02/feign-uma-forma-simples-para-consumir-servicos/] |
| Feign | [https://www.youtube.com/watch?v=zRZuZrwYYc0] |
| ModelMapper | [https://www.youtube.com/watch?v=HU7bfKG8nV4] |
| ModelMapper| [https://medium.com/@hectordemedeiros/criando-uma-api-rest-em-springboot-utilizando-modelmapper-b56515c62e84] |

