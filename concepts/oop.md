# Object Oriented Programming

##### Basic Class
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

