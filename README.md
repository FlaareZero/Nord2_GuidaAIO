# Tutorials per Nord 2 in Italiano 

## Sommario

- [Sblocco Bootloader](#sblocco-bootloader) e [Re-Lock del Bootloader](#Re-Lock-del-Bootloader)
- [Rooting del dispositivo](#Rooting-del-dispositivo)
- [Backup / Ripristino del dispositivo tramite MTKClient](#Backup-o-Ripristino-tramite-MTKClient)

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

## Re-Lock del Bootloader

Ribloccare il bootloader può essere un pò tedioso alle volte, seppur il procedimento sia simile a sopra, apparte per il comando usato, che è  `fastboot flashing lock`. Può variare soprattutto per i seguenti motivi:

- Precedenti installazioni di Magisk/Zygisk ancora attive sul device;
- Altre Mod installate, se ne avete qualcuna;
- Precedenti e ancora attive installazioni di TWRP / OrangeFox / Custom recovery varie;

### Procedimento
- Riavviate il vostro device (connesso al PC) in Fastboot in uno dei seguenti modi:
  - Se siete su Android 11, potrete riavviare in recovery con la combinazione di tasti Vol - e Power.
  - Se site su Android 12, dovrete scrivere sul vostro terminale / console / cmd / powershell `adb reboot fastboot`.
- Scrivete, appunto, `fastboot flashing lock`, poi `fastboot reboot`.
- Fatto!

Se vi capita di incappare nella seguente scritta: "Boot image destroyed/corrupted" condita da grande triangolo rosso, calma: E' tutto sotto controllo. Miglior cosa da fare è:

- Basterà usare un backup (gentilmente offerto da Giovix92 nel suo gist [qui](https://files.giovix92.workers.dev/0:/OnePlus%20Nord%202/Stock%20ROMs/)) che combacia con la versione di OxygenOS che avete sul vostro device. Ad esempio, se siete tornati ad A11 con il pacchetto di Rollback, avrete la A20 installata.
  - Le immagini da avere a disposizione sono le seguenti: dtbo, recovery, vbmeta, boot.
- Riavviate il vostro device (connesso al PC) in Fastboot in uno dei seguenti modi
  - Se siete su Android 11 (E vi consiglio di esserci), potrete riavviare in recovery con la combinazione di tasti Vol - e Power.
  - Se site su Android 12, dovrete scrivere sul vostro terminale / console / cmd / powershell `adb reboot fastboot`.
  - EXTRA: Se non potete usare ADB per qualche strano motivo (boh, forse siete bloccati in Fastboot) vi basterà usare `fastboot reboot fastboot` per riavviare in Fastbootd da, per esempio, la modalità bootloader.
  - EXTRA 2:Se non potete usare la modalità Fastbootd, FERMATEVI. Vi servirà MTKClient (spegnete il telefono e tenete premuti i tasti vol - , vol + e power, da PC scaricate MTKClient da [qui](https://t.me/OnePlusNord2GlobalOfficial/156958) e installate prima i Drivers, poi aprite MTKClient_Gui. Una volta aperto, collegate il telefono al PC)
- Se siete su Fastboot, usate i seguenti comandi per caricarli sul vostro device: 
  
  - fastboot flash boot boot.img
  - fastboot flash recovery recovery.img
  - fastboot flash vbmeta vbmeta.img
  - fastboot flash dtbo dtbo.img`
  
- Eseguite `fastboot flashing lock`, poi `fastboot reboot` per completare il processo.
- Il vostro Nord è tornato ufficiale! Congratulazioni!


## Rooting del dispositivo

Il Root sul Nord 2 comporterà il patching del boot.img relativo alla vostra versione di OxygenOS installata. Si, un pò diverso dal solito :)
Va sia su Android 11 che su Android 12!

### Prerequisiti

- LEGGETE E RILEGGETE GLI STEPS PRIMA DI ANDARE AVANTI! Non sia mai che non capite :p
- Telefono caricato al 100%, onde evitare problemi

### Procedimento

- Collegatevi [qui](https://t.me/moddingopnord/6390) per avere accesso a tutte le versioni stock dei vari boot.img disponibili. Ovviamente, vi servirà quello allineato alla vostra versione di Oxygen!
- Scaricate l'ultima versione dell'APK Magisk dal [Github Ufficiale](https://github.com/topjohnwu/Magisk/releases), e installatela.
- Apritela, selezionate 'Installa' e poi `Seleziona e Applica su File`
- Selezionate il file scaricato da Telegram
- Lasciate che lo patchi.
- Copiate quel file sul vostro pc (in qualunque modo vi venga più comodo)
- Riavviate il device in Modalità Fastboot
  - Se siete su Android 11 (E vi consiglio di esserci), potrete riavviare in recovery con la combinazione di tasti Vol - e Power.
  - Se site su Android 12, dovrete scrivere sul vostro terminale / console / cmd / powershell `adb reboot fastboot`.
- Supponendo che il file si chiami 'vattellapesca.img', Il comando sarà, da fastboot: `fastboot flash boot vattellapesca.img`. Cambiate il nome adeguatamente!
- Riavviate il device con il comando `fastboot reboot`

Voilà! Il Vostro Nord 2 ha anche il root adesso :)

Per l'unroot basterà riscaricare il boot.img ed installarlo da Fastboot come citato sopra, niente di più semplice!

## Backup o Ripristino tramite MTKClient

Questo è il metodo più efficace per ripristinare il vostro device come di fabbrica.

- Prima di fare qualsiasi cosa, è consigliato, da MTKClient, salvare tramite la voce Read le seguenti partizioni:
  - seccfg , persist, nvcfg , nvdata , nvram , protect1 , protect2
Così sarete sempre coperti in caso di perdita IMEI, Wi-Fi non funzionante, che può capitare ripristinando il device con un backup magari diverso da quelli di Giovix92, oppure da Custom Rom poco conosciute.

- Seguite l'installazione del programma dalla [repo ufficiale](https://github.com/bkerler/mtkclient) o del [prebuilt se volete la via semplice](https://t.me/OnePlusNord2GlobalOfficial/156958). Vi serviranno anche i [Driver MTK](https://drive.google.com/file/d/1TPbW-v9-yOrzH15OaHmsPQad420mULeF/view) per far collegare il device al pc correttamente. 
Basterà seguire letteralmente le istruzioni a schermo, in modo da avviare il device in BROM mode. Le riporto per comodità e per informazione:

  - Essenzialmente, spegnete il device, e con il programma aperto in background tenete premuto vol - , vol + e collegate il cavo USB mentre lo fate. 
  - Dovreste vedere il programma riconoscere il telefono. 
  - Aspettate, e non appena il programma si sarà avviato, potete staccare le dita dai tasti volume. 
  - Da qua in poi, basterà avere a disposizione un backup completo (disponibile [qui](https://t.me/moddingopnord/6390) per tutte le versioni attualmente disponibili) e   potrete tornare (selezionando la voce Write, poi Select Directory e indicandogli la directory dove avete scompattato lo zip del backup) quando volete alla versione     stock. 
  **Attenzione, servirà del tempo per ripristinare tutto, quindi prendetevi un caffè, fate una passeggiata nel frattempo :)**

