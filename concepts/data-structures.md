# Basics

##### Primitive Variables (Immutable)
```
# STRING
s = "hello world" # string
for c in s:
    print( c )
print(s[-1])
num = "123"
num.isdigit() # True 
message = "Hello how are you?"
sep = message.split(' ') # ["Hellow", "how", "are", "you?"]

# BOOLEAN
bool x = True # or False
if x and True:
    print("true and ")

# NUMBER
x = 10
div = x // 4
rem = x % 4
two_to_power = 5 ** 3
res = max(res, 1000)
print(type(x)) # prints the type
```

##### Lists 
```
# BASICS
l = [1, "hello world", 10.312]
a.append(10)
a.extend([0,2,3])
a.insert(2, "yo") # insert "yo" at position 2
a.pop() # returns the last item
N = len(l) # length of list
idx = l.index(10.312) # index position of first occurence of 10.312, else ValueError

# LIST COMPREHENSION
l = [2 ** x for x in range(10)]

# SORTING
sort(l) # sorts the list in ascneding order
sort(l, key=lambda e : (e.salary, e.workhours))
sort(l, key=lambda e : (e.salary, e.workhours), reverse=True)

# DECLARATION
arr = [0] * n
dp = [[0 for x in n] for x in m] # m by n dp array
```
##### Dictionary 
```
d = {}
cars = {"brand" : "Ford", "year" : 2000}
cars["colour"] = "blue"
print(cars["year"])

for k in d:
    print(f"key is {k}")
    print(f"val is {d[k]}")
for k, v in d.items():
    print(f"key is {k}")
    print(f"val is {v}")
```

#### Sets, Stacks, and Queues
```
# Set
s = set()
s.add("banana")
s.discard("apple")
apple_in_set = "apple" in set

# Stack and Queue
from collections import deque
d = deque()
d.append(10)
d.appendleft(4)
print(d.pop())
print(d.popleft())
```

#### Prioirty Queue
```
from queue import PriorityQueue
minHeap = PriorityQueue()
minHeap.put(10)
while not minHeap.empty():
    print(minHeap.get())

maxHeap = PriorityQueue()
```
