# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App.

### Step 4:
Create python programs for views and urls.

### Step 5:
Create a HTML file of forms.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
Name : Thirukaalathessvarar S
Reg.no : 212222230161
```

## View.py
```
from django.shortcuts import render
from django.contrib.auth.decorators import login_required
from django.contrib.auth.decorators import permission_required
# Create your views here.


def home(request):
    return render(request,"myapp/home.html")


@login_required(login_url='/accounts/login')
def students(request):
    qr=Student.objects.all()
    context={'qres':qr}
    return render(request,"myapp/students.html",context)




@permission_required('myapp.view_labs')
def view_labs(request):
    qr=lab.objects.all()
    context={'qres':qr}
    return render(request,"myapp/labs.html",context)
```
```
from django.contrib import admin
from django.urls import path


from django.contrib.auth import views as auth_views
from myapp import views


urlpatterns = [
    path('',auth_views.LoginView.as_view(template_name='login.html'),name='login'),
    path('admin/', admin.site.urls),
    path('accounts/login',auth_views.LoginView.as_view(template_name='login.html'),name='login'),
    path('logout/',auth_views.LogoutView.as_view() , name='logout'),
    path('home/', views.home , name='home'),
    path('students/', views.Students , name='Students'),
    path('lab/', views.lab , name='lab'),
]
```
## OUTPUT:
![2023-05-17 (1)](https://github.com/Thirukaalathessvarar-S/serversideprocessing/assets/121166390/baa6b0a1-4114-4a1e-af8d-1e9c48339b05)

### Home Page:
![2023-05-17](https://github.com/Thirukaalathessvarar-S/serversideprocessing/assets/121166390/330879d6-c3c8-49ef-a008-f6665dc0cdc0)

## Result:
Thus the program is executed successfully .
