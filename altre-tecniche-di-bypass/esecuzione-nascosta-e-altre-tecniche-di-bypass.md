---
icon: code-branch
---

# Esecuzione Nascosta e Altre Tecniche di Bypass

Questa sezione illustra **alcune** delle tecniche di bypass più sofisticate rispetto a quelle trattate precedentemente in questa guida che sfruttano delle funzionalità per eseguire codice in modo non convenzionale o "nascosto". A differenza della semplice cancellazione di file, questi metodi mirano a eludere i meccanismi di logging standard del sistema operativo, rendendo l'individuazione più complessa.

Quelli elencati di seguito sono solo alcuni esempi delle molteplici tipologie di bypass avanzati esistenti e conosciuti. Rilevare queste tecniche richiede un'analisi approfondita e la conoscenza di artefatti specifici. L'utilizzo di uno di questi metodi, o di qualsiasi altra tecnica analoga non elencata, è considerato un'infrazione gravissima, poiché dimostra un livello di premeditazione e conoscenza tecnica finalizzata a ingannare lo staff.

***

#### 1. Esecuzioni "Fileless" (Senza File)

* **Scopo della Tecnica:** L'esecuzione "fileless" consiste nell'avviare codice malevolo (come un cheat loader) direttamente nella memoria del sistema (RAM), senza prima salvarlo come un file su disco. Questo bypassa la maggior parte dei controlli basati sulla scansione di file.

(Seguono i Metodi di Rilevamento)

***

#### 2. Utilizzo del Task Scheduler (Utilità di Pianificazione)

* **Scopo della Tecnica:** I bypasser creano un'attività pianificata per eseguire un cheat o uno script di pulizia in modo automatico a un determinato evento (es. all'avvio del PC, al login dell'utente, o persino all'avvio di `AnyDesk.exe`). L'esecuzione avviene tramite il servizio di sistema dello Scheduler, rendendola meno diretta e più difficile da tracciare.

(Seguono i Metodi di Rilevamento)

***

#### 3. Utilizzo di Alternate Data Streams (ADS) e WMIC

* **Scopo della Tecnica:** Il cheat viene nascosto all'interno di un flusso di dati alternativo (ADS) di un file innocuo (es. un file di testo o un'immagine), rendendolo invisibile a Esplora File. Viene poi eseguito tramite Windows Management Instrumentation (WMIC).

(Seguono i Metodi di Rilevamento)

***

#### 4. Process Hollowing

* **Scopo della Tecnica:** È una tecnica di iniezione di codice avanzata in cui un processo legittimo (es. `svchost.exe`) viene avviato in stato sospeso, la sua memoria viene "svuotata" (hollowed) e sostituita con il codice del cheat, e infine il processo viene ripreso. Il cheat viene così eseguito mascherato da processo di sistema.

(Seguono i Metodi di Rilevamento)

***

#### Sanzione

L'utilizzo di una qualsiasi delle tecniche descritte in questa pagina, **o di qualsiasi altra tecnica di bypass avanzato non elencata**, dimostra una chiara premeditazione e un alto livello di competenza finalizzato a eludere i controlli. Per questo motivo, è considerata una delle infrazioni più gravi.

{% hint style="danger" %}
**Motivazione:** `TODO`

**SANZIONE:** `TODO`
{% endhint %}
