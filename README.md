# Python Practical

## Student Information
| Name     | Vinay Kumar Sharma |
| -------- | :------: |
| Roll Number  | 26570065 |   
| Department   | B.Sc. (Hons.) Computer Science |
| Semester | 1  |
|Tool      | Python 3 |

# Practical 1: Roots of a Quadratic Equation

**Question:** Write a program to find the roots of a quadratic equation.

## Code:
```python
import cmath


def quadratic_roots(a, b, c):
    """Return the two roots of ax^2 + bx + c = 0 (real or complex)."""
    d = b ** 2 - 4 * a * c            # discriminant
    root1 = (-b + cmath.sqrt(d)) / (2 * a)
    root2 = (-b - cmath.sqrt(d)) / (2 * a)
    return d, root1, root2


print("Quadratic equation: ax^2 + bx + c = 0")
a = float(input("Enter a: "))
b = float(input("Enter b: "))
c = float(input("Enter c: "))

if a == 0:
    print("'a' cannot be 0 - this is not a quadratic equation.")
    if b != 0:
        print("It is linear, with root x =", -c / b)
else:
    d, r1, r2 = quadratic_roots(a, b, c)
    print("Discriminant =", d)
    if d > 0:
        print("Roots are real and distinct.")
        print("x1 =", r1.real, "\nx2 =", r2.real)
    elif d == 0:
        print("Roots are real and equal.")
        print("x1 = x2 =", r1.real)
    else:
        print("Roots are complex conjugates.")
        print("x1 =", r1, "\nx2 =", r2)
```
## Code implementation
<img width="1165" height="966" alt="image" src="https://github.com/user-attachments/assets/78f5431e-4f6e-4c43-86e0-b93b99f591e1" />

## Output

<img width="1316" height="676" alt="image" src="https://github.com/user-attachments/assets/5c8758be-2a6e-4fa3-a0bc-5f12840118ac" />

# Practical 2 : Prime Numbers

**Question:** Write a program to accept a number 'n' and

- a. Check if 'n' is prime
- b. Generate all prime numbers till 'n'
- c. Generate first 'n' prime numbers

## Code:
```python
def is_prime(num):
    """Return True if num is a prime number."""
    if num < 2:
        return False
    i = 2
    while i * i <= num:
        if num % i == 0:
            return False
        i += 1
    return True


def primes_till(n):
    """Return a list of all primes <= n."""
    return [i for i in range(2, n + 1) if is_prime(i)]


def first_n_primes(n):
    """Return a list of the first n primes."""
    result = []
    candidate = 2
    while len(result) < n:
        if is_prime(candidate):
            result.append(candidate)
        candidate += 1
    return result


n = int(input("Enter a number n: "))

# a
if is_prime(n):
    print(f"a) {n} is a prime number")
else:
    print(f"a) {n} is not a prime number")

# b
print(f"b) Prime numbers till {n}:", primes_till(n))

# c
print(f"c) First {n} prime numbers:", first_n_primes(n))
```
## Code implementation
<img width="753" height="1030" alt="image" src="https://github.com/user-attachments/assets/eccb0152-788a-4d0a-971d-fabadd421ca5" />


## Output
<img width="1381" height="472" alt="image" src="https://github.com/user-attachments/assets/34f11fb3-8ea7-476f-aa04-4697f582e620" />

# Practical 3: Pyramid and Reverse Pyramid

**Question:** Write a program to create a pyramid of the character '\*' and a reverse pyramid.

## Code:
```python
# Practical 3: WAP to create a pyramid of the character '*' and a reverse pyramid


def pyramid(rows):
    """Print a pyramid with the given number of rows (1, 3, 5, ... stars)."""
    for i in range(1, rows + 1):
        print(" " * (rows - i) + "*" * (2 * i - 1))


def reverse_pyramid(rows):
    """Print a reverse (inverted) pyramid with the given number of rows."""
    for i in range(rows, 0, -1):
        print(" " * (rows - i) + "*" * (2 * i - 1))


rows = int(input("Enter the number of rows: "))

print("\nPyramid:\n")
pyramid(rows)

print("\nReverse pyramid:\n")
reverse_pyramid(rows)
```
## Code implementation
<img width="967" height="653" alt="image" src="https://github.com/user-attachments/assets/9eeb1574-c34a-438a-94c2-2b2c35e52a2d" />


## Output
<img width="1307" height="796" alt="image" src="https://github.com/user-attachments/assets/f2176d8b-ba47-478f-909b-71dfceeca0b0" />

# Practical 4: Character Check

**Question:** Write a program that accepts a character and performs the following:

- a. print whether the character is a letter or numeric digit or a special character.
- b. if the character is a letter, print whether the letter is uppercase or lowercase
- c. if the character is a numeric digit, prints its name in text (e.g., if input is 9, output is NINE)

