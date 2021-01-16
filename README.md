> <h1>Algaworks - Curso Spring REST para Iniciantes</h1>
<p align="center">De 11/01 à 15/01/2021</p> 1 hora 08 minutos 13 segundos de video
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
- [JDK11]('https://www.oracle.com/br/java/technologies/javase-jdk11-downloads.html')
- [STS - Spring Tools Suite]('https://spring.io/tools')
- [Postman]('https://www.postman.com/downloads/')
- [MySQL]('https://www.mysql.com/')
- [Git]('https://git-scm.com/downloads')

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
