# Plann.er-NLWJorney-Rocketseat

![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white)

## Descrição:
O projeto Journey é uma API tem como objetivo simplificar o planejamento de viagens, sejam elas de trabalho 
ou lazer. Com o Journey, você pode criar e gerenciar suas viagens de forma organizada e eficiente. Crie 
uma nova viagem, defina as datas de início e término e planeje cada detalhe, incluindo as atividades diárias.

### Funcionalidades:
* **Criar viagem:** Inicie o planejamento de sua próxima aventura criando uma nova viagem.
* **Confirmar a viagem:** Verifique e confirme os detalhes da sua viagem.
* **Convida participante:** Adicione amigos, colegas ou familiares à sua viagem.
* **Confirmar participante:** Confirme a participação dos convidados na viagem.
* **Registrar link:** Adicione links importantes relacionados à viagem, como reservas de hotel ou passagens.
* **Registrar atividade:** Planeje atividades para cada dia da viagem, desde reuniões de trabalho até passeios turísticos.
* **Recuperar detalhes da viagem:** Acesse todas as informações da viagem a qualquer momento.
* **Recupera partivipantes da viagem:** Veja quem está confirmado para participar.
* **Recupera atividades da viagem:** Visualize todas as atividades planejadas.
* **Recupera links da viagem:** Encontre rapidamente os links registrados.
* **Atualização de viagem:** Faça alterações nos detalhes da viagem conforme necessário.

## Estrutura do projeto
````
Plann.er-NLWJorney-Rocketseat/
├── mvnw
├── mvnw.cmd
├── pom.xml
└── src/
    ├── main/
    │   ├── java/
    │   │   └── com.rocketseat.planner/
    │   │       ├── activity
    │   │       │   ├── Activity
    │   │       │   ├── ActivityData
    │   │       │   ├── ActivityRepository
    │   │       │   ├── ActivityRequestPayload
    │   │       │   ├── ActivityResposnse
    │   │       │   └── ActivityService
    │   │       ├── link
    │   │       │   ├── Link
    │   │       │   ├── LinkData
    │   │       │   ├── LinkRepository
    │   │       │   ├── LinkRequestPayload
    │   │       │   ├── LinkResposnse
    │   │       │   └── LinkService
    │   │       ├── partipant
    │   │       │   ├── Partipant
    │   │       │   ├── PartipantController
    │   │       │   ├── PartipantData
    │   │       │   ├── PartipantRepository
    │   │       │   ├── PartipantRequestPayload
    │   │       │   ├── PartipantResposnse
    │   │       │   └── PartipantService
    │   │       ├── trip
    │   │       │   ├── Trip
    │   │       │   ├── TripController
    │   │       │   ├── TripCreateResposinse
    │   │       │   ├── TripRepository
    │   │       │   └── TripRequestPayload
    │   │       └── PlannerApplication
    │   │       
    │   └── resources
    │       ├── application.properties
    │       ├── static
    │       ├── templates
    │       └── db.migration
    │           ├── V1__create-table-trips.sql
    │           ├── V2__create-table-participant.sql
    │           ├── V3__create-table-activities.sql
    │           └── V4__create-table-links.sql
    └── test
````

## Instalação:

````bash
  git clone https://github.com/BrunoHenriqueOliveira/Plann.er-NLWJorney-Rocketseat.git
````

