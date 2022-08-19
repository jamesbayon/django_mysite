# django_mysite
 Writing my first Django app

### Part 1
Creating a project

`django-admin startproject django_mysite`

Creating the Polls app

`python manage.py startapp polls`

add polls.views.index
modify polls.urls - add path for views.index
modify mysite.urls - include polls.urls

### Part 2
Database setup
modify mysite/settings.py - set timezone to Asia/Hong_Kong

`python manage.py migrate`

created Question and Choice class in polls/models.py
add polls.apps.PollsConfig in mysite/settings.py

make migrations and create tables 

`python manage.py makemigrations polls`

`python manage.py sqlmigrate polls 0001`

apply migrations

`python manage.py migrate`

add __self__ and was_published_recently() in polls.models.Question
add __self__ in polls.models.Choice

Creating an admin user

`python manage.py createsuperuser`