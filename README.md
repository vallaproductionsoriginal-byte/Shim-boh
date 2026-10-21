# Shim-boh

**Versione 1.0.1**

Riverbero shimmer di **Valla Productions**, **gratuito** nei formati **VST3 per Windows x64**, **VST3 e Audio Unit (AU) per macOS 11 o successivo / Apple Silicon (ARM64)**.

[Scarica Windows x64 VST3 1.0.1](https://github.com/vallaproductionsoriginal-byte/Shim-boh/releases/download/v1.0.1/Shim-boh-1.0.1-Windows-x64.zip) · [Scarica macOS VST3 1.0.1](https://github.com/vallaproductionsoriginal-byte/Shim-boh/releases/download/v1.0.1/Shim-boh-1.0.1-macOS-arm64.zip) · [Scarica macOS AU 1.0.1](https://github.com/vallaproductionsoriginal-byte/Shim-boh/releases/download/v1.0.1/Shim-boh-1.0.1-macOS-arm64-AU.zip) · [Pagina della release 1.0.1](https://github.com/vallaproductionsoriginal-byte/Shim-boh/releases/tag/v1.0.1)

![Interfaccia di Shim-boh](docs/Shim-boh-interface.png)

## Installazione macOS

Richiede **macOS 11 o successivo e un Mac con chip Apple Silicon (M1 o successivo)**. Apri il tuo programma audio (DAW) in modalità nativa Apple Silicon, senza Rosetta. La build non supporta i Mac Intel.

### 1. Copia il plugin nella cartella corretta

1. Chiudi la DAW.
2. Scarica lo ZIP macOS dai link in alto: **AU** per Logic Pro e GarageBand, oppure **VST3** per le DAW che supportano questo formato. Puoi installare entrambi.
3. Fai doppio clic sullo ZIP per estrarlo.
4. Nel **Finder**, premi **⇧⌘G** (Maiuscole + Comando + G), oppure scegli **Vai → Vai alla cartella**. Incolla il percorso del formato scelto e premi Invio:

   | Formato | Elemento da copiare per intero | Cartella di destinazione |
   | --- | --- | --- |
   | Audio Unit (AU) | `Shim-boh.component` | `~/Library/Audio/Plug-Ins/Components/` |
   | VST3 | `Shim-boh.vst3` | `~/Library/Audio/Plug-Ins/VST3/` |

5. Trascina nella destinazione **l'intero elemento estratto**, senza aprirlo né spostare i file al suo interno. Se la cartella di destinazione non esiste, apri `~/Library/` con lo stesso comando del Finder e crea le sottocartelle mancanti `Audio`, `Plug-Ins` e `Components` oppure `VST3`.
6. Riapri la DAW e cerca **Shim-boh**, produttore **Valla Productions**, categoria **Reverb**. Se macOS ne blocca il caricamento, segui la sezione qui sotto.

Il simbolo `~` indica la tua cartella utente: questi percorsi installano il plugin solo per il tuo account. Shim-boh si usa all'interno della DAW; non è un'app da aprire con un doppio clic.

### 2. Se macOS blocca il plugin: sviluppatore non verificato

**I plugin non sono firmati con un certificato Apple Developer ID e non sono notarizzati da Apple.** Usano una firma locale (*ad hoc*), che non equivale alla verifica di Apple. Per questo macOS può mostrare un avviso sullo sviluppatore non verificato o sull'impossibilità di verificare la presenza di software dannoso.

Dopo aver provato a caricare Shim-boh nella DAW:

1. Apri ** → Impostazioni di Sistema → Privacy e sicurezza** e scorri fino alla sezione **Sicurezza**. Su macOS 11 e 12 il percorso è **Preferenze di Sistema → Sicurezza e Privacy → Generali**.
2. Se compare un avviso relativo a **Shim-boh**, premi **Apri comunque** e conferma l'autorizzazione, se richiesta.
3. Chiudi e riapri la DAW, quindi ripeti la scansione dei plugin.

La procedura di autorizzazione è descritta anche nella [guida ufficiale Apple](https://support.apple.com/it-it/102445).

Se il pulsante non compare o il plugin resta bloccato, puoi rimuovere la quarantena dal **solo plugin installato**. Fallo soltanto sulla copia scaricata dalle [release ufficiali di Shim-boh](https://github.com/vallaproductionsoriginal-byte/Shim-boh/releases).

Chiudi la DAW, apri **Terminale** (premi **⌘Spazio**, scrivi `Terminale` e premi Invio), quindi copia il comando del formato che hai installato e premi Invio. Se hai installato entrambi i formati, esegui entrambi i comandi, uno alla volta.

**Per Audio Unit (AU):**

```sh
xattr -dr com.apple.quarantine "$HOME/Library/Audio/Plug-Ins/Components/Shim-boh.component"
```

**Per VST3:**

```sh
xattr -dr com.apple.quarantine "$HOME/Library/Audio/Plug-Ins/VST3/Shim-boh.vst3"
```

Se il comando termina senza messaggi, puoi proseguire. Se leggi `No such file or directory`, controlla di aver copiato il plugin nella cartella indicata nella tabella. I comandi non richiedono `sudo` né la password di amministratore; rimuovono solo l'attributo di quarantena di Shim-boh e non aggiungono una certificazione Apple. Non serve disattivare Gatekeeper o altre protezioni del Mac.

### 3. Se il plugin non compare nella DAW

Riapri la DAW ed esegui una nuova scansione dal suo gestore dei plugin; se Shim-boh è stato escluso dopo il primo tentativo, selezionalo e ripeti la scansione. Per l'Audio Unit, se ancora non compare, chiudi la DAW e riavvia il Mac per aggiornare la registrazione AU. Verifica anche di usare la DAW in modalità Apple Silicon e il formato compatibile con il tuo programma.

## Installazione Windows x64

1. Scarica ed estrai `Shim-boh-1.0.1-Windows-x64.zip`.
2. Copia **l'intera cartella** `Shim-boh.vst3` in `C:\Program Files\Common Files\VST3\`. Mantieni le sottocartelle `Contents` e `x86_64-win`.
3. Riavvia la DAW a 64 bit o ripeti la scansione VST3.
4. Cerca **Shim-boh**, produttore **Valla Productions**, categoria **Reverb**.

Il runtime C++ è incluso staticamente nella build. La versione Windows è VST3 x64; non include AU, VST2, x86 a 32 bit o un'applicazione standalone.

## Funzioni

- Mix, Shift da −12 a +12 semitoni, Feedback, Diffusion e Size.
- Low Cut 10–2000 Hz, High Cut 1000–20000 Hz, Mod Rate 0.02–10 Hz e Mod Depth.
- Riverbero Center, Studio, Atrium e Horizon.
- Pitch Shift, Split, Rewind, Rewind Split e Off, inserito nel feedback del riverbero.
- Color Glass/Velvet, bypass del plugin, automazione dei 13 parametri e salvataggio/ripristino della sessione.
- Otto preset originali: Lumen Drift, Felt Arcade, Copper Bloom, Paper Satellites, Ember Vault, Ribbon Wake, Still Meridian, Prism Current.
- Ingresso/uscita stereo, mono e mono→stereo. Interfaccia ridimensionabile.

## Uso

Per un aux/send, imposta Mix a 1.00. Per lo shimmer, parti da Lumen Drift; Ember Vault usa un'ottava discendente e Prism Current due voci reverse. Per un riverbero senza pitch scegli Pitch Mode Off.

Center somma gli ingressi nella rete, Studio usa ritardi brevi, Atrium una geometria intermedia e Horizon uno spazio ampio. Shift segue il valore del controllo Shift; Split aggiunge la trasposizione opposta. Rewind e Rewind Split leggono i grani al contrario. Glass mantiene la banda impostata, Velvet attenua le alte frequenze nella coda.

Il bypass del pitch mantiene il riverbero attivo; BYPASS in alto disattiva l'effetto. L'uscita dry resta senza latenza; la componente wet ha il ritardo naturale della rete di riverbero e dei grani.

## Distribuzione e licenze

Questo repository distribuisce i tre archivi dei plugin compilati e la relativa documentazione, con lo screenshot dell'interfaccia. Il codice sorgente del plugin non è distribuito.

La [licenza proprietaria delle parti originali](LICENSE), le [note sulle licenze](LICENSE_NOTES.md) e gli [avvisi delle dipendenze](THIRD_PARTY_NOTICES.md) sono disponibili nella repo. I testi delle licenze e gli avvisi sono inclusi anche nelle risorse interne di ciascun bundle, in `Contents/Resources`. JUCE e le altre dipendenze mantengono le proprie licenze.

## Segnalazioni

Per problemi o incompatibilità, apri una [issue](https://github.com/vallaproductionsoriginal-byte/Shim-boh/issues) indicando sistema operativo, DAW, formato del plugin e versione.
