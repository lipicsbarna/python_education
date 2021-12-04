# String operations

Egy stringet többféleképpen parametrizálhatunk.
Ennek előnye, hogy dinamikusan tudunk szövegeket kitölteni; egy egyszerű példa meghívók, levelek megfogalmazása, ahol csak a név, cím változik.

### String templating
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
