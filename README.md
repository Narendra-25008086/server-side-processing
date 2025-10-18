# Ex.05 Design a Website for Server Side Processing
## Date:02.10.2025

## AIM:
 To design a website to calculate the Body Mass Index (BMI) in the server side. 


## FORMULA:
BMI= W/H<sup>2</sup>
<br> BMI --> Body Mass Index
<br> W --> Weight
<br> H --> Height

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
math.html
<html>
    <head>
        <title>BMI Calculator</title>
        <style>
        body{
          background-color: green;
          border-top: 20;
        }
        .m{
          background-color: red;
          border-style: dotted;
          margin-top: 150px;
          margin-left: 500px;
          margin-right: 500px;
          
        }
            .main{
                font-size: 250%;
                text-align: center;
                background-color: red;
                 margin-left: 50px;
                  margin-right: 50px;
                  padding: 50px;
                  
                  
            }
            .a{
                font-size: 150%;
                text-align: center;
                background-color: red;
                 margin-left: 50px;
                  margin-right: 50px;
                
                 
            }
            form{
              text-align: center;
              background-color: red;
               margin-left: 50px;
             margin-right: 50px;
             padding: 50px;
            }
           
        </style>
    </head>
    <body>

       <div class="m">
        <div class="main">BMI Calculator</div>
        <div class="a">
         Kervin.S(25012113)</div>
        <form method="post">
          {% csrf_token %}
           
           
            <label>Weight(kg)=</label>
            <input type="text" name="weight" value="{{w}}"><br><br>
             <label>Height(cm)=</label>
            <input type="text" name="height" value="{{h}}"><br><br>
            <button type="submit">Calculate</button><br><br>
            <label>BMI=</label>
            <input type="text" name="bmi" value="{{bmi}}">
        </div>
        </form>
        
        
    </body>
</html>

views.py

from django.shortcuts import render
def calculate_bmi(request):
    context={}
    context['bmi']="0"
    context['w']="0"
    context['h']="0"
    if(request.method=='POST'):
       w= float(request.POST.get('weight','0'))
       h=float(request.POST.get('height','0'))
       print('request=',request)
       
       print('Weight=',w)
       print('Height=',h)
       bmi=w/((h/100)**2)
       context['bmi']=bmi
       context['w']=w
       context['h']=h
       print('BMI=',bmi)
    return render(request,'myapp/math.html',context)

urls.py

from django.contrib import admin
from django.urls import path
from myapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('bmi/',views.calculate_bmi,name="bmi"),
    path('',views.calculate_bmi,name="bmicalculator")
]
```
## SERVER SIDE PROCESSING:
<img width="1920" height="1080" alt="Screenshot 2025-10-18 090107" src="https://github.com/user-attachments/assets/a2f9dfbe-1909-43cb-b8f4-0454e032b5f3" />


## HOMEPAGE:
<img width="1920" height="1080" alt="Screenshot 2025-10-18 090759" src="https://github.com/user-attachments/assets/080649c0-0d3b-4cd4-927b-1d1e058b89dd" />



## RESULT:
The program for performing server side processing is completed successfully.
