# Microsite-Checklist
The purpose of this Readme to is provide guidance on what is needed to create a microsite here at Alaska Airlines.  

This is a living document and will be updated as needed.
Using the provided checklists below can help with accuracy on TShirt sizing of the feature as well as it's related stories.

This document can also be cloned & used to create the necessary documentation to meet your team's Definition of Done (DoD).


## Engineering Assumptions within this Checklist:

1. You are using a microservice architecture
1. You are using a BFF (Backend for Frontend) pattern
1. You are using a Domain Service pattern
1. You are using React for the front end patter & the Alaska Airlines Design System.
1. Authentication is handled by AS.com & the token is passed down to the React Microsite which is then passed to the BFF as needed.


## UI Checklist
### UI Designs
1. [Design mockups or prototypes]()
1. [UI Web components being used)]() 
1. [UI Grid / Layout being used)]() 
1. List Any other import design / or front end patterns, libraries, etc. being used

### Security
Security Diagram on how Token is shared between AS.com & the Frontend here.

### Testing
- [ ] List what testing framework, libraries, etc will be used.
1. [Playwright](https://playwright.dev/)
1. [Jest](https://jestjs.io/)

## BFF Checklist
### Security
Security Diagram on how Token is shared between the UI & BFF here.

### Testing
- [ ] List what testing framework, libraries, etc will be used.

1. [XUnit](https://xunit.net)
1. [Nunit](https://nunit.org)

- [ ] Determine the type of integration testing that will be used.
1. [Postman](https://www.postman.com)
1. [Microsoft e2e]
1. [Custom C# e2e, like C# Postman requests] 

## Domain Service Checklist
### Security
Security Diagram on how Token is shared between the BFF & Domain Service here.

### Testing
- [ ] List what testing framework, libraries, etc will be used.
1. [XUnit](https://xunit.net)
1. [Nunit](https://nunit.org)