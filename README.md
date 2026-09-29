# Athenaeum - Digital Library Management System

ASP.NET Core 10 MVC + Entity Framework Core (SQLite) + Bootstrap 5.

## Run it
1. Install the .NET 10 SDK: https://dotnet.microsoft.com/download
2. In this folder run:

       dotnet run

3. Open the URL printed in the terminal (usually http://localhost:5000 or https://localhost:5001).
4. Sign in with **admin / Admin@123**.

The SQLite database (`library.db`) and sample data are created automatically on first run.
To reset everything, stop the app and delete `library.db`.

## Features
- Sign-in for librarians (cookie auth, hashed passwords)
- Dashboard: totals, overdue list, recent activity, collection by category
- Books: add, edit, delete, search by title/author/ISBN, filter by category and availability, loan history per book
- Members: register, edit, activate/deactivate, delete, borrowing history and fines per member
- Loans: issue, renew, return; automatic due dates and late fines; limit on books per member

## Settings (appsettings.json -> "Library")
- `LoanDays` (default 14)
- `FinePerDay` in rupees (default 5)
- `MaxLoansPerMember` (default 5)

## Change the admin password
Add a new user or replace the seed in `Data/SeedData.cs`, delete `library.db`, and run again.

## Project layout
- `Models/` entities and view models
- `Data/` DbContext and seed data
- `Controllers/` Account, Home, Books, Members, Loans
- `Views/` Razor views (shared layout in `Views/Shared`)
- `wwwroot/css/site.css` all custom styling

Bootstrap, Bootstrap Icons and Google Fonts load from a CDN, so the first run needs internet access in the browser.
