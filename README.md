## What Is This?

This is an example repo corresponding to multiple lessons within the LearnHowToProgram.com walkthrough on creating a To Do List application in [Section 5: Authentication with Identity](https://www.learnhowtoprogram.com/c-and-net/authentication-with-identity).

This project corresponds to the classwork and lessons that describe how to use Identity in an ASP.NET Core MVC project to authenticate users. This project contains a one-to-many relationship between `Item` and `Category`, and a many-to-many relationship between `Item` and `Tag`, and a one-to-many relationship between `ApplicationUser` and `Item`. There are multiple lessons in this series. The first lesson in the series is [Identity Setup and Configuration](https://www.learnhowtoprogram.com/c-and-net/authentication-with-identity/identity-setup-and-configuration).

There are multiple branches in this repo that are described more below.

## How To Run This Project

### Install Tools

Install the tools that are introduced in [this series of lessons on LearnHowToProgram.com](https://www.learnhowtoprogram.com/c-and-net/getting-started-with-c).

If you have not already, install the `dotnet-ef` tool by running the following command in your terminal:

```
dotnet tool install --global dotnet-ef --version 6.0.0
```

### Set Up and Run Project

1. Clone this repo.
2. Open the terminal and navigate to this project's production directory called "ToDoList".
3. Within the production directory "ToDoList", create a new file called `appsettings.json`.
4. Within `appsettings.json`, put in the following code, replacing the `uid` and `pwd` values with your own username and password for MySQL. For the LearnHowToProgram.com lessons, we always assume the `uid` is `root` and the `pwd` is `epicodus`.

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Port=3306;database=to_do_list_with_auth;uid=root;pwd=epicodus;"
  }
}
```

5. Create the database using the migrations in the To Do List project. Open your shell (e.g., Terminal or GitBash) to the production directory "ToDoList", and run `dotnet ef database update`. 
    - To optionally create a migration, run the command `dotnet ef migrations add MigrationName` where `MigrationName` is your custom name for the migration in UpperCamelCase. To learn more about migrations, visit the LHTP lesson [Code First Development and Migrations](https://www.learnhowtoprogram.com/c-and-net-part-time/many-to-many-relationships/code-first-development-and-migrations).
6. Within the production directory "ToDoList", run `dotnet watch run` in the command line to start the project in development mode with a watcher.
4. Open the browser to _https://localhost:5001_. If you cannot access localhost:5001 it is likely because you have not configured a .NET developer security certificate for HTTPS. To learn about this, review this lesson: [Redirecting to HTTPS and Issuing a Security Certificate](https://www.learnhowtoprogram.com/lessons/redirecting-to-https-and-issuing-a-security-certificate).

## Available Branches

**1_identity_setup**: This branch includes the code we added after working through the following lesson:

- https://www.learnhowtoprogram.com/c-and-net/authentication-with-identity/identity-setup-and-configuration

**2_authentication**: This branch includes the code we added after working through the following lessons:

- https://www.learnhowtoprogram.com/c-and-net/authentication-with-identity/authentication-with-identity-user-registration-controller
- https://www.learnhowtoprogram.com/c-and-net/authentication-with-identity/authentication-with-identity-user-registration-viewmodel-validation-and-views
- https://www.learnhowtoprogram.com/c-and-net/authentication-with-identity/authentication-with-identity-user-login-and-logout

**3_authorization**: This branch includes the code we added after working through the following lesson:

- https://www.learnhowtoprogram.com/c-and-net/authentication-with-identity/adding-authorization-and-associating-users-with-items