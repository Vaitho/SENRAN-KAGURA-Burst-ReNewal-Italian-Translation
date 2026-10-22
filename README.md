# SENRAN KAGURA Burst Re:Newal — Traduzione italiana 🇮🇹

> **Progetto amatoriale e non ufficiale, realizzato con l'assistenza dell'intelligenza artificiale e aperto ai contributi della community.**
>
> Le traduzioni iniziali sono state prodotte e revisionate con il supporto di **ChatGPT (OpenAI)**. **Non sono una localizzazione professionale o ufficiale**: potrebbero contenere imprecisioni, formulazioni poco naturali, errori di contesto e problemi di impaginazione. La revisione umana è particolarmente gradita.

Questo progetto ha l'obiettivo di rendere giocabile in **italiano** la versione **PC/Steam** di *SENRAN KAGURA Burst Re:Newal*: dialoghi della storia, interfaccia, missioni, tutorial, glossario e sottotitoli aggiuntivi.

**Non è affiliato né approvato dagli sviluppatori, dagli editori o dai titolari dei diritti del gioco.** Per utilizzare la patch è necessaria una propria copia legittima del gioco.

## Stato del progetto

Stato di riferimento: **Rifinitura italiana 01**, successiva al Lotto 19. I numeri indicano i **record diversi dall'originale inglese**, non la percentuale di contenuto effettivamente tradotto o visibile in partita.

| Area | Archivio | Record modificati | Stato |
|---|---|---:|---|
| Dialoghi narrativi | `AdvText.cat` | **4.182 / 4.381** (95,5%) | Revisione e test da completare |
| Menù, missioni, tutorial e galleria | `EN.cat` | **3.202 / 8.382** (38,2%) | Ampia traduzione; verifiche visive in corso |
| Sottotitoli e battute aggiuntive | `Sub.cat` | **7.021 / 9.702** (72,4%) | Traduzione parziale; alcuni testi potrebbero non essere usati nel gioco |

**Importante:** molti record non modificati sono nomi propri, esclamazioni, segnaposto disattivati o stringhe valide anche in italiano. Viceversa, una percentuale elevata non garantisce che ogni schermata sia perfettamente localizzata: alcune scritte sono incorporate nelle **immagini** e non sono modificabili tramite i JSON testuali.

### Cosa funziona e cosa resta da fare

- La community ha già confermato il funzionamento nel gioco delle patch cumulative di dialoghi, menù e sottotitoli precedenti.
- Gli archivi CAT delle nuove build sono stati sottoposti a verifiche di ricostruzione e rilettura; **questo non sostituisce il collaudo in Steam**.
- Restano utilissimi controlli su **testi tagliati o fuori dai riquadri**, resa di punteggiatura e accenti, terminologia, coerenza narrativa e schermate ancora in inglese.
- Alcune voci di `Sub.cat` contengono riferimenti a *Estival Versus*: non è garantito che vengano tutte visualizzate in *Burst Re:Newal*.

## Download e installazione

La versione installabile dovrebbe essere distribuita nella sezione **[Releases](../../releases)** di GitHub (quando pubblicata). Scarica l'ultimo archivio ZIP verificato.

