# Spring MVC and Thymeleaf.

Spring is a Java framework the implements the MVC patter to enable rabid easy development.

Getting started guide: https://spring.io/guides/gs/serving-web-content/
Home: https://spring.io/why-spring


# Thymeleaf 

is a template engine that  makes dynamically inserting data into the html templates simple.

Home: https://www.thymeleaf.org/doc/articles/springmvcaccessdata.html

# @RequestMapping

RequestMapping is for mapping mapping web requests onto request-handling classes and methods.

See https://www.baeldung.com/spring-requestmapping for a overview of how to use this and see: https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/web/bind/annotation/RequestMapping.html for documentation on the expected parameters and their effects.

# JPA

Spring Data JPA is NOT an ORM but creates Data Access Objects at compile that can the used to access the data with a tool such as an ORM.

One of the largest advantages of this is that it will automatically create most of the logic used to save and retrieve information from the database. 

https://spring.io/projects/spring-data-jpa
>As a developer you write your repository interfaces, including custom finder methods, and Spring will provide the implementation automatically.

getting started: https://spring.io/guides/gs/accessing-data-jpa/

# Security

