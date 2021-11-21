 # Kezdő lépések a szükséges környezet telepítéséhez




# GitHub

Szükséges, hogy regisztráljunk a GitHub.com-on egy felhasználót.
[GitHub registration](https://github.com/join)



Ezután töltsük le a GitHub desktop alkalmazást -
[GitHub Desktop](https://desktop.github.com/) - 
majd jelentkezzünk be az előző lépésben létrehozott felhasználóval.


Érdemes lehet egy külön _git_ mappát létrehozni a számunkra megfelelő helyen a számítógépen.


Következő lépésben keressük meg a _clone repository_ gombot, és 
ezt a repositoryt clone-ozzuk az előzőleg létrehozott _git_ mappába: _https://github.com/lipicsbarna/python_education_




# Python


A képzéshez Python 3.10-es verzióra lesz szükség; jelenleg még bugfix fázisban van, viszont tartalmaz olyan feature-öket, amiket mindenképp szeretnék megmutatni.


Éles vállalati rendszeren még nem futtatnám ezt a verziót, de hamarosan jönnek a hibajavítások, és legalább addigra ismerni fogjátok.




Aki Macintosh/Linux alól telepít, természetesen lehet a megfelelő package managerrel is telepíteni, de aki ismeri ezek használatát, nem fog gondot okozni a telepítés, és nincs szükség az alábbiak elolvasására.




## Telepítés


[Python letöltése](https://www.python.org/downloads/)

A Download Python3.10 gombra rányomva töltsük le a telepítőt. Az operációs rendszernek megfelelő telepítő varázslót végig kell majd kattintgatni.

Érdemes feljegyezni, hogy hova kerül telepítésre, 
Windowson pl. a képen is látható minta alapján jó eséllyel ide kerül:

C:\Users\MyUser\AppData\Local\Programs\Python\Python3.10

![alt text](https://docs.python.org/3/_images/win_installer.png)

Az utolsó oldalon érdemes _Add Python 3.10 to PATH_ gombot kipipálni.




### Honnan tudom, hogy sikerült telepítenem?
Parancssorba/terminálba beírva az indító parancsot, elindul a Python interaktív shell.
Ez jó eséllyel a _python3.10_lesz, de lehet _py3_, _py_, vagy _python_ is.

A dokumentáció következő részein a `python3.10` aliast fogjuk használni, de ha a saját gépen nem ez az alias, akkor értelemszerűen a megfelelőre cseréljük le a saját gépünkön.

Akkor találtuk el a jó parancsot, ha indulás után is azt látjuk, hogy a 3.10-es verzió indult el.





```
lipicsbarna@Lipics-MacBook-Pro ~ % python3.10
Python 3.10.0 (v3.10.0:b494f5935c, Oct  4 2021, 14:59:20) [Clang 12.0.5 (clang-1205.0.22.11)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```





A legtöbb programozást oktató anyag egy “Hello world” szösszenettel kezdődik, megmutatja, hogy tudjuk kiírni konzolra a szöveget.

Hogy igazán érezzétek, hogy már egy kicsit része vagytok a programozás világának, írjátok be:


`print("Hello world")`


Ha sikerült jól begépelni, akkor vissza fog köszönni:


```
>>> print("Hello world")
Hello world
```

Az `exit()` paranccsal lehet kilépni a shellből.




Ezután számítógépen parancssorban (Windows Parancssor, vagy Linux/Mac terminál) lépjünk be abba a mappába, 
ahova clone-oztuk a repositoryt, pl. (`cd C:\Users\MyUser\git\python_education`).


Gépeljük be a következőt:


`pip install -r requirements.txt`


Ezzel a paranccsal telepítésre kerülnek a szükséges csomagok.

Ha nem találja, a `pip` parancsot, akkor próbáljuk helyette a 

`python3.10 -m pip install -r requirements.txt` 

parancsot.

