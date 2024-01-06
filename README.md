# Fraction Class

## Introduction

The Fraction class is a custom Python implementation of a basic fraction data type. This class enables users to work with fractions, supporting common arithmetic operations such as addition, subtraction, multiplication, and division.

## Class Definition

```python
class Fraction:
    def __init__(self, numerator, denominator):
        """
        Constructor to initialize a fraction with a numerator and denominator.

        Parameters:
        - numerator (int): Numerator of the fraction.
        - denominator (int): Denominator of the fraction (non-zero).
        """
        self.num = numerator
        self.den = denominator

    def __str__(self):
        """
        String representation of the fraction.

        Returns:
        str: Formatted string representation of the fraction.
        """
        return '{}/{}'.format(self.num, self.den)

    def __add__(self, other):
        """
        Overloaded addition operator for fractions.

        Parameters:
        - other (Fraction): Another fraction to add.

        Returns:
        Fraction: Result of the addition operation.
        """
        temp_num = self.num * other.den + other.num * self.den
        temp_den = self.den * other.den
        return Fraction(temp_num, temp_den)

    def __sub__(self, other):
        """
        Overloaded subtraction operator for fractions.

        Parameters:
        - other (Fraction): Another fraction to subtract.

        Returns:
        Fraction: Result of the subtraction operation.
        """
        temp_num = self.num * other.den - other.num * self.den
        temp_den = self.den * other.den
        return Fraction(temp_num, temp_den)

    def __mul__(self, other):
        """
        Overloaded multiplication operator for fractions.

        Parameters:
        - other (Fraction): Another fraction to multiply.

        Returns:
        Fraction: Result of the multiplication operation.
        """
        temp_num = self.num * other.num
        temp_den = self.den * other.den
        return Fraction(temp_num, temp_den)

    def __truediv__(self, other):
        """
        Overloaded division operator for fractions.

        Parameters:
        - other (Fraction): Another fraction to divide.

        Returns:
        Fraction: Result of the division operation.
        """
        temp_num = self.num * other.den
        temp_den = self.den * other.num
        return Fraction(temp_num, temp_den)
```

## Usage Example

```python
# Creating fraction objects
fraction1 = Fraction(1, 2)
fraction2 = Fraction(3, 4)

# Performing arithmetic operations
result_addition = fraction1 + fraction2
result_subtraction = fraction1 - fraction2
result_multiplication = fraction1 * fraction2
result_division = fraction1 / fraction2

# Displaying results
print("Fraction 1:", fraction1)         # Output: Fraction 1: 1/2
print("Fraction 2:", fraction2)         # Output: Fraction 2: 3/4
print("Addition:", result_addition)     # Output: Addition: 5/4
print("Subtraction:", result_subtraction)  # Output: Subtraction: -1/4
print("Multiplication:", result_multiplication)  # Output: Multiplication: 3/8
print("Division:", result_division)     # Output: Division: 2/3
```

Feel free to integrate this Fraction class into your projects and modify it according to your specific requirements.
