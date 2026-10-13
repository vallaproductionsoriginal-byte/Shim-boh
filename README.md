# Shim-boh

**Versione 1.0.1**

Riverbero shimmer di **Valla Productions**, **gratuito** nei formati **VST3 per Windows x64**, **VST3 e Audio Unit (AU) per macOS 11 o successivo / Apple Silicon (ARM64)**.

[Scarica Windows x64 VST3 1.0.1](https://github.com/vallaproductionsoriginal-byte/Shim-boh/releases/download/v1.0.1/Shim-boh-1.0.1-Windows-x64.zip) · [Scarica macOS VST3 1.0.1](https://github.com/vallaproductionsoriginal-byte/Shim-boh/releases/download/v1.0.1/Shim-boh-1.0.1-macOS-arm64.zip) · [Scarica macOS AU 1.0.1](https://github.com/vallaproductionsoriginal-byte/Shim-boh/releases/download/v1.0.1/Shim-boh-1.0.1-macOS-arm64-AU.zip) · [Pagina della release 1.0.1](https://github.com/vallaproductionsoriginal-byte/Shim-boh/releases/tag/v1.0.1)

![Interfaccia di Shim-boh](docs/Shim-boh-interface.png)

## Installazione macOS

1. Scarica ed estrai lo ZIP del formato desiderato dalla release.
2. Per VST3, copia **l'intera cartella** `Shim-boh.vst3` in `~/Library/Audio/Plug-Ins/VST3/`. Per Audio Unit, copia **l'intera cartella** `Shim-boh.component` in `~/Library/Audio/Plug-Ins/Components/`. In Finder puoi raggiungere la cartella con **Vai → Vai alla cartella**.
3. Riavvia la DAW o ripeti la scansione dei plugin. Se il nuovo AU non compare, esci dalla DAW e riavvia il Mac per aggiornare la registrazione Audio Unit.
4. Cerca **Shim-boh**, produttore **Valla Productions**, categoria **Reverb**.

Avvia la DAW in modalità Apple Silicon. La build macOS non include supporto Intel o un'applicazione standalone.

Il bundle è firmato ad hoc, non notarizzato e non firmato con un certificato Developer ID. macOS o la DAW possono richiedere l'autorizzazione al caricamento del plugin; una firma ad hoc non equivale a una verifica Apple.

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

Questo repository contiene i tre archivi dei plugin compilati, il README e lo screenshot dell'interfaccia. Il codice sorgente del plugin non è distribuito.

La licenza delle parti originali di Shim-boh e gli avvisi delle dipendenze sono inclusi nelle risorse interne di ciascun bundle, in `Contents/Resources`. JUCE e le altre dipendenze mantengono le proprie licenze.

## Segnalazioni

Per problemi o incompatibilità, apri una [issue](https://github.com/vallaproductionsoriginal-byte/Shim-boh/issues) indicando sistema operativo, DAW, formato del plugin e versione.
