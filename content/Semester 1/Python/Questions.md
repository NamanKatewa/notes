
# 1. For loop to Print All Even Numbers Between limits

```python
lower_range: int = int(input("Enter the lower range: "))

upper_range: int = int(input("Enter the upper range: "))

  

for x in range(lower_range + 1, upper_range):

    if x % 2 == 0:

        print(x)
```


# 2. Table of a Number

```python
num: int = int(input("Enter a number: "))

  

for x in range(1, 11):

    print(f"{num} X {x} = {num*x}")
```


# 3. Factorial of a Number

```python
num: int = int(input("Enter a number: "))

  

product: int = 1

  

for x in range(2, num + 1):

    product *= x

  

print(f"Factorial of {num} is {product}")
```


# 4. Leap Year

```python
def isLeap(year: int) -> bool:

    leap: bool = False

    if year % 4 == 0:

        if year % 100 == 0:

            if year % 400 == 0:

                leap = True

            else:

                pass

        else:

            leap = True

    return leap

  
  

year: int = int(input("Enter an year: "))

check: bool = isLeap(year)

  

if check:

    print(f"{year} is a Leap Year")

else:

    print(f"{year} is not a Leap Year")
```


# 5. Fibonacci Series

```python
def fibonacci(n: int) -> list:

    num1: int = 0

    num2: int = 1

    series: list = [num1, num2]

    for x in range(n - 2):

        temp = num1 + num2

        series.append(temp)

        num1 = num2

        num2 = temp

    return series

  
  

number: int = int(input("Enter the number of terms to generate: "))

  

series = fibonacci(number)

print(series)
```

# 6. Pass, Continue Break

## print only even numbers, skip odd using **continue**

```python
for x in range(1, 20):

    if x % 2 == 1:

        continue

    print(x)
```

## stop the loop when number is 15 using **break**

```python
for x in range(1, 20):

    print(x)

    if x == 15:

        break
```

## **pass** statement

The pass statement is a placeholder when a statement is syntactically required but no code is required to run

EXAMPLE

```python
def placeholder_function()
	pass
```


# 7. Count vowels in a string

```python
vowels: list[str] = ["a", "e", "i", "o", "u", "A" , "E" ,"I", "O", "U"]

count: int = 0

  

string: str = input("Enter a string: ")

  

for x in string:

    if x in vowels:

        count += 1

  

print(f"There are {count} vowels in '{string}'")
```


# 8. Reverse a string

```python
inputString: str = input("Enter a string: ")

  
  

def revString(string: str) -> str:

    return string[::-1]

  
  

reversedString = revString(inputString)

  

print(f"The string '{inputString}' reversed is '{reversedString}'")
```


# 9. Dictionary Basics

## **Creating** and **Accessing** Dictionary

```python
students: dict = {"Alice": 85, "Bob": 78, "Charlie": 92, "Diana": 88, "Ethan": 76}

  

for name, marks in students.items():

    print(f"{name} scored {marks} marks.")
```

## **Updating** content in Dictionary

```python
students["Alice"] = 96


for name, marks in students.items():

    print(f"{name} scored {marks} marks.")
```


# 10. File Handling

## **Read** from file

```python
with open("students.xml", "r") as file:

    print(file.read())
```

## **Create** , **Add** to a file

```python
with open("test.txt", "w+") as file:

    file.write("This is a new line")

    file.seek(0)

    print(file.read())
```


# 11. Regular Expressions

## **Email Address**

```python
import re

  

pattern = r"^[\w%+-]+@[\w.-]+\.[a-z]{2,}$"

email_address = "namankatewa2004@gmail.com"

  

print(bool(re.match(pattern, email_address)))
```

## **All Occurrences**

```python
import re

  

pattern = r"\bthe\b"

text = "The quick brown fox jumps over the lazy dog. The fox is quick."

  

print(re.findall(pattern, text, re.IGNORECASE))
```


# 12. Inheritance

