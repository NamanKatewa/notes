
# 1. Odd or Even

	Write a program that takes a number as input and checks if it is odd or even.
	Print "Even" if the number is even and "Odd" if it is odd.

```python

# Take input, convert the input to Integer
num = int(input("Enter number : "))

# Check if divisible by 2
if num % 2 == 0:
	print("Even")
else:
	print("Odd")

```


# 2. Grade Classification

	Write a program that takes a student's score (0 -100) as input & prints the grade based on the following criteria
	A : 90 and above
	B : 80 to 89
	C : 70 to 79
	D : 60 to 69
	F : Below 60

```python

# Take input, convert the input to Integer
marks = int(input("Enter marks : "))

# Marks in the range of 90 to 100
if marks >= 90 and marks <=100:
	print("A")

# marks in the range of 80 to 89
elif marks >=80 and marks <90:
	print("B")

# marks in the range of 70 to 79
elif marks >=70 and marks <80:
	print("C")

# marks in the range of 60 to 69
elif marks >=60 and marks <70:
	print("D")

# marks in the range of 0 to 59
elif marks >=0 and marks < 60:
	print("F")

# marks outside the range of 0 to 100
else:
	print("Invalid input")
```


# 3. Temperature Conversion

	Write a program that asks the user for a temperture in Celsius & converts it to Fahrenheit.
	Use the formula $F = (C * 9/5) + 32$.
	Print whether the temperature is "Hot", above 30°C
	or "Cold", 30°C or below, after the conversion.

```python

# Take input of temperature in Fahrenheit, convert the input to Decimal
tempF = float(input("Enter the temperature in Fahrenheit : "))

# Convert temperature to Celsius
tempC = (tempF - 32) * (5/9)

# Temp in Celsius higher than 30
if tempC > 30:
	print("Hot")

# Temp in Celsius lower than or equal to 30
else:
	print("Cold")

```


# 4. Leap Year Checker

	Write a program that takes a year as an input & checks whether it is a leap year
	Conditions for a leap year:
	1. Divisible by 4
	2. Not divisble by 100, unless also divisible by 400
	Print "Leap" or "Not Leap"

```python

# Take input, convert the input to Integer
year = int(input("Enter the year : "))

# Divisible by 400 OR (divisible by 4 AND dnot divisible by 100)
if (year % 400 == 0) or ((year % 4 == 0) and (year % 100 != 0) )
	print("Leap")
else:
	print("Not Leap")

```


# 5. Basic Login

	 Prompts the user for username & password. 
	 username - admin
	 password - password123
	 if username & password correct, print "Access Granted"
	 if incorrect print "Access Denied"

```python

# Define the username & password
user = "admin"
passw = "password123"

# Take username & password input, convert input to String
username = str(input("Enter username : "))
password = str(input("Enter password : "))

# Username & Password is correct
if (username == user) and (password == passw):
	print("Access Granted")

# Username & Password incorrect
else:
	print ("Access Denied")

```


# 6. Positive, Negative, Zero

	Takes a number as an input, & checks whether it is positive, negative or xero.

```python

# Take input, convert the input to Decimal
num = float(input("Enter the number : "))

# num is zero
if num == 0:
	print("Zero")

# num is greater than 0
elif num > 0:
	print("Positive")

# num is less than 0
else:
	print("Negative)

```

# 7. Shopping Discount

	Write a program that takes the total amount spent by a customer & applies a discount based on following criteria
	No discount for below 100
	10% discount for 100 to 499
	20% discount for 500 & above
	Print the final amount after discount

```python

# Take input, convertthe input to Decimal
amount = float(input("Enter the amount : "))

# Initialize the discount
discount = 0

# amount less than 100, and more than 0
if amount < 100 and amount > 0:
	discount = 0

# amount in range 100 to 499
elif amount >= 100 and amount < 500:
	# 10% discount
	discount = amount / 10

# amount more than or equal to 500
elif amount >= 500:
	# 20% discout
	discount = amount / 5

print(amount - discount)

```
