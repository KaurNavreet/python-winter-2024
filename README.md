# python-winter-2024

1# Function to convert temperature from Fahrenheit to Celsius
def fahrenheit_to_celsius(temperature: float) -> float:
    """
    Converts temperature from Fahrenheit to Celsius.

    Parameters:
    temperature (float): Temperature in Fahrenheit.

    Returns:
    float: Equivalent temperature in Celsius.
    """
    # Conversion formula from Fahrenheit to Celsius
    celsius = (temperature - 32) * 5 / 9
    return celsius

# Function to solve quadratic equation
def quadratic_solver(a: float, b: float, c: float) -> tuple:
    """
    Solves a quadratic equation of the form ax^2 + bx + c = 0.

    Parameters:
    a (float): Coefficient of x^2.
    b (float): Coefficient of x.
    c (float): Constant term.

    Returns:
    tuple: Two possible solutions as a tuple.
    """
    # Calculate discriminant
    discriminant = b**2 - 4*a*c
    if discriminant >= 0:
        # Calculate roots if discriminant is non-negative
        root1 = (-b + discriminant**0.5) / (2*a)
        root2 = (-b - discriminant**0.5) / (2*a)
        return (root1, root2)
    else:
        return ("No real roots")

# Function to calculate sum of squares of given numbers
def sum_of_squares(*args: float) -> float:
    """
    Calculates the sum of squares of a variable number of arguments.

    Parameters:
    *args (float): Variable number of arguments.

    Returns:
    float: Sum of squares of the arguments.
    """
    # Calculate sum of squares using list comprehension
    return sum(arg**2 for arg in args)

# Function to calculate BMI (Body Mass Index)
def calculate_bmi(weight: float, height: float) -> float:
    """
    Calculates the Body Mass Index (BMI) of a person.

    Parameters:
    weight (float): Weight in kilograms.
    height (float): Height in meters.

    Returns:
    float: BMI.
    """
    # Calculate BMI using weight and height
    bmi = weight / (height ** 2)
    return bmi

# Function to calculate factorial of a non-negative integer
def factorial(n: int) -> int:
    """
    Calculates the factorial of a non-negative integer.

    Parameters:
    n (int): Non-negative integer for which factorial is to be calculated.

    Returns:
    int: Factorial value.
    """
    # Base case: factorial of 0 is 1
    if n == 0:
        return 1
    else:
        # Recursive call to calculate factorial
        return n * factorial(n - 1)

# Function to get user input and display results
def main():
    while True:
        print("\n1. Fahrenheit to Celsius Converter")
        print("2. Quadratic Equation Solver")
        print("3. Sum of Squares Calculator")
        print("4. Body Mass Index (BMI) Calculator")
        print("5. Factorial Calculator")
        print("6. Exit")

        choice = int(input("Enter your choice (1-6): "))

        if choice == 1:
            temperature = float(input("Enter temperature in Fahrenheit: "))
            print("Equivalent temperature in Celsius:", fahrenheit_to_celsius(temperature))
        elif choice == 2:
            a = float(input("Enter coefficient of x^2: "))
            b = float(input("Enter coefficient of x: "))
            c = float(input("Enter constant term: "))
            print("Roots of the quadratic equation:", quadratic_solver(a, b, c))
        elif choice == 3:
            numbers = [float(x) for x in input("Enter numbers separated by spaces: ").split()]
            print("Sum of squares:", sum_of_squares(*numbers))
        elif choice == 4:
            weight = float(input("Enter weight in kilograms: "))
            height = float(input("Enter height in meters: "))
            print("BMI:", calculate_bmi(weight, height))
        elif choice == 5:
            n = int(input("Enter a non-negative integer: "))
            print("Factorial:", factorial(n))
        elif choice == 6:
            print("Exiting...")
            break
        else:
            print("Invalid choice!")

if __name__ == "__main__":
    main()

