def calculate(numberOne, numberTwo, operation):
    match operation:
        case "+":
            return numberOne + numberTwo
        case "-":
            return numberOne - numberTwo
        case "*":
            return numberOne * numberTwo
        case "/":
            if(numberTwo == 0):
                return("Error: Division by zero")
            return numberOne / numberTwo
        case "%":
            if(numberTwo == 0):
                return("Error: Division by zero")
            return numberOne % numberTwo
        case "**":
            return numberOne ** numberTwo
        case _:
            return "Invalid Result"

listOperations = {
    "+"            : "Addition",
    "-"            : "Subtraction",
    "*"            : "Multiplication",
    "/"            : "Division",
    "%"            : "Module",
    "**"           : "Power",
    "history"      : "See History",
    "clear"        : "delete history",
    "save history" : "Save in txt",
    "exit"         : "Exit"
}

history = []

def addHistory(numberOne, numberTwo, operation, result):
    history.append(f"{numberOne} {operation} {numberTwo} = {result}")

def showHistory(history):
    print("\n--- HISTORY ---")
    if(not history):
        print("There is no history\n")
        return

    for item in history:
        print(item)

def deleteHistory(history):
    if(not history):
        print("\n There is no history to delete.");
        return
    
    print("\n --- Deleting History ---")

    history.clear()

def saveInTxt(history):
    if(not history):
        print("There's no way to save")
        return
    
    for item in history:
        with open("calculate.txt", "a", encoding="utf-8") as file:
            file.write(item + "\n")

while True:
        print("\n Available operations")
        for op, name in listOperations.items():
            print(f"{op} -> {name}")

        operation = input("Desired operation: ")

        if(operation == "exit"):
            break

        if(operation == "history"):
            showHistory(history)
            continue

        if(operation == "clear"):
            deleteHistory(history)
            continue

        if(operation == "save history"):
            saveInTxt(history)
            continue

        try:
            numberOne   = int(input("Digite um número: "))
            numberTwo   = int(input("Digite outro número: "))
        except ValueError:
            print("Error: You did not enter a valid number. \n")
            continue

        result      = calculate(numberOne, numberTwo, operation)
        addHistory(numberOne, numberTwo, operation, result)

        print("The result is:", result, "\n")
