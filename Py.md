```
# Practical 1: Find the roots of a quadratic equation
def quadratic_roots(a, b, c):
    import math
    discriminant = b**2 - 4*a*c
    if discriminant > 0:
        root1 = (-b + math.sqrt(discriminant)) / (2 * a)
        root2 = (-b - math.sqrt(discriminant)) / (2 * a)
        return root1, root2
    elif discriminant == 0:
        root = -b / (2 * a)
        return root, root
    else:
        return "No real roots"
```
```
# Practical 2: Prime number-related tasks
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

def primes_till_n(n):
    return [i for i in range(2, n + 1) if is_prime(i)]

def first_n_primes(n):
    primes = []
    num = 2
    while len(primes) < n:
        if is_prime(num):
            primes.append(num)
        num += 1
    return primes
```
```
# Practical 3: Create pyramids
def create_pyramid(n):
    for i in range(1, n + 1):
        print(' ' * (n - i) + '*' * (2 * i - 1))

def create_reverse_pyramid(n):
    for i in range(n, 0, -1):
        print(' ' * (n - i) + '*' * (2 * i - 1))
```
```
# Practical 4: Character analysis
def analyze_character(char):
    if char.isalpha():
        case = "uppercase" if char.isupper() else "lowercase"
        return f"Letter: {case}"
    elif char.isdigit():
        names = ["ZERO", "ONE", "TWO", "THREE", "FOUR", "FIVE", "SIX", "SEVEN", "EIGHT", "NINE"]
        return f"Digit: {names[int(char)]}"
    else:
        return "Special character"
```
```
# Practical 5: String operations
def char_frequency(string, char):
    return string.count(char)

def replace_char(string, old, new):
    return string.replace(old, new)

def remove_first_occurrence(string, char):
    return string.replace(char, '', 1)

def remove_all_occurrences(string, char):
    return string.replace(char, '')
```
```
# Practical 6: Swap first n characters of two strings
def swap_first_n_chars(s1, s2, n):
    return s2[:n] + s1[n:], s1[:n] + s2[n:]
```
```
# Practical 7: Find occurrences of one string in another
def find_occurrences(s1, s2):
    indices = [i for i in range(len(s1)) if s1.startswith(s2, i)]
    return indices if indices else -1
```
```
# Practical 8: Cubes of even integers
def cubes_of_evens(lst):
    cubes_for = [x**3 for x in lst if isinstance(x, int) and x % 2 == 0]
    cubes_list_comp = list(map(lambda x: x**3, filter(lambda x: isinstance(x, int) and x % 2 == 0, lst)))
    return cubes_for, cubes_list_comp
```
```
# Practical 9: File operations
def file_operations(filename):
    with open(filename, 'r') as file:
        lines = file.readlines()
        chars = sum(len(line) for line in lines)
        words = sum(len(line.split()) for line in lines)
        even_lines = lines[1::2]
        odd_lines = lines[0::2]
        
    with open('File1.txt', 'w') as file1:
        file1.writelines(even_lines)

    with open('File2.txt', 'w') as file2:
        file2.writelines(odd_lines)

    return chars, words, len(lines)
```
```
# Practical 10: Class Point
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __repr__(self):
        return f"Point({self.x}, {self.y})"

    def distance(self, other):
        return ((self.x - other.x)**2 + (self.y - other.y)**2)**0.5
```
```
# Practical 11: Dictionary with cubes
def cubes_dict():
    return {x: x**3 for x in range(1, 6)}
```
```
# Practical 12: Tuple operations
def tuple_operations(t1):
    half = len(t1) // 2
    even_numbers = tuple(x for x in t1 if x % 2 == 0)
    t2 = (11, 13, 15)
    concatenated = t1 + t2
    return t1[:half], t1[half:], even_numbers, concatenated, max(t1), min(t1)
```
```
# Practical 13: Exception handling for name input
def validate_name(name):
    if not name.isalpha():
        raise ValueError("Name contains digits or special characters!")
    return f"Valid name: {name}"
```

Practical List
List of Practicals
1. Write a program to find the roots of a quadratic equation
2. Write a program to accept a number ‘n’ and a. Check if ’n’ is prime b. Generate all prime
numbers till ‘n’ c. Generate first ‘n’ prime numbers This program may be done using functions
3. Write a program to create a pyramid of the character ‘*’ and a reverse pyramid
4. Write a program that accepts a character and performs the following:
a. print whether the character is a letter or numeric digit or a special character.
b. if the character is a letter, print whether the letter is uppercase or lowercase
c. if the character is a numeric digit, prints its name in text (e.g., if input is 9, output is
NINE)
5. Write a program to perform the following operations on a string
a. Find the frequency of a character in a string.
b. Replace a character by another character in a string.
c. Remove the first occurrence of a character from a string.
d. Remove all occurrences of a character from a string.
6. Write a program to swap the first n characters of two strings.
7. Write a function that accepts two strings and returns the indices of all the occurrences of the
second string in the first string as a list. If the second string is not present in the first string then
it should return -1.
8. Write a program to create a list of the cubes of only the even integers appearing in the input
list (may have elements of other types also) using the following:
a. 'for' loop
b. list comprehension
9. Write a program to read a file and
a. Print the total number of characters, words and lines in the file.
b. Calculate the frequency of each character in the file. Use a variable of dictionary type
to maintain the count.
c. Print the words in reverse order.
d. Copy even lines of the file to a file named ‘File1’ and odd lines to another file named
‘File2’.
10. Write a program to define a class Point with coordinates x and y as attributes. Create
relevant methods and print the objects. Also define a method distance to calculate the distance
between any two point objects.
11. Write a function that prints a dictionary where the keys are numbers between 1 and 5 and
the values are cubes of the keys.
12. Consider a tuple t1=(1, 2, 5, 7, 9, 2, 4, 6, 8, 10). Write a program to perform following
operations:
a. Print half the values of the tuple in one line and the other half in the next line.
b. Print another tuple whose values are even numbers in the given tuple.
c. Concatenate a tuple t2=(11,13,15) with t1.
d. Return maximum and minimum value from this tuple
13. Write a program to accept a name from a user. Raise and handle appropriate exception(s) if
the text entered by the user contains digits and/or special characters.
