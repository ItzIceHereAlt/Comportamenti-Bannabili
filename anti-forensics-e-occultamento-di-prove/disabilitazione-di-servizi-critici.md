---
icon: eraser
---

# Disabilitazione di Servizi Critici

Uno dei metodi di bypass più comuni consiste nel disabilitare o fermare intenzionalmente alcuni servizi di Windows. Questi servizi sono fondamentali per l'analisi forense perché registrano le attività del sistema e dei programmi. La loro disattivazione è considerata un'azione di **anti-forensics**, in quanto mira a nascondere le tracce e a ostacolare il controllo.

In questa pagina sono elencati i servizi critici monitorati durante uno screenshare. La loro disattivazione o il loro stato "arrestato" costituisce un'infrazione.

***

#### Come Verificare lo Stato di un Servizio

La procedura standard per verificare lo stato di un servizio da parte di un player è utilizzare il **Prompt dei Comandi (CMD)** con privilegi di amministratore.

1. Apri il menu Start, cerca `cmd`, clicca con il tasto destro su "Prompt dei comandi" e seleziona "Esegui come amministratore".
2. Digita il comando `sc query [nome_servizio]`, sostituendo `[nome_servizio]` con il nome del servizio che vuoi controllare (es. `sc query sysmain`).
3. Analizza il campo `STATE`. Lo stato normale è `RUNNING`. Uno stato `STOPPED` è un forte indicatore di manipolazione.



***

#### Servizi Critici Monitorati

**1. SysMain (Superfetch)**

* **Scopo del Servizio:** Il servizio `SysMain` è responsabile della gestione della funzionalità **Prefetch**. Senza questo servizio attivo, Windows non crea né aggiorna i file `.pf`, che sono una delle prove principali per tracciare l'esecuzione dei programmi.
* **Nome Servizio per il Comando:** `sysmain`
* **Comando di Verifica:** `sc query sysmain`

**2. DPS (Diagnostic Policy Service)**

* **Scopo del Servizio:** Il `DPS` è responsabile della diagnostica di sistema, ma in ambito forense è noto per registrare informazioni sull'esecuzione dei processi, inclusi timestamp di compilazione che possono aiutare a identificare file sostituiti (file replacement).
* **Nome Servizio per il Comando:** `dps`
* **Comando di Verifica:** `sc query dps`

**3. EventLog (Windows Event Log)**

* **Scopo del Servizio:** È il servizio principale che gestisce la registrazione di tutti gli eventi di sistema nei **Log degli Eventi** (Event Viewer). Se questo servizio è fermo, azioni critiche come la cancellazione del Journal, i cambi di orario o i crash di sistema non verranno registrate.
* **Nome Servizio per il Comando:** `eventlog`
* **Comando di Verifica:** `sc query eventlog`

**4. PcaSvc (Program Compatibility Assistant Service)**

* **Scopo del Servizio:** Il `PcaSvc` aiuta a garantire la compatibilità delle applicazioni, ma registra anche informazioni utili sull'esecuzione dei programmi. Le sue tracce possono corroborare le prove trovate in altri artefatti.
* **Nome Servizio per il Comando:** `PcaSvc`
* **Comando di Verifica:** `sc query PcaSvc`

**5. PlugPlay (Plug and Play)**

* **Scopo del Servizio:** Gestisce il riconoscimento dei dispositivi hardware, ma è anche stato osservato che la sua memoria contiene spesso tracce relative all'esecuzione di file `.jar` (Java). La sua disattivazione può nascondere l'uso di certi client basati su Java.
* **Nome Servizio per il Comando:** `PlugPlay`
* **Comando di Verifica:** `sc query PlugPlay`

**6. BAM (Background Activity Moderator)**

* **Scopo del Servizio:** Il `BAM` è un servizio che monitora l'attività delle applicazioni in background per ottimizzare le risorse. In ambito forense, il suo log nel Registro di Sistema è una prova di esecuzione estremamente affidabile, in quanto registra il percorso completo dei file eseguiti e il loro ultimo orario di attività. La sua disattivazione impedisce la registrazione di queste preziose tracce.
* **Nome Servizio per il Comando:** `bam`
* **Comando di Verifica:** `sc query bam`

***

#### Sanzione

La disabilitazione intenzionale di uno o più dei servizi sopra elencati durante una sessione di gioco o immediatamente prima di un controllo è considerata un tentativo di ostacolare l'indagine e nascondere le prove.

{% hint style="danger" %}
**Motivazione:** `TODO`

**SANZIONE:** `TODO`
{% endhint %}

> **Nota:** Se un player sostiene che un servizio è stato disabilitato da un "optimizer" o per motivi di performance, la responsabilità ricade comunque su di lui. In un ambiente competitivo come quello di Titanet, è dovere del player assicurarsi che il proprio sistema sia configurato in modo da non interferire con le procedure di controllo standard.
