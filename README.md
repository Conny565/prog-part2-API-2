# prog-part2-API-2
1. Project Overview

RaceDay is an ASP.NET Core Web API developed to manage running events and race registrations. The system allows users to register and log in, view running events, choose race categories, and enrol in races. Organisers can manage events and view race information. The system also stores event routes, weather information, and race results.

2. Technologies Used

- C#
- ASP.NET Core Web API
- SQL Server
- ADO.NET or Entity Framework Core (depending on the database approach used in the project)
- Swagger for API testing
- BCrypt for password hashing
- GitHub and GitHub Actions for version control and automated builds and tests
- Unit testing framework (depending on the test project)

3. Project Structure

Models

File| Description
"User.cs"| Stores user information, including name, email, password hash and role.
"Event.cs"| Stores running event details, such as name, date, description and location.
"Weather.cs"| Stores weather information linked to an event.
"Category.cs"| Stores race categories, such as 5 km and 10 km.
"EventRoute.cs"| Stores route details and race distances.
"Enrolment.cs"| Stores participant registration information for events.
"Result.cs"| Stores race finishing times and positions.

Controllers

File| Description
"UsersController.cs"| Handles user registration and login.
"EventsController.cs"| Handles running event operations.
"CategoriesController.cs"| Manages race categories.
"EventRouteController.cs"| Manages event routes and distances.
"EnrolmentsController.cs"| Handles participant enrolments.
"ResultsController.cs"| Manages race results.
"WeatherController.cs"| Manages event weather information.

Middleware and Configuration

- "SessionCheck.cs": Checks whether a user has an active session before accessing protected endpoints, where configured.
- "Program.cs": Configures and starts the API, registers services and middleware, and enables Swagger.
- "appsettings.json": Contains application configuration, including the database connection string.
- "Races.sql": Contains the SQL script used to create the database and tables, if included in the repository.

4. User Roles

Organiser

The organiser manages running events. Depending on the permissions implemented in the API, the organiser can create, update, view or delete events and manage related event information.

Participant

The participant can register and log in, view available events, select a race category and enrol in a running event. Participants can also view relevant race information and results where these features are available.

5. Database Setup

1. Install and open SQL Server Management Studio (SSMS).
2. Connect to your SQL Server instance.
3. Open the "Races.sql" script from the project, if available.
4. Execute the script to create the database and tables.
5. Open "appsettings.json" in the API project.
6. Update the connection string to match your local SQL Server instance.
7. Do not upload database passwords or other secret information to GitHub.

6. How to Run the Project

1. Install the .NET SDK required by the project.
2. Clone or download the repository.
3. Open the solution in Visual Studio.
4. Check that the SQL Server database and connection string are configured correctly.
5. Restore the NuGet packages.
6. Build the solution and fix any errors.
7. Set the API project as the startup project.
8. Run the project.
9. Open the Swagger URL displayed by the application to test the API endpoints.

7. API Testing

Swagger is used to test the API endpoints. It allows users to send requests and view the responses returned by the API.

The API includes endpoints for user registration and login, event management, categories, routes, enrolments, results and weather information, depending on the endpoints implemented in the project.

Protected endpoints should be tested with and without valid authentication to confirm that access is handled correctly.

8. Authentication and Security

The API supports user registration and login. Passwords should be hashed using BCrypt before being stored in the database. Passwords should never be stored as plain text.

Protected endpoints should verify the appropriate session or authentication information. Users should only be allowed to perform actions permitted by their roles.

9. Unit Testing

Unit tests are used to check whether parts of the application work as expected. The tests should cover important operations, including user authentication, event management and validation.

Run the unit tests using Visual Studio Test Explorer or the "dotnet test" command from the solution directory, where a test project is available.

10. GitHub Actions CI/CD

GitHub Actions is used to automate the build and testing process. The workflow should run whenever code is pushed to the repository. It should restore dependencies, build the project and run the unit tests.

Successful Build Screenshot


11. Demonstration Video

The demonstration video explains the project structure and shows the API running. It demonstrates the endpoints in Swagger, authentication and unit testing.


12. Conclusion

RaceDay provides a way to manage running events and participant registrations through a Web API. The project uses C#, ASP.NET Core and SQL Server to manage information. Swagger supports API testing, while GitHub Actions can automate building and running unit tests.
