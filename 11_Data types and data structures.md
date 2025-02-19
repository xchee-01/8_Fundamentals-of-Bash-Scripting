# 11. Data types and data structures

## 11.1. Basic data types 
In shell programming, all variables are stored as strings by default. However, we can work with several types of data:

**(a) Strings**

```
#!/bin/bash

# String variables
name="John"
echo "Name: $name"
```

**(b) Integers**

```
#!/bin/bash

# Integer
age=25
echo "Age: $age"
```

**(c) Floating point**

```
#!/bin/bash

# Floating point
price=23.50
echo "Price: $price"
```

**(d) Boolean**

```
#!/bin/bash

# Boolean
is_active=true
is_valid=1
```

## 11.2. Arrays

You can also create arrays. As a reminder, an array is a data structure that can store multiple values in a single variable.

```
#!/bin/bash

# Array creation
fruits=("apple" "banana" "orange" "mango")

# Print specific element
echo "First fruit: ${fruits[0]}"

# Print all elements
echo "All fruits: ${fruits[@]}"

# Print array length
echo "Number of fruits: ${#fruits[@]}"
```

## 11.3. Basic array operations 

Here are some of the arithmetic operations that can be done using bash scripts

```
#!/bin/bash

# Initialize array
numbers=(1 2 3 4 5)

# 1. Adding elements
numbers+=(6)                    # Append to end
echo ${numbers[@]}              # Prints the entire list
numbers=("0" "${numbers[@]}")   # Prepend to start
echo ${numbers[@]}

# 2. Removing elements
unset 'numbers[2]'              # Remove specific element
echo ${numbers[@]}

numbers=("${numbers[@]:1}")     # Remove first element because first element is 0
echo ${numbers[@]}

numbers=("${numbers[@]:0:${#numbers[@]}-1}")  # Remove last element

# 3. Slicing
echo "First three elements: ${numbers[@]:0:3}"
```

## 11.4. Array iterations

You can also combine these arrays with conditions. 

For example, 

```
#!/bin/bash

# Ask user for a number
echo "Enter a number:"
read number

# Check if number is positive, negative, or zero
if [ $number -gt 0 ]; then
    echo "$number is positive"
elif [ $number -lt 0 ]; then
    echo "$number is negative"
else
    echo "$number is zero"
fi
```

> [!NOTE]
> The basic comparison operators are:
> - `gt`: greater than
> - `lt`: less than
> - `eq`: equal to