## API Endpoints
Utilizando um programa para realizar chamadas para os endpoint, como o [Insomnia](https://insomnia.rest/download) ou o [Postman](https://www.postman.com/).
No exemplo a seguir tera o link da requisição com o json de uma viagem

### Criação de viagem:
```markdown
POST localhost:8080/trips
```
````json
{
  "destination": "Brasil Game Show (BGS), SP",
  "starts_at": "2024-10-11T10:00:00",
  "ends_at": "2024-10-13T20:00:00",
  "emails_to_invite": ["perna.longa@gmail.com","doom.guy@gmail.com"],
  "owner_name": "Bruno Henrique",
  "owner_email": "bruno.henrique@gmail.com"
}
````
**Retorno da requisição com o UUID da viagem**
````json
{
  "tripId": "{UUID da viagem}"
}
````

### Confirma viagem:
```markdown
GET localhost:8080/trips/{UUID da viagem}/confirm
```
**Retorno da requisição com o UUID da viagem**
````json
{
  "id": "{UUID}",
  "destination": "Brasil Game Show (BGS), São Paulo, SP",
  "startsAt": "2024-10-11T10:00:00",
  "endsAt": "2024-10-13T20:00:00",
  "isConfirmed": true,
  "ownerName": "Bruno Henrique",
  "ownerEmail": "bruno.henrique@gmail.com"
}
````

### Convida Participante
````markdown
POST localhost:8080/trips/{UUID da viagem}/invite
````
````json
{
  "email": "batman@gmail.com"
}
````
**Retorno com a UUID do convidado**
````json
{
  "id": "{UUID do viajante}"
}
````

### Confirma Participante
````markdown
POST localhost:8080/participants/{UUID do viajante}/confirm
````
````json
{
  "name": "Bruce Waine"
}
````

### Registrar link
````markdown
POST localhost:8080/trips/{UUID da viagem}/links
````
````json
{
  "title": "Busão da BGS",
  "url": "https://www.brasilgameshow.com.br/"
}
````

### Registrar atividade
````markdown
POST localhost:8080/trips/{UUID da viagem}/activities
````
````json
{
  "title": "Visita ao concurso de cosplays",
  "occurs_at": "2024-10-11T14:00:00"
}
````

### Recuperar detalhes da viagem
````markdown
GET localhost:8080/trips/{UUID da viagem}
````

### Recupera partivipantes da viagem
````markdown
GET localhost:8080/{UUID da viagem}/participants
````

### Recupera atividades da viagem
````markdown
GET localhost:8080/trips/{UUID da viagem}/activities
````

### Recupera links da viagem
````markdown
GET localhost:8080/trips/{UUID da viagem}/links
````

### Atualização de viagem
````markdown
PUT localhost:8080/trips/2{UUID da viagem}
````
````json
{
  "destination": "Comic Con Experience (CCXP), SP",
  "starts_at": "2024-12-07T10:00:00",
  "ends_at": "2024-12-08T20:00:00"
}
````

## Licença:

* Este projeto é licenciado sob a MIT License.

## Autores:

* Bruno Henrique

## Agradecimentos:
Esse projeto foi desenvolvido durante a NLW da [Rocketseat](https://www.rocketseat.com.br/) com a tutoria da [Fernanda Kepper](https://github.com/Fernanda-Kipper)

### Documentação de referencia
Para referência futura, considere as seguintes seções.

* [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)
* [Spring Boot Maven Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/3.3.1/maven-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/3.3.1/maven-plugin/reference/html/#build-image)
* [Spring Web](https://docs.spring.io/spring-boot/docs/3.3.1/reference/htmlsingle/index.html#web)
* [Flyway Migration](https://docs.spring.io/spring-boot/docs/3.3.1/reference/htmlsingle/index.html#howto.data-initialization.migration-tool.flyway)
* [Spring Boot DevTools](https://docs.spring.io/spring-boot/docs/3.3.1/reference/htmlsingle/index.html#using.devtools)
* [Spring Data JPA](https://docs.spring.io/spring-boot/docs/3.3.1/reference/htmlsingle/index.html#data.sql.jpa-and-spring-data)

### Guias
Os guias a seguir ilustram como usar algumas funcionalidades de forma concreta:

* [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)
* [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/)
* [Building REST services with Spring](https://spring.io/guides/tutorials/rest/)
* [Accessing Data with JPA](https://spring.io/guides/gs/accessing-data-jpa/)