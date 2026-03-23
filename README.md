Sprint 3 Report – StudyBuddy
1. Introduction

Sprint 3 marks the beginning of the development phase of the StudyBuddy project. In the previous sprint, we focused on planning and design, but in this sprint we started building the actual application. The aim was to implement core features and connect the frontend, backend, and database together using the technologies introduced in the module.

2. Sprint 3 Objectives

The main objectives of this sprint were:

To set up the backend using Express.js
To connect the application to a MySQL database
To create dynamic pages using PUG
To populate the database with sample data
To ensure all group members contributed to the code
To run the application using Docker
3. User Stories Implemented

In this sprint, we focused on implementing a small number of core user stories from Sprint 2.

User 1 – Register Account
Users are able to register by entering their name, email, and password. The data is stored securely in the database.

User 2 – Login
Users can log into the system using their email and password. The system checks the credentials and either allows access or shows an error message.

User 3 – Create Profile
Users can create a profile where they can add their course, subjects, and a short description about their skills.

User 5 – Search by Subject
Users can search for other students based on subjects. The system returns matching results from the database.

4. System Implementation

Backend Development
The backend was developed using Node.js and Express.js. Different routes were created for handling user registration, login, profile creation, and search functionality. The backend also handles communication with the database.

Frontend Development
The frontend was created using PUG templates. These templates allow us to display dynamic data from the database instead of static content. Pages such as user lists and profiles are rendered using data passed from the backend.

Database Integration
MySQL was used as the database. The application is connected to the database and can store and retrieve user data, profiles, and subjects.

5. Database Design

The database was designed to support the main features of the application.

Tables used:

Users (id, name, email, password)
Profiles (id, user_id, course, subjects, description)
Subjects (id, subject_name)

Relationships:

Each user has one profile (one-to-one relationship)
Profiles are linked to subjects
6. Features Developed

During this sprint, we implemented the following dynamic pages:

Users List Page
Displays all users stored in the database
User Profile Page
Shows detailed information about a specific user
Listing Page
Displays available study support listings
Detail Page
Shows full details of a selected listing
Tags / Categories
Subjects are used as categories to organise and filter data

All of these pages retrieve data directly from the database.

7. Development Environment

The application was set up using Docker to ensure consistency across all team members’ environments. We used docker-compose to run both the application and the database.

The application can be started using:

docker-compose up --build
8. Task Allocation

The work was divided among the team members as follows:

Mohsin worked on backend development and database integration
Vijohnson worked on frontend development using PUG templates
Gautam worked on database design and routing

All members contributed to the project and made commits to the GitHub repository.

9. GitHub and Version Control

GitHub was used to manage the project and track progress. Each team member contributed code through commits. The GitHub repository also helped us collaborate and keep track of changes.

(Screenshot of contributions should be added here)

10. Kanban Board

We used GitHub Projects as a Kanban board to organise our tasks. Tasks were divided into:

To Do
In Progress
Done

This helped us keep track of progress and manage the workload effectively.

(Screenshot should be added here)

11. Meeting Record

Date: Week 9/10
Goal: Work on Sprint 3 implementation

Discussion:
We discussed progress on backend and database integration. Most core features were implemented, and initial testing was carried out. Some issues were identified and resolved during the meeting.

Actions:

Complete remaining features
Test the application
Prepare for sprint review
12. Challenges Faced

During this sprint, we faced a few challenges:

Connecting the backend to the MySQL database initially caused some errors
Docker setup was difficult at the beginning
Rendering dynamic data in PUG required debugging

How we solved them:
We fixed these issues by testing queries, checking configurations, and working together to debug problems.

13. Conclusion

Overall, Sprint 3 was successful as we managed to implement the core features of the application. The system is now able to store and display data dynamically. This provides a strong foundation for Sprint 4, where we will focus on adding more advanced features and improving the overall functionality of the application.
