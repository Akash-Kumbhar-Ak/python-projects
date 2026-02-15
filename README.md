![My Image](https://miro.medium.com/1*U0wjuYJe09zE9tCXKPVgUQ.jpeg)



# ✅ 1. Importing libraries

```python
import random 
import math
```

### 👉 `random`

Used to generate random numbers and shuffle the password.

Examples used:

* `random.randint()` → picks random characters
* `random.shuffle()` → mixes password characters

### 👉 `math`

Used for mathematical operations.

Here:

* `math.ceil()` → rounds numbers UP.

---

# ✅ 2. Character sets

```python
alpha ="abcdefghijklmnopqrstuvwxyz"
num = "0123456789"
spec = "!@#$%^&*()"
```

These define possible characters:

* `alpha` → lowercase alphabet
* `num` → digits
* `spec` → special symbols

---

# ✅ 3. Getting password length

```python
pass_len=int(input("Enter the length of the password :"))
```

User enters how long the password should be.

Example:

```
Enter the length of the password :10
```

---

# ✅ 4. Calculating character distribution

```python
alpha_len = pass_len//2
num_len = math.ceil(pass_len*30/100)
special_len = pass_len - (alpha_len + num_len)
```

This divides password into:

### 👉 Letters

```
alpha_len = pass_len // 2
```

Half of password length.

Example (length = 10):

```
10 // 2 = 5 letters
```

---

### 👉 Numbers

```
num_len = math.ceil(pass_len * 30 / 100)
```

30% of password length.

Example:

```
10 * 30% = 3 numbers
```

`ceil()` ensures rounding UP.

---

### 👉 Special characters

```python
special_len = pass_len - (alpha_len + num_len)
```

Remaining characters become special symbols.

---

# ✅ 5. Password storage

```python
password=[]
```

An empty list where characters will be added.

---

# ✅ 6. Password generation function

```python
def generate_pass(length, array, is_alpha=False):
```

This function generates characters.

### Parameters:

* `length` → how many characters to generate
* `array` → source characters (alpha/num/spec)
* `is_alpha` → True if alphabet (for uppercase/lowercase logic)

---

## Inside the function

### Loop

```python
for i in range(length):
```

Runs specified number of times.

---

### Random character selection

```python
index=random.randint(0,len(array)-1)
character=array[index]
```

1. Generate random index
2. Pick character from array

---

### Uppercase/lowercase logic

```python
if is_alpha:
    case=random.randint(0,1)
    if case==1:
        character=character.upper()
```

If character is alphabet:

* randomly decide if uppercase
* gives mix of upper and lowercase letters.

---

### Add to password

```python
password.append(character)
```

---

# ✅ 7. Generating password parts

```python
generate_pass(alpha_len, alpha, True)
generate_pass(num_len, num)
generate_pass(special_len, spec)
```

Creates:

* alphabet characters
* numbers
* special symbols

All stored in `password` list.

---

# ✅ 8. Shuffle password

```python
random.shuffle(password)
```

Mixes characters randomly so they aren’t grouped.

---

# ✅ 9. Convert list to string

```python
gen_password=""
for i in password:
    gen_password=gen_password+str(i)
```

Combines characters into a single string.

Example:

```
['A','3','!','b'] → "A3!b"
```

---

# ✅ 10. Print final password

```python
print(gen_password)
```

Displays generated password.

---

# 🎯 Example Output

Input:

```
Enter length = 10
```

Output:

```
a3B!9@kP2#
```

(Random each time)

---
