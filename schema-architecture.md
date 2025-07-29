This Spring Boot application uses both MVC and REST controllers, Thymeleaf templates are used for the Admin and Doctor dashboards,  while REST APIs serve all other modules.

The application interactes with two databases, MySQL (for patient, doctor, appointment and admin data) and MongoDB ( for prescription). All controllers route requests through a common service layer, which routs to the corect repos, MySQL uses JPA entities while MongoDB uses document models.

Data flow:

1. The dashboards that ahve AdminDashboard and DoctorDashboard interact/uses Thymeleaf controllers.

2. REST modules such as Appointments that uses JSON API, PatientDashboards and PatientRecords interact with REST controllers.

3. Both Thymeleaf Controllers and REST controllers calls the service layer.

4. The service layer uses two dbs (MySQL repositories and MongoDB repositories) 

5. The MySQL repo have access to MySQL Database which interacts with MySQL modules.

6. MySQL modules contain Patient,Doctor,Appointment, and Admin that are JPA entities.

7. THe MongoDB repo have access to MongoDB database, and interacts with MongoDB model that hold prescriptions as document.