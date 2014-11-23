# Create Django project

Contents:

- [Create a project](#create-a-project)
- [Default project structure](#default-project-structure)
- [Customize project settings](#customize-project-settings)
- [Create default database tables](#create-default-database-tables)

## Create a project

If Django is installed properly, `django-admin.py` will be in your `PATH`.

If you want to create a Django project called 'mysite' in the current working directory, use:

```sh
django-admin.py startproject mysite
```

Alternatively, if you want to create a Django project called 'mysite' in a directory called 'project_dir', use:

```sh
django-admin.py startproject mysite project_dir
```

## Default project structure

When you start a project, you should get a set of files and directories that look like:

    .
    └── mysite
        ├── manage.py
        └── mysite
            ├── __init__.py
            ├── settings.py
            ├── urls.py
            └── wsgi.py

## Customize project settings

There are many settings for a default Django project. Most are fine as-is to start with.

I typically start by changing the default time zone from 'UTC' to:

    TIME_ZONE = 'America/Los_Angeles'

The database can also be changed here. The default is SQLite, which is typically fine for development, but not production. To information on changing the database, start by check out the [Database setup](https://docs.djangoproject.com/en/1.7/intro/tutorial01/#database-setup) section of the [official Django tutorial](https://docs.djangoproject.com/en/1.7/intro/).

## Create default database tables

A new Django project includes some default apps that require some database tables to be created.

To perform this initial database migration, change to the project directory and run:

```sh
./manage.py migrate
```

The `manage.py` script provides the same functions as `django-admin.py`, but with the current Django project's settings.

The `manage.py` script should be executable, but if it is not for some reason, do one of the following:

- Change permissions with `chmod +x manage.py`, or
- Explicitly call Python to run the script: `python manage.py migrate`
