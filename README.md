# SensorApp - Ivan Matejčić

## Kratak opis
Izrađena je aplikacija koja koristi sensor akcelerometra te dohvaća real-time poziciju uređaja i njegove koordinate.
Za testiranje korišten je fizički mobitel.
Koristi se vrlo jednostavno: pokrene se aplikacija te će, kako se uređaj kreće, mijenjati unutar aplikacije vrijednosti X, Y i Z koordinata.

Izrađen je akcelerometar te je profiliran CPU.

## Kod

Kod aplikacije je jednostavan.  Od default tempalte-a nije mnogo promijenjeno.
Za izgled same aplikacije, koristio sam slijedeći kod:

```
<GridLayout rows="40, 40, 40" columns="30,*,30">
    <Label text="{{ x }}" row="0" col="1" backgroundColor="#CC0000"></Label>
    <Label text="{{ y }}" row="1" col="1" backgroundColor="#CC0000"></Label>
    <Label text="{{ z }}" row="2" col="1" backgroundColor="#CC0000"></Label>
</GridLayout>
```
Postavio sam da je pozadinska boja crvena i da se ispišu sve 3 koordinate.

Također, dodao sam kod kako bi se prikazao tekst svih triju koodrinata i njihove vrijednosti zaokružene na tri decimale.

```
viewModel.set('x', "X = " + data.x.toFixed(3))
    viewModel.set('y', "Y = " + data.y.toFixed(3))
    viewModel.set('z', "Z = " + data.z.toFixed(3))
```

## Problemi

U ```home-view-model.js``` datoteci sam imao problem da mi se aplikacija nije htjela ispravno pokrenuti i to sam promijenio tako da sam zamijenio ime funkcije ```SensorViewModel()``` i ```HomeViewModel()```.

```
export function HomeViewModel() {
  const viewModel = new Observable()
```

Nadalje, u prvom poku[aju sam poku[ao koristiti emulator. Svaki put kada bi ga poku[ao pokrenuti, dobio bih slijedeću pogrešku:

![Error](/error.png)

Ovaj problem sam riješio tako da sam u terminal unio slijedeću komandu:

```
$ sudo chown $USER:$USER $ANDROID_HOME -R
```

S ovom komandom postajem administrator i nakon toga sam mogao uspješno pokrenuti Android emulator.

Tijekom izrade projekta, skakao sam između Linux-a i Windows-a.
Dok nisam shvatio prijašnji problem na Linux-u, prebacio sam se na WIndows u nadi da će mi raditi sa manje problema.
No, pojavio se problem kojeg nisam uspio shvatiti:

![Error 2](/error2.png)

Provjerio sam je li mi je slučajno bila ugašena virtualizacija u BIOS-u, no nije, tako da nisam znao kako preći ovaj problem, te sam nastavio na Linux-u.

Naposlijetku, u Android Studio-u sam imao problem sa pokretanjem Profiler-a, nije mi se pojavljivao doduše.
Taj problem sam riješio tako da sam u postavkama dodao Android facet.

![Error 3](/Screenshot%20from%202022-03-31%2001-03-07.png)

## Profiliranje

Kao što je na početku navedeno, provedeno je profiliranje CPU-a.
Pokrenuta sesija je snimana (nekoliko sekundi) te iz povratno primljenog flow-charta se može zaključiti da je aplikacija poprilično dobro optimizirana, s time da je vrlo mala, nema mnogo koda niti značajki te zauzima jako malo prostora i memoriji. Također, uređaj koji je korišten za prikaz same aplikacije ima više nego dovoljne mogućnosti da pokrene takvu aplikaciju.
Navedeno je pokazano u priloženoj ```.trace``` datoteci.

Flow chart:

![Profiliranje](/Screenshot_from_2022-03-31_00-27-48.png)

Screenshot aplikacije:

![Aplikacija](/unknown.png)

Kod je dostupan na: https://github.com/IvanMatejcic/SensorApp
    
# Literatura

https://hackmd.io/@mateaturalija/HJxGpje6t
https://hackmd.io/@mateaturalija/SylevVscF
https://hackmd.io/@mateaturalija/rJhpueW9Y
https://hackmd.io/@mateaturalija/SJ4rilo2F

https://developer.android.com/studio/run/managing-avds
https://stackoverflow.com/questions/18368748/android-studio-module-wont-show-up-in-edit-configuration
https://stackoverflow.com/questions/69034879/how-can-i-resolve-the-error-the-mincompilesdk-31-specified-in-a-dependencys
https://developer.android.com/studio/run/emulator-acceleration#vm-windows-aehdamd
