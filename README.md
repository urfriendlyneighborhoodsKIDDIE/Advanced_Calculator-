# Credit - sKIDDIE - Python

import math

def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    try:
        return x / y
    except ZeroDivisionError:
        print("error")
        return None

def power(x, y):
    return x ** y

def root(x, y):
    try:
        return x ** (1 / y)
    except Exception:
        print("error")
        return None

def factorial(x):
    try:
        return math.factorial(x)
    except Exception:
        print("error")
        return None

def sin(x):
    return math.sin(math.radians(x))

def cos(x):
    return math.cos(math.radians(x))

def tan(x):
    try:
        return math.tan(math.radians(x))
    except Exception:
        print("error")
        return None

def log(x, base):
    try:
        return math.log(x, base)
    except Exception:
        print("error")
        return None

def show_menu():
    print("\nSelect operation:")
    print("1. Add")
    print("2. Subtract")
    print("3. Multiply")
    print("4. Divide")
    print("5. Power (x^y)")
    print("6. Root (x^(1/y))")
    print("7. Factorial")
    print("8. Sine")
    print("9. Cosine")
    print("10. Tangent")
    print("11. Logarithm")
    print("0. Exit")

def main():
    while True:
        show_menu()
        try:
            choice = int(input("Enter choice (0-11): "))
        except ValueError:
            print("error")
            continue

        if choice == 0:
            print("Exiting calculator.")
            break

        if choice in [1,2,3,4,5,6,11]:
            try:
                num1 = float(input("Enter first number: "))
                num2 = float(input("Enter second number: "))
            except ValueError:
                print("error")
                continue

            if choice == 1:
                print("Result:", add(num1, num2))
            elif choice == 2:
                print("Result:", subtract(num1, num2))
            elif choice == 3:
                print("Result:", multiply(num1, num2))
            elif choice == 4:
                result = divide(num1, num2)
                if result is not None:
                    print("Result:", result)
            elif choice == 5:
                print("Result:", power(num1, num2))
            elif choice == 6:
                result = root(num1, num2)
                if result is not None:
                    print("Result:", result)
            elif choice == 11:
                result = log(num1, num2)
                if result is not None:
                    print("Result:", result)
        elif choice == 7:
            try:
                num = int(input("Enter an integer: "))
                print("Result:", factorial(num))
            except ValueError:
                print("error")
        elif choice in [8,9,10]:
            try:
                angle = float(input("Enter angle in degrees: "))
