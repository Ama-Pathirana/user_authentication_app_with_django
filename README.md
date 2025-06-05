# Django Authentication App (Login, Register, Logout & Reset Password)

This project is a Django backend application demonstrating a full user authentication system including registration, login, logout, and password reset functionalities. It's built following a tutorial to teach about authentication and registration in Django.

## Table of Contents

* [Features](#features)
* [How to Run the Project](#how-to-run-the-project)
    * [1. Prerequisites](#1-prerequisites)
    * [2. Clone the Repository](#2-clone-the-repository)
    * [3. Set Up the Virtual Environment](#3-set-up-the-virtual-environment)
    * [4. Install Project Dependencies](#4-install-project-dependencies)
    * [5. Configure Environment Variables / Settings](#5-configure-environment-variables--settings)
    * [6. Apply Database Migrations](#6-apply-database-migrations)
    * [7. Create a Superuser (Admin Account)](#7-create-a-superuser-admin-account)
    * [8. Run the Development Server](#8-run-the-development-server)
* [Important Notes](#important-notes)

## Features

This project implements the following authentication features:

* **User Registration:** Allows new users to create accounts.
* **User Login:** Enables registered users to authenticate with their credentials.
* **User Logout:** Provides functionality for authenticated users to log out.
* **Password Reset (via Email):** Users can reset forgotten passwords by receiving a unique reset link via email.

## How to Run the Project

Follow these steps to get the Django authentication project up and running on your local machine.

### 1. Prerequisites

Before you begin, ensure you have the following installed:

* **Python 3.11:** Download from [python.org](https://www.python.org/downloads/).
* **pip (Python package installer):** Usually comes pre-installed with Python.
* **pipenv (Recommended for virtual environment management):** You'll install this globally if you don't have it.

### 2. Clone the Repository

First, clone the project from its GitHub repository to your local machine. Open your terminal or command prompt and run:

```bash
git clone https://github.com/Ama-Pathirana/user_authentication_app_with_django.git
cd user_authentication_app_with_django
```
## 3. Set Up the Virtual Environment

It's crucial to use a virtual environment to isolate project dependencies and avoid conflicts with other Python projects.

```bash
pip install pipenv # Install pipenv globally if you haven't already
pipenv shell        # Create and activate a new virtual environment
```

You'll see a message indicating the virtual environment is activated (e.g., `(user_authentication_app_with_django)` preceding your prompt).

To deactivate the environment later, simply type `exit` and press Enter.  
To reactivate it, navigate back to the project directory and run `pipenv shell` again.

## 4. Install Project Dependencies

With your virtual environment active, install Django (and any other required packages, though Django is the primary one for this project):

```bash
pip install django
```

(If you were provided with a Pipfile or requirements.txt file, you would typically run `pipenv install` or `pip install -r requirements.txt` respectively to install all dependencies listed there.)

## 5. Configure Environment Variables / Settings

Important: You must configure your email settings in `userPrefApp/settings.py` for the password reset functionality to work.

Open `userPrefApp/settings.py` in your code editor and update the following lines:

```python
# ... other settings ...

# Email Settings for Password Reset
# IMPORTANT: Replace with your actual email credentials.
# For Gmail, you'll need to generate an 'App Password'.
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST="smtp.gmail.com"
EMAIL_PORT=465
EMAIL_USE_SSL=True
EMAIL_HOST_USER="your_email@gmail.com"          # <--- REPLACE THIS with your Gmail address
EMAIL_HOST_PASSWORD="your_google_app_password"  # <--- REPLACE THIS with your Google App Password

# ... rest of your settings ...
```

### How to get a Google App Password (for Gmail users):

If you're using Gmail, you cannot use your regular account password directly for `EMAIL_HOST_PASSWORD`. You need to generate an **App Password**:

1. Go to your Google Account: [myaccount.google.com](https://myaccount.google.com)  
2. Navigate to **Security** on the left sidebar.  
3. Under **How you sign in to Google**, select **2-Step Verification** (if it's off, you'll need to enable it first).  
4. Scroll down to **App passwords** and click on it.  
5. Follow the instructions to generate a new app password. This 16-character code is what you'll use for `EMAIL_HOST_PASSWORD`.  

## 6. Apply Database Migrations

This step sets up your database tables (`db.sqlite3` by default) based on the Django models defined in the project, including the built-in User model and the custom PasswordReset model for password recovery.

Ensure your virtual environment is active, then run:

```bash
python manage.py makemigrations
python manage.py migrate
```

## 7. Create a Superuser (Admin Account)

You'll need a superuser account to access the Django administration panel (`/admin`) and to manage users directly.

```bash
python manage.py createsuperuser
```

Follow the prompts in your terminal to enter a username, email address, and a strong password for your admin account.

## 8. Run the Development Server

Finally, start the Django development server:

```bash
python manage.py runserver
```
Open your web browser and navigate to:

- [http://127.0.0.1:8000/](http://127.0.0.1:8000/): This is the home page of your authentication application.  
- [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin): Access the Django administration panel using the superuser credentials you created in step 7.

You are now ready to test the registration, login, logout, and password reset functionalities of the application!

## Important Notes

- **Security:** For a production environment, ensure you use a strong `SECRET_KEY` in `settings.py` and consider deploying with HTTPS to encrypt communications.  
- **Email Configuration:** The password reset functionality relies on correct email settings. Double-check your `EMAIL_HOST_USER` and `EMAIL_HOST_PASSWORD` in `settings.py`.  
- **Error Handling:** The provided code includes basic error handling for user input and data validation. For production-grade applications, more robust error handling and logging would be beneficial.  
- **Template Paths:** Verify that the paths to your HTML templates in `views.py` and `settings.py` (`TEMPLATES['DIRS']`) are accurate.  
- **Static Files:** Ensure your static files (e.g., `style.css`) are correctly linked in your HTML templates using the Django `{% static 'your_file.css' %}` template tag.
