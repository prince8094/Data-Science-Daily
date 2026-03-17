# Python Programming Learning: February 11, 2026

## 1. Core Concepts: Control Flow & Data Structures

### Variables & Input
* **Dynamic Typing:** In Python, we don't declare variable types; the interpreter automatically detects them (e.g., `a = 5`).
* **Multiple Assignment:** You can assign the same value to multiple variables (`x = y = z = 0`) or different values simultaneously (`a, b, c = 1, 2, 3`).
* **`input()`:** Always takes input in **string** format. To use it for math, you must typecast it: `n = int(input())`.

### Decision Making (If-Else)
* **Logic:** Used to execute blocks of code only if a condition is `True`.
* **Keywords:** `if`, `elif` (else if), and `else`.
* **Nesting:** You can place an `if` statement inside another to check multiple layers of conditions.

### Loops (Iteration)
1. **For Loop:** Used for iterating over sequences (like lists or ranges).
   * **`range(start, stop, step)`:**
     * `range(5)` -> 0, 1, 2, 3, 4
     * `range(1, 11)` -> 1 to 10
     * `range(1, 11, 2)` -> 1, 3, 5, 7, 9 (increments by 2)
2. **While Loop:** Executes as long as a condition is `True`. **Warning:** Always include an update/increment to avoid an "infinite loop."
3. **Loop Control:**
   * `break`: Exit the loop immediately.
   * `continue`: Skip the current iteration and move to the next.
   * `pass`: A null statement used as a placeholder.
   * `enumerate()`: Used to keep track of the index (`i`) and the value (`j`) simultaneously.

### Data Structures: Lists
Lists are ordered, mutable (changeable) collections that can hold mixed data types.
* **Operations:**
    * `.append()`: Add one element to the end.
    * `.extend()`: Add multiple elements (another list) to the end.
    * `.remove()`: Removes a specific element by value.
    * `.pop(index)`: Removes an element by its position.
    * `.reverse()` / `[::-1]`: Reverses the list.
    * `len()`, `min()`, `max()`, `sorted()`: Useful built-in functions.
* **Multidimensional Lists:** Lists inside lists (e.g., Matrices/2D Arrays). Accessed via `list[row][column]`.

---

## 2. Python Code Implementation


```python
# --- 1. Variables & Inputs ---
name = "Prince"
age = int(input("Enter your age: ")) # Typecasting string input to int

# --- 2. Control Flow (If-Else) ---
if age >= 18:
    print("Eligible to Vote")
elif age > 0:
    print("Minor")
else:
    print("Invalid Age")

# --- 3. Loops & Range ---
# Printing a multiplication table for 2
for i in range(2, 21, 2):
    print(i, end=' ') 

# While loop example: Sum of digits
n = 123
total_sum = 0
while n != 0:
    total_sum += n % 10
    n //= 10
print(f"\nSum of digits: {total_sum}")

# --- 4. Advanced Iteration (Enumerate) ---
fruits = ["Apple", "Banana", "Cherry"]
for index, value in enumerate(fruits):
    print(f"Index {index}: {value}")

# --- 5. Lists & Multidimensional Arrays ---
# Matrix (3x3)
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
print(f"Accessing center element: {matrix[1][1]}") # Output: 5

# List Operations
nums = [10, 20, 30]
nums.append(40)
nums.extend([50, 60])
print(f"Updated List: {nums}")