## Code:
```python
# Practical 4: WAP that accepts a character and performs the following:
#   a. print whether the character is a letter or numeric digit or a special character
#   b. if the character is a letter, print whether the letter is uppercase or lowercase
#   c. if the character is a numeric digit, print its name in text (e.g. 9 -> NINE)

DIGITS = {
    '0': "ZERO", '1': "ONE", '2': "TWO", '3': "THREE", '4': "FOUR",
    '5': "FIVE", '6': "SIX", '7': "SEVEN", '8': "EIGHT", '9': "NINE",
}

ch = input("Enter a single character: ")

if len(ch) != 1:
    print("Please enter exactly one character.")
elif ch.isalpha():
    print(f"'{ch}' is a letter")
    if ch.isupper():
        print("It is an uppercase letter")
    else:
        print("It is a lowercase letter")
elif ch.isdigit():
    print(f"'{ch}' is a numeric digit")
    print("Name in text:", DIGITS.get(ch, "(not a decimal digit 0-9)"))
else:
    print(f"'{ch}' is a special character")
```
## Code implementation
<img width="1172" height="803" alt="image" src="https://github.com/user-attachments/assets/bcb4b753-d80d-4858-a444-30af76d9e57b" />


## Output
<img width="1293" height="335" alt="image" src="https://github.com/user-attachments/assets/51820aab-1906-4975-bd15-b2860779d68c" />

# Practical 5: Operations on a String

**Question:** Write a program to perform the following operations on a string

- a. Find the frequency of a character in a string.
- b. Replace a character by another character in a string.
- c. Remove the first occurrence of a character from a string.
- d. Remove all occurrences of a character from a string.


## Code:
```python


def frequency(s, ch):
    count = 0
    for c in s:
        if c == ch:
            count += 1
    return count


def replace_char(s, old, new):
    result = ""
    for c in s:
        result += new if c == old else c
    return result


def remove_first(s, ch):
    index = s.find(ch)
    if index == -1:
        return s
    return s[:index] + s[index + 1:]


def remove_all(s, ch):
    result = ""
    for c in s:
        if c != ch:
            result += c
    return result


text = input("Enter a string: ")

ch = input("a) Enter a character to find its frequency: ")[:1]
print(f"   '{ch}' occurs {frequency(text, ch)} time(s)")

old = input("b) Enter the character to be replaced: ")[:1]
new = input("   Enter the new character: ")[:1]
print("   Result:", replace_char(text, old, new))

ch = input("c) Enter a character to remove its first occurrence: ")[:1]
print("   Result:", remove_first(text, ch))

ch = input("d) Enter a character to remove all its occurrences: ")[:1]
print("   Result:", remove_all(text, ch))
```
## Code implementation
<img width="1098" height="1062" alt="image" src="https://github.com/user-attachments/assets/19bd7d4f-697d-4a1b-982c-99a97e90b129" />


## Output
<img width="1368" height="763" alt="image" src="https://github.com/user-attachments/assets/8c0b77b2-fcc1-4832-97b8-e88fcbc34c17" />

# Practical 6: Swap the First n Characters of Two Strings

**Question:** Write a program to swap the first n characters of two strings.

## Code:
```python
def swap_first_n(s1, s2, n):
    """Return (s1', s2') after exchanging the first n characters."""
    return s2[:n] + s1[n:], s1[:n] + s2[n:]


str1 = input("Enter the first string: ")
str2 = input("Enter the second string: ")
n = int(input("Enter n (number of characters to swap): "))

if n < 0 or n > len(str1) or n > len(str2):
    print("n must be between 0 and the length of the shorter string.")
else:
    new1, new2 = swap_first_n(str1, str2, n)
    print("Before swapping:", str1, "|", str2)
    print("After swapping :", new1, "|", new2)
```
## Code implementation
<img width="1266" height="653" alt="image" src="https://github.com/user-attachments/assets/4eb527e1-7ebc-4a16-992d-76cb50872e9a" />


## Output
<img width="1361" height="583" alt="image" src="https://github.com/user-attachments/assets/5ca16f2f-1988-4bcb-a493-a48867eedae3" />

# Practical 7: Indices of a Substring

**Question:** Write a function that accepts two strings and returns the indices of all the occurrences of the second string in the first string as a list. If the second string is not present in the first string then it should return -1.

## Code:
```python
def find_all(first, second):
    indices = []
    start = first.find(second)
    while start != -1:
        indices.append(start)
        start = first.find(second, start + 1)   # +1 also finds overlapping matches
    return indices if indices else -1


s1 = input("Enter the first string: ")
s2 = input("Enter the second string: ")

if s2 == "":
    print("The second string must not be empty.")
else:
    print("Result:", find_all(s1, s2))
```
## Code implementation
<img width="1265" height="786" alt="image" src="https://github.com/user-attachments/assets/bc7c335e-8e76-4d53-ba08-ccc422aaf304" />


