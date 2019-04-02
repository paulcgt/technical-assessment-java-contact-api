# Java Developer Assessment - ContactAPI

## Brief
You should develop a RESTful API to manage a list of contacts. Your API should fully implement the accompanying Swagger/OpenAPI contract provided in JSON and YAML format, ContactAPI.json and ContactAPI.yml.

The API should allow a client application to add, update, delete, and view contacts. The client application should be able to use the API to search for contacts, and should return contacts in ascending order using a pagination setting defaulted to 5 records.

Your API should use common REST standards and should use JSON as its data format.

## Specifics
Your RESTful API should be developed in Java using SpringBoot 2 or greater. You may use EJB if you’re not familiar with Spring, but then ensure that you provide us with the application server if necessary.

Your application should use an in-memory database such as H2, and use JPA to access the data. We expect to see a full suite of unit tests that achieve a high degree of code coverage and test your solution appropriately.

It should be easy for us to run your API and test it using Postman. You should provide us with the source code, including a readme.md file that describes the application and contains instructions on how to run/deploy the application. 

Save for Maven dependencies, any other external dependencies such as an application server should be supplied if required. 

Please ensure that it’s easy to run/deploy your application as we cannot allocate a lot of time to troubleshooting.

## Deliverables
1.	A Maven or Gradle Java project with all source code. You may provide your application source in one zip file, or on a public repo such as Github or Bitbucket.
2.	A readme.md file containing steps to build and deploy. You can optionally provide us with a Docker image that we can pull from Docker Hub.
3.	If your application requires pre-populated static data, then provide a way to easily populate the database.

## BDD Feature

```feature
Feature: Contact List Management

As an API client application I want to manage contact records in a contacts list.

  Scenario: Add a contact
    When a Contact is received
    Then the contact is saved to the database
    And the saved Contact is returned

  Scenario: Update a contact
    Given a contact already exists
    When new contact information is supplied
    Then the existing Contact is updated
	
  Scenario: Retrieve a single contact
    Given a contact already exists
    When a contractId is provided
    Then the Contact is return

  Scenario: Retrieve a contacts by first name
    When a client provides a first name
    Then zero or more Contacts who’s first name partially matches the supplied first name are returned.
	
  Scenario: Delete a contact that exists
    Given a contact exists
    When a client deletes a contact with a specific contactId
    Then the contact is deleted
```