def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Error: Division by zero"
    return x / y

def main():
    print("Simple Calculator Tool")
    print("Supported operations: +, -, *, /")
    print("Enter your calculation in the format: number operator number")
    print("Type 'exit' to quit.\n")
    
    while True:
        user_input = input("Calc> ")
        if user_input.lower() == "exit":
            print("Exiting Calculator. Goodbye!")
            break
        
        try:
            # Split input into tokens expecting a format like: 3 + 4
            tokens = user_input.split()
            if len(tokens) != 3:
                print("Invalid input. Please enter in format: number operator number")
                continue
            
            num1, op, num2 = tokens
            num1 = float(num1)
            num2 = float(num2)
            
            if op == "+":
                result = add(num1, num2)
            elif op == "-":
                result = subtract(num1, num2)
            elif op == "*":
                result = multiply(num1, num2)
            elif op == "/":
                result = divide(num1, num2)
            else:
                print("Unsupported operator. Use +, -, *, or /.")
                continue
            
            print("Result:", result)
        except Exception as e:
            print("Error:", e)

if __name__ == "__main__":
    main()
