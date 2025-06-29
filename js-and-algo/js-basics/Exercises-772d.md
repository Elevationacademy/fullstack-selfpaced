# Exercises: Conditional Statements

## Exercise 1

**Basic Age Check**. Create variables for a person's age and use an if statement to check if they're old enough to vote (18 or older). Display an appropriate message.

```javascript
let age = 20;
// Your conditional code here
```


## Exercise 2

**Grade Classification**. Create a variable for a test score (0-100) and use if-else if-else statements to assign and display a letter grade:
- A: 90-100
- B: 80-89  
- C: 70-79
- D: 60-69
- F: Below 60

```javascript
let score = 85;
// Your conditional code here
```

## Exercise 3

**Weather Decision Making**. Create variables for temperature (in Celsius) and weather condition (sunny, rainy, cloudy). Use nested conditionals to decide what activity to recommend:
- If sunny and temp > 24°C: "Go to the beach"
- If sunny and temp 15-24°C: "Go for a walk"  
- If sunny and temp < 15°C: "Stay inside and read"
- If rainy: "Watch a movie indoors"
- If cloudy and temp > 21°C: "Go hiking"
- If cloudy and temp <= 21°C: "Visit a museum"

```javascript
let temperature = 20;
let weather = "sunny";
// Your conditional code here
```

## Exercise 4

**Multiple Condition Validator**. Create variables for username length, password length, and user age. Use logical operators (&&, ||, !) to check if a user can create an account:
- Username must be at least 5 characters
- Password must be at least 8 characters  
- User must be 13 or older
- Display specific error messages for each failed condition or success message if all pass

```javascript
let usernameLength = 6;
let passwordLength = 7;
let userAge = 15;
// Your conditional code here
```

## Exercise 5: 

**Complex Business Logic**. Create variables for customer type (regular, premium, vip), purchase amount, and day of week. Calculate discount using nested conditionals and ternary operators:
- VIP customers: 20% discount always
- Premium customers: 15% on weekends, 10% on weekdays
- Regular customers: 10% if purchase > $100, 5% if purchase > $50, 0% otherwise
- Weekends are represented by day 6 (Saturday) or 0 (Sunday)

```javascript
let customerType = "premium";
let purchaseAmount = 150;
let dayOfWeek = 6; // 0 = Sunday, 1 = Monday, etc.
// Your conditional code here
```

## Exercise 6

**Leap Year Calculator**. Create a variable for a year and determine if it's a leap year using conditional statements. A year is a leap year if:
- It's divisible by 4 AND
- If it's divisible by 100, then it must also be divisible by 400

```javascript
let year = 2024;
// Your conditional code here
// Examples: 2024 = leap, 1900 = not leap, 2000 = leap, 2023 = not leap
```