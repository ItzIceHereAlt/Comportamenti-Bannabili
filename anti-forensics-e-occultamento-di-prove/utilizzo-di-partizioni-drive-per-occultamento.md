---
icon: usb-drive
---

# Utilizzo di Partizioni/Drive per Occultamento

Un'altra categoria di tecniche di bypass consiste nello sfruttare drive esterni, partizioni del disco o volumi cifrati per isolare e nascondere file e attività sospette. L'obiettivo è spostare le prove al di fuori del raggio d'azione di un'analisi standard, che spesso si concentra sul drive principale del sistema operativo (C:).

Queste azioni sono considerate infrazioni perché rappresentano un tentativo deliberato di rendere inaccessibili o difficilmente rintracciabili le prove di cheating.

***

#### 1. Esecuzione da Drive Esterni (USB, Hard Disk Esterni)

* **Scopo della Tecnica:** Il player memorizza ed esegue i cheat direttamente da un dispositivo di archiviazione USB o da una partizione dedicata. Spesso, il dispositivo viene scollegato o la partizione nascosta subito prima del controllo per rimuovere fisicamente le prove. L'efficacia di questa tecnica evasiva aumenta notevolmente se viene utilizzato un file system specifico.
* **Il Ruolo del File System (FAT32/exFAT vs. NTFS):**
  * **FAT32/exFAT:** Questi file system, molto comuni sulle chiavette USB, **non supportano il journaling (USN Journal)**. Questo significa che le operazioni sui file (creazione, cancellazione, rinomina) non vengono registrate in un log centrale come su un drive NTFS. La cancellazione di un cheat da un drive FAT32 lascia molte meno tracce ed è più difficile da provare.
  * **NTFS:** Se il drive esterno o la partizione è formattato in NTFS, avrà il suo USN Journal, che può essere analizzato separatamente per tracciare le attività.

{% hint style="danger" %}
**La semplice connessione** di un dispositivo USB, disco o partizione formattato in **FAT32 o exFAT non è, di per sé, un'infrazione.**

Tuttavia, **è considerata un'infrazione l'esecuzione di qualsiasi file da un volume FAT32 o exFAT durante la stessa sessione di avvio del PC (dall'ultimo boot).**

**Motivazione:** Sebbene esistano metodi per tracciare file cancellati o manipolati su volumi FAT32, le tecniche di bypass più avanzate possono rendere questa analisi estremamente lunga, complessa e, in alcuni casi, inconcludente. Poiché non esiste una ragione pratica legittima per eseguire file da un volume FAT32/exFAT durante una sessione di gioco competitiva, questa regola viene implementata per due scopi principali:

1. **Semplificare e rendere più efficiente il lavoro degli SS Verified.**
2. **Disincentivare attivamente l'uso di questa nota tecnica di bypass.**
{% endhint %}

***

#### 2. Creazione e Cancellazione di Partizioni

* **Scopo della Tecnica:** Il player crea una nuova partizione sul proprio hard disk, la utilizza per installare ed eseguire i cheat, e poi la cancella prima del controllo. Questo rimuove non solo i file, ma l'intera struttura del file system di quella partizione, incluso il suo USN Journal.

***

#### 3. Utilizzo di Volumi Cifrati o Nascosti

* **Scopo della Tecnica:** Il player utilizza software di crittografia (come **VeraCrypt** o **BitLocker** di Windows) per creare un "contenitore" cifrato o un'intera partizione cifrata. I file dei cheat vengono memorizzati all'interno. Senza la password, il contenuto del volume è completamente inaccessibile allo staffer.

***

#### Sanzione

L'utilizzo di queste tecniche per nascondere o rendere inaccessibili le prove è considerato un'infrazione grave, poiché dimostra un chiaro intento di eludere il controllo.

{% hint style="danger" %}
**Motivazione:** `TODO`

**SANZIONE:** `TODO`&#x20;
{% endhint %}

> **Nota:** Se durante un controllo viene scoperto un volume cifrato montato, e il player si rifiuta di fornire la password per l'analisi, tale rifiuto può essere considerato equivalente a un'interruzione del controllo o a un'ammissione di occultamento di prove, a seconda del regolamento specifico del server.
