# Ex.03 Design a Website for Server Side Processing
## Date: 10.11.2026

## AIM:
To create a web page to calculate Churn Rate using server-side scripts.

## FORMULA:
Churn Rate = (CustLost / InitCust) * 100
<br> InitCust --> Initial Customers Count
<br> CustLost --> Customers Lost Count

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create a HTML file to implement form based input and output.

### Step 5:
Create python programs for views and urls to perform server side processing.

### Step 6:
Receive input values from the form using request.POST.get().

### Step 7:
Calculate the Result using the given formula.

### Step 8:
Display the calculated result in the server console.

### Step 9:
Render the result to the HTML template.

### Step 10:
Publish the website in Localhost.

## PROGRAM:
```
math.html


<html>
    <head>
        <title>Churn rate
            </title>
        </head>
        <body bgcolor="aqua">
            <h1>POOJA SHREE K</h1>
            <h2>26018233</h2>
            <form method="POST">
            {%csrf_token %}<br><br>
                

        <label>INITIAL CUSTOMER:</label>
        <input type="number" name="initial_cust" value="{{l}}" ><br><br>

        <label>PRESENT CUSTOMER:</label>
        <input type="number" name="present_cust" value="{{i}}" ><br><br>

        <input type="submit" value="Calculate"><br><br>

        <label>CHURN RATE:</label>
        <input type="number" value="{{churnrate}}"><br><br>

            </form>
        </body>


        views.py



        from django.shortcuts import render

def churn_rate(request):
    l = float(request.POST.get('initial_cust', '0'))
    i = float(request.POST.get('present_cust', '0'))

    churnrate = (l/i)*100 if request.method == 'POST' and i != 0 else 0

    print("INITIAL CUSTOMER =", l)
    print("PRESENT CUSTOMER=", i)
    print("CHURN RATE =", churnrate)

    return render(
        request,
        'mathapp/math.html',
        {'l': l, 'i': i, 'churnrate': churnrate}
    )

    urls.py


from django.contrib import admin
from django.urls import path
from mathapp import views

urlpatterns = [
    path('', views.churn_rate, name='churn_rate'),
]


```


## OUTPUT - SERVER SIDE:

![alt text](<Screenshot (32)-1.png>)

## OUTPUT - WEBPAGE:

![alt text](<Screenshot (34)-1.png>)

## RESULT:
The the web page to calculate Churn Rate using server-side scripts is created successfully.
