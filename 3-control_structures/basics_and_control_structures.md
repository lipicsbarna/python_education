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

### Type casting
Néhány típus közt minden nehézség nélkül van átjárás, át tudjuk castolni a típusokat a másikra:

```python
int("5") # str -> int
str(5) # int -> str
tuple([1,2,3]) # list -> tuple; és fordítva is 
```

### Comments 
A hashtag jel (#) azt mondja a compilernek, hogy ezt a sort nem kell lefordítania - így a hashtaggel kezdődő sorok nem fognak lefutni. Így tudunk kommenteket, megjegyzéseket írni a kódunkhoz.

```python
# This is a comment
x = 5 # This is a comment too
# x = 6
print(x)
output: 5

'''
This
is
a
multiline
comment
'''

```

### Variables
Változók. Amikor tudjuk, hogy egy kódrészletet/értéket többször fogunk használni, akkor változókba tudjuk menteni, és utána azt meghivatkozni. Így később elég egy helyen módosítani, hogy mindenhol módosításra kerüljön - illetve el tudjuk kerülni a redundáns kódrészleteket.

```python
Változók nélkül

print("Shae egy amerikai pitbull terier")
print("Sokak szerint az amerikai pitbull terier veszélyes")
print("Az amerikai pitbull teriert veszélyesen nem lehet leküldeni a kanapéról")

## Ajjaj, teriert írtam terrier helyett, most három helyen kell módosítanom.
## Legközelebb okosabb leszek:

shae_breed = "amerikai pitbull terrier"

print(f"Shae egy {shae_breed}")
print(f"Sokak szerint az {shae_breed} veszélyes")
print(f"Az {shae_breed}t veszélyesen nem lehet leküldeni a kanapéról")
```

Innentől kezdve elég egy helyen módosítanunk, hogy a módosítást végigvezessük az egész kódon.


### Operators

```python
1 + 2 # Add
3 - 2 # Subtract
3 * 2 # Multiply
9 / 3 # Divide
3 ** 2 # Raise to the power of
9 // 2 # Floor division
10 % 3 # Modulo

# Assignment
x = 5 # x is assigned to 5
x = 6 # now x is assigned to 6

x += 1 # Same as x = x + 1
x -= 1 # Same as x = x - 1
# etc.

# Comparison
x == y # Checks if x equals to y
x != y # Not equal
x > y # Greater
x < y # Less than
x >= # Greater or equal to
x <= # Less than or equal to
```

Logical operators: _and_, _or_, _not_

```python
# And returns True only when all comparisons are true
if 5 < 10 and 4 < 10:
    print("I am True!")

# Or returns True when at least on of the comparisons are true
if 1 == 0 or 1 == 1:
    print("I am True")

# Not returns the opposite of the comparison:
if not(5 < 10 and 4 < 10):
    print("This will not be evaluated, since I am False")
else:
    print("Here I Am")
```

Identity and membership operators:

```python
my_bool = True

# is
if my_bool is True:
    print("I am True")

# is not 
if my_bool is not False:
    print("This will not be evaluated, since I am False")
else:
    print("Here I Am")

# in
print(
    "Csuti" in ["Csuti", "Shae", "Boni"]
)
# True

# not in
print(
    "Csuti" not in ["Csuti", "Shae", "Boni"]
)
# False
```

### Control structures

If, elif, else

```
# Syntax:
if statement1:
    do something
elif statement2:
    do something else
elif statement3:
    do a 3rd different thing
else:
    if none of the before were true, do this
```

Példa:
```python
bodyweight = 120

if bodyweight < 90:
    print("Száz kiló alatt magyar ember karácsonyfadísz!")
elif bodyweight >= 90 and bodyweight < 100:
    print("Alakul ez.")
else:
    print("Egy rendes ember.")


# nested if condition

bodyweight = 120
do_i_like_him = 'yes'

if bodyweight < 90:
    print("Száz kiló alatt magyar ember karácsonyfadísz!")
elif bodyweight >= 90 and bodyweight < 100:
    print("Alakul ez.")
else:
    if do_i_like_him == 'yes':
        print("Egy rendes ember.")
    else:
        print("Egy kövér ember!")

```
