# Blog web app
#### Video Demo:  <URL https://youtu.be/UEIot_5Xxd8>
#### Description:
Basic Blog website with user registration and login forms.
Flask, Python, SQLite.

flaskr/__init__.py is The application factory with create_app function which creates Flask instance.
In __init__.py we import and register the sql database functions created in db.py. 
Also, we need to import and register any blueprint, in this case that would be blueprint from
auth.py and blog.py

flaskr/auth.py containes the blueprint for auth and the views related to authentication.
#### Views:
Register:
When visiting auth/register register() function will render the template with HTML for registration auth/register.html
If request method is POST -
register() function uses request.form to receive username and password from the registration form.
Also, it generates the password hash and stores both the username and the encoded password in the sql database.
Fucntion also checks that the username isn't registered via except db.IntegrityError
After the user is registered fucntion returns the template with HTML for login. (auth/login.html)

Login:
When visiting auth/login login() function will render the template with HTML for login auth/login.html
If request method is POST -
login() function uses request.form to receive username and password from the login form.
Function selects the user from the database, if the username doesn't exist it returns an error.
Function decoded the password with check_password_hash and returns an error if incorrect.
If username and password are correct function will add the user to the session dictionary.

Logout:
When selecting logout route the logout() function will clear the session and redirect to the index page (blog/index.html)

Login required:
login_required() function is used for in blog views as decorator to make sure createing ,editing or deleting of posts
can be done only by the logged user


flaskr/blog.py containes the blueprint for blog and the views related to blog displaying, creating, editing and deleting.
#### Views:
Index:
index() function renders the template with all the posts in the database. (blog/index.html)

Create:
When visiting blog/create create() function will render the template with HTML for creation of the post blog/create.html
If request method is POST -
create() function uses request.form to receive title and content from the create form.
Function checks that title is entered and returns an error if not. Functions inserts new post and title into the database.
After the post is created fucntion renders the template with HTML for index. (blog/index.html)

Update:
When visiting blog/update update() function will render the template with HTML for updating of the post blog/create.html
If request method is POST -
update() function uses request.form to receive title and content from the create form.
Function checks that title is entered and returns an error if not. Functions updates the post and title in the database.
After the post is updated fucntion renders the template with HTML for index. (blog/index.html)

Delete:
delete(id) function deltes the psot from the database

#### Installation:
Install with pip:
$ pip install -r requirements.txt
$ pip3 install virtualenv
$py -3 -m venv venv
$venv\Scripts\activate
$pip install Flask

Initialize the database
$ flask --app flaskr init-db

Run in development server
$ flask --app flaskr --debug run

#### Project Directory:
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