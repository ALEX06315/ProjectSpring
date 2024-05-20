# ProjectSpring

## Functional Requirements

### Add New Student
- The system must allow the addition of new students with basic details such as first name, last name, date of birth, gender, and contact information.
### Create Medical Record for Student
- For each student, the system must create a medical record that includes essential medical data, medical history, allergies, and vaccinations.
### Manage Doctor Information
- The system must store information about doctors, including first name, last name, specialty, and contact details.
### Record and Manage Visits
- The system must record details of each student's visit to a doctor, including visit date, symptoms, and treatment plans.
### Record Diagnoses and Medications
- Each visit can have one or more diagnoses, which must be recorded with relevant details and prescribed medications.
### Search and View Medical Records
- The system must provide the ability to search for and view students' medical records based on various criteria (e.g., name, student ID).
### Manage Allergies Information
- The system must allow recording and updating of students' allergy information.
### Manage Vaccinations Information
- The system must record data about students' vaccinations, including vaccine name and vaccination date.
### Generate Reports and Analytics
- The system must generate reports and provide analytical information based on stored medical data (e.g., reports on the frequency of specific illnesses among students).
### Access Control and Security
- The system must implement access control mechanisms to ensure that only authorized personnel can access or modify sensitive medical information.

## System Behaviours

1. User Authentication and Authorization
   - Secure Login: Implement a secure login process requiring usernames and strong passwords.
   - Role-Based Access Control: Define roles (e.g., admin, doctor, nurse) with specific permissions.
   - Session Management: Ensure user sessions are securely managed, including automatic logout after inactivity.
2. Data Validation
   - Required Fields: Ensure all required fields are filled before submission.
   - Format Validation: Validate data formats, such as date of birth, contact information, and medical IDs.
   - Logical Consistency: Check for logical consistency, such as future dates for birth dates or visits.
3. Audit Logging
   - Change Tracking: Record details of every change made to the medical records, including what was changed.
   - User Identification: Log the user ID of the person who made the change.
   - Timestamping: Include timestamps for when each change was made.
4. Automated Notifications
   - Visit Reminders: Send notifications for upcoming scheduled visits.
   - Vaccination Alerts: Notify users of upcoming or due vaccinations.
   - Critical Updates: Alert relevant users about critical updates in a student’s medical status.
5. Search Functionality
   - Criteria-Based Search: Allow searches by name, student ID, medical record number, and visit date.
   - Filter Options: Provide filters for refining search results (e.g., date range, doctor).
   - Quick Access: Implement quick access to recently viewed or frequently accessed records.
6. Data Encryption
   - In-Transit Encryption: Use SSL/TLS for encrypting data transmitted over networks.
   - At-Rest Encryption: Encrypt sensitive data stored in the database.
   - Key Management: Implement secure key management practices for encryption keys.
7. Backup and Recovery
   - Regular Backups: Schedule regular backups of the database.
   - Recovery Procedures: Establish and test data recovery procedures to ensure data can be restored in case of loss.
   - Redundancy: Use redundant storage systems to protect against data loss.
8. Scalability
   - Load Balancing: Implement load balancing to distribute user requests and optimize performance.
   - Database Optimization: Optimize database queries and indexing for better performance.
   - Resource Scaling: Allow for scaling of resources (e.g., servers, storage) to handle increased load.
9. User Interface Responsiveness
   - Cross-Device Compatibility: Ensure the UI is responsive and functional on desktops, tablets, and smartphones.
   - Performance Optimization: Optimize UI elements for quick loading and smooth interaction.
   - Accessibility: Design the interface to be accessible to users with disabilities (e.g., screen readers).
10. Compliance with Regulations
    - Data Protection: Ensure the system adheres to data protection laws such as GDPR (General Data Protection Regulation) and HIPAA (Health Insurance Portability 
      and Accountability Act).
    - Consent Management: Implement features to manage user consent for data collection and processing.
    - Regular Audits: Conduct regular audits to ensure ongoing compliance with relevant regulations.

## REST API Endpoints

### User Endpoints
- GET /users: Retrieve a list of all users.
- GET /users/{user_id}: Retrieve a specific user by ID.
- POST /users/register: Register a new user.
- POST /users/login: Authenticate a user.
- PUT /users/{user_id}: Update a user by ID.
- DELETE /users/{user_id}: Delete a user by ID.
### Student Endpoints
- GET /students: Retrieve a list of all students.
- GET /students/{student_id}: Retrieve a specific student by ID.
- POST /students: Add a new student.
- PUT /students/{student_id}: Update a student by ID.
- DELETE /students/{student_id}: Delete a student by ID.
### Visit Endpoints
- GET /students/{student_id}/visits: Retrieve all visits for a specific student.
- GET /visits/{visit_id}: Retrieve a specific visit by ID.
- POST /students/{student_id}/visits: Add a visit to a specific student.
- PUT /visits/{visit_id}: Update a visit by ID.
- DELETE /visits/{visit_id}: Delete a visit by ID.
### Diagnosis Endpoints
- GET /visits/{visit_id}/diagnoses: Retrieve all diagnoses for a specific visit.
- GET /diagnoses/{diagnosis_id}: Retrieve a specific diagnosis by ID.
- POST /visits/{visit_id}/diagnoses: Add a diagnosis to a specific visit.
- PUT /diagnoses/{diagnosis_id}: Update a diagnosis by ID.
- DELETE /diagnoses/{diagnosis_id}: Delete a diagnosis by ID.
### Medication Endpoints
- GET /diagnoses/{diagnosis_id}/medications: Retrieve all medications for a specific diagnosis.
- GET /medications/{medication_id}: Retrieve a specific medication by ID.
- POST /diagnoses/{diagnosis_id}/medications: Add a medication to a specific diagnosis.
- PUT /medications/{medication_id}: Update a medication by ID.
- DELETE /medications/{medication_id}: Delete a medication by ID.
