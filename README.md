# FlaskApp starter app v1.5

![Screenshot](https://github.com/twintechlabs/flaskapp/blob/master/app/static/images/screenshot.png)

This code base serves as starting point for writing your next Flask application.

It's based on the awesome work of the Ling Thio and includes the open source
BootStrap ThemesGuide theme and a number of enhancements to the base Flask
Starter app including adding basic user management and a separate view file for
API code. This template is designed as a way to quickly get started building a
wide variety of applications based on Python and Flask.

## Code characteristics

* Tested on Python 2.6, 2.7, 3.3, 3.4, 3.5 and 3.6
* Well organized directories with lots of comments
    * app
        * commands
        * models
        * static
        * templates
        * views
    * tests
* Includes test framework (`py.test` and `tox`)
* Includes database migration framework (`alembic`)
* Sends error emails to admins for unhandled exceptions


## Setting up a development environment

We assume that you have `git` and `virtualenv` and `virtualenvwrapper` installed.

    # Clone the code repository into ~/dev/my_app
    mkdir -p ~/dev
    cd ~/dev
    git clone https://github.com/twintechlabs/flaskdash.git my_app

    # Create the 'my_app' virtual environment
    mkvirtualenv -p PATH/TO/PYTHON my_app

    # Install required Python packages
    cd ~/dev/my_app
    workon my_app
    pip install -r requirements.txt


# Configuring SMTP

Edit the `local_settings.py` file.

Specifically set all the MAIL_... settings to match your SMTP settings

Note that Google's SMTP server requires the configuration of "less secure apps".
See https://support.google.com/accounts/answer/6010255?hl=en

Note that Yahoo's SMTP server requires the configuration of "Allow apps that use less secure sign in".
See https://help.yahoo.com/kb/SLN27791.html


## Initializing the Database

    # Create DB tables and populate the roles and users tables
    python manage.py init_db

    # Or if you have Fabric installed:
    fab init_db


## Running the app (development)

    # Start the Flask development web server
    python manage.py runserver

    # Or if you have Fabric installed:
    fab runserver

Point your web browser to http://localhost:5000/

You can make use of the following users:
- email `member@example.com` with password `Password1`.
- email `admin@example.com` with password `Password1`.

## Running the app (production)

To run the application in production mode, gunicorn3 is used (and included in requirements.txt.

    # Run the application in production mode
    ./runserver.sh

## Running the automated tests

    # Start the Flask development web server
    py.test tests/

    # Or if you have Fabric installed:
    fab test


## Trouble shooting

If you make changes in the Models and run into DB schema issues, delete the sqlite DB file `app.sqlite`.


## Acknowledgements

With thanks to the following Flask extensions:
* [ThemesGuide](https://github.com/ThemesGuide/bootstrap-themes)
* [Alembic](http://alembic.zzzcomputing.com/)
* [Flask](http://flask.pocoo.org/)
* [Flask-Login](https://flask-login.readthedocs.io/)
* [Flask-Migrate](https://flask-migrate.readthedocs.io/)
* [Flask-Script](https://flask-script.readthedocs.io/)
* [Flask-User](http://flask-user.readthedocs.io/en/v0.6/)

<!-- Please consider leaving this line. Thank you -->
[Flask-User-starter-app](https://github.com/lingthio/Flask-User-starter-app) was used as a starting point for this code repository.

## Authors
- Matt Hogan - matt AT twintechlabs DOT io
- Ling Thio -- ling.thio AT gmail DOT com
