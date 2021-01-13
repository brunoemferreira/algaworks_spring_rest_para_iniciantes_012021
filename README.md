> <h1>Algaworks - Curso Spring REST para Iniciantes</h1>
<p align="center">De 11/01 à 15/01/2021</p>
<p align="center">Em desenvolvimento : Aula 02 Terminada</p>
<!-- ************************************* Baadges ********************************************* -->
<p align="center">
  <img alt="GitHub language count" src="https://img.shields.io/github/languages/count/brunoemferreira/algaworks_spring_rest_para_iniciantes_012021?color=%2304D361">

 <img alt="Repository size" src="https://img.shields.io/github/repo-size/brunoemferreira/algaworks_spring_rest_para_iniciantes_012021">

  <a href="https://github.com/tgmarinho/nlw1/commits/master">
    <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/brunoemferreira/algaworks_spring_rest_para_iniciantes_012021">
  </a>
</p>

<!-- ************************************* Sobre *********************************************** -->
> <h2>🚀 Sobre o Projeto</h2>
<p>O Projeto criado é uma API simples de ordens de serviço </p>

 <!-- ************************************* Diagrama de Classes ********************************** -->
> <h2 id="diagramadeclasses"> 🗺️ Diagrama de Classes do Projeto</h2>

<h1 align="center">
    <img alt="Logo" src="./images/diagrama.png" width="600px" />
</h1>

<!-- ***************** Tecnologias e Ferramentas *********************************************** -->
> <h2>🛠️ Ferramentas</h2>
* STS ( Spring Tools Suite )
* PostMan

> <h2>Linguagem e Dependências</h2>
* Java11
  * Spring Boot Starter Web
  * Spring Boot Starter Test
  * Spring Boot Starter JPA ( Spring Data JPA é uma biblioteca que ajuda criar repositórios com o Jakarta Persistence ) 
  * Spring Boot DevTools
  * MySql Connector Java
  * FlyWay

> <h2>🎲 Banco de Dados</h2>
* MySQL


Observações : 
 Repositório : é uma Classe que tem responsabilidade de implementar métodos que fazem as operações de persistência de dados;




















<p align="center">
  <a href="#sobre">Sobre o Projeto</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#diagramadeclasses">Diagrama de Classes do Projeto</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#padraocamadasadotado">Padrão de camadas adotado</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#ferramentas">Ferramentas Utilizadas</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#api">Back end</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#database">Banco de Dados</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
</p>

<!-- ********************************* Padrões de Camadas ************************************** -->
<h2 id="padraocamadasadotado"> 🛡️ Padrão de camadas adotado</h2>

<h1 align="center">
    <img alt="Logo" src="./images/camadas.png" width="900px" />
</h1>
<!-- ************************************* Ferramentas Utilizadas ************************** -->
<h2 id="ferramentas"> 🛠️ Ferramentas Utilizadas</h2>

- [JDK11]('https://www.oracle.com/br/java/technologies/javase-jdk11-downloads.html')
- [STS - Spring Tools Suite]('https://spring.io/tools')
- [Postman]('https://www.postman.com/downloads/')
- [Postgres 12 e pgAdmin]('https://www.postgresql.org/download/')
- [Heroku CLI]('https://devcenter.heroku.com/articles/heroku-cli')
- [Git]('https://git-scm.com/downloads')

<hr>

<!-- *********************************** Imagens do Projeto ************************************ -->
<h2 id="padraocamadasadotado"> 🖼️ Imagens do Projeto </h2>
</br>
<h2 align="center">Imagens Front-end WEB</h2>
</br>
<h1 align="center">
    <img alt="Logo" src="./images/front1.png" width="600px" />
    <img alt="Logo" src="./images/front2.png" width="600px" />
    <img alt="Logo" src="./images/front3.png" width="600px" />
</h1>
</br>

<!-- ************************************* Back End ******************************************** -->
<h2 id="backend"> 🧰 API </h2>

<h4> 🔨 Tecnologias</h4>

* Java
* PostGreSQL ( Banco de Dados de Produção )
* H2 ( Banco de Dados de Testes )

<h4> ⚙️ Dependências</h4> 

* Spring Boot
  * Starter Web 
  * Starter Data JPA ( Mapemaneto Objeto Relacional )
  * Starter Validation
  * Starter Security
  * Starter Test
* H2 ( Banco de Dados em memória. Usado nos testes da aplicação )
* PostGreSQL 

<h4 style="font-weight:bold"> ⚙️ Arquivos de Configuração</h4> 

Arquivo                      | Tipo de Configuração
---------------------------  | ------
application.properties       | Configurações Gerais
application-test.properties  | Configurações para Testes
application-dev.properties   | Configurações para Desenvolvimento
application-prod.properties  | Configurações para Produção

</br>
<h4> ⚙️ Local dos Arquivos de Configuração</h4>

- Controller : São Classes reponsáveis por receber as requisições externas http e responder.
- Model : 

```bash
# Local dos arquivos 
|- /osworks-api
  |- src/main/resources
    |- application.properties
    |- application-test.properties
    |- application-dev.properties
    |- application-prod.properties
```    

<h2>application.properties</h2>

```properties
# Seta o profile que ficará ativo
spring.profile.active=test    

# Restringe o uso do jpa até a camada de serviço não podendo ser usado para acesso aos dados
# na camada de controladores REST
spring.jpa.open-in-view=false
```

<h2>application-test.properties</h2>

```properties
# Caminho para conexão com o banco de testes
spring.datasource.url=jdbc:h2:mem:testdb 

# usuario do banco de testes
spring.datasource.username= <informar_usuario> 

# senha do banco de testes
spring.datasource.password= <informar_senha> 
```

<h2>application-dev.properties</h2>

```properties
# Rotinas comentadas são para gerar o script de criação do Banco de Dados
#spring.jpa.properties.javax.persistence.schema-generation.create-source=metadata
#spring.jpa.properties.javax.persistence.schema-generation.scripts.action=create
#spring.jpa.properties.javax.persistence.schema-generation.scripts.create-target=create.sql
#spring.jpa.properties.hibernate.hbm2ddl.delimiter=;

spring.datasource.url=jdbc:postgresql://localhost:5432/dsdeliver
spring.datasource.username=postgres
spring.datasource.password=1234567

spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation=true
spring.jpa.hibernate.ddl-auto=none

```

<h2>application-prod.properties</h2>

```properties
# Caminho da Base de Dados de Produção
spring.datasource.url=${DATABASE_URL}
```
</br>
<h2 style="font-weight:bold"> 🔚 End Points da API</h2> 

<h3 style="font-weight:bold"> API de Clientes </h3>

| Route             | Response Formats | Resource URL                                 |  Parameters |
|-------------------|------------------|----------------------------------------------|-------------|
| GET  /clientes    | JSON             | http://localhost:8080/clientes               | None        |

</br>

| Route             | Description                                                                    |
|-------------------|--------------------------------------------------------------------------------|
| GET  /clientes    | Retorna uma lista de todos os Clientes                                         |

</br>
<h3 style="font-weight:bold">Ordens de Serviço</h3>

| Route             | Response Formats | Resource URL                                 |  Parameters |
|-------------------|------------------|----------------------------------------------|-------------|
| GET  /orders      | JSON             | http://localhost:8080/orders                 | None        |
| POST /orders      | JSON             | http://localhost:8080/orders                 | JSON Body   |
| PUT  /orders      | JSON             | http://localhost:8080/orders/{id}/delivered  | Id Order    |

</br>

| Route             | Description                                                                   |
|-------------------|---------------|
| GET  /orders      | Retorna todos os Pedidos de status 'PENDING' juntamente com os produtos em ordem Ascendente |
| POST /orders      | Efetua a gravação do Pedido no Banco de Dados juntamente com os Produtos selecionados |
| PUT  /orders      | Atualiza o status do Pedido para 'DELIVERED'               |

</br>
<h3 style="font-weight:bold">POST /orders ( Formato de envio do Pedido )</h3>

```json
{
    "address": "Avenida Paulista, 1500",
    "latitude": -23.56168,
    "longitude": -46.656139,
    "products": [
        {
            "id": 2
        },
        {
             "id": 5
        }
     ]
}
```

</br>
<h3> 🎲 Rodando a API</h3>

```bash
# Clone este repositório
$ git clone https://github.com/brunoemferreira/algaworks_spring_rest_para_iniciantes_012021.git

# Acesse a pasta backend
$ cd osworks-api

# execute o comando
$ yarn start
ou
$ npm start

# O servidor inciará na porta:3000
```

<hr>
<h2 id="database"> 🗄️ Banco de Dados de Testes ( H2 )</h2>

```
// Após Rodar o Backend com profile de testes este é o endereço de acesso a interface do Banco

http://localhost:8080/h2-console

```

<hr>
<h2 id="database"> 🗄️ Banco de Dados Produção ( PostgreSQL )</h2>

<h4> 🔨 Scripts para Popular as Tabelas </h4>

