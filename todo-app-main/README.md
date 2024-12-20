# To-Do App by Elkasmi Fatima Zahra

This is a simple yet functional To-Do application built with PHP and MySQL. It allows users to manage their tasks effectively by adding, completing, and deleting them. Additionally, the app sends email notifications whenever a new task is created, using PHPMailer.

---

## Features
- Add new tasks to your to-do list.
- Mark tasks as completed.
- Delete tasks from the list.
- View tasks separately: open tasks and completed tasks.
- Get an email notification each time a new task is added.

---

## Requirements
To run this application, you need the following:
- **PHP**: Version 7.4 or higher.
- **MySQL**: For the database.
- **Web server**: Such as XAMPP, WAMP, or MAMP.
- **Composer**: To manage dependencies (optional if already configured).

---

## Installation

### 1. Clone the Repository
Clone this project to your local machine using the following commands:
```bash
git clone git@github.com:yourusername/todo-app.git
cd todo-app

### 2. Install Dependencies
Install the required dependencies using Composer:
```bash
composer install
```

### 3. Set Up the Database
1. **Run the database setup script**:
   Execute the following command to create the database and tables automatically:
   ```bash
   php setup_database.php
   ```
   This will:
   - Create a database named `tasks_db`.
   - Create a table named `tasks` with the necessary structure.
   - Create a users table to manage user accounts.
---

### 4. Configure the Database
1. Open the `db.php` file in the root directory.
2. Update the database credentials if necessary:
   ```php
   define('DB_HOST', 'localhost');
   define('DB_USER', 'root');
   define('DB_PASS', '');
   define('DB_NAME', 'tasks_db');
   ```

---

### 5. Configure PHPMailer
1. **Set your email credentials**:
   Open the `send_mailer.php` file and update the following:
   ```php
   $mail->Host       = 'smtp.gmail.com'; // Update to your SMTP server
   $mail->Username   = 'your-email@gmail.com'; // Your email address
   $mail->Password   = 'your-app-password';   // Gmail app password (not your regular password)
   ```
2. **Gmail users**:
   - Use a Gmail-specific app password if using a Gmail account. You can generate an app password in your Google account security settings: [Generate App Password](https://support.google.com/accounts/answer/185833?hl=en).
   - Enable "Less secure app access" in your Gmail account if necessary (not recommended for production environments).

---

### 6. Start the Application
1. Place the project in your web server's root directory (e.g., `htdocs` for XAMPP).
2. Start your web server.
3. Access the app in your browser:
   ```
   http://localhost/todo-app/index.php
   ```

---

## Project Structure
```
todo-app/
│
├── index.php               # Main file for task management
├── db.php                  # Database connection file
├── send_mailer.php         # Sends email notifications
├── complete_task.php       # Marks a task as completed
├── delete_task.php         # Deletes a task
├── setup_database.php      # Sets up the database and table
├── composer.json           # Composer dependencies
└── README.md               # Project instructions
```

---

## Usage
1. **Add a Task**:
   - Enter a task name in the input box and click "Add Task."
   - An email notification will be sent to the specified address.

2. **Complete a Task**:
   - Click the "Complete" button next to the task.

3. **Delete a Task**:
   - Click the "Delete" button to remove a task.

---

## Troubleshooting
- **Database Connection Error**: If you see an error about the database connection, ensure you've run the `setup_database.php` script and updated the credentials in `db.php`.
- **Email Sending Error**: Check the following:
   - SMTP server settings in `send_mailer.php` are correct.
   - Email credentials are valid (use an app password for Gmail).
   - Port 587 is open on your server.
- **No Tasks Displayed**: Ensure the `tasks` table has been created correctly in your database.

---

## License
This project is open-source and available under the MIT License.

---
```