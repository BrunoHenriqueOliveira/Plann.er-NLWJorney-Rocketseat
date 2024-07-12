# Plann.er-NLWJorney-Rocketseat
 O projeto Journey tem como objetivo ajudar o usuário a organizar viagens à trabalho ou lazer.
 O usuário pode criar uma viagem com nome, data de início e fim. Dentro da viagem o usuário pode planejar sua viagem adicionando atividades para realizar em cada dia.

# Iniciando

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

### Sobreposições do Maven Parent

Devido ao design do Maven, elementos são herdados do POM pai para o POM do projeto.
Embora a maior parte da herança seja adequada, também herda elementos indesejados como <license> e <developers> do pai.
Para evitar isso, o POM do projeto contém sobreposições vazias para esses elementos.
Se você alternar manualmente para um pai diferente e realmente desejar a herança, precisará remover essas sobreposições.

