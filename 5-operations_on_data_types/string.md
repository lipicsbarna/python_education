# String operations

### String létrehozása
```python
# These are one-liners
my_str = 'Hi, I am a string.'
my_str_two = "Hi, I'm also a string."

# This way you can define a multiline string
my_str_multiline = """
Hi there, I 'm a quite long string.
Honestly.
Frankly.
No doubt.
"""
```

Mi a különbség?

Az egysorosok közt szinte semmi, kivéve egy apróságot. Az a gondolatmenet segíthet, hogy az aposztrófos definiálás nem engedi, hogy escape-elés nélkül (pár sorral lejjebb lesz róla szó) aposztróf kerüljön a szövegbe:

```python
my_str = 'I'm a string'
  File "<stdin>", line 1
    my_str = 'I'm a string'
             ^^^^
SyntaxError: invalid syntax. Perhaps you forgot a comma?
```

És ugyanez igaz a macskakörömre is:
```python
my_str = " She answered. "No, thanks" "
  File "<stdin>", line 1
    my_str = " She answered. "No, thanks" "
             ^^^^^^^^^^^^^^^^^^^
SyntaxError: invalid syntax. Perhaps you forgot a comma?
```

Ha a másikat használjuk a szövegben, akkor nem lesz gond:

```python
my_str = "I'm a string."
my_str2 = 'She answered. "No, thanks."'
```

### Escape

Ha olyan karakter kerül a string mezőnkbe, amelyet a Python alapvetően nem abban a formában értelmezne (pl. newline, azaz \n, vagy aposztrófot tennénk ki a stringen belül), akkor egy backslash, azaz __\\__ karakterrel tudjuk jelezni a Pythonnak, hogy legyen kedves szövegként értelmezni.

Javítsuk ki az előző aposztrófos kódot:

```python
my_str = 'I\'m a string'
print(my_str)
```

```
Output: "I'm a string"
```


### String templating

Egy stringet többféleképpen parametrizálhatunk.
Ennek előnye, hogy dinamikusan tudunk szövegeket kitölteni; egy egyszerű példa meghívók, levelek megfogalmazása, ahol csak a név, cím változik.


Az interneten és a cégeknél is gyakran találkozni a string formatting stílusú parametrizálással. Egyik változata, amikor így jelöljük a beillesztendő string helyét: ```%s```
Vélemény: nem jól olvasható, nehezen karbantartható.
```python
print("Hi, I am %s, %s year old" % ("Uruk Hai", "1"))
```

```
output: Hi, I am Uruk Hai, 1 year old
```

Eggyel tisztább megoldás a ```{}```
Ezt lazy evaluationnek hívjuk, mert amíg nem töltjük ki a lyukakat, addig ez csak egy template, teljes értékű string csak a kitöltéskor lesz; nem dob hibát, ha nem kapott még paramétert.

```python
my_str = "Hi, i am {}, {} year old."
my_str.format("Uruk-hai", 1)
```

Ugyanúgy lazy evaluationnel előkészíthetjük elnevezett paraméterekkel is. Ennek előnye, hogy olvasható, jól karbantartható, és továbbra is fennáll a lazy evaluation intézménye.
```python
my_str = "Hi, i am {name}, {age} year old."
my_str.format(name="Uruk-hai", age=1)
```
### F-string
Az F-string külsőre hasonló a string templatinghez, de nem lazy, hibát fog dobni, ha nem léteznek a meghivatkozott paraméterek.

```python
last_name = "Bond"
full_name = "James Bond"
x = f"My name is {name}. {full_name}"
```

```
output: My name is Bond. James Bond
```

### Operations
A python nyelv számos beépített string-műveletet biztosít számunkra.
Ezeket a funkciókat a következő szintaxissal tudjuk elérni:
```
my_str.function()
```
Például:
```python
print("hello".capitalize()) # Hello
print("hello".upper()) # HELLO
print("HELLO".swapcase()) # hello
```


### Splitting
Tudunk például listát készíteni stringekből egy adott delimiter string mentén:
```python
delimiter = ","
my_string = "Pavarotti,Domingo,Carreras,del Monaco,Björling"
print(my_string.split(delimiter))
```

```
Output: ['Pavarotti', 'Domingo', 'Carreras', 'del Monaco', 'Björling']
```