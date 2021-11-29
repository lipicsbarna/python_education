# What is Python?

[Python.org](https://www.python.org/)

### Wikipedia
Python is an interpreted high-level general-purpose programming language. 

Its design philosophy emphasizes code readability with its use of significant indentation. 

Its language constructs as well as its object-oriented approach aim to help programmers write clear, logical code for small and large-scale projects.

Python is dynamically-typed and garbage-collected. 


It supports multiple programming paradigms, including structured (particularly, procedural), object-oriented and functional programming. 




![alt text](https://i.kym-cdn.com/photos/images/original/000/746/678/5cd.png)




### Interpreted

A forráskódot, amit szövegfájlként írunk meg, az interpreter lefordítja bytecode-ra, ezt futtatja a Virtual Machine.

![alt text](https://media.geeksforgeeks.org/wp-content/uploads/python_working.png)



### High-level

Nem szükséges kézzel kezelnünk a hardver elemeit (memóriaallokációk, stb.), sokkal magasabb szinten elegendő leírnunk a szándékunk.


### General-purpose

Vannak nyelvek, amelyek egy bizonyos területre alkalmasak, vagy legalábbis arra fókuszálnak (pl. Matlab, R). A Python használható szinte az IT bármely területére, pl. webfejlesztés, data science, data engineering, asztali szoftverek, stb.



### Dynamically typed

Pythonban nem lehet meghatározni, hogy egy változó milyen típusú legyen, azt az interpreteren keresztül fogja kitalálni.

Például Java-ban szükséges megadni a változóink típusát:
```java
String my_text = String("Hello World")
```

Vagy Scalában:
```scala
val myString: String = "Hello World"
```

Pythonban ez nincs kikényszerítve:
```python
my_string = "Hello World
```

Bár a nyelv lehetőséget ad arra, hogy a kód olvasójának, szövegszerkesztőnek segítsünk a type hintek segítségével:

```python
# Itt pl. magától értetődő a típus
my_string: str = "Hello World"

# Bonyolultabb eseteknél viszont segítség
class Cat:
    def __init__(self, name):
        self.name = name

cirmos: Cat = Cat("cirmos")

# ...viszont semmi sem történik, ha nem mondtunk igazat:
x: int = "hi"
x
'hi'
```

ellentétben az erősen, statikusan típusos nyelvekkel:
```scala
// Scala
val myString: String = 5

type mismatch;
 found   : Int(5)
 required: String
```


### Garbage-collected

Alacsonyabb szintű nyelveknél, pl. C, C++, ha lefoglaltunk egy memóriaterületet, azt nekünk kell feloldanunk a kódban explicit, ha már nem lesz szükségünk valamire.

```c++
// C++
int *ptr;
ptr = (int*) malloc(5*sizeof(int));

for (int i=0; i<5; i++)
	{
		cout << *(ptr+i) << " ";
	}
free(ptr);
```

Pythonban erre nincs szükség, a beépített garbage collector az interpretált kód alapján tudja, hogy nincs már szükségünk a változóra, ezért szabaddá teszi a memóriaterületet. (Ez az automatizmus járhat hátránnyal is az alacsonyabb szintű nyelvekhez képest.)


## Multi-paradigm

### Procedural

Alacsonyabb szintű nyelveknél található meg, pl. C

A program állapotát változtatjuk egyszerű utasításokkal.

```python
state = [1,2,3,4,5]

def double_them(state_to_double: list[int]):
    _temp_list = []
    for num in state_to_double:
        _temp_list.append(num * 2)

new_state = double_them(state)
```


### Object-oriented

```python
# Procedurális verzió

boni_name = 'Boni'
boni_age = 3
boni_breed = 'bulltype'

csuti = {
    'name' : 'Csuti',
    'age'  : 13,
    'breed': 'mutt'
}

shae = {
    'name'  : 'Shae',
    'age'   : 8,
    'breed' : 'american pitbull terrier'
}

def print_dog(name, age, breed):
    print(
        f"{name} is {age} old and a {breed}"
    )

print_dog(boni_name, boni_age, boni_breed)    
print_dog(shae["name"], shae["age"], shae["breed"])

# Minden alkalommal bővíteni fogjuk?
def voice(breed):
    if breed == 'american pitbull terrier':
        print('avuvuvuvu')
    elif breed == 'napolitan':
        print('bu')
    elif breed == 'beagle':
        print('never-ending-vu-vu-vu-vu')
    else:
        print('vau')

# Mi van, ha szeretnék egy új attribútumot hozzáadni a kutyákhoz?
# Végig kell vezetnem az összes egyedi változón.

# Mit tud az objektum-orientált paradigma?

class Dog:

    def __init__(self, name, age, breed):
        self.name = name
        self.age = age
        self.breed = breed

    def print_dog(self):
         print(
        f"{self.name} is {self.age} old and a {self.breed}"
    )

    def voice(self):
        print("Vau")

# Ha szeretnénk valamit hozzáadni, egy helyen kell megtennünk

class Dog:

    def __init__(self, name, age, breed, color="black"):
        self.name = name.capitalize()
        self.age = age
        self.breed = breed
        self.color = color

    def print_dog(self):
         print(
        f"{self.name} is a {self.age} old {self.color} colored {self.breed}"
    )

    def voice(self):
        print(f"{self.name} says vau.")

csuti = Dog("Csuti", 13, "mutt")
shae = Dog("Shae", 8, "american pitbull terrier")

csuti.print_dog()

###################################

class Beagle(Dog):

    def __init__(self, name, age):
        self.name = name.capitalize()
        self.age = age
        self.breed = "beagle"

    def voice(self):
        print(f"{self.name} says never-ending-painly-vu-vu-vu")

class Caucasian(Dog):

    def voice(self):
        print(f"{self.name} doesn't say anything, just bites.")

my_beagle = Beagle("bigli", 5)
my_beagle.voice()

output: Bigli says never-ending-painly-vu-vu-vu

kau = Caucasian("feri", 2, "caucasian")
kau.voice()
output: Feri doesn't say anything, just bites.

kau.print_dog()
Feri is a 2 old black colored caucasian.
```

### Functional paradigm

A funkcionális paradigma egyik alapköve, hogy olyan _pure_ funkciókat készítsünk, amelyek determinisztikusak, azaz mindig ugyanazt az outputot kapjuk ugyanarra az inputra. Ez egyszerűnek tűnik, de nem az.

Nem szabad, hogy legyen a funkcióinknak _side effect_-je, azaz amit módosítunk, arról a funkciónak mind tudnia kell.

Ennek egyik előfeltétele, hogy az objektumainkat _immutable_-ként kezeljük, nem módosítjuk őket. Ez Pythonban nem lehetséges technikailag úgy mint pl. Scalában, ezt a szemlélet tudja hozni. 

Ez jelentősen megkönnyíti a debugolást, és jól karbantartható kódot eredményez.

```python
# Not functional
state = [1,2]

state.append(3) # Side effect

state.valami()
```

```python
state = [1,2]
new_state = state.copy()
new_state.append(3)

print(state)
print(new_state)

output: [1,2]
output: [1,2,3]
```

```scala
val state = List(1,2)
val newState = state :+ 3
```

