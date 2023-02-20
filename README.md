# Publicis Sapient- Design for movie ticket booking application
The use case was to build an online movie ticket booking platform that caters to both B2B (theatre partners) and B2C (end customers) clients.
 
Key goals it wants accomplished as part of its solution:
* Enable theatre partners to onboard their theatres over this platform and get access to a bigger customer base while going digital. 
* Enable end customers to browse the platform to get access to movies across different cities, languages, and genres, as well as book tickets in advance with a seamless experience.

## Component Diagram
![compoenet_diagram](https://user-images.githubusercontent.com/103522950/220185569-0b46afdc-84b1-43e5-8e31-176499590ce0.jpeg)

## Data Model
![Database ER diagram (Ticket Booking App)](https://user-images.githubusercontent.com/103522950/220183924-ed240f76-6376-402e-bf63-1ffb9a606f51.jpeg)

## High level sequence Diagram for main workflow
![Sequence diagram for Ticket Booking App](https://user-images.githubusercontent.com/103522950/220184709-db68534f-440d-4cca-a2ad-a1306b938959.jpeg)

## Security Consideration
For end user OATH along with OIDC compliance can be used. Authentication can federated to any public provider like Google / Facebook on top of self registration. Did not show this as part of design but can be discussed in more detail.
### Prevention against OWASP Top 10
* Injection - Using parameterized queries when coding and segregating commands from data
* Broken Authentication - use MFA, send passwords over encrypted connections
* Sensitive Data Exposure - secure URL’s, encrypting all sensitive information before storing
* XML External Entities (XXE) - use JSON, SAST tools
* Broken Access Controls - delete unused accounts/user, use penetration testing
* Security Misconfiguration - use Dynamic application security testing (DAST), disable use of default passwords
* Cross-Site Scripting (XSS) - use proper response headers, filtering iput / encoding the output, using the content security policy
* Insecure Deserialization - implementing digital signatures, using penetration testing
* Using Components with known vulnerabilities - removing all unnecessary dependencies, using components only from official and verified sources
* Insufficient Logging and Monitoring - implement logging and audit software (ELK), establishing an effective monitoring system (Grafana)

## Exception Handling
