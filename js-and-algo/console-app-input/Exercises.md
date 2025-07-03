# Exercises

## Exercise 1

Create a simple calculator that takes two numbers and an operation from command line arguments.

- Take 3 arguments: number1, operation (+, -, *, /), number2
- Perform the calculation and display result
- Use `process.argv`
- Handle invalid operations

Example:
```bash
node calculator.js 10 + 5
# Output: 10 + 5 = 15

node calculator.js 20 / 4
# Output: 20 / 4 = 5
```

## Exercise 2

Create a quiz with 3 questions and score tracking.

- Install and use `prompt-sync`
- Ask 3 questions (any topic you like)
- Use an array to store questions and answers (adding a question and answer to the array will prompt 4 questions...)
- Keep track of correct answers
- Display final score

```js
// Question 1: What is 2 + 2?
// Question 2: What is the capital of France?
// Question 3: What year is it?
// Final Score: 2/3 correct!
```

## Exercise 3

Create a user registration system that collects user information.

- Use `readline` 
- Collect: name, email, age, favorite color
- Display a summary of entered information

Example Output:
```bash
Registration Summary:
Name: John Doe
Email: john@example.com
Age: 25
Favorite Color: Blue
```

## Exercise 4

Create a simple banking system with menu options.

- Display menu: 1) Check Balance, 2) Deposit, 3) Withdraw, 4) Exit
- Validate menu choices (only accept 1-4)
- For deposit/withdraw: validate positive numbers only
- Keep running until user chooses exit
- Use any input method you prefer

Example:
```bash
=== Banking System ===
1) Check Balance
2) Deposit Money
3) Withdraw Money
4) Exit
Choose option (1-4): 2
Enter amount to deposit: $50
New balance: $150
```