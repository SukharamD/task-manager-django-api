# TASK MANAGER API

This project is a simple Django REST API built to manage users and their tasks.  
It demonstrates clean API design using Django REST Framework (DRF) with PostgreSQL as the database.

---

# Tech Stack

- Python 3
- Django
- Django REST Framework (DRF)
- PostgreSQL

---

# Features

## Users

- Create a user
- List all users

## Tasks

- Create a task
- List all tasks
- Retrieve task details
- Update a task
- Delete a task
- Filter tasks by status (Pending / In Progress / Completed)

---

# Project Structure

task_manager/
├── config/
├── users/
├── tasks/
├── manage.py
├── requirements.txt
├── .env.example
└── README.md

---

# Setup Instructions

1. Clone the Repository

git clone <your-github-repository-url>
cd task_manager

2. Create and Activate Virtual Environment

python -m venv venv
venv\Scripts\activate

3. Install Dependancies

pip install -r requirements.txt

---

## PostgreSQL Configuration

# Create Database

You can create the database using pgAdmin or SQL shell:
CREATE DATABASE task_db;

---

# Environment Variables

Create a .env file in the project root with the following values:

DEBUG=True
SECRET_KEY=your-secret-key
DB_NAME=task_db
DB_USER=postgres
DB_PASSWORD=your_postgres_password
DB_HOST=localhost
DB_PORT=5432

# Database Migrations

Run the following commands to apply migrations:

python manage.py makemigrations
python manage.py migrate

# Create Superuser (Admin Access)

python manage.py createsuperuser

# Run Development Server

python manage.py runserver

The API will be available at:
http://127.0.0.1:8000/

---

# API Endpoints

### Users

1. Create User
   POST /users/
   {
   "username": "ram",
   "email": "ram@gmail.com"
   }

2. List Users
   GET /users/

### Tasks

Create Task

POST /tasks/
{
"title": "First Task",
"description": "Task description",
"status": "Pending",
"user_id": 1
}

3. List Tasks
   GET /tasks/

4. Get Task Details
   GET /tasks/{id}/

5. Update Task
   PUT /tasks/{id}/
   {
   "title": "Updated Task",
   "description": "Updated description",
   "status": "In Progress",
   "user_id": 1
   }

6. Delete Task
   DELETE /tasks/{id}/

7. Filter Tasks by Status
   GET /tasks/?status=Completed

# Admin Panel

Django Admin is enabled for managing users and tasks:
http://127.0.0.1:8000/admin/

# Notes

- Uses Django’s built-in User model
- All request validation is handled using DRF serializers
- PostgreSQL configuration is managed using environment variables
- Clean and modular Django app structure is followed
- .env file should not be committed to version control.
