# Basics

##### Variable Arguments and Unpacking (Immutable)
```python
# Unpacking to arguments
def foo(a, b, c):
    return a + b + c

l = [1, 3, 5]
print(foo(*l)) # Unpacking

# Packing any number of arguments
def customSum(*args):
    total = 0
    for x in args:
        total += x if x <= 100 else 0
    return total

print(customSum([10, 20, 120, 80]))

# Equivalent for key-variable pairs
def concatenate(**kwargs):
    res = ""
    for arg in kwards.values():
        res += arg
    return res

print(concatenate(a="read ", b="Python"))
```

##### Pass by Reference vs Value
```python
# Pass by Value: When primitive or immutable varaibles (int, string, tuple) are passed over, the data is copied over
# Pass by Reference: When mutable data is passed over , the reference is copied over and the changes affect the original data 
# Note for pass by reference: When want to pass mutalbe data by value, call func(l.copy()) instead of func(l)
 ```

##### Deep copy vs Shallow 
```python
# Basics
l = ['a', 'b', 'c']
a = l
b = l.copy()
print(a == l) # True
print(b == l) # True
print(a is l) # True
print(b is l) # False, compares the id
l[0] = 'A' # Affects l and 

# Shallow and Deep Copy
# Creates a new object that is a copy, but some references to some nested child objects remain the same
x = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
y = list(x)  # Shallow copy
x.append(["A", "B", "C"])
print(y) # [[1, 2, 3], [4, 5, 6], [7, 8, 9]] - won't be affected
x[0][1] = 20
print(y) # [[1, 20, 3], [4, 5, 6], [7, 8, 9]] - child reference is affected!

import copy 
deepY = copy.deepcopy(x) # instead of the alternative cope.copy() method

# What to do for custom objects?

```

##### Dunder Methods
```python
# Dunder methods exist within every Class. Important ones are as follows:

# For classes
def __init__(self, x, y):
    The initialization function

def __new__(cls):
    The object creation (generally not overriden)

def __str__(self):
    # Return a string (user friendly)

def __repr__(self):
    # return a string when called with repr() (developer friendly)

def __setitem__(self, k, v): # car["tire"] = "big"
    self.l[k] = v 

def __getitem__(self, k): # print(car["tire"])
    return self.l[k]

def __delitem__(self, k): # del car["tire"]
    if k in self.l:
        del self.l[k]
    else:
        raise Exception("key doesn't exist")

def __len__(self): # len(car)
    return n

def __contains__(self, k): # Returns boolean i in car -> True/False
    return k in self.l

def __add__(self, p2):
    return self.price + p2.price

# Override iter and next to provide iterator supper to iter(CarClass) function. Also for x in car support
def __iter__(self):
    return self

def __next__(self):
    x = self.val
    if x > 20:
        raise StopIteration
    self.val += 1
    return x

# For an object to work with the 'with' word,
class Custom:
    def __enter__(self):
    # Do something
    return self.apple

    def _exit__(self, exception_type, exception_value, traceback):
    # Code when 'with' section ends

with Custom() as c:
    # Do stuff 

```

##### Slicing
```python
l = [1, 2, 3, 4, 5]
# l[a:b:c] <- start at a, until b, with steps c. If c is negative reverse from b to a
```

##### Zip
```python
first_name = ['Joe','Earnst','Thomas','Martin','Charles']
last_name = ['Schmoe','Ehlmann','Fischer','Walter','Rogan','Green']
age = [23, 65, 11, 36, 83]
for first_name, last_name, age in zip(first_name, last_name, age):
    print(f"{first_name} {last_name} is {age} years old")
# Output
#
# Joe Schmoe is 23 years old
# Earnst Ehlmann is 65 years old
# Thomas Fischer is 11 years old
# Martin Walter is 36 years old
# Charles Rogan is 83 years old##### Mutable vs Immutable types
```

##### Mutable and Immutable Types
```python
# immutable types - int, string, boolean, tuple
# Mutable types - list, set, custom objects
```

##### Map, Filter, Reduce
```python  
items = [1, 2, 3, -4, 5, -6]

squared = list(map(lambda x: x**2, items)) # Returns iterator that maps element form an item

less_than_zero = list(filter(lambda x: x < 0, number_list)) # Returns iterator

product = reduce((lambda x, y: x * y), [1, 2, 3, 4])
```

##### Decorators
```python
# EVerything in Python is an objet, including functions - so we can pass functions to functions
def dec(func):
    def wrapper():
        print("before call function!")
        func()
        print("after function call!")
    return wrapper

addMethod = def(addMethod)

# Alternativelt, 
@dec
def addMethod():
    pass
```

##### Generators
```python
def getN(n):
    num = 0
    while num < n:
        yield num
        num += 1

gen = getN(100)
for i in gen:
    print(f"value is {i}")
```


