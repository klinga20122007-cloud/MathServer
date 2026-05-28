# Ex.04 Design a Website for Server Side Processing
## Date:

## AIM:
To create a web page to calculate total bill amount with GST from price and GST percentage using server-side scripts.

## FORMULA:
Bill = P + (P * GST / 100)
<br> P --> Price (in Rupees)
<br> GST --> GST (in Percentage)
<br> Bill --> Total Bill Amount (in Rupees)

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
Calculate the total bill amount (including GST).

### Step 8:
Display the calculated result in the server console.

### Step 9:
Render the result to the HTML template.

### Step 10:
Publish the website in Localhost.

## PROGRAM:
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>GST Calculator</title>

    <style>

        *{
            margin:0;
            padding:0;
            box-sizing:border-box;
            font-family:Arial, sans-serif;
        }

        body{
            height:100vh;
            display:flex;
            justify-content:center;
            align-items:center;
            background:linear-gradient(to right, #4facfe, #00f2fe);
        }

        .container{
            width:400px;
            background:white;
            padding:35px;
            border-radius:15px;
            box-shadow:0px 0px 20px rgba(0,0,0,0.2);
        }

        h2{
            text-align:center;
            margin-bottom:25px;
            color:#333;
        }

        label{
            font-weight:bold;
            display:block;
            margin-bottom:8px;
            color:#444;
        }

        input{
            width:100%;
            padding:12px;
            border:1px solid #ccc;
            border-radius:8px;
            margin-bottom:20px;
            font-size:16px;
        }

        button{
            width:100%;
            padding:12px;
            border:none;
            border-radius:8px;
            background:#007bff;
            color:white;
            font-size:16px;
            cursor:pointer;
            transition:0.3s;
        }

        button:hover{
            background:#0056b3;
        }

        .result{
            margin-top:25px;
            background:#f5f5f5;
            padding:20px;
            border-radius:10px;
        }

        .result p{
            margin:10px 0;
            font-size:18px;
            font-weight:bold;
            color:#333;
        }

        .total{
            color:green !important;
            font-size:22px !important;
        }

        .error{
            margin-top:20px;
            color:red;
            text-align:center;
            font-weight:bold;
        }

    </style>
</head>

<body>

    <div class="container">

        <h2>GST Calculator</h2>

        <form method="POST">

            {% csrf_token %}

            <label>Price</label>
            <input type="number" name="price" required>

            <label>GST (%)</label>
            <input type="number" name="gst" required>

            <button type="submit">Calculate</button>

        </form>

        {% if gst_amt is not None %}

            <div class="result">

                <p>Price : ₹ {{ request.POST.price }}</p>

                <p>GST Percentage : {{ request.POST.gst }}%</p>

                <p>GST Amount : ₹ {{ gst_amt|stringformat:".2f" }}</p>

                <p class="total">
                    Total Amount : ₹ {{ total_amt|stringformat:".2f" }}
                </p>

            </div>

        {% endif %}

    </div>

</body>

</html>
```

## OUTPUT - SERVER SIDE:

<img width="936" height="342" alt="{B83A2D2C-6768-4F3F-98D3-FFFDA7E82075}" src="https://github.com/user-attachments/assets/58767f18-0549-4294-b211-392c0e71c3e8" />


## OUTPUT - WEBPAGE:

<img width="1915" height="995" alt="{D3FE8987-A457-434D-86AB-7C1FD5D1ED75}" src="https://github.com/user-attachments/assets/657beeca-9575-4d0b-b23f-ca18af0597dc" />



## RESULT:
The a web page to calculate total bill amount with GST from price and GST percentage using server-side scripts is created successfully.
