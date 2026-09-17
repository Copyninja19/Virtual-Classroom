# Virtual Classroom

A web-based classroom management system developed using ASP.NET Web Forms and Microsoft SQL Server. The application provides separate interfaces for students, teaching staff, and administrators to manage classroom activities, attendance, learning materials, communication, and user information.

## Overview

Virtual Classroom provides a centralized platform for managing academic activities through role-based interfaces.

The system supports three primary roles:

* **Administrator** — manages courses, staff, uploads, and user-related reports.
* **Staff** — manages learning materials, communicates with students, and accesses staff-related functionality.
* **Student** — accesses attendance information, learning materials, profile information, and communication features.

## Key Features

### Student Module

* Student registration and login
* Student profile management
* Profile image upload and update
* Attendance status tracking
* Course-wise attendance percentage calculation
* Downloadable learning materials
* Messaging and reply functionality
* Password change functionality
* Forgot-password functionality

### Staff Module

* Staff authentication
* Staff profile and account functionality
* Uploading learning materials
* Course-wise material management
* Activation/deactivation of uploaded resources
* Deletion of uploaded resources
* Student/staff communication
* Message and notification management
* Password management

### Administrator Module

* Administrator authentication
* Course/category management
* Staff management
* Upload management
* Staff reports
* User reports
* Feedback management
* Administrative data management

## Technology Stack

| Category             | Technology                      |
| -------------------- | ------------------------------- |
| Programming Language | C#                              |
| Web Framework        | ASP.NET Web Forms               |
| Frontend             | HTML, CSS, ASP.NET Web Controls |
| Database             | Microsoft SQL Server            |
| Data Access          | ADO.NET                         |
| IDE                  | Visual Studio                   |
| Version Control      | Git / GitHub                    |

## Application Architecture

The application follows a role-based web application structure:

```text
                         Virtual Classroom
                                |
                +---------------+---------------+
                |               |               |
             Admin            Staff          Student
                |               |               |
        Course Management   Upload Files    Attendance
        Staff Management    Messaging       Profile
        User Reports        Notifications   Messages
        Upload Management   Account         Downloads
        Feedback            Management      Password
                |               |               |
                +---------------+---------------+
                                |
                         Microsoft SQL Server
```

## Project Structure

```text
OTeaching/
│
├── Admin/
│   ├── AddCategory.aspx
│   ├── Feedback.aspx
│   ├── StaffReport.aspx
│   ├── Upload.aspx
│   └── UserReport.aspx
│
├── Staff/
│   ├── Default.aspx
│   ├── Message.aspx
│   ├── Password.aspx
│   ├── Upload.aspx
│   └── Staff.master
│
├── Student/
│   ├── Default.aspx
│   ├── Download.aspx
│   ├── Message.aspx
│   ├── MyProfile.aspx
│   ├── Password.aspx
│   ├── SSAttend.aspx
│   └── Student.master
│
├── App_Code/
│   ├── DataSet1.xsd
│   ├── DataSet2.xsd
│   ├── DS_CATE.xsd
│   ├── DS_FEED.xsd
│   ├── DS_MSG.xsd
│   ├── DS_REGI.xsd
│   ├── DS_STAFF.xsd
│   └── DS_UPLOAD.xsd
│
├── data1/
│   └── images/
│
├── app configuration
├── MasterPage.master
├── Default.aspx
├── Registartion.aspx
├── ContactUs.aspx
├── Feedback.aspx
├── Notification.aspx
└── web.config
```

## Database

The application uses **Microsoft SQL Server** for persistent data storage.

The project uses database tables and typed DataSet/TableAdapter components for operations related to:

* Student registration and profiles
* Staff information
* Courses/categories
* Uploaded learning materials
* Messages
* Notifications
* Feedback
* Attendance

The application also performs database operations through ADO.NET using `SqlConnection`, `SqlCommand`, and `SqlDataAdapter`.

## Attendance Management

The student attendance module retrieves attendance records for the selected course and calculates the attendance percentage based on the number of present classes and total recorded classes.

```text
Attendance Percentage =
(Present Classes / Total Classes) × 100
```

## Learning Material Management

Staff members can upload learning resources associated with courses. Uploaded resources can be viewed and managed through the staff interface, while students can search for resources by staff member and download available files.

## Communication

The system provides messaging functionality between students and staff.

Users can:

* View incoming messages
* Read message details
* Reply to messages
* Send new messages
* Manage message status

The system also maintains notifications associated with messages.

## Setup

### Prerequisites

* Windows
* Visual Studio
* .NET Framework 4.8
* Microsoft SQL Server / SQL Server Express
* SQL Server Management Studio (recommended)

### 1. Clone the Repository

```bash
git clone https://github.com/Copyninja19/virtual-classroom.git
cd virtual-classroom
```

### 2. Configure SQL Server

Create an `OTeaching` database in SQL Server and restore/import the required database schema and data.

The original project was configured to use SQL Server Express with Windows Authentication.

### 3. Configure the Connection String

Update the connection string in `web.config` according to your local SQL Server configuration.

Example:

```xml
<connectionStrings>
    <add name="OTeachingConnectionString2"
         connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=OTeaching;Integrated Security=True;TrustServerCertificate=True"
         providerName="System.Data.SqlClient"/>
</connectionStrings>
```

Do not commit credentials or environment-specific secrets to the repository.

### 4. Open the Project

Open the ASP.NET Web Forms project in Visual Studio.

Configure the appropriate startup page and SQL Server connection.

### 5. Run the Application

Run the project using Visual Studio and access the application through the local development server.

## Learning Outcomes

This project provided hands-on experience with:

* ASP.NET Web Forms development
* C# server-side programming
* SQL Server database integration
* ADO.NET
* CRUD operations
* Role-based application design
* File upload and download functionality
* Session-based user management
* Database-driven web applications
* Git and GitHub version control

## Author

**Sumit Singh**

GitHub: [Copyninja19](https://github.com/Copyninja19)

Project Repository: [Virtual Classroom](https://github.com/Copyninja19/virtual-classroom)
