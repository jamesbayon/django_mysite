# Django Polls App
Django Polls App

Created 1 app in django where the user can create a Poll and create Choices for the Poll
where each Choice has a vote count

static and templates were used in this app.

Here are the sample screenshots for the Polls App:

<img src="./readme_images/Polls_Index.JPG" alt="Polls_Index_Image" width="200" style="display:block"/>
<img src="./readme_images/Poll_Choices.JPG" alt="Poll_Choices_Image" width="200" style="display:block"/>
<img src="./readme_images/Poll_Vote_Results.JPG" alt="Poll_Vote_Results_Image" width="200" style="display:block"/>

tutorial source: https://docs.djangoproject.com/en/4.1/intro/tutorial01/

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

make poll app modifiable in admin

### Part 3
write more views: detail, results, vote

wire views to polls.urls

modify polls.views.index to display 5 Question

add new template for polls.index - templates/polls/index.html

modify polls.views.index for new template

Raising a 404 error

modify polls.views.detail to raise Http404

Namespacing URL names

add app_name in polls.urls

in html change url usage to 'polls:detail'


### Part 4
write minimal form for polls detail.html

update polls.views.vote for modified detail html

update polls.views.results to use get_object_or_404

add template results.html

Use generic views

Amend URLconf in polls.urls - use IndexView.as_view() etc

Amend views in polls.views - remove index, detail, results and replace with IndexView etc

### Part 5
create automated tests in polls.tests - create QuestionModelTests class

fix bug in was_published_recently

add some more tests

Test a view

amend polls.views.get_queryset

create helper function polls.tests.create_question

add tests for views - create QuestionIndexViewTests

create QuestionDetailViewTests with tests

### Part 6
customize look

add static/polls/style.css

### Part 7
create class QuestionAdmin with fields

add related objects - display the choices

### Additional
Add django REST framework

source https://www.django-rest-framework.org/

install the following

```
pip install djangorestframework
pip install markdown       # Markdown support for the browsable API.
pip install django-filter  # Filtering support
```

add 'rest_framework' to mysite.settings INSTALLED_APPS .

```
INSTALLED_APPS = [
    ...
    'rest_framework',
]
```

add rest_framework in mysite.urls url_patterns

add REST_FRAMEWORK in mysite.settings

add API in mysite.urls
