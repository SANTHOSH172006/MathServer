# Ex.05 Design a Website for Server Side Processing
## Date:08-04-2024

## AIM:
To design a website to find surface area of a Right Cylinder in server side.

## FORMULA:
Surface Area = 2Πrh + 2Πr<sup>2</sup>
<br>r --> Radius of Right Cylinder
<br>h --> Height of Right Cylinder

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
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Area of Square Prism</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body   {
            background-color: blueviolet;
        }
.edge  {
            display: flex;
            height: 100vh;
            width: 100%;    
            justify-content: center;
            align-items: center;
        }
.box   {
            display: block;
            width: 500px;
            min-height: 300px;
            font-size: 20px;
            background: rgb(7,85,152);
            background:black;
            border-radius: 10px;
            box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
        }
.formelt  {
            color: whitesmoke;
            text-align: center;
            margin-top: 7px;
            margin-bottom: 6px;
            }
h1 {
            color: white;
            text-align: center;
            padding-top: 22px;
    }
input{
            margin: 5px;
            padding: 5px;
            border-radius: 5px;
            border: none;

     }
</style>
</head>
<h1> SANTHOSH.D (212223220099)</h1>
<body>
<div class="edge">
<div class="box">
<h1>Area of a Square Prism</h1>
<form method="POST">
{% csrf_token %}
<div class="formelt">
Side : <input type="text" name="length" value="{{l}}"></input>(in m)<br />
</div>
<div class="formelt">
Height : <input type="text" name="breadth" value="{{b}}"></input>(in m)<br />
</div>
<div class="formelt">
<input type="submit" value="Calculate"></input><br />
</div>
<div class="formelt">
Area : <input type="text" name="area" value="{{area}}"></input>m<sup>2</sup><br />
</div>
</form>
</div>
</div>
</body>
</html>


views.py

from django.shortcuts import render
def rectarea(request):
    context={}
    context['area'] = "0"
    context['l'] = "0"
    context['b'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        l = request.POST.get('length','0')
        b = request.POST.get('breadth','0')
        print('request=',request)
        print('Length=',l)
        print('Breadth=',b)
        area = int(l) * int(b)
        context['area'] = area
        context['l'] = l
        context['b'] = b
        print('Area=',area)
    return render(request,'ludusapp/math.html',context)

urls.py

from django.contrib import admin
from django.urls import path
from ludusapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaofrectangle/',views.rectarea,name="areaofrectangle"),
    path('',views.rectarea,name="areaofrectangleroot")
]


```

## SERVER SIDE PROCESSING:
![alt text](<Screenshot 2024-04-08 141156.png>)

## HOMEPAGE:
![alt text](<Screenshot 2024-04-08 141208.png>)



## RESULT:
The program for performing server side processing is completed successfully.
