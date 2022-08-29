# Tutorials per Nord 2 in Italiano 

## Sblocco Bootloader 
La seguente guida è stata tradotta e adattata da quella di [Giovix92](https://gist.githubusercontent.com/Giovix92/c7e69123dbc51adf3f3a26f9c3c0208e/raw/67f889028f68d929b7ada0db846980fb599a2253/Nord2Guides.md)

### Prerequisiti

- Un Nord 2, varianti incluse (ovvio) 
- Un backup completo del tuo dispositivo (Vi ricordo che sbloccare il dispositivo **CANCELLERA' TUTTI I DATI SUL TELEFONO!**)
- ADB funzionante sul vostro PC
- Delle conoscenze quantomeno basiche di quello che state per fare. Sai, vorremmo evitare che fotteste a vita il vostro telefono 

### Procedimento

- Apri qualunque finestra di cmd / Powershell / Terminale / Console sul vostro pc (Non so cosa usate, quindi vado un pò a caso lol) 
- Assicuratevi di aver correttamente installato ADB (dovreste essere in grado di poter digitare `adb devices` sul vostro terminale e vedere qualcosa. In caso contrario, vi invito a settare ADB cercando un pochetto su Google)
- Dalle opzioni sviluppatore (visibili premend 7 volte su Numero Build) attivate Sblocco OEM e Debug USB
- Riavviate il vostro device (connesso al PC) in Fastboot in uno dei seguenti modi
  - Se siete su Android 11 (E vi consiglio di esserci), potrete riavviare in recovery con la combinazione di tasti Vol - e Power.
  - Se site su Android 12, dovrete scrivere sul vostro terminale / console / cmd / powershell `adb reboot fastboot`.
- Scrivete sul vostro terminale `fastboot flashing unlock` per iniziare il processo di sblocco. Dopodichè, premete Vol + per accettare.
- Dopo qualche secondo, potete riavviare nel sistema con il comando: `fastboot reboot`
