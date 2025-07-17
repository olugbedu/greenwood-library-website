# Bash Multiplication Table Generator

## Project Overview

This project implements a Bash script that generates multiplication tables for user-specified numbers. The script provides flexibility in choosing between full tables (1-10) or partial tables with custom ranges, demonstrating proficiency in Bash scripting fundamentals including loops, conditional logic, and user interaction.

## Features

- **Interactive User Input**: Prompts for number and table type preferences
- **Flexible Range Options**: Full multiplication table (1-10) or custom partial ranges
- **Input Validation**: Handles invalid inputs with appropriate error messages
- **Multiple Loop Implementations**: Demonstrates both list-form and C-style for loops
- **Clear Output Formatting**: User-friendly display of multiplication results
- **Error Handling**: Graceful handling of invalid ranges and inputs

## Requirements Analysis

### Core Requirements Addressed

1. **User Input for Number**
   - Script prompts user to enter a number for multiplication table generation
   - Uses `read` command to capture input into variables

2. **Choice of Table Range**
   - Asks user to choose between full table (1-10) or partial table
   - For partial tables, prompts for start and end range values

3. **Use of Loops**
   - Implements both list-form and C-style for loops
   - Demonstrates different loop syntax approaches

4. **Conditional Logic**
   - Uses if-else statements for user choice handling
   - Validates range inputs and table type selection

5. **Input Validation**
   - Validates numeric inputs
   - Checks range boundaries (1-10)
   - Provides fallback to full table for invalid ranges

6. **Readable Output**
   - Clear, formatted multiplication table display
   - Consistent formatting across different table types

7. **Comments and Code Quality**
   - Well-commented code explaining logic and sections
   - Clean, readable formatting

## Implementation Steps

### Step 1: Project Setup
```bash
# Create the script file
touch multiplication_table.sh
chmod +x multiplication_table.sh
```

### Step 2: User Input Collection
- Implement user prompting for the base number
- Add choice selection for full vs. partial table
- Collect range parameters for partial tables

### Step 3: Input Validation Implementation
- Validate numeric inputs using conditional statements
- Check range boundaries (1-10)
- Implement error handling for invalid inputs

### Step 4: Loop Implementation - List Form
```bash
# List form loop example
for i in {1..10}; do
    result=$((number * i))
    echo "$number x $i = $result"
done
```

### Step 5: Loop Implementation - C-style
```bash
# C-style loop example
for ((i=start; i<=end; i++)); do
    result=$((number * i))
    echo "$number x $i = $result"
done
```

### Step 6: Conditional Logic Integration
- Implement if-else statements for table type selection
- Add range validation logic
- Handle invalid input scenarios

### Step 7: Output Formatting
- Design clear, consistent output format
- Implement different display options for full vs. partial tables
- Add informative headers and error messages

## Usage Examples

### Full Table Generation
```
Enter a number for the multiplication table: 3
Do you want a full table or a partial table? (Enter 'f' for full, 'p' for partial): f

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

### Partial Table Generation
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

### Invalid Range Handling
```
Enter a number for the multiplication table: 3
Do you want a full table or a partial table? (Enter 'f' for full, 'p' for partial): p
Enter the starting number (between 1 and 10): 8
Enter the ending number (between 1 and 10): 2

Invalid range, showing full table instead.
The full multiplication table for 3:
[Full table output...]
```

## Technical Implementation Details

### Loop Types Demonstrated

1. **List Form Loop**
   - Syntax: `for i in {1..10}`
   - Best for: Fixed ranges and simple iterations
   - Advantages: Clean syntax, easy to read

2. **C-style Loop**
   - Syntax: `for ((i=start; i<=end; i++))`
   - Best for: Variable ranges and complex iterations
   - Advantages: More control over iteration variables

### Validation Logic

- **Numeric Validation**: Ensures inputs are valid numbers
- **Range Validation**: Checks that start ≤ end and both are within 1-10
- **Choice Validation**: Validates 'f' or 'p' selection for table type

### Error Handling Strategies

- **Invalid Range**: Defaults to full table with warning message
- **Non-numeric Input**: Prompts for re-entry with error message
- **Out-of-bounds Range**: Adjusts to valid range or defaults to full table

## Assessment Criteria Coverage

| Criteria | Weight | Implementation |
|----------|---------|----------------|
| **Correctness and Functionality** | 20% | Script correctly generates multiplication tables for all input scenarios |
| **Implementation and Use of Loops** | 20% | Both list-form and C-style loops implemented and demonstrated |
| **Code Quality and Readability** | 20% | Well-commented, structured code with clear variable names |
| **Input Validation and Error Handling** | 20% | Comprehensive validation with graceful error handling |
| **User Interaction and Presentation** | 20% | Intuitive prompts and clear, formatted output |

## Learning Outcomes

Through this project, the following Bash scripting concepts are demonstrated:

- **Variable Management**: Storing and manipulating user inputs
- **Loop Constructs**: Mastery of different loop types and their applications
- **Conditional Logic**: Complex decision-making with if-else statements
- **User Interaction**: Creating interactive command-line applications
- **Error Handling**: Robust input validation and error recovery
- **Code Organization**: Structured, maintainable script development

## Future Enhancements

- **Sorting Options**: Ascending/descending order display
- **Multiple Numbers**: Process multiple numbers in one session
- **Export Options**: Save results to file
- **Enhanced Formatting**: Table-style output with borders
- **Advanced Validation**: Support for decimal numbers and larger ranges

## Conclusion

This multiplication table generator demonstrates comprehensive Bash scripting skills while meeting all specified requirements. The implementation showcases best practices in user interaction, input validation, loop usage, and code organization, providing a solid foundation for more advanced Bash scripting projects.