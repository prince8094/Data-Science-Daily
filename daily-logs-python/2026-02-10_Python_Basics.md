# Python Programming Learning: February 10, 2026

## 1. Core Concepts: Python Fundamentals

### Data Types & Print Functionality
* **Basic Types:** `int`, `float`, `string`, `bool` (True/False).
* **`type()`:** Used to check the data type of a variable.
* **Print Customization:**
    * `end=' '`: Changes what happens at the end of a print statement (default is a newline).
    * `sep=' '`: Changes the separator between multiple objects in a single print statement.

### Operators
1. **Arithmetic:** Standard operations like `+`, `-`, `*`. 
   * **Note:** You cannot concatenate a `string` and a `float` directly.
   * **Booleans:** `True + True` equals `2` because `True` is treated as `1` and `False` as `0`.
2. **Division:** * `/` : Standard division (returns a float, e.g., `3/2 = 1.5`).
   * `//`: Floor division (returns the integer part, e.g., `3//2 = 1`).
   * `%` : Modulo (returns the remainder).
3. **Exponentiation:** `**` or `pow(base, exp)` (e.g., `3**5` or `pow(3, 5)`).
4. **Comparison:** Returns Boolean values (`==`, `!=`, `>`, `<`, `>=`, `<=`).
5. **Logical:** `and` (all must be true), `or` (any one true), and `not`.

### Typecasting
Converting one data type to another:
* `int("10")` works, but `int("A")` or `int("3.14")` will throw an error.
* **To convert a decimal string to int:** Use `int(float("3.14"))`.
* **Boolean Conversion:** `bool(0)` or `bool("")` is `False`; any other value is `True`.

### String Manipulation & Slicing
* **Slicing:** `[start : end + 1]` 
  * *Logic:* "Jaha se chaiye waha se, jaha tak chaiye usse ek zyada."
  * Negative indexing is supported (starts from `-1` at the end).
* **Methods:**
    * `.strip()`: Removes leading/trailing spaces (not middle spaces).
    * `.replace('old', 'new')`: Replaces all occurrences.
    * `.find()`: Returns the start index of a substring.
    * `.count()`: Frequency of a character/substring.
    * `.capitalize()` vs `.title()`: Capitalizes first letter of the first word vs all words.
* **Alignment:** * `.center(20, '-')`: Centers string with padding.
    * `.ljust()` / `.rjust()`: Left or Right justify.

---

## 2. Python Code Implementation

```python
# --- 1. Operations & Booleans ---
print(True + True) # Output: 2
print("Prince" + " " + "Gupta") # Concatenation

# --- 2. Division & Exponents ---
print(3 / 2)   # 1.5
print(3 // 2)  # 1 (Floor)
print(3 ** 5)  # 243
print(pow(3, 5)) 

# --- 3. String Slicing ---
name = "Prince"
# Positive: P=0, r=1, i=2, n=3, c=4, e=5
# Negative: P=-6, r=-5, i=-4, n=-3, c=-2, e=-1
print(name[1:3]) # Output: "ri"
print(name[:])   # Full string

# --- 4. String Methods ---
text = "  python learning  "
print(text.strip().capitalize()) # "Python learning"

msg = "hello world"
print(msg.replace("h", "_")) # "_ello world"
print(msg.title())           # "Hello World"

# --- 5. Alignment & Checking ---
s = "Prince"
print(s.center(20, "-"))     # "-------Prince-------"
print(s.startswith("Pri"))    # True
print(s.isalpha())           # True