## **Single** Inheritance

```python
class Person:

    def __init__(self, name: str, age: int):

        self.name: str = name

        self.age: int = age

  

    def introduce(self):

        print(f"HI! I am {self.name} and I am {self.age} years old.")

  
  

class Student(Person):

    def __init__(self, name: str, age: int, student_id: str):

        super().__init__(name, age)

        self.id: str = student_id

  

    def study(self):

        print(f"{self.name} is studying. Student ID: {self.id}")

  
  

student = Student("Alice", 20, "S12345")

student.introduce()

student.study()
```

## **Multiple** Inheritance

```python
class Parent1:

    def skill1(self):

        print("Parent1: Good at cooking.")

  
  

class Parent2:

    def skill2(self):

        print("Parent2: Good at painting.")

  
  

class Child(Parent1, Parent2):

    def own_skill(self):

        print("Child: Excellent at coding.")

  
  

child = Child()

child.skill1()

child.skill2()

child.own_skill()
```

## **Multilevel** Inheritance

```python
class Grandparent:

    def family_history(self):

        print("Grandparent: Family has a rich history.")

  
  

class Parent(Grandparent):

    def parenting_skill(self):

        print("Parent: Good at parenting.")

  
  

class Child(Parent):

    def own_ambition(self):

        print("Child: Wants to be a software engineer.")

  
  

child = Child()

child.family_history()

child.parenting_skill()

child.own_ambition()
```


# 13. List

## **Largest** Number in List

```python
numbers: list[int] = [89, 34, 45, 32, 79, 69, 1, 0, 21]

  

largest_num: int = max(numbers)

  

print(largest_num)
```

## **Remove Duplicates** from a list

```python
numbers: list[int] = [89, 89, 34, 34, 45, 32, 79, 69, 1, 0, 21]

  

remove_duplicates: set = set(numbers)

  

numbers = list(remove_duplicates)

  

print(numbers)
```


# 14. Tuple

## **Length** of Tuple

```python
sample: tuple[int] = (89, 34, 45, 32, 79, 69, 1, 0, 21)

  

print(len(sample))
```

## **Max** and **Min** in tuple

```python
sample: tuple[int] = (89, 34, 45, 32, 79, 69, 1, 0, 21)

  
  

print(f"Maximum Number : {max(sample)}\nMinimum Number : {min(sample)}")
```


# 15. Packing & Unpacking Tuple

## **Unpacking**

```python
data: tuple[str, int, str] = ("Naman", 20, "New Delhi")

  

(name, age, city) = data

  

print(f"Name: {name}")

print(f"Age: {age}")

print(f"City: {city}")
```

## **Packing**

```python
name: str = input("Enter your name: ")

age: int = int(input("Enter your name: "))

city: str = input("Enter your city: ")

  

data: tuple[str, int, str] = (name, age, city)

  

(name, age, city) = data

  

print(f"Name: {name}")

print(f"Age: {age}")

print(f"City: {city}")
```


# 16. **Encapsulation**

```python
class BankAccount:

    def __init__(self, account_number: str, initial_balance: float = 0):

        self.__account_number: str = account_number

        self.__balance: float = initial_balance

  

    def get_balance(self):

        return self.__balance

  

    def deposit(self, amount: float):

        if amount > 0:

            self.__balance += amount

            print(f"Deposited {amount}. New Balance: {self.__balance}")

        else:

            print("Deposit amount must be positive.")

  

    def withdraw(self, amount: float):

        if 0 < amount <= self.__balance:

            self.__balance -= amount

            print(f"Withdrew {amount}. New balance: {self.__balance}")

  

        elif amount > self.__balance:

            print("Insufficient funds.")

  

        else:

            print("Withdrawl amount must be positive.")

  
  

account = BankAccount("12345678", 5000)

  

print("Account Balance:", account.get_balance())

  

account.deposit(1500)

account.withdraw(2000)

account.withdraw(10000)
```
