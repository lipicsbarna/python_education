# GitHub Desktop használata

A git jelenleg a világ legelterjedtebb verziókezelő rendszere.

Feladata, hogy egyszerű parancsokkal tudjunk szinkronizálni, üzembe helyezni, másolni, verziózni kódokat.

A GitHub a git egy online, ingyenesen (is) használható platformja, itt fogunk együttműködni a kurzuson megjelenő kódokkal.

Érdemes elolvasni legalább az _about git_ fület, az nagyjából le is fedi az általunk is használandó funkciókat.

Eredeti, angol nyelvű dokumentáció: [git](https://docs.github.com/en/get-started/using-git/about-git).


Mi nem fogjuk használni a kurzuson a command line megoldást, helyette a GitHub Desktopban végezzük a verziózást.

A következőképp fog működni egy átlagos eset:


## Saját kód, pl. házi feladat, projektmunka kezelése a GitHubon

### Clone/Init
A clone paranccsal egy létező repositoryt húzunk le a saját számítógépünkre; az Init paranccsal egy létező kódbázist tudunk repositoryként létrehozni.


### Branch
Saját branch létrehozása.

Egy branch a kódnak egy párhuzamos valósága. Többen tudunk dolgozni ugyanazon a kódbázison anélkül, hogy a _main_ módosulna.




Branchek:
![alt text](https://www.nobledesktop.com/image/gitresources/git-branches-merge.png)

Forrás: [Git branches](https://www.nobledesktop.com/learn/git/git-branches)



Ennek egyik előnye, hogy nem törjük el egymás kódjait, nem keletkeznek conflictok.

A másik, hogy egy éles kódbázisba nem kerül teszteletlen, még fejlesztés alatt álló kód.

A házi feladatok, projektek során saját branchre tudunk dolgozni, és ide tudjuk commitolni, pusholni a megoldásainkat.


### Kódok írása/módosítása
Nem a githez köthető, de ezek implikálják a repositoryban végbemenő változásokat.


### Commit
Pillanatkép arról, ahogy éppen most kinéz a kód. Egy logikai egység, pl. egy új funkció lefejlesztése. Csak a saját számítógépen történik meg.


### Push
Az utolsó push és az azóta "lefotózott" pillanatképek, commitok publikálása a távoli repositoryba (esetünkben GitHubra.)


## Egyéb funkciók

### Fetch origin
A távoli szerverről a lokális számítógépre letölti a módosításokat - az adott branchre!

### Checkout
A checkout paranccsal válthatunk a branchek közt. 