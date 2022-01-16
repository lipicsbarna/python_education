# Dictionary operations
### Creating dicts

```python
empty_dict = {}
empty_dict2 = dict()

my_dict = {
    'Csuti': 'mutt',
    'Shae' : 'sufni pitbull terrier',
    'Boni' : 'german staffordherd terrier'
}

# You can create a dict from list:
dict_keys = ['Csuti', 'Shae', 'Boni']
my_dict_from_list = dict.fromkeys(dict_keys)
# {'Csuti': None, 'Shae': None, 'Boni': None}

# You can define a dict with default values
from collections import defaultdict

my_defaultdict = defaultdict.fromkeys(['Csuti', 'Shae', 'Boni'], 'unknown')
# defaultdict(None, {'Csuti': 'unknown', 'Shae': 'unknown', 'Boni': 'unknown'})
```

### Accessing values based on keys

```python
my_dict = {
    'Csuti': 'mutt',
    'Shae' : 'sufni pitbull terrier',
    'Boni' : 'german staffordherd terrier'
}

print(my_dict['Csuti'])
# 'mutt'

# This method throws an exception if key is not present:
print(my_dict['Lilike'])
```

```
Output:
mutt

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'Lilike'
```

### The __get__ method
```python
my_dict = {
    'Csuti': 'mutt',
    'Shae' : 'sufni pitbull terrier',
    'Boni' : 'german staffordherd terrier'
}

print(my_dict.get('Boni'))
# 'german staffordherd terrier'

# This doesn't throw exception if key is not present, but the value vill be None
print(my_dict.get('Lilike'))
# None

# Or you can define a default
print(my_dict.get('Lilike', 'unkown'))
# unkown
```

```
Output: 
german staffordherd terrier
None
unknown
```

You can ask for all keys or all values of dict:
```python

my_dict = {
    'Csuti': 'mutt',
    'Shae' : 'sufni pitbull terrier',
    'Boni' : 'german staffordherd terrier'
}

# Keys
print(my_dict.keys())

# Values
print(my_dict.values())

# Don't worry, you can convert them to e.g a list without problem:
print(list(my_dict.values()))
```

```
Output:
dict_keys(['Csuti', 'Shae', 'Boni'])

dict_values(['mutt', 'sufni pitbull terrier', 'german staffordherd terrier'])

['mutt', 'sufni pitbull terrier', 'german staffordherd terrier']
```

You can get the key-value pairs as tuples, which is important of you want to iterate through a dictionary:

```python
my_dict = {
    'Csuti': 'mutt',
    'Shae' : 'sufni pitbull terrier',
    'Boni' : 'german staffordherd terrier'
}

print("These are the items as tuple pairs:")
print(my_dict.items())

for key,value in my_dict.items():
    print(
        f"My dog,{key} is a {value}."
    )
```

```
Output:
These are the items as tuple pairs:
dict_items([('Csuti', 'mutt'), ('Shae', 'sufni pitbull terrier'), ('Boni', 'german staffordherd terrier')])

My dog,Csuti is a mutt.
My dog,Shae is a sufni pitbull terrier.
My dog,Boni is a german staffordherd terrier.
```
Többféleképp tudjuk módosítani az értékeket:
```python
my_dict = {
    'Csuti': 'mutt',
    'Shae' : 'sufni pitbull terrier',
    'Boni' : 'german staffordherd terrier'
}

my_dict['Boni'] = 'german helicopherd staffbull'
my_dict.update({'Boni', 'gemarican staffherd'}) 
```

Akár egy másik dictionary több értékével is módosíthatok
```python
my_dict = {
    'Csuti': 'mutt',
    'Shae' : 'sufni pitbull terrier',
    'Boni' : 'german staffordherd terrier'
}

my_second_dict = {
    'Csuti': 'street special',
    'Shae' : 'half dog-half couch'
}

my_dict.update(my_second_dict)
print(my_dict)
```

```
Output:
{'Csuti': 'street special', 'Shae': 'half dog-half couch', 'Boni': 'german staffordherd terrier'}
```

