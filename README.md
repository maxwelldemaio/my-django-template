# My Django Template Setup

## Overview
The following commands will create a new Django project using this template and initialize a new Git repository for you (remove command depends on OS):
```
django-admin startproject [example_project_name] --template=project_name --name=Procfile
cd [example_project_name]
rmdir /s .git
git init
```
In short, this will set you up for success to use SQLite as a local development database and PostgreSQL in a production environment. This is geared towards [Heroku](https://www.heroku.com/), however a similar approach could be used for another cloud deployment platform. Also, we will use `venv` the built-in Python library to create a virtual environment for all requirements.

- [Documentation on deploying to Heroku](https://devcenter.heroku.com/articles/deploying-python)
- [Example video on deploying to Heroku](https://www.youtube.com/watch?v=kBwhtEIXGII)

## Environment Variables Explained
Using the Python library `dotenv`, we load our environment variables with `config.py`. We import `config.py` at the top of `settings.py` so our environment variables are populated before anything starts. For development, we can use our local SQLite database, and for production we will use PostgreSQL.

To distinguish between the production and development environment, we can setup "config vars" when deploying to Heroku. Normally you would add the database url, secret key, and an extra key value pair {"ENV": "heroku"}, that way our app can tell if it's in a production environment or not.