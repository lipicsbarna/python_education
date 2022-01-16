### Tuple operations

### Tuple creation
```python
my_tuple = (1,2,5)

# This one is tricky
my_tuple_one_element = (1,)
# Yes, you need a comma to parse it as a tuple
# otherwise it will be parsed as int(1)
```

A tuple elemek elérése megegyezik a listtel:

```python
cheesecakes = ('strawberry', 'caramel', 'salted caramel', 'blueberry')
print(cheesecakes[2])
```

```
Output: salted caramel
```

Módosítani viszont nem lehetséges, mivel a tuple immutable típus:
```python
cheesecakes = ('strawberry', 'caramel', 'salted caramel', 'blueberry')
cheesecakes[0] = 'ginger'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```
Egyedül akkor van rá mód, ha egy nested (beágyazott) tuple, amelynek az eleme collection típus; azon meg tudjuk hívni a saját collection metódosait, amelyekkel esetleg módosulhat a tartalma:

```python
cakes: tuple[list[str]] = (
    ['strawberry', 'caramel', 'salted caramel', 'blueberry'],
    ['vanilla', 'coconut', 'almond']
)
cakes[1].append('salted caramel')
print(cakes[1])
# ['vanilla', 'coconut', 'almond', 'salted caramel']

cakes[1].remove('coconut')
print(cakes)
# ['vanilla', 'almond', 'salted caramel']
```