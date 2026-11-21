# Mathematics Aptitude App (Django Full Stack)

A beginner-friendly mathematics aptitude practice website built with Python, Django, HTML, CSS and JavaScript.

## Features
- Topic-wise aptitude practice (Percentages, Profit & Loss, Time & Work, Number System)
- Multiple-choice questions
- Timed quiz (30 seconds per question)
- Instant answer feedback and explanations
- Score summary with accuracy
- Question bank stored in the database
- Django admin to add, edit and delete questions
- Responsive interface

## 1. Requirements
- Python 3.10+
- pip
- MySQL Server (optional; SQLite works by default)

## 2. Install and run (SQLite - easiest)
```bash
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

pip install -r requirements.txt
python manage.py migrate
python manage.py seed_questions
python manage.py createsuperuser
python manage.py runserver
```
Open http://127.0.0.1:8000/

## 3. Use MySQL instead (optional)
Create a database:
```sql
CREATE DATABASE aptitude_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```
Set these environment variables before running Django.

Windows PowerShell:
```powershell
$env:DB_ENGINE="mysql"
$env:DB_NAME="aptitude_db"
$env:DB_USER="root"
$env:DB_PASSWORD="your_mysql_password"
$env:DB_HOST="127.0.0.1"
$env:DB_PORT="3306"
```

macOS/Linux:
```bash
export DB_ENGINE=mysql
export DB_NAME=aptitude_db
export DB_USER=root
export DB_PASSWORD=your_mysql_password
export DB_HOST=127.0.0.1
export DB_PORT=3306
```

Then run:
```bash
python manage.py migrate
python manage.py seed_questions
python manage.py runserver
```

## 4. Admin
Visit http://127.0.0.1:8000/admin/ and sign in with the superuser account.
Use the Questions section to manage your own question bank.

## Project structure
```text
mathematics_aptitude_app/
├── aptitude_project/
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── quiz/
│   ├── management/commands/seed_questions.py
│   ├── migrations/
│   ├── templates/quiz/
│   ├── static/quiz/
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
├── manage.py
└── requirements.txt
