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
