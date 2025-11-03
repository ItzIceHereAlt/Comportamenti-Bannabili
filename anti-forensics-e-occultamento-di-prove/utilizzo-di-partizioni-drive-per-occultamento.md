---
icon: usb-drive
---

# Utilizzo di Partizioni/Drive per Occultamento

Un'altra categoria di tecniche di bypass consiste nello sfruttare drive esterni, partizioni del disco o volumi cifrati per isolare e nascondere file e attività sospette. L'obiettivo è spostare le prove al di fuori del raggio d'azione di un'analisi standard, che spesso si concentra sul drive principale del sistema operativo (C:).

Queste azioni sono considerate infrazioni perché rappresentano un tentativo deliberato di rendere inaccessibili o difficilmente rintracciabili le prove di cheating.

***

#### 1. Esecuzione da Drive Esterni (USB, Hard Disk Esterni)

* **Scopo della Tecnica:** Il player memorizza ed esegue i cheat direttamente da un dispositivo di archiviazione USB. Spesso, il dispositivo viene scollegato subito prima del controllo per rimuovere fisicamente le prove. L'efficacia di questa tecnica dipende dal file system utilizzato sul drive esterno.
* **Il Ruolo del File System (FAT32/exFAT vs. NTFS):**
  * **FAT32/exFAT:** Questi file system, molto comuni sulle chiavette USB, **non supportano il journaling (USN Journal)**. Questo significa che le operazioni sui file (creazione, cancellazione, rinomina) non vengono registrate in un log centrale come su un drive NTFS. La cancellazione di un cheat da un drive FAT32 lascia molte meno tracce.
  * **NTFS:** Se il drive esterno è formattato in NTFS, avrà il suo USN Journal, che può essere analizzato separatamente.

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
