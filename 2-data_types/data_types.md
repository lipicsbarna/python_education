# Python data types


## Text type

### string

"Hello"

'Hello'


## Numeric

### int
5

1000


### float

10.27


### complex
1j


## Mapping

### dictionary (dict)

* Ordered
* Mutable
* Duplicate keys are not allowed, duplicate values are

```python
my_dict = {
    'Csuti': 'mutt',
    'Shae' : 'pitbull,
    'Boni' : 'bull type mix'
}

shae_breed = my_dict['Shae']
print(f"Shae is a dog, she is a {shae_breed}")
output: Shae is a dog, she is a pitbull

```


## Sequence types

### list

* Ordered
* Mutable
* Duplicates are allowed

A listben nincsenek kulcsszavak, a sorszámukra tudunk hivatkozni.


0-tól kezdjük a számolást, az első elemet a [0] accessorral tudjuk lekérni.

```python
my_basket = ['eggs', 'milk', 'bread', 'chocolate', 'chocolate']

print(my_basket[0])

output: eggs

print(my_basket[2])

output: ???


# Adding an element
my_basket.append('beer')

print(my_basket)
['eggs', 'milk', 'bread', 'chocolate','chocolate','beer']


# Changing an element
my_basket[0] = 'butter'
print(my_basket)
output: ['butter', 'milk', 'bread', 'chocolate','chocolate','beer']

# Length of list
print(len(my_basket))
output: 6

```


### tuple

* Ordered
* Immutable
* Duplicates are allowed

```python
lotr_tuple = ('The Fellowship of the Ring,', 'The Two Towers', 'The Return of the King')

# Access an element
print(lotr_tuple[0])
output: The Fellowship of the Ring

# Cannot change an element
lotr_tuple[0] = 'Rambo II'
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
...code.py in <module>
----> 1 x[0] = 'Rambo II'

TypeError: 'tuple' object does not support item assignment

```


### set

* Unorderd
* Set is mutable, elements are not
* Duplicates are not allowed

```python
dogs_set = {'beagle', 'american pitbull terrier', 'fox terrier', 'puli', 'pumi', 'napolitan'}
print(dogs_set)
output: {'puli', 'fox terrier', 'napolitan', 'pumi', 'american pitbull terrier', 'beagle'}
# Python caches this print, that's why I create a new set
dogs_set2 = {'beagle', 'american pitbull terrier', 'fox terrier', 'puli', 'pumi', 'napolitan'}
print(dogs_set2)
output: {'pumi', 'american pitbull terrier', 'beagle', 'puli', 'fox terrier', 'napolitan'}


# pop() gets and removes an element from the set:
dogs_set.pop()
output: 'puli'
print(dogs_set)
# puli is not there anymore
output: {'american pitbull terrier', 'beagle', 'fox terrier', 'napolitan', 'pumi'}

```




