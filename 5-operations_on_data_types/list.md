# List operations

A következőképp tudjuk elérni egy list n-edik elemét:
```python
n = 1
my_list = ['choc', 'banana', 'peanut butter']
print(my_list[n]) # equals print(my_list[1])
```

Negatív indexeléssel tudunk a list végéről számítva elemet választani:
```python
my_list = ['choc', 'banana', 'peanut butter']
print(my_list[-1]) 
```

```
Output: peanut butter
```


Az egyik leggyakoribb művelet a list bővítése:

```python
my_list = ['choc', 'banana']
my_list.append('peanut butter')
print(my_list)
```

```
Output: ['choc', 'banana', 'peanut butter']
```
Az utolsó elemét pedig a __pop__ paranccsal tudjuk eltávolítani - ezt megkapjuk visszatérési értéknek:
```python
my_list = ['choc', 'banana', 'peanut butter']
print(my_list)
last_one = my_list.pop()
print(last_one)
print(my_list)
```

```
Output:
['choc', 'banana', 'peanut butter']
peanut butter
['choc', 'banana']
```

A __pop__ metódust emellett tudjuk paraméterezni; a paraméterként megadott index helyén lévő elemet fogja eltávolítani:
```python
my_list = ['choc', 'banana', 'peanut butter']
print(my_list)
first = my_list.pop(1)
print(first)
print(my_list)
```

```
Output:
['choc', 'banana', 'peanut butter']
banana
['choc', 'peanut butter']
```

Ha kíváncsiak vagyunk egy elem indexére, arra is van mód:
```python
my_list = ['choc', 'banana', 'peanut butter']
print(my_list.index('choc'))
```

```
Output: 0
```

Érték alapján tudunk törölni elemet:
```python
my_list = ['choc', 'banana', 'peanut butter']
my_list.remove('choc')
print(my_list)
```

```
Output: ['banana', 'peanut butter']
```
Egy collection elemszámát a __len__ funkcióval tudjuk kideríteni:

```python
my_list = ['choc', 'banana', 'peanut butter']
print(len(my_list))
```

```
Output: 3
```
Két listát össze tudunk concatenálni:
```python
my_list = ['choc', 'banana', 'peanut butter']
my_list2 = ['brownie', 'mezeskremes']
print(my_list + my_list2)
```

```
Output: ['choc', 'banana', 'peanut butter', 'brownie', 'mezeskremes']
```
Még a szorzás is értelmezhető:
```python
my_list = ['choc', 'banana', 'peanut butter']
print(my_list * 3)
```

```
Output: ['choc', 'banana', 'peanut butter', 'choc', 'banana', 'peanut butter', 'choc', 'banana', 'peanut butter']
```
Listet össze lehet fűzni stringgé:
```python
my_list = ['choc', 'banana', 'peanut butter']
my_sweets = " and ".join(my_list)
print(f"My favourite sweets are {my_sweets}.")
```

```
Output: My favourite sweets are choc and banana and peanut butter.
```
SQL-ek jó módszer lehet
```python
needed_columns = ['id', 'dog_name', 'dog_age', 'breed']
filter_ids = [1, 5, 77, 87]
filter_ids_str = ",".join([str(idx) for idx in filter_ids])
print(f"""
SELECT {",".join(needed_columns)}
FROM dogs_table
WHERE id in ({filter_ids_str})
""")
```

```
Output:
SELECT id,dog_name,dog_age,breed
FROM dogs_table
WHERE id in (1,5,77,87)
```