This Spring Boot application uses both MVC and REST controllers. Thymeleaf templates are used for the Admin and Doctor dashboards, while REST APIs serve all other modules.

The application interacts with two databases: MySQL (for patient, doctor, appointment, and admin data) and MongoDB (for prescriptions). All controllers route requests through a common service layer, which directs them to the appropriate repositories. MySQL uses JPA entities, while MongoDB uses document models.

Data Flow:

1. The AdminDashboard and DoctorDashboard use Thymeleaf controllers.

2. REST modules, such as Appointments (which use JSON APIs), PatientDashboards, and PatientRecords, interact with REST controllers.

3. Both Thymeleaf controllers and REST controllers call the service layer.

4. The service layer uses two types of repositories: MySQL repositories and MongoDB repositories.

5. The MySQL repositories access the MySQL database, which stores data for MySQL modules.

6. MySQL modules include Patient, Doctor, Appointment, and Admin, all of which are JPA entities.

7. The MongoDB repository accesses the MongoDB database and interacts with the MongoDB model, which stores prescriptions as documents.