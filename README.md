# Microsite-Checklist
The purpose of this Readme to is provide guidance on what is needed to create a microsite here at Alaska Airlines.  

This is a living document and will be updated as needed.
Using the provided checklists below can help with accuracy on TShirt sizing of the feature as well as it's related stories.

This document can also be cloned & used to create the necessary documentation to meet your team's Definition of Done (DoD).


## Engineering Assumptions within this Checklist:

1. You are using a microservice architecture
1. You are using a BFF (Backend for Frontend) pattern
1. You are using a Domain Service pattern
1. You are using React for the front end pattern & the Alaska Airlines Design System. It's easily substituted with other Frontend technologies, VueJS, Angular, etc.
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

### Instrumentation / Monitoring
1. Determine what tagging & analytics will be used.
1. Determine tech used for logging. (App Insights, Splunk, Sumo Logic, etc.)
 1. Determine what log queries will be useful to troubleshooting issues when on-call.
 1. Determine what alerts / email notifications will be useful to troubleshooting issues when on-call.
    Ex: 15 errors of type -> 500 or 400 in the last 5 minutes will trigger an email to the on-call team @ this email address.
1. Will it be useful to have a dashboard to monitor the health of the microsite? If so, what will be on it?
    Ex: [MpActivity Dashboard for Sumo Logic](https://service.sumologic.com/ui/#/dashboardv2/cDMSV5Muh9MroKcyvPeYKRi6Xmzr6EuG4FfVBngVmAgFavDIsVpjthdOofBn)

## BFF Checklist
### Necessary Azure Resources:
1. Azure Configuration Service (ACS) or a means of storing configuration settings.
1. Azure Key Vault (KV) or a means of storing secrets.
1. Front door (FD) or a means of routing & load balancing traffic to the BFF.

### Pipeline Checklist:
1. Terraform pipeline - needed to create secrets in ACS & Key Vault.
1. AKS Pipeline needed to deploy the API to the cluster.
1. APIM Pipeline needed to wrap the deployed API in APIM.

### Deployment Checklist
Follow the deployment instructions within your BFF repo. The specifics & general order may differ from the categories listed below:
1. Setup Frontdoor on QA & Prod
1. Deploy API to QA & Prod
1. Verify QA & Prod ACS / KV keys are in place.
1. Create PR to merge develop to main.
1. Create a CR


This is build upon this story as an example: [BFF Story](https://itsals.visualstudio.com/E_Retain_MileagePlan/_workitems/edit/870454)

### Security
Security Diagram on how Token is shared between the UI & BFF here.

### Testing
- [ ] List what testing framework, libraries, etc will be used.

1. [XUnit](https://xunit.net)
1. [Nunit](https://nunit.org)

- [ ] Determine the type of integration testing that will be used.
1. [Postman](https://www.postman.com)
1. [Custom C# e2e, like C# Postman requests]
1. [Microsoft e2e] 

Pros / Cons on the first two options:
- Tests on actual deployed stack on network. This requires providing security tokens in the request header. This is the most accurate, but requires more setup and won't provide direct access to existing internal classes and methods.

Pros / Cons on the third option:
- Tests on in memory endpoint, so no need to configure usage of security tokens. Also, you can naturally reference internal classes and methods. This is the easiest to setup and generate more relevant tests, but does not test the full deployed stack.


### Instrumentation / Monitoring
1. Determine what tagging & analytics will be used.
1. Determine tech used for logging. (App Insights, Splunk, Sumo Logic, etc.)
 1. Determine what log queries will be useful to troubleshooting issues when on-call.
 1. Determine what alerts / email notifications will be useful to troubleshooting issues when on-call.
    Ex: 15 errors of type -> 500 or 400 in the last 5 minutes will trigger an email to the on-call team @ this email address.
1. Will it be useful to have a dashboard to monitor the health of the microsite? If so, what will be on it?
    Ex: [MpActivity Dashboard for Sumo Logic](https://service.sumologic.com/ui/#/dashboardv2/cDMSV5Muh9MroKcyvPeYKRi6Xmzr6EuG4FfVBngVmAgFavDIsVpjthdOofBn)

## Domain Service Checklist
### Security
Security Diagram on how Token is shared between the BFF & Domain Service here.

### Testing
- [ ] List what testing framework, libraries, etc will be used.

1. [XUnit](https://xunit.net)
1. [Nunit](https://nunit.org)

- [ ] Determine the type of integration testing that will be used.
1. [Postman](https://www.postman.com)
1. [Custom C# e2e, like C# Postman requests]
1. [Microsoft e2e] 

Pros / Cons on the first two options:
- Tests on actual deployed stack on network. This requires providing security tokens in the request header. This is the most accurate, but requires more setup and won't provide direct access to existing internal classes and methods.

Pros / Cons on the third option:
- Tests on in memory endpoint, so no need to configure usage of security tokens. Also, you can naturally reference internal classes and methods. This is the easiest to setup and generate more relevant tests, but does not test the full deployed stack.

### Instrumentation / Monitoring
1. Determine what tagging & analytics will be used.
1. Determine tech used for logging. (App Insights, Splunk, Sumo Logic, etc.)
 1. Determine what log queries will be useful to troubleshooting issues when on-call.
 1. Determine what alerts / email notifications will be useful to troubleshooting issues when on-call.
    Ex: 15 errors of type -> 500 or 400 in the last 5 minutes will trigger an email to the on-call team @ this email address.
1. Will it be useful to have a dashboard to monitor the health of the microsite? If so, what will be on it?
    Ex: [MpActivity Dashboard for Sumo Logic](https://service.sumologic.com/ui/#/dashboardv2/cDMSV5Muh9MroKcyvPeYKRi6Xmzr6EuG4FfVBngVmAgFavDIsVpjthdOofBn)