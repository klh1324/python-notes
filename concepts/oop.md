# Object Oriented Programming

##### Basic Class
```python
class Person:
    country = "Canada" # define class attribute country with default value "Canada"

    def __init__(self, name, age): # define 2 new class attributes
        self.name = name
        self.age = age


p = Person("Jason", 51)
print(p.name)
print(p.country)
print(Person.country) # point of class attribute!
```

