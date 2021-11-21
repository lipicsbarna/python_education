# Jupyter notebook futtatása

A Jupyter a Python ökoszisztéma kihagyhatatlan eleme, amely hatalmas segítség abban, hogy kényelmesen, 
böngészőben tudjunk kódokat kipróbálni, elemezni, adatokat vizualizálni, stb. 

[Jupyter](https://jupyter.org/)




A kurzus során a Jupyter újabb változatát a Jupyter-Labot fogjuk használni. Ez nemcsak a notebookokat foglalja magába, hanem konzolt, IDE funkciót is, stb.



Amennyiben végrehajtottuk a Python telepítésekor a `pip install -r requirements.txt` lépést, az azt jelenti, hogy már fel van telepítve a számítógépünkre a Jupyter-lab.


Lépjünk be parancssorba, majd futtassuk le a következőt:

`python3.10 -m jupyter-lab --no-browser`

(Amennyiben biztosak vagyunk, hogy a rendszer alapértelmezett böngészője jó nekünk, a --no-browser kapcsolót lehagyhatjuk)




A terminálon keressük ki ezt a részt, majd valamelyik http-vel kezdődő linket másoljuk be a böngészőbe, és nyissuk meg.
```
[C 2021-11-21 23:24:12.152 ServerApp]

    To access the server, open this file in a browser:
        file:///path/path/path/Library/Jupyter/runtime/jpserver-1234-open.html
    Or copy and paste one of these URLs:
        http://localhost:8888/lab?token=78bb9841893b5673075607a096c84ba10dfd01bb3ea2dbac
     or http://127.0.0.1:8888/lab?token=78bb9841893b5673075607a096c84ba10dfd01bb3ea2dbac
```



Amikor végeztünk, Ctrl+C, Ctrl+C billentyűkombinációval (igen, kétszer) le tudjuk zárni a Jupyter szervert.


# TODO - Verziókezelés