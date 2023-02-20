# Publicis Sapient- Design for movie ticket booking application
The use case was to build an online movie ticket booking platform that caters to both B2B (theatre partners) and B2C (end customers) clients.
 
Key goals it wants accomplished as part of its solution:
* Enable theatre partners to onboard their theatres over this platform and get access to a bigger customer base while going digital. 
* Enable end customers to browse the platform to get access to movies across different cities, languages, and genres, as well as book tickets in advance with a seamless experience.

## Technology to be Used
* FE Interface: ReactJS & BootStrapJS
* BE language and Framework: Java, Spring Boot
* Security: OATH2
* Database: Oracle
* Server: Tomcat
* Caching: Redis
* Notifications: JMS queue
* Payment API: Paypal/ Stripe
* Deployment: Docker & K8
* Code repository: Git
* Logging: Log4J
* Log Management: ELK Stack
* Load balancer: Cloud provided LB

## Component Diagram
![compoenet_diagram](https://user-images.githubusercontent.com/103522950/220185569-0b46afdc-84b1-43e5-8e31-176499590ce0.jpeg)

## Data Model
![Database ER diagram (Ticket Booking App)](https://user-images.githubusercontent.com/103522950/220183924-ed240f76-6376-402e-bf63-1ffb9a606f51.jpeg)

## Candidate APIs
* getCities()
* getMoviesByCity(CityId)
* getMovieTheatres(MovieId)
* getMovieShowTimes(MovieId, TheatreId)
* getUnbookedSeat(MovieId, TheatreId, ShowtimeId)
* verifyAndbookTempSeat(MovieId, TheatreId, ShowtimeId, Seat, User)
* bookTickets()
* addTheatre()
* add/modify/deleteCapacity()

## High level sequence Diagram for main workflow
![Sequence diagram for Ticket Booking App](https://user-images.githubusercontent.com/103522950/220184709-db68534f-440d-4cca-a2ad-a1306b938959.jpeg)

## Exception Handling and Fault Tolerance
* Exception scenarios are not covered in design. Most situation checked exceptioned will thrown from method level, unknown exception are to be grouped into methodical and structured custom exception. These will be addressed though Spring's controller advice which reads exception and prepare as per response entity.
* Runtime exception to be handled to avoid or to be catched and rethrown wrapping it with custom exception.
* Fault tolerance can be handled in circuit breaker pattern using hystrix framework

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

## Scaling Consideration
In a controlled and clustered environment scaling is taken care by K8 like application. All kind of scaling (horizontal and verticle). service component just need to declare configuration in a deplyment manifest file.


