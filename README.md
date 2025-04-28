# Scientific-calcy
import math

def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y


def divide(x, y):
    if y == 0:
        return "Error! Division by zero."
    return x / y

def square_root(x):
    if x < 0:
        return "Error! Negative number cannot have a square root."
    return math.sqrt(x)

def trigonometry(choice, angle):
    angle_rad = math.radians(angle) 
    if choice == 'sin':
        return math.sin(angle_rad)
    elif choice == 'cos':
        return math.cos(angle_rad)
    elif choice == 'tan':
        return math.tan(angle_rad)
    elif choice == 'sec':
        return 1 / math.cos(angle_rad)
    elif choice == 'csc':
        return 1 / math.sin(angle_rad)
    elif choice == 'cot':
        return 1 / math.tan(angle_rad)


def logarithm(x, base=10):
    if x <= 0:
        return "Error! Logarithm undefined for non-positive values."
    return math.log(x, base)

def power(base, exponent):
    return math.pow(base, exponent)


def symbolic_expression(expr):
    try:
       
        sym_expr = sp.sympify(expr)
        return sym_expr.simplify()
    except:
        return "Error! Invalid expression."

def main():
    print("Scientific Calculator")

    while True:
        print("\nSelect an operation:")
        print("1. Addition (+)")
        print("2. Subtraction (-)")
        print("3. Multiplication (*)")
        print("4. Division (/)")
        print("5. Square Root (sqrt)")
        print("6. Trigonometry (sin, cos, tan, sec, csc, cot)")
        print("7. Logarithm (log)")
        print("8. Exponentiation (x^y)")
        print("9. Symbolic Expression (Advanced)")
        print("0. Exit")

      
        choice = input("Enter choice: ")

        if choice == '0':
            print("Exiting Calculator.")
            break

        if choice in ['1', '2', '3', '4', '8']:
            num1 = float(input("Enter first number: "))
            num2 = float(input("Enter second number: "))

        if choice == '1':
            print(f"{num1} + {num2} = {add(num1, num2)}")

        elif choice == '2':
            print(f"{num1} - {num2} = {subtract(num1, num2)}")

        elif choice == '3':
            print(f"{num1} * {num2} = {multiply(num1, num2)}")

        elif choice == '4':
            print(f"{num1} / {num2} = {divide(num1, num2)}")

        elif choice == '5':
            num = float(input("Enter number for square root: "))
            print(f"Square root of {num} = {square_root(num)}")

        elif choice == '6':
            trig_choice = input("Enter trigonometric function (sin, cos, tan, sec, csc, cot): ").lower()
            angle = float(input("Enter angle in degrees: "))
            print(f"{trig_choice}({angle}) = {trigonometry(trig_choice, angle)}")

        elif choice == '7':
            num = float(input("Enter number for logarithm: "))
            base = float(input("Enter base (default 10): ") or 10)
            print(f"log({num}, {base}) = {logarithm(num, base)}")

        elif choice == '8':
            base = float(input("Enter base: "))
            exponent = float(input("Enter exponent: "))
            print(f"{base}^{exponent} = {power(base, exponent)}")

        elif choice == '9':
            expr = input("Enter symbolic expression (e.g., 2*x + 3): ")
            print(f"Simplified expression: {symbolic_expression(expr)}")

        else:
            print("Invalid Input! Please select a valid option.")

if __name__ == "__main__":
    main()
