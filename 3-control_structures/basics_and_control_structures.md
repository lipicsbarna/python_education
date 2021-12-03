# Basics and control structures

### Indendation
Intendációval (Tab vagy 4 szóköz) tagoljuk a kódunk logikai egységeit:
```python
x = 11
y = 27

def add_numbers(first, second):
    return_value = first + second

    def inner_print_function(value_to_print):
        print(value_to_print)

    inner_print_function(return_value)

    return return_value

added = add_numbers(x, y)

output: 38
```

### Data types
```python
my_str: str = "Ajjajje kokodzsambo..."
my_int: int = 2021
my_float: float = 18.23
my_boolean: bool = True
my_dict: dict = {
    'csuti': 'mix',
    'shae' : 'pitbull'
}
my_list: list = ["Anyám tyúkja", "Nemzeti dal", "Dicsőséges nagyurak"]
my_tuple: tuple = ('Dreher', 'Gösser', 'Pécsi')
my_set: set = {"Milka", "Bocsi", "Piros mogyorós"}
my_frozenset: frozenset = frozenset(my_set)

### Won't be covered in this course:
my_binary: bytes = b"Hi"
my_bytearray: bytearray = bytearray(5)
my_memoryview: memoryview = memoryview(bytes(5))

# There are many others that can be imported
from collections import deque
my_double_ended_queue: deque = deque()

# We can implement ours
@dataclass
class Cat:
    name: str,
    lifes: int

my_cat: Cat = Cat("cica", "9")
```