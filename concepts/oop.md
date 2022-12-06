# Object Oriented Programming

##### Basic Class
```python
class Person:
    country = "Canada" # define class attribute country with default value "Canada" (lives in class namespace)

    def __init__(self, name, age = 10): # define 2 new class attributes (lives in instance namespace)
        self._name = name # special behavior with getter/setter
        self.age = age 

    @property # getter
    def name(self):
        return self._name 

    @name.setter
    def name(self, n):
        if n > 50:
            raise ValueError("Too old!")
        self._name = n


p = Person("Jason", 51)
print(p.name)
print(p.age)
print(Person.country)
```


##### Inheritance in Python
```python
class Student(Person):
    def __init__(self, fname, lname):
        super().__init__(fname)  # Since technically init is initializer and not construction, not called by default
        self.last_name = lname

class SquareNumber(int):
    def __new__(cls, value):
        return super().__new__(cls, value ** 2)

sq = SquareNumber(3)
print(sq) # 9
```


##### Composition
```python
class Car:
    pass

class Composite:
    def __init__(self):
        self.car = Car() # Composition
```
