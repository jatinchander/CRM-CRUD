# CRM-CRUD

Description: Customer Relationship Management Application that allows users to add, update, delete, and view customers in a database.

Utilizes:
1. Spring MVC - For Dependency Injection, as well as following Model-View-Controller design pattern.
2. Hibernate - To interact with the database through the use of ORM: Object-to-Relational Mapping.
3. MySQL - To define and create tables, as well as relationships between these tables.
4. DAO Pattern - Having a helper class to interact with the database.
5. Apache Tomcat -  Server to execute Java servlets and render webpages.

Project Organization: 1. Customer Controller <-> 2. Customer Service <-> 3. Customer DAO <-> 4. Database
                                |
                                v
                      5. JSP Pages
                     
Customer Controller: Contains business logic
  - Request Mappings to different URLs
  - Renders JSP (View)
  - Injects Customer Service class
  - Binds data from form (Model)
  
Customer Service: The purpose of the Service class is to add a layer that integrates from one or more DAO classes.
  - Injects Customer DAO
  
Customer DAO: The purpose of the DAO class is to define methods that will interact with the database.
  - Injects Session Factory to build connection to the database
  - Utilizes HQL: Hibernate Query Language to retrieve java objects, which is ultimately passed to the Customer Controller and displayed by the JSP
  
JSP: The view part of MVC, it is used to render a response to the browser
  - Uses HTML & CSS for front-end

