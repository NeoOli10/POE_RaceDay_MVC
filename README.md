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
GitHub Actions workflow.
README documentation.
A minimum of 20 meaningful commits is required for Part 3.
Error Handling and User Interface
The application provides a consistent interface across its pages.
Navigation is based on user roles.
Enrolment statuses are displayed using different colours.
Invalid inputs are handled appropriately.
The interface uses consistent fonts, colours and spacing.
Bootstrap is used to support responsive layouts.
Conclusion
The RaceDay Part 3 project brings the different components of the RaceDay platform together through an ASP.NET Core MVC application.
It provides separate interfaces for Organisers and Participants, integrates with the Part 2 API, supports Azure Blob Storage for image uploads, and uses Docker for containerisation.
GitHub and GitHub Actions are used to manage the source code and automate the build process.

Features
Authentication and navigation
Register and log in through the Part 2 API.
The API's JWT and the user's role are kept in a server-side session (HttpOnly cookie, 60-minute idle timeout).
Role-based navigation: Organisers and Participants each see only their own menu.
Secure logout; protected pages redirect unauthenticated users to the login page, and wrong-role access shows an "Access denied" page.
Pages are served with Cache-Control: no-store, so the back button after logout cannot reveal protected content.
Organiser interface
Dashboard with event information and enrolment summaries.
Create, edit and delete events.
Manage event categories (age and distance categories).
View the participants enrolled in each event and their enrolment statuses, and update a status.
Capture finishing times and positions.
Upload event banner images.

Participant interface
Browse upcoming events and filter them.
View event information and categories.
Enrol in an event and choose a category.
View personal enrolments and their statuses, and withdraw.
View personal race results.
Update personal information and upload a profile picture.
UI and error handling
Bootstrap-based responsive layout with consistent fonts, colours and spacing.
Enrolment statuses shown as colour-coded badges.
Server-side validation on all forms, with every POST protected by an anti-forgery token.
API failures are turned into friendly messages and error pages, never stack traces.
Steps
Clone or download the repository.
Configure the API in POE_RaceDay_API/POE_RaceDay_API/appsettings.json: the SQL connection string, the AzureBlobStorage connection string and container name, and the Jwt key (at least 32 characters).
Start the Part 2 API with the http profile. It listens on http://localhost:5146 and opens Swagger.
Check the API address in POE_RaceDay_MVC/appsettings.json:
POE_RaceDay_MVC/
├── .github/workflows/ci.yml
├── Controllers/      Account, Events, Home, Media, Organiser*, Participant
├── Filters/          RoleAuthorize, ApiExceptionFilter
├── Helpers/          UiHelpers
├── Models/           ApiModels, ViewModels
├── Services/         RaceDayApi, SessionUser, ApiException
├── Views/            Account, Events, Home, Organiser*, Participant, Shared
├── wwwroot/          css, js
├── Dockerfile
├── Program.cs
└── appsettings.json
