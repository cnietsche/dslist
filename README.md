# DSList - Java Spring

Immersion follow-up project presented by devsuperior: https://github.com/devsuperior/dslist-backend

## Notes
### Day 1

**1. Create the init project**

&emsp;Created the springboot project from https://start.spring.io/ using the following dependencies:
- Spring Web
- H2 Database
- PostgreSQL Driver
- Spring Data JPA

&emsp;Extra:

&emsp;Added the following plugin to the **pom.xml** config:
```xml
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-resources-plugin</artifactId>
	<version>3.1.0</version> <!--$NO-MVN-MAN-VER$ -->
</plugin>
```

**2. Entity (ORM) - Game.java**

&emsp;The entity that connects to the respective DB (persistence).

&emsp;PS1: The **shortDescription** and **longDescription** attributes are long texts, so the **TEXT** definition was informed.

&emsp;PS2: The **year** attribute was named as **game_year** in its DB column.

**3. Properties configuration**

&emsp;Configured the following .properties files:
- application.properties

- application-test.properties

**H2 Connection**

| Property | Value |
| ----- | ----- |
| name | testdb |
| username | sa |
| password | |

**4. Seed - import.sql**

&emsp;Seed file that is automatically run in the Spring startup.

**5. Repository - GameRepository.java**

&emsp;The **Game** entity repository to allow obtaining records from the DB.

**6. Service - GameService.java**

&emsp;The service to allow handling the business rule from the **Game** entity.

**7. Controller - GameController**

&emsp;The controller class where the program will receive the request from another API (endpoints).

**8. DTO - GameMinDTO.java**

&emsp;A DTO file for the **Game** entity to allow the service and controller to find the game records in a restricted model (the **findAll** method will only return some of the table fields).

### Day 2

**1. Domain model**

&emsp;Created the entities **Belonging.java** and **GameList.java**.

&emsp;Created the PK through the **BelongingPK.java** class, generating the relationship between the entities.

**2. Find game by ID**

&emsp;New endpoint create to make possible to get a game by its Id code.

**3. GameList: Repository, Service, Controller and DTO**

&emsp;Created the REST Controller for the GameList entity and created the Service and Repository for it.

**4. Custom QUERY for the GameRepository.java**

&emsp;Created a custom query that obtains the games from a list Id code.

&emsp;Created a projection from the query.

&emsp;Created the method at the **GameService.java** class that runs the query.

&emsp;Added a new endpoint at the **GameListController.java** that executes the new method declared at the **GameService.java** class.
