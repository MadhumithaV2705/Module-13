# Exp.No:34  
## PREFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction.

---

### ALGORITHM

1. **Start the program.**
2. Define a set of valid operators: `*, -, +, %, /, **`.
3. Initialize an empty stack.
4. Traverse the prefix expression from **right to left**:
   - If the character is a **digit**, convert it to an integer and push it onto the stack.
   - If the character is an **operator**, pop two elements from the stack.
     - Apply the operator on the two popped operands.
     - Push the result back onto the stack.
   - If an invalid character is encountered, raise an error.
5. After traversal, the stack should contain only **one element**.
6. Return the **single element** as the evaluation result.
7. **End the program.**

---

### PROGRAM

```
Reg.No: 212223060145
Name: Madhumitha V

OPERATORS=set(['*','-','+','%','/','**']) 
def evaluate(expression):
	stack = []

	for c in expression[::-1]:

		if c not in OPERATORS:
			stack.append(int(c))
		else:
			o1 = stack.pop()
			o2 = stack.pop()

			if c == '+':
				stack.append(o1 + o2)

			elif c == '-':
				stack.append(o1 - o2)

			elif c == '*':
				stack.append(o1 * o2)
	return stack.pop()
			    
test_expression = input()
print("Prefix Expression :",test_expression)
print("Evaluation result :", evaluate(test_expression))

```


### OUTPUT
<img width="819" height="244" alt="image" src="https://github.com/user-attachments/assets/e0d6f5de-34b5-468f-b28d-dc908d7356d0" />

### RESULT
The program evaluates the given prefix expression using stack operations and displays the final result.
