# POE_RaceDay_MVC

Project Overview
RaceDay is a web-based event management system designed to manage running events. Part 3 focuses on developing an ASP.NET Core MVC web application that connects to the Part 2 API.
The system provides two types of users: Organisers and Participants. Each user has access to different features depending on their role.
Main Features
Authentication and Navigation
Users can register and log in.
The system maintains the user’s authenticated session.
Role-based navigation is provided for Organisers and Participants.
Users can log out securely.
Unauthenticated users cannot access protected pages.
Organiser Interface
Dashboard displaying event information and enrolment summaries.
Create, edit and delete events.
Manage event categories, including age and distance categories.
View participants enrolled in specific events.
View enrolment statuses.
Capture participants’ finishing times and positions.
Upload event banner images.
Participant Interface
View upcoming events.
Filter available events.
View event information and categories.
Enrol in events and select categories.
View personal enrolments and enrolment statuses.
View personal race results.
Update personal information and profile pictures.
Technologies Used
C#
ASP.NET Core MVC
ASP.NET Core Web API (Part 2)
HTML
CSS
Bootstrap
Azure Blob Storage
Docker
GitHub Actions
System Architecture
The RaceDay MVC application communicates with the Part 2 API to retrieve and manage information.
The MVC application does not directly access the database. All data operations are handled through the Part 2 API.
The application follows the Model-View-Controller (MVC) architecture:
Models: Represent application data.
Views: Display the user interface.
Controllers: Handle user requests and communicate with the API.
Azure Blob Storage Integration
Azure Blob Storage is integrated through the Part 2 API.
Organisers can upload event banner images, while Participants can upload profile pictures.
The MVC application sends image uploads to the Part 2 API. The API handles the storage of images in Azure Blob Storage and makes them available for display in the application.
How to Run the Application Locally
Requirements
Visual Studio 2022 or compatible development environment.
.NET SDK required by the project.
Access to the Part 2 API.
SQL Server and required database configuration for the API.
Steps
Clone or download the GitHub repository.
Open the MVC project in Visual Studio.
Ensure the Part 2 API is running.
Check that the API base URL is correctly configured.
Build the solution.
Run the MVC application.
Open the application using the local URL provided by Visual Studio.
GitHub and CI/CD
GitHub is used for source code management and version control.
GitHub Actions is used to automate the build process.
The project includes:
Source code for the MVC application.
Dockerfile for containerisation.

