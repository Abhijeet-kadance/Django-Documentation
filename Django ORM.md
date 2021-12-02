## To better get a grip on Django ORM we will try our commands on python shell

***

### Accessing shell inside your virtual enviornment

> Once inside virtual Enviornment (venv) type th following command

    $(venv) : python manage.py shell

### Once inside shell you would get a pointer ">>>" like this:

Now begin with importing a Model to get your hands on ORM

    >>> from blog.models import Author,Post,Category,Tag

This above command would import your model and objects with it .
