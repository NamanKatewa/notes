
# 1. Sum of even numbers

	Write a program that calculates the sum of all even numbers from 1 to a given number n (inclusive).

```python

# Take input, convert the input to Integer
n = int(input("Enter the num : "))

# Initialize sum to 0
sum = 0

# Run for loop from 1 to n, n+1 because range excludes the last parameter i.e (if we did range(1,n), it woud run till n -1, excluding n)
for i in range (1, n+1):
	#shorthand for sum = sum + i
	sum += i
print(sum)

```


# 2. Factorial

	Write a program that takes a nukber n as input and calculates its factorial using while loop.
	Include a condition to habdle negative inputs by printing "Not Valid"


```python

# Take input, convert the input to Integer
n = int(input("Enter the num : "))

# Check negative
if n < 0 :
	print("Not Valid")

# Not Negative
else:
	# Initialize result & count
	result = 1
	count = 1
	
	# Runs till count reaches the number
	while count <=n :
		# Shorthand for result = result * count
		result *= count
		count +=1
	print(result)

```


# 3. Prime Number Checker

	Write a program that takes a number n as input & checks if it a prime number.
	Print "Prime" or "Not Prime"

```python

num = int(input("Enter the num : "))

# Assume a prime number until proven otherwise
prime = True

# Less than or equals to one, means not a prime
if num <= 1:
	prime = False
else:
	# Run for loop from 2 to square root of the number
	for i in range(2, int(num**0.5) +1):
		# divisible by any number, not a prime
		if num % i == 0:
			prime = False
			# Proven not prime, so no need to run the for loop after this, so break
			break

if prime:
	print("Prime")
else:
	print("Not Prime")

```


# 4. Fibonacci Sequence

	Write a program that generates fibonacci sequence upto provided n-th term.
	Also to print "Even" or "Odd" for each term.

```python

n = int(input("Enter the num : "))

# Initialize the first two terms
a = 0
b = 1

# Initialize count
count = 0

# Will run upto n, will not run when eqaul to n
while count < n:
	# Print the term
	print(a)
	# Print even or odd
	if a % 2 == 0 :
		print("Even")
	else:
		print("Odd")
	
	# Update a to b
	a = b
	# Update b to the sum of a & b
	b = a + b
	# Increase the count
	count += 1
```

# 5. Counting Vowels

	Write a program that takes a string as an input and counts the number of vowels in the string.
	Print the count of vowels

```python

string = str(input("Enter the string : "))

# Initialize the vowels
vowels = "aeiou"
# Initialize the count
count = 0

# Iterate through the string
for char in string:
	# Check if the char is in vowels & increase the count
	if char in vowels:
		count +=1

# Print the number of vowels
print(count)

```


# 6. Guess the Number

	Write a simple game where the user has to guess the number.
	After each guess, print whether the guess is "Too High", "Too Low", "Correct"

```python

# The number to guess
num = 69

# Initialize guess to Nothing, dont initialize as a number
guess = None

# Will run until the user guesses the correct num
while guess != num:
	# Take input for guess
	guess = int(input("Enter guess : "))
	
	if guess < num:
		print("Too Low")
	elif guess > num:
		print("Too High")
	else:
		# If this condition is true that means the guess = num. While loop wont run further
		print("Correct")

```



# 7. Printing Patterns

	Write a program that takes a number as input, and prints a right-agnled triangle from "*" of height n.
	
		for eg - : n = 4
		*
		**
		***
		****

```python

n = int(input("Enter num : "))

for i in range(1, n+1):
	# print "*", i number of times
	print("*" * i)

```


# 8. Sum of Digits

	Write a program that takes a positive integer as input & calculates the sum of its digits

```python

n = int(input("Enter the num : "))

# Initialize the sum to 0
sum = 0

# Will run till the number is greater than 0, not negative integers
while n > 0:
	# sum is set to the last digit of the number, using modulus returns the remainder
	sum += number % 10
	# change the number to remove the last digit, // returns only the dividend
	num //= 10

print(sum)

```