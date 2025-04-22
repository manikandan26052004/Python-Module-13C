# Postfix Expression Evaluation using Stack

## 📌 Aim
To write a Python program that evaluates a given **postfix expression** using a stack. The program will handle valid postfix expressions consisting of two-digit numbers and binary operators (`+`, `-`, `*`, `/`, `%`).

---

## 🛠 Procedure
1. Define the set of valid operators: `+`, `-`, `*`, `/`, `%`.
2. Initialize an empty stack to store operands.
3. Split the input expression into individual tokens (numbers and operators).
4. Iterate over the tokens:
   - If the token is a number, push it onto the stack.
   - If the token is an operator, pop two numbers from the stack, apply the operator, and push the result back onto the stack.
5. After processing all tokens, the final result will be the only element remaining in the stack.

---

## 💻 Program

```python
OPERATORS = set(['+', '-', '*', '/', '%'])

def evaluate_postfix(expression):
    stack = []
    
    for char in expression.split():  
        if char.isdigit():  
            stack.append(int(char))
        elif char in OPERATORS:
            b = stack.pop()
            a = stack.pop()
            if char == '+':
                stack.append(a + b)
            elif char == '-':
                stack.append(a - b)
            elif char == '*':
                stack.append(a * b)
            elif char == '/':
                stack.append(a / b)  
            elif char == '%':
                stack.append(a % b)
    
    return stack[0]

expression = input("Enter a postfix expression: ")
print("Postfix expression:", expression)
print("Evaluation result:", evaluate_postfix(expression))
```
---
## OutPut

![image](https://github.com/user-attachments/assets/02f7165c-9b01-4ab6-b5c8-16612d2ca384)

---
## Result

Thus, the program was successfully created and executed to evaluate a postfix expression.
