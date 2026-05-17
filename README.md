# 🏥 Sistema Gestionale Ospedaliero

Un applicativo web gestionale sviluppato per digitalizzare, ottimizzare e rendere sicura la comunicazione interna tra l'**Area Medica** e l'**Area Farmacia** di una struttura ospedaliera.

Il sistema permette ai medici di gestire i pazienti e inviare prescrizioni direttamente dai reparti, e ai farmacisti di monitorare le richieste e aggiornare le scorte del magazzino in tempo reale.

---

## 🎨 Caratteristiche del Front-End & UX

L'interfaccia utente è stata progettata con un focus particolare sulla leggibilità dei dati clinici e sulla prevenzione degli errori di inserimento:

* **Stile Unificato:** Un unico file `style.css` gestisce la veste grafica dell'intero applicativo, utilizzando una palette di colori istituzionali (sfumature di blu `#2c3e50` e grigio) adatta a un contesto sanitario.
* **Layout Scannabile:** I dati complessi sono organizzati visivamente tramite elementi `.card` per le dashboard e tabelle HTML (`<table>`) pulite e reattive.
* **Moduli Intelligenti:** I form utilizzano attributi nativi HTML5 (`required`, `min="1"`, `readonly`) per convalidare i dati lato client prima dell'invio.
* **Interfaccia Dinamica:** Uno script JavaScript controlla i flussi di registrazione (`registrazione.php`), mostrando il menu a tendina dei reparti ospedalieri solo se l'utente seleziona il ruolo "Medico", ottimizzando lo spazio a schermo.

---

## 📂 Struttura dei File

### 🔐 Autenticazione e Sicurezza
* `login.php`: Modulo di accesso centralizzato. Gestisce la distruzione e il reset sicuro delle sessioni precedenti (funzione di Logout).
* `registrazione.php`: Modulo per il censimento di nuovi medici o farmacisti con campi condizionali gestiti in JavaScript.

### 🩺 Area Medica
* `index_medico.php`: Dashboard del medico con l'agenda delle visite del giorno e lo storico delle prescrizioni.
* `pazienti.php`: Elenco e ricerca dei pazienti associati al medico loggato.
* `aggiungi_paziente.php`: Form per l'inserimento anagrafico dei pazienti con mascheramento nativo della data e del Codice Fiscale.
* `visita.php`: Cartella clinica di dettaglio del singolo paziente (sintomi, diagnosi e terapie) strutturata tramite griglia CSS.
* `prescrizioni.php`: Pannello per l'invio di nuove ricette farmaceutiche verso la farmacia.

### 💊 Area Farmacia
* `index_farmacista.php`: Dashboard del farmacista per il monitoraggio delle richieste in tempo reale e lo stato del magazzino.
* `aggiungi_farmaco.php`: Form per la catalogazione di nuovi medicinali.
* `ordina.php`: Modulo di rifornimento scorte con blocco in sola lettura (`readonly`) sul nome del farmaco selezionato.

---

## 🗄️ Struttura del Database

Il database MySQL è composto da 5 tabelle principali relazionate tra loro:
1. `REPARTI`: Elenco delle unità operative dell'ospedale.
2. `MEDICI`: Credenziali dei dottori e associazione al reparto di competenza.
3. `PAZIENTI`: Anagrafica e cartelle cliniche.
4. `FARMACIA_OSPEDALIERA`: Punti di stoccaggio e sedi della farmacia interna.
5. `FARMACI`: Registro dei medicinali e quantità disponibili a magazzino.

---

## 🚀 Installazione e Requisiti

### Requisiti
* Server Web (es. Apache tramite **XAMPP**, WAMP o MAMP)
* PHP 7.4 o superiore
* MySQL / MariaDB

### Configurazione
1. Clonare la repository nella cartella del server locale (es. `htdocs` per XAMPP):
   ```bash
   git clone [https://github.com/tuo-username/nome-repo.git](https://github.com/tuo-username/nome-repo.git)
