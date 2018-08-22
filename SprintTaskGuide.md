# Task Creation Guide

## Backend Service 
	
- Service calls
  - Controller/Action
  - Service that gets called by the Controller Action
  - Any new repositories/changes, repository methods
- New Services
  - Generate and Add api-key for new service where required
  - Add api-key middleware to service
  - Add new key to and other services it needs to use
  - Create database for new service
  - Upload data to database for new service
  - Unit Tests
    - Most important unit tests for the service layer
    - Repository tests if there is complicated logic inside the repo
    - Business layer should have tests 
    - Controller you can test, but only if it makes sense, you could always use postman 


## Client Application
- New Client Application
  - Create components/pages for views
  - Create controllers/data controllers
  - Create any frontend Services
  - Generate and store api-key for client 
  - Create any backend services that need called by the datacontroller(s)/controllers
  - Unit Tests
    - Angular/Frontend portion
      - Write unit tests in jasmine run by the karma test runner
      - Test your component code, and any service code
      - Pretty much test anything .TS, as long as there are testable pieces in it
    - Backend/Data Controllers
      - Test any services/code that require testing
