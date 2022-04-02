# SensorApp - Ivan Matejčić

## Kratak opis
Izrađena je aplikacija koja koristi sensor akcelerometra te dohvaća real-time poziciju uređaja i njegove koordinate.
Za testiranje korišten je fizički mobitel.
Koristi se vrlo jednostavno: pokrene se aplikacija te će, kako se uređaj kreće, mijenjati unutar aplikacije vrijednosti X, Y i Z koordinata.

Izrađen je akcelerometar te je profiliran CPU.

## Profiliranje

Kao što je na početku navedeno, provedeno je profiliranje CPU-a.
Pokrenuta sesija je snimana (nekoliko sekundi) te iz povratno primljenog flow-charta se može zaključiti da je aplikacija poprilično dobro optimizirana, s time da je vrlo mala, nema mnogo koda niti značajki te zauzima jako malo prostora i memoriji. Također, uređaj koji je korišten za prikaz same aplikacije ima više nego dovoljne mogućnosti da pokrene takvu aplikaciju.
    
![unknown](https://user-images.githubusercontent.com/84573071/161389247-012f897c-8790-477d-b981-e58501c4459d.png)    
    
# Literatura

https://hackmd.io/@mateaturalija/HJxGpje6t
https://hackmd.io/@mateaturalija/SylevVscF
https://hackmd.io/@mateaturalija/rJhpueW9Y
https://hackmd.io/@mateaturalija/SJ4rilo2F

https://developer.android.com/studio/run/managing-avds
https://stackoverflow.com/questions/18368748/android-studio-module-wont-show-up-in-edit-configuration
https://stackoverflow.com/questions/69034879/how-can-i-resolve-the-error-the-mincompilesdk-31-specified-in-a-dependencys
https://developer.android.com/studio/run/emulator-acceleration#vm-windows-aehdamd
