# Blog web app
#### Video Demo:  <URL https://youtu.be/UEIot_5Xxd8>
#### Description:
Basic Blog website with user registration and login forms.
Flask, Python, SQLite.

#### Installation:
Install with pip:
$ pip install -r requirements.txt

#### Flask application structure:
/home/user/Projects/FLASK_BLOG
├── flaskr/
│   ├── __init__.py
│   ├── db.py
│   ├── schema.sql
│   ├── auth.py
│   ├── blog.py
│   ├── templates/
│   │   ├── base.html
│   │   ├── auth/
│   │   │   ├── login.html
│   │   │   └── register.html
│   │   └── blog/
│   │       ├── create.html
│   │       ├── index.html
│   │       └── update.html
│   └── static/
│   │    |── style.css
│   │    └── img/
│   │         ├── background.jpg
│   │         └── logo-no-background.png
│   │       
├── venv/
├── setup.py
└── MANIFEST.in
└── README.md