```sql
INSERT INTO tb_product (name, price, image_Uri, description) VALUES ('Pizza Bacon', 49.9, 'https://raw.githubusercontent.com/devsuperior/sds2/master/assets/pizza_bacon.jpg', 'Pizza de bacon com mussarela, orégano, molho especial e tempero da casa.');
INSERT INTO tb_product (name, price, image_Uri, description) VALUES ('Pizza Moda da Casa', 59.9, 'https://raw.githubusercontent.com/devsuperior/sds2/master/assets/pizza_moda.jpg', 'Pizza à moda da casa, com molho especial e todos ingredientes básicos, e queijo à sua escolha.');
INSERT INTO tb_product (name, price, image_Uri, description) VALUES ('Pizza Portuguesa', 45.0, 'https://raw.githubusercontent.com/devsuperior/sds2/master/assets/pizza_portuguesa.jpg', 'Pizza Portuguesa com molho especial, mussarela, presunto, ovos e especiarias.');
INSERT INTO tb_product (name, price, image_Uri, description) VALUES ('Risoto de Carne', 52.0, 'https://raw.githubusercontent.com/devsuperior/sds2/master/assets/risoto_carne.jpg', 'Risoto de carne com especiarias e um delicioso molho de acompanhamento.');
INSERT INTO tb_product (name, price, image_Uri, description) VALUES ('Risoto Funghi', 59.95, 'https://raw.githubusercontent.com/devsuperior/sds2/master/assets/risoto_funghi.jpg', 'Risoto Funghi feito com ingredientes finos e o toque especial do chef.');
INSERT INTO tb_product (name, price, image_Uri, description) VALUES ('Macarrão Espaguete', 35.9, 'https://raw.githubusercontent.com/devsuperior/sds2/master/assets/macarrao_espaguete.jpg', 'Macarrão fresco espaguete com molho especial e tempero da casa.');
INSERT INTO tb_product (name, price, image_Uri, description) VALUES ('Macarrão Fusili', 38.0, 'https://raw.githubusercontent.com/devsuperior/sds2/master/assets/macarrao_fusili.jpg', 'Macarrão fusili com toque do chef e especiarias.');
INSERT INTO tb_product (name, price, image_Uri, description) VALUES ('Macarrão Penne', 37.9, 'https://raw.githubusercontent.com/devsuperior/sds2/master/assets/macarrao_penne.jpg', 'Macarrão penne fresco ao dente com tempero especial.');

INSERT INTO tb_order (status, latitude, longitude, address, moment) VALUES (0, -23.561680, -46.656139, 'Avenida Paulista, 1500', TIMESTAMP WITH TIME ZONE '2021-01-01T10:00:00Z');
INSERT INTO tb_order (status, latitude, longitude, address, moment) VALUES (1, -22.946779, -43.217753, 'Avenida Paulista, 1500', TIMESTAMP WITH TIME ZONE '2021-01-01T15:00:00Z');
INSERT INTO tb_order (status, latitude, longitude, address, moment) VALUES (0, -25.439787, -49.237759, 'Avenida Paulista, 1500', TIMESTAMP WITH TIME ZONE '2021-01-01T16:00:00Z');
INSERT INTO tb_order (status, latitude, longitude, address, moment) VALUES (0, -23.561680, -46.656139, 'Avenida Paulista, 1500', TIMESTAMP WITH TIME ZONE '2021-01-01T12:00:00Z');
INSERT INTO tb_order (status, latitude, longitude, address, moment) VALUES (1, -23.561680, -46.656139, 'Avenida Paulista, 1500', TIMESTAMP WITH TIME ZONE '2021-01-01T08:00:00Z');
INSERT INTO tb_order (status, latitude, longitude, address, moment) VALUES (0, -23.561680, -46.656139, 'Avenida Paulista, 1500', TIMESTAMP WITH TIME ZONE '2021-01-01T14:00:00Z');
INSERT INTO tb_order (status, latitude, longitude, address, moment) VALUES (0, -23.561680, -46.656139, 'Avenida Paulista, 1500', TIMESTAMP WITH TIME ZONE '2021-01-01T09:00:00Z');

INSERT INTO tb_order_product (order_id, product_id) VALUES (1 , 1);
INSERT INTO tb_order_product (order_id, product_id) VALUES (1 , 4);
INSERT INTO tb_order_product (order_id, product_id) VALUES (2 , 2);
INSERT INTO tb_order_product (order_id, product_id) VALUES (2 , 5);
INSERT INTO tb_order_product (order_id, product_id) VALUES (2 , 8);
INSERT INTO tb_order_product (order_id, product_id) VALUES (3 , 3);
INSERT INTO tb_order_product (order_id, product_id) VALUES (3 , 4);
INSERT INTO tb_order_product (order_id, product_id) VALUES (4 , 2);
INSERT INTO tb_order_product (order_id, product_id) VALUES (4 , 6);
INSERT INTO tb_order_product (order_id, product_id) VALUES (5 , 4);
INSERT INTO tb_order_product (order_id, product_id) VALUES (5 , 6);
INSERT INTO tb_order_product (order_id, product_id) VALUES (6 , 5);
INSERT INTO tb_order_product (order_id, product_id) VALUES (6 , 1);
INSERT INTO tb_order_product (order_id, product_id) VALUES (7 , 7);
INSERT INTO tb_order_product (order_id, product_id) VALUES (7 , 5);
```