## Output
<img width="1318" height="410" alt="image" src="https://github.com/user-attachments/assets/71a524d1-de8c-4798-a7ed-5bf44e24cda9" />


# Practical 8: Cubes of Even Integers

**Question:** Write a program to create a list of the cubes of only the even integers appearing in the input list (may have elements of other types also) using the following:

- a. 'for' loop
- b. list comprehension

## Code:
```python
data = [1, 2, 3, 4, "hello", 6, 7.0, 8, 9, 10, True, None, "12", 14, -2]
print("Input list:", data)


def is_integer(x):
    # bool is a subclass of int in Python, so it is excluded explicitly
    return isinstance(x, int) and not isinstance(x, bool)


# a. using a for loop
cubes_loop = []
for item in data:
    if is_integer(item) and item % 2 == 0:
        cubes_loop.append(item ** 3)
print("a) Using for loop          :", cubes_loop)

# b. using list comprehension
cubes_comp = [x ** 3 for x in data if is_integer(x) and x % 2 == 0]
print("b) Using list comprehension:", cubes_comp)
```
## Code implementation
<img width="1222" height="707" alt="image" src="https://github.com/user-attachments/assets/97760596-116b-4617-aaf8-9d9f8540c595" />


## Output
<img width="1358" height="552" alt="image" src="https://github.com/user-attachments/assets/5d624673-208a-44f1-ace1-7a72d3a4bc08" />


# Practical 9: File Handling

**Question:** Write a program to read a file and

- a. Print the total number of characters, words and lines in the file.
- b. Calculate the frequency of each character in the file. Use a variable of dictionary type to maintain the count.
- c. Print the words in reverse order.
- d. Copy even lines of the file to a file named 'File1' and odd lines to another file named 'File2'.

## Code:
```python
import os

filename = input("Enter the file name (press Enter to use sample.txt): ").strip() or "sample.txt"

# Create a sample file if the default one does not exist yet
if filename == "sample.txt" and not os.path.exists(filename):
    with open(filename, "w") as f:
        f.write("Python is a popular programming language.\n"
                "It is easy to learn and read.\n"
                "File handling is an important topic.\n"
                "This is the fourth line of the file.\n"
                "And this is the last line.\n")
    print("(sample.txt created)")

try:
    with open(filename, "r") as f:
        lines = f.readlines()
except FileNotFoundError:
    print("File not found:", filename)
    raise SystemExit

content = "".join(lines)

# a. characters, words, lines
print("\na) Total characters:", len(content))
print("   Total words     :", len(content.split()))
print("   Total lines     :", len(lines))

# b. frequency of each character (dictionary)
freq = {}
for ch in content:
    freq[ch] = freq.get(ch, 0) + 1
print("\nb) Frequency of each character:")
for ch, count in sorted(freq.items()):
    print(f"   {repr(ch):6} -> {count}")

# c. words in reverse order
print("\nc) Words in reverse order:")
print("  ", " ".join(content.split()[::-1]))

# d. even lines -> File1, odd lines -> File2  (line numbers start from 1)
with open("File1", "w") as f1, open("File2", "w") as f2:
    for number, line in enumerate(lines, start=1):
        if number % 2 == 0:
            f1.write(line if line.endswith("\n") else line + "\n")
        else:
            f2.write(line if line.endswith("\n") else line + "\n")
print("\nd) Even lines copied to 'File1' and odd lines copied to 'File2'.")
```
## Code implementation
<img width="1027" height="981" alt="image" src="https://github.com/user-attachments/assets/b0b24b40-f89e-4a5c-8d8a-a1f563735ecc" />


## Output
<img width="1367" height="910" alt="image" src="https://github.com/user-attachments/assets/a0b0d6c2-0e16-40b7-b86e-93a98dc6de50" />
<img width="1376" height="902" alt="image" src="https://github.com/user-attachments/assets/4a1f5e8b-d09a-4d9e-972d-888071a8bc69" />


# Practical 10:  Dictionary of Cubes

**Question:**  Write a function that prints a dictionary where the keys are numbers between 1 and 5 and the values are cubes of the keys.


## Code:
```python

def print_cubes_dict():
    cubes = {}
    for n in range(1, 6):
        cubes[n] = n ** 3
    print(cubes)
    return cubes


print_cubes_dict()
```
## Code implementation
<img width="1042" height="656" alt="image" src="https://github.com/user-attachments/assets/c833ab3f-2e95-4f52-922f-a3a283ceffc9" />


## Output
x
