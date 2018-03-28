# DjangoGirls Tutorial

## Setup & Installation

- Python 3
- Venv
- Django 1.11.x
- IDE
- Git

## How the Internet Works

Everything is files on a disk, disks reside in servers.
The address system for these servers uses TCP/IP.
DNS resolves a name to an IP.
Routers use IP (and DNS) to route data between systems.
Every data packet takes a unique route to arrive at destination.
Data represents itself using protocols (ex. HTTP).
Protocols are just established language conventions.

## Intro to the CLI

[SS64 References](https://ss64.com/)

Try it out:

```
  $ whoami
  $ ls
  $ cd ~
  $ mkdir TEST_DIR
  $ cd TEST_DIR && mkdir NESTED_DIR
  $ touch test.txt
  $ cp test.txt NESTED_DIR/
  $ cd ..
  $ rm -r TEST_DIR
  $ exit
```

## Diving Into Python

- Installation (using pyenv: https://github.com/pyenv/pyenv)
- Install IDE (Using Atom, but any works)

### Working with the Python CLI

- Open terminal
- Execute some commands
- Numbers, Strings, Operators, Functions
- Errors
- Variables
- Print
- Lists [], Indexes
- Dictionaries {}, key-value pairs, KeyErrors
- Comparators: <, >, =, <=, >=, !=, ==, ===, and, or, is
- Booleans
- Save code to a python file
- If...elif...else
- Comments
- Functions
- Loops
  - for name in names:
  - for i in range(0,10):

Language Ref Tutorial: https://docs.python.org/3/tutorial/

## What is Django

Django is a free and open source web application framework, written in Python. A web framework is a set of components that helps you to develop websites faster and easier.

Imagine a mailbox (port) which is monitored for incoming letters (requests). This is done by a web server. The web server reads the letter and then sends a response with a webpage. But when you want to send something, you need to have some content. And Django is something that helps you create the content.

When a request comes to a web server, it's passed to Django which tries to figure out what is actually requested. It takes a web page address first and tries to figure out what to do. This part is done by Django's urlresolver (note that a website address is called a URL – Uniform Resource Locator – so the name urlresolver makes sense). It is not very smart – it takes a list of patterns and tries to match the URL. Django checks patterns from top to bottom and if something is matched, then Django passes the request to the associated function (which is called view).

In the view function, all the interesting things are done: we can look at a database to look for some information. Maybe the user asked to change something in the data? Like a letter saying, "Please change the description of my job." The view can check if you are allowed to do that, then update the job description for you and send back a message: "Done!" Then the view generates a response and Django can send it to the user's web browser.

## Project Setup

- Venv
- Django Install
- Make new project (`$ django-admin startproject mysite .`)
- Migrate DB changes (`$ python manage.py migrate`)
- Run webserver (`$ python manage.py runserver`)

## Make Blog App

```
  $ python manage.py startapp blog

  # Add blog app to INSTALLED_APPS in settings.py.

  $ python manage.py makemigrations blog
  $ python manage.py migrate blog
```

## Create a superuser

```
  $ python manage.py createsuperuser
```

- Restart webserver (CTRL+C && python manage.py runserver).
- Login to admin (localhost:8000/admin) with superuser.
- Make some blog Post entries.
  -- Make sure a few of them have no published_date

## Use VCS

Push your code into VCS.
Setup a server.
Test basic default webpage.

## Django URLs

- Create urls entry in urls.py to include blog.urls.py
- Create urls.py file in blog app.
- Add urlresolver for post_list
- Restart webserver
  - This will ERROR because there is no view code yet.

## Django Views
