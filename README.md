# Serve Smart: Restaurant Management System

A restaurant website and management system built as an academic team project. Restaurant owners sign up for an account and manage their own menu (categories, dishes and prices), and customers can browse the menu, read about the restaurant, make reservations and send messages through a contact form.

![PHP](https://img.shields.io/badge/PHP-backend-777BB4?logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-database-4479A1?logo=mysql&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-UI-7952B3?logo=bootstrap&logoColor=white)

## Features

- **Owner accounts**: sign up and log in, with a session-protected admin area (`mainproject/admin.php`)
- **Per-restaurant menu**: each account gets its own menu table with category, dish and price
- **Customer pages**: home, menu, about us and reservations
- **Contact form**: messages are saved to the database (`mainproject/ContactUs.php`)
- **Responsive UI** built on a Bootstrap restaurant template

## Tech stack

| Layer    | Technology                                  |
|----------|---------------------------------------------|
| Backend  | PHP with sessions                           |
| Database | MySQL / MariaDB (`mysqli`)                  |
| Frontend | HTML, CSS, Bootstrap, JavaScript            |

## Repository layout

```text
mainproject/       PHP application: login/signup, admin menu manager, contact, home, about
homepage/          Static marketing pages (home, menu, reservation, contact)
restoran-1.0.0/    Third-party Bootstrap template used for styling (see credits)
Images/            Logos and images
```

## Run it locally

1. Install a local PHP + MySQL stack such as [XAMPP](https://www.apachefriends.org/).
2. Copy the repo into your web root (for XAMPP: `htdocs/serve-smart`).
3. Create a MySQL database named `project` with an `accounts` table and a `contact` table.
4. Open `http://localhost/serve-smart/mainproject/login.php`.

## Credits

The visual design uses the free **Restoran** Bootstrap template by [HTML Codex](https://htmlcodex.com/bootstrap-restaurant-template) (license in `restoran-1.0.0/LICENSE.txt`). The PHP application logic, database integration and admin features in `mainproject/` were written by our team.

## Known limitations and what I'd do differently

This was one of my first full-stack projects. Looking back at it with what I know now, I would:

- **Use prepared statements** everywhere. The current queries are built by concatenating form input, which is vulnerable to SQL injection.
- **Hash passwords** with `password_hash()` instead of storing them as entered (my later project, TraceIt, does this).
- Store all menus in one `menu_items` table with a `restaurant_id` column instead of creating a table per account.
- Move database credentials into environment variables.

My more recent work (for example the [DevSecOps Automation Engine](https://github.com/Veershah027/next-gen-devsecops-automation-engine)) focuses on exactly these kinds of security issues.
