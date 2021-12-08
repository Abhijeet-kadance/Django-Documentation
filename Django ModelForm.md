
## Django Model Form 

**Files Struture**

* forms .py
* models .py
* views .py
* template.html 

### models.py ### 

    form django.db import models

    class User(models.Model):
        name=models.CharField(max_length=70)
        email = models.EmailField(max_length=100)
        password = models.CharField(max_length=100)


**The Use of Model Form**

> ModelForm will remove the redundancy of writing the model objects again while writing forms. py form Class.

instead what will do is :


***form.py***

    for django.core import validators
    form django import forms
    form .models import User
    class StudentRegistration(forms.ModelForm):
        class Meta:
        model = User
        fields = ['name','password','email]

> We have replaced the redundant data members with fields object where we mention all the members to be included

> we have mentionded 
    model= User over here 

> dont forget to import the User model

from .models import User


> also the order in which we mention the data fields it will be represented in the same order




Django provides a helper class that lets you create a Form class from a Django Model. This helper class ic called as ModelForm


Steps:-

* Create Model Class
* Create ModelForm Class

Syntax:-
forms.py


    class ModelFormClassName(forms.ModelForm):
        class Meta:
            model = ModelClassName
            fields = ['fieldname1','fieldname2',fieldname3]
            field = ('fieldname1','fieldname2','fieldname3')



## Lets start crating student Registration Form 

> Step1 : Go to forms.py file and import 

    //This File is important for us to use ModelForm

    from django import forms
    
    // This file is our Model User
    from .models import User

    class StudentRegistration(forms.ModelForm):
        class Meta:
        model = User
        fields = ['name','email','password']


> Step 2 : Go to Views.py and create a function showformdata

    def showformdata(request):
        fm = StudentRegistration(request.POST)
        if fm.is_valid():
            nm = fm.cleaned_data['name']

            em = fm.cleaned_data['email']

            pw = fm.cleaned_data['password']

            print(nm)
            print(em)
            print(pw)
        
        else:
            fm=StudentRegistration()

        return render(request, 'enroll/userregistration.html',{'form':form})


## Dont Forget To run Make migration Command as follows

    > python manage.py makemigrations

    > python manage.py migrate

    > python manage.py runserver
    // to check if evrething is working fine



