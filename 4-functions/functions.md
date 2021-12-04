# Functions

Miért használjuk a funkciókat?

```python
guitar = ['bass', 'acoustic', 'electric']
dog = ['Csuti', 'Shae', 'Boni']

for instr in guitars:
    print("This is a guitar")
    print(f"This is {instr} guitar")
    print(f"I LOVE {instr.upper()}")

for dog in dogs:
    print("This is a dog")
    print(f"This is {instr} named dog")
    print(f"I LOVE {instr.upper()}")

# We can use one function to do this:
def print_love(iterable, name):
    for i in iterable:
        print(f"This is a(n) {name}")
        print(f"This is a(n) {i}")
        print(f"I LOVE {i.upper()}")

print_love(guitar, 'guitar')
print_love(dog, 'dog')
```

Syntax:
```
def function(*args, **kwargs):
    action
```

Lehet paraméter nélküli funkciónk:
```python
def szuper():
    print("Szuper!")
```

```
output: Szuper!
```

Adhatunk meg tetszőleges paramétereket:
```python
def szuper(mi_szuper):
    print(f"Szuper a(z) {mi_szuper}!")

szuper("kutyafuttató")
```

```
output: Szuper a(z) kutyafuttató!
```
Adhatunk többet is:
```python
def szuper(mennyire, mi_szuper):
    print("{mennyire} szuper a(z) {mi_szuper}!")

szuper(mennyire="Nagyon", mi_szuper="sós-karemelles almás pite")
```

```
output: Nagyon szuper a sós-karamelles almás pite!
```
Egymásba is ágyazhatunk több funkciót:
```python
def my_function():
    print("Hello from the outer function!")

    # Not accessible outside my_function
    def inner_function():
        print("Hi, I'm in!")

    inner_function()

my_function()
```

```
output: 
Hello from the outer function!
Hi, I'm in!
```

```python
# Call the inner function outside its parent function
inner_function()
```

```python
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'inner_function' is not defined
```
*args - Amikor ugyanazt szeretnénk csinálni a paraméterekkel, logikailag egyforma típusúak, és részünkről lehet bármennyi belőle. A *args szintaxist úgy hívjuk, hogy list unpacking.
```python
def friends(*args):
    print("They are all my friends:")
    print(", ".join(args))

# They are the same
friends("Santa", "Geez", "East-Coast Rabbit")
friends(*["Santa", "Geez", "East-Coast Rabbit"])
```

```
output: 
They are all my friends:
Santa, Geez, East-Coast Rabbit
```

Ha szeretnénk fogadni olyan paramétereket, aminek nemcsak az értéke, de a neve is fontos, akkor a **kwargs-okat is bevethetjük:
```python
def print_dogs_with_age(**kwargs):
    for dog, age in kwargs.items():
        print(f"{dog} is {age} years old.")

print_dogs_with_age(csuti=13, boni=5, shae=8)
```

```
output:
csuti is 13 years old.
boni is 5 years old.
shae is 8 years old.
```