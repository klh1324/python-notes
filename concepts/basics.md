# Basics

##### Variable Arguments and Unpacking (Immutable)
```
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
```
# Pass by Value: When primitive or immutable varaibles (int, string, tuple) are passed over, the data is copied over
# Pass by Reference: When mutable data is passed over , the reference is copied over and the changes affect the original data 
# Note for pass by reference: When want to pass mutalbe data by value, call func(l.copy()) instead of func(l)
 ```

##### Deep copy vs Shallow 
```
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
Creates a new object that is a copy, but some references to some nested child objects remain the same
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
```

```

##### Slicing

##### Mutable vs Immutable types

##### Composition



##### Decorators

##### Generators



