# Technical Notes EasyMED

This is a collection of technical points, open for discussion.

Main technology

- Java
- Angular
- MySQL
- Keycloak or Spring Authorization Server?
- Microservice → API Gateway

External libraries

- Tailwind CSS
- Mapstruct: The mapping will be done at Controller.
- Lombok.
- cz.habarta.typescript-generator? - Generating frontend DTO from Java code.
- hibernate-jpamodelgen

Query

- For simple queries: Use Spring JPA query
- For complex queries: JPACriteria, entity graph
- Use Repository

I18n

- Backend: manually handle.
- Frontend: ngx-translate.

External API

- Follow RESTful conventions: GET, POST, PUT, PATCH, DELETE, ...
- Validate DTO with annotations if possible. Only do manual validation for business if required.

Exception handling:

- All busines exceptions must extends EasyMedBusinessException, which extends Exception.
- Transaction roll back on Throwable.

N+1

- Use fetch mode SubSelect by default.
- Use JPA joinFetch() in query.

Unit test / integration test

- Unit test: Mockito to mock other services, H2 database.
- Integration test: RestAssured, TestContainers.
- Api test: Karate?

Angular

- NgModule (ng generate module) config routing enable lazy loading, disable standalone
- use Resolver to fetch and render data
- isolated module, don’t call, import anything from other module

Git:

- Use strategy: **squash + rebase** instead, push —force to overwrite → caution when merging (make git graph will be clear and reduce detail and conflict by using squash before merge code)