1. **Chiudi il gioco.**
2. Esegui un **backup** dei file `.cat` originali (o utilizza la verifica dell'integrità dei file tramite Steam per ripristinarli, se necessario).
3. Estrai lo ZIP della patch.
4. Copia la cartella `GameData` estratta nella **cartella principale del gioco**, mantenendo la struttura e confermando la sostituzione dei file indicati nella release.
5. Avvia il gioco e controlla menù, tutorial e dialoghi.

Percorsi dei tre archivi interessati, relativi alla cartella del gioco:

```text
GameData/
└── Localize/
    └── EN/
        └── Binary/
            ├── Adv/
            │   └── AdvText.cat
            └── Text/
                ├── EN.cat
                └── Sub.cat
```

**Non sovrascrivere mai i file senza un backup.** La patch è destinata alla localizzazione inglese (`EN`) della versione PC/Steam; altre versioni o aggiornamenti del gioco potrebbero non essere compatibili.

## Come puoi collaborare 🤝

Sono benvenuti contributi di **traduttori, revisori, giocatori, sviluppatori e tester**, anche piccoli. Le attività più preziose sono:

- **Revisione dell'italiano:** correggere grammatica, registro, espressioni innaturali e traduzioni inesatte prodotte con IA.
- **Controllo del contesto:** verificare che una battuta rispecchi personaggio, situazione e significato, confrontandola con l'inglese e, se lo conosci, con il giapponese.
- **QA nel gioco:** segnalare stringhe ancora inglesi, testi troncati, caratteri visualizzati come `*`, errori nei tutorial e problemi introdotti da una patch.
- **Coerenza terminologica:** proporre una terminologia comune per accademie, modalità, abilità, tecniche e voci di menù.
- **Sviluppo strumenti:** migliorare conversione, validazione automatica, generazione delle release e test degli archivi.
- **Accessibilità e grafica:** individuare eventuali testi nelle immagini, proponendo soluzioni **solo se legalmente distribuibili**.

### Segnala un errore con una Issue

Apri una **[Issue](../../issues)** e, quando possibile, indica:

```text
Titolo: [Tutorial] Testo tagliato in «Aggancio bersaglio»

Versione patch: Rifinitura italiana 01
Versione gioco: PC / Steam
Posizione nel gioco: Tutorial → Aggancio bersaglio
Testo visualizzato: ...
Testo italiano proposto: ...
File / record (se noto): EN_3.json, ID 372
Come riprodurre: ...
Screenshot: allegato, senza dati personali
```

Per gli errori di traduzione, basta anche una **frase originale + proposta corretta + contesto**. Se non conosci l'ID del record, non è un problema. Evita screenshot con informazioni personali e non caricare archivi originali del gioco.

### Proponi modifiche con una Pull Request

1. Crea un **fork** della repository e un branch, ad esempio `fix/tutorial-aggancio-bersaglio`.
2. Individua il JSON sorgente interessato e modifica **solo il testo italiano attivo**, senza cambiare la struttura dei dati.
3. Conserva **ID, ordine, metadati, codici di controllo e caratteri speciali** già presenti.
4. Indica nella PR **file, ID/record_key**, spiegazione della correzione e, se disponibile, uno screenshot del risultato in gioco.
5. Se puoi, verifica che i JSON siano validi e che gli archivi si ricostruiscano senza errori. Segnala esplicitamente ciò che **non hai potuto testare**.

Esempio di titolo PR: `fix(EN_3): corregge spiegazione Aggancio bersaglio`.

**Le PR generate con IA sono ammesse**, ma richiediamo di dichiararlo e di fare almeno una revisione umana del significato. Non accettiamo grandi sostituzioni automatiche non controllate.

## Organizzazione dei sorgenti

Il progetto di estrazione/ricostruzione utilizza **41 unità JSON**: 5 per la narrativa, 10 per menù e testi standard, 26 per i sottotitoli.

Una possibile disposizione dei file nella repository è:

```text
translation/
├── translation_manifest.json      # se si usa il formato canonico v2
├── advtext/
│   ├── AdvText_0.json
│   └── ... AdvText_4.json
└── text/
    ├── en/
    │   ├── EN_0.json
    │   └── ... EN_9.json
    └── sub/
        ├── Sub_0.json
        └── ... Sub_25.json
repack.py                           # strumento di build (se ridistribuibile)
```

> **Nota:** questo è uno schema consigliato per lavorare con i file canonici, **non una garanzia che questi percorsi esistano già nella repository**. Le distribuzioni di lavoro attuali possono anche contenere cartelle `Sorgenti_narrativi/`, `Sorgenti_menu/` e `Sorgenti_sottotitoli/`. Adegua i percorsi alla struttura che pubblicherai effettivamente.

Nei JSON canonici (formato 2), ciascun record contiene, tra gli altri, questi campi:

| Campo | Utilizzo |
|---|---|
| `record_key` | Identificativo stabile del record |
| `technical` | ID, ordine, dati di regia o struttura: **non modificare** |
| `jp` | Testo giapponese di riferimento: **non modificare** |
| `en_original` | Testo inglese originale: **non modificare** |
| `en` | **Testo attivo da tradurre in italiano** |
| `control_tokens` | Codici speciali da preservare |
| `immutable_sha256` | Metadato di integrità: **non modificare** |

Anche se il campo si chiama `en`, **contiene la stringa effettivamente usata nella build**, quindi può ospitare la traduzione italiana.

### Regole tecniche fondamentali

1. **Non cambiare la struttura JSON**, né aggiungere/eliminare record senza una modifica concordata agli strumenti.
2. **Non modificare mai i codici di regia o i segnaposto**: token racchiusi tra `<...>` o `[...]`, sequenze di formattazione, variabili (`%s`, `%d` ecc.), riferimenti a pulsanti e simboli con significato tecnico devono essere preservati **nel loro ordine e nella loro posizione logica**.
3. Nei **sorgenti italiani** usa gli accenti corretti (`è`, `à`, `ò`, `ù`, `ì`). Per il **font di gioco attualmente utilizzato**, la build compatibile converte le lettere accentate in forme ASCII (`e'`, `a'`, ecc.), perché alcuni accenti vengono visualizzati come asterischi. **Non introdurre conversioni indiscriminate nei token o nei metadati.**
4. **Mantieni la terminologia consistente** e, in caso di dubbio, spiega la scelta nella PR; non italianizzare automaticamente i nomi propri delle tecniche.
5. **Controlla la lunghezza**: una traduzione corretta può comunque fuoriuscire da una finestra del gioco.
6. Modifica prima i **sorgenti**, non i file CAT binari: gli archivi devono essere prodotti da un processo di build ripetibile.

## Ricostruzione tecnica

Il progetto utilizza `repack.py` per convertire i JSON in file DAT e creare i tre archivi CAT. Con Python 3 installato, in un checkout che contenga **il manifest canonico e tutte le 41 unità richieste**, la modalità di build è:

```bash
python repack.py --pack --base-dir . --translation-root ./translation
```

Lo script può produrre le cartelle di lavoro `packed_dat/`, `repacked_cats/` e `Patch/` (a seconda degli argomenti e della struttura locale). Usa `python repack.py --help` per verificare le opzioni disponibili.

**Attenzione:** la modalità canonica ricostruisce le **41 unità complete** e può cancellare/ripopolare le cartelle di output durante la build. Lavora in una copia del progetto e non mettere i backup originali nelle cartelle generate. Per i pacchetti basati sulla precedente struttura dei JSON è prevista anche una modalità `--legacy-pack`: consultare lo script prima dell'uso.

Checklist consigliata prima di una release:

- Il JSON è valido e tutti i record sono presenti.
- ID, ordine dei record, struttura, segnaposto e control token corrispondono agli originali.
- I DAT generati possono essere riletti e producono le stesse stringhe attive.
- I CAT risultanti contengono esattamente le unità previste (5 `AdvText`, 10 `EN`, 26 `Sub`).
- Il gioco si avvia; menù e scene campione sono testati **visivamente**; nessuna scritta esce dai riquadri.
- La release include versione, changelog, compatibilità e un avviso di backup.

## Trasparenza sull'intelligenza artificiale

Questo progetto è nato da una collaborazione tra una persona e un assistente IA. ChatGPT è stato utilizzato per **produrre proposte di traduzione, riscrivere battute, creare script, effettuare verifiche automatiche e preparare pacchetti**. Le scelte dell'IA **possono essere errate**; la validazione automatica degli archivi dimostra la correttezza tecnica della conversione, **non** la qualità linguistica o la corretta visualizzazione delle battute.

Vogliamo che la community possa **correggere apertamente** ogni traduzione, anche sostituendo completamente una proposta dell'IA quando una versione umana è migliore. Non chiediamo di nascondere l'uso dell'IA: chiediamo **trasparenza, cura e verifiche**.

Nelle PR indica, quando pertinente, se il testo è stato scritto o corretto con IA e quali controlli umani o in gioco hai effettuato.

## Diritti, distribuzione e licenza

*SENRAN KAGURA Burst Re:Newal*, i nomi, i personaggi, i testi originali, le immagini, le musiche e i relativi asset appartengono ai rispettivi titolari dei diritti. Questa è una **fan translation gratuita e non ufficiale**: non viene venduto alcun contenuto e non si rivendica alcun diritto sugli asset del gioco.

**Prima di rendere pubblica la repository o una release, verificare i permessi di ridistribuzione.** I JSON estratti possono contenere ampie porzioni dei testi originali e gli archivi `.cat` possono includere dati proprietari: **non dare per scontato che possano essere pubblicati** solo perché sono utili alla traduzione. Quando necessario, pubblicare soltanto **contributi originali, script e patch differenziali** che l'utente applica alla propria copia legittima, anziché i contenuti completi del gioco.

Se `repack.py` o altri strumenti provengono da progetti terzi (ad esempio UNBURGER), **conservarne attribuzione, copyright e condizioni di licenza** e ottenere le autorizzazioni necessarie per ridistribuirli.

La **licenza dei contributi originali di questa repository è ancora da definire**: prima della pubblicazione, aggiungi un file `LICENSE` appropriato solo per i materiali di cui puoi effettivamente concedere i diritti. Una licenza open source non può attribuirti i diritti sui contenuti originali del videogioco.

## Ringraziamenti ❤️

Grazie a tutte le persone che proveranno la patch, segnaleranno errori e miglioreranno la traduzione. Un ringraziamento anche agli autori degli strumenti di estrazione e repacking impiegati nel progetto, da accreditare con precisione nella repository pubblica.

**L'obiettivo non è raggiungere un numero artificiale del 100%, ma una traduzione italiana naturale, comprensibile e funzionante.** Ogni correzione, anche piccola, ci avvicina a questo risultato.
