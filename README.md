# Build-a-calculator-CLI-app
Create a command-line calculator supporting basic operations
# calculator.py

def add(x, y):
    """Add two numbers."""  # Docstring for function description
    return x + y

def subtract(x, y):
    """Subtract the second number from the first."""
    return x - y

def multiply(x, y):
    """Multiply two numbers."""
    return x * y

def divide(x, y):
    """Divide the first number by the second."""
    if y == 0:  # Check for division by zero
        raise ValueError("Cannot divide by zero!")  # Raise an error if true
    return x / y

def main():
    print("Welcome to the Command-Line Calculator!")  # Greeting
    print("Supported operations: + (add), - (subtract), * (multiply), / (divide)")
    print("Type 'exit' to quit.")

    while True:  # Infinite loop for continuous operation
        operation = input("\nEnter operation (+, -, *, /) or 'exit': ").strip()  # Get operation, remove extra spaces

        if operation.lower() == 'exit':  # Case-insensitive exit check
            print("Goodbye!")
            break  # Exit the loop

        if operation not in ['+', '-', '*', '/']:  # Validate operation
            print("Invalid operation! Please try again.")
            continue  # Skip to next iteration

        try:
            num1 = float(input("Enter first number: "))  # Convert to float
            num2 = float(input("Enter second number: "))
        except ValueError:  # Handle non-numeric input
            print("Invalid input! Please enter numbers.")
            continue

        try:
            if operation == '+':  # Call appropriate function
                result = add(num1, num2)
            elif operation == '-':
                result = subtract(num1, num2)
            elif operation == '*':
                result = multiply(num1, num2)
            elif operation == '/':
                result = divide(num1, num2)

            print(f"Result: {result}")  # Output the result
        except ValueError as e:  # Catch division by zero or other errors
            print(f"Error: {e}")

if __name__ == "__main__":  # Standard Python idiom to run main() when script is executed directly
    main()
