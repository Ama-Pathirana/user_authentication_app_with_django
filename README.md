# Django Authentication Tutorial (Login, Register, Logout & Reset Password)

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
* [Project Structure Overview](#project-structure-overview)
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

* **Python 3.x:** Download from [python.org](https://www.python.org/downloads/).
* **pip (Python package installer):** Usually comes pre-installed with Python.
* **pipenv (Recommended for virtual environment management):** You'll install this globally if you don't have it.

### 2. Clone the Repository

First, clone the project from its GitHub repository to your local machine. Open your terminal or command prompt and run:

```bash
git clone https://github.com/Ama-Pathirana/user_authentication_app_with_django.git
