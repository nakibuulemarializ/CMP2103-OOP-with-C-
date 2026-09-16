# Credit Card Validation Program

## Overview
This program validates a credit card number using the Luhn algorithm and checks whether the card belongs to a valid issuer before accepting it as valid.

## OOP Concepts Used
Although the solution is implemented in a procedural style, it clearly uses several object-oriented ideas:

- Encapsulation: each helper function performs a specific part of the validation logic.
- Abstraction: the user only interacts with `isValid()` and does not need to know the details of the calculation.
- Modularity: functions such as `getDigit()`, `sumOfDoubleEvenPlace()`, and `prefixMatched()` divide the task into manageable pieces.
- Reusability: the validation logic can be reused in other programs that check identification or transaction codes.
- Data organization: the card digits are stored in a `vector<int>`, which makes traversal and calculation simple and structured.

## Algorithm
The program follows these steps:

1. Read the credit card number as input.
2. Convert each character to an integer digit and store the digits in a vector.
3. Check that the number has a valid length between 13 and 16 digits.
4. Check the issuer prefix:
   - `4` for Visa
   - `5` for MasterCard
   - `37` for American Express
   - `6` for Discover
5. Starting from the right, double every second digit.
6. If the doubled digit is greater than 9, add its digits together.
7. Add the remaining digits that were not doubled.
8. If the total sum is divisible by 10, print that the number is valid; otherwise, print that it is invalid.

The overall decision is based on the condition:

- valid length
- valid prefix
- Luhn checksum divisible by 10

## Possible Error Points
The following issues can cause incorrect results or runtime problems:

- Empty or missing input.
- Non-numeric characters in the card number.
- Using the wrong starting position when doubling digits.
- Incorrect treatment of the `37` prefix for American Express.
- Forgetting to reduce doubled numbers like `14` to `5` by using `getDigit()`.
- Mistakes in indexing when iterating through the vector.
- Accepting a number whose length is outside the required 13-16 range.
- Failing to validate the prefix before declaring a card valid.

## Example
A valid number such as `4242424242424242` can be checked successfully using this logic.

## Conclusion
This assignment demonstrates how a real-world validation rule can be implemented with modular C++ functions and structured data. The solution is a practical example of using reusable helper methods to solve a problem efficiently and clearly.
