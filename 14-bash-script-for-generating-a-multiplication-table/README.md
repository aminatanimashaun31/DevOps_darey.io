# Bash Script For Generating a Multiplication Table
**Objective:** Create a Bash script that generates a multiplication table for a number entered by the user. This project will help you practice using loops, handling user input, and applying conditional logic in Bash scripting.
## Project Description
Your script should prompt the user to enter a number and then ask if they prefer to see a full multiplication table from 1 to 10 or a partial table within a specified range. Based on the user's choice, the script will display the corresponding multiplication table.
## Project Requirements
**User Input for Number:** The script must first ask the user to input a number for which the multiplication table will be generated.

**Choice of Table Range:** Next, ask the user if they want a full multiplication table (1 to 10) or a partial table. If they choose partial, prompt them for the start and end of the range.

**Use of Loops:** Implement the logic to generate the multiplication table using loops. You may use either the list form or C-style for loop based on what's appropriate.

**Conditional Logic:** Use if-else statements to handle the logic based on the user's choices (full vs. partial table and valid range input).

**Input Validation:** Ensure that the user enters valid numbers for the multiplication table and the specified range. Provide feedback for invalid inputs and default to a full table if the range is incorrect.

**Readable Output:** Display the multiplication table in a clear and readable format, adhering to the user's choice of range.

**Comments and Code Quality:** Your script should be well-commented, explaining the purpose of different sections and any important variables or logic used. Ensure the code is neatly formatted for easy readability.

 **Example Script Flow:**
 1. Prompt the user to enter a number for the multiplication table.
2. Ask if they want a full table or a partial table.
•
If partial, prompt for the start and end numbers of the range.
3. Validate the range inputs and handle invalid or out-of-bound entries.
4. Generate and display the multiplication table according to the specified range.
5. Provide clear output formatting for ease of reading. Bonus
6. Enhanced User Interaction: Incorporate additional checks or features, like repeating the program for another number without restarting the script.
7. Creative Display Options: Offer different formatting styles for the table display and let the user choose.

Below is an example output for a full multiplication:
```
The full multiplication table for 3:
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
3 x 6 = 18
3 x 7 = 21
3 x 8 = 24
3 x 9 = 27
3 x 10 = 30
```
Below is an example output for a partial table display:

If the user chooses a partial table:

```
Enter a number for the multiplication table: 3

Do you want a full table or a partial table? (Enter 'f' for full, 'p' for partial): p

Enter the starting number (between 1 and 10): 2

Enter the ending number (between 1 and 10): 4

The partial multiplication table for 3 from 2 to 4:
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
```

**Handling Invalid Range** If the user enters an invalid range:

```
Enter a number for the multiplication table: 3
Do you want a full table or a partial table? (Enter 'f' for full, 'p' for partial): p

Enter the starting number (between 1 and 10): 8

Enter the ending number (between 1 and 10): 2

Invalid range. Showing full table instead.
The full multiplication table for 3:
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
3 x 6 = 18
3 x 7 = 21
3 x 8 = 24
3 x 9 = 27
3 x 10 = 30
```

This project is designed to be a practical application of Bash scripting fundamentals, focusing on loops, conditional logic, and user interaction. By completing this task, you'll gain valuable experience in
automating tasks and improving your scripting proficiency.

Objective: Write a Bash script that generates a multiplication table for a given number. The script should prompt the user to enter a number and then display the multiplication table for that number up to 10. Your task is to use both styles of for loops to achieve this: the list form and the C-style form.
![multiplication_table_script](./img/multiplication_table-script.png)

![multiplication_script_contd](./img/multiplication_table_script_contd.png)

**Part 1: Using List Form For Loop** Prompt the User: First, your script should ask the user to input a number. Use the read command to capture this input into a variable.

Generate Multiplication Table: Use a list form **for** loop to iterate through the numbers 1 to 10. In each
iteration, calculate the product of the user's number and the iterator variable, then print the result in a clear format.

Example output for a number is:
```
Enter a number: 3
3 x 1 = 3
3 x 2 = 6
...
3 x 10 = 30
```

![list-form-for-loop](./img/list-form-for-loop.png)
**Part 2: Using C-style For Loop** Repeat the Prompt: You don't need to ask the user again if you're making this a single script. Just proceed with the C-style loop using the same variable.

Generate Multiplication Table with C-style Loop: Now, write a C-style for loop to achieve the same task as in Part 1. Compare how this approach differs from the list form loop in terms of syntax and clarity.

![c-style-for-loop](./img/c-style-for-loop.png)

### Guidelines:
- Make sure the output is user-friendly and clearly formatted.

- Comment your code to explain which part is using the list form and which part is using the C-style.

- Bonus: Ask the user if they want to see the table in ascending or descending order, and implement this feature using if-else statements combined with your loop of choice.
![result](./img/result.png)
