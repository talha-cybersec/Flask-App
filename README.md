# Flask Auth & CRUD App

A Flask web application with **secure user authentication** and a full **CRUD** (create, read, update, delete) interface for managing records. Passwords are hashed with bcrypt, sessions are handled by Flask-Login, and data is stored in SQLite through SQLAlchemy.

## ✨ Features

- **User registration** that rejects duplicate usernames
- **Secure login:** passwords are stored as **bcrypt hashes**, never in plain text
- **Session management** with Flask-Login; protected pages redirect to login
- **CRUD records:** add, view, update and delete people (first and last name)
- **Flash messages** for success and error feedback
- **Responsive UI** built with Bootstrap 5

## 🔐 Security Notes

| Practice | Implementation |
|---|---|
| Password storage | bcrypt hashing via `Flask-Bcrypt` |
| Access control | `@login_required` on every data route |
| Secret key | Read from the `SECRET_KEY` environment variable (random if unset), never hard-coded |
| Debug mode | Off by default; turned on only with `FLASK_DEBUG=1` |
| ORM | SQLAlchemy parameterised queries help prevent SQL injection |

## 🛠 Tech Stack

Python · Flask · Flask-SQLAlchemy · Flask-Login · Flask-Bcrypt · SQLite · Bootstrap 5

## 🚀 Getting Started

```bash
git clone https://github.com/talha-cybersec/Flask-App.git
cd Flask-App
pip install -r requirements.txt

# optional: set a fixed secret key so logins survive restarts
export SECRET_KEY="change-me-to-a-long-random-string"     # Windows: set SECRET_KEY=...

python app.py
```

Open http://127.0.0.1:5000, register an account and log in. The SQLite database is created automatically on first run.

## 📁 Project Structure

```
Flask-App/
├── app.py              # Routes, models, auth logic
├── requirements.txt    # Python dependencies
├── .gitignore
└── templates/
    ├── index.html      # Dashboard: add, list, delete records
    ├── login.html
    ├── register.html
    └── update.html
```

## 🔮 Possible Improvements

- CSRF protection with Flask-WTF
- Change delete from a GET link to a POST request
- Password strength rules and login rate-limiting

## 👤 Author

**Muhammad Talha** · [@talha-cybersec](https://github.com/talha-cybersec)
