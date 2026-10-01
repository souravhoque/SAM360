S.A.M.360 — revisione della versione personale

MODIFICHE
- Corretta la gestione dei ruoli negli utenti: il form ora usa il valore che il server si aspetta.
- Corretto il crash del pulsante Nuovo dipendente: la scheda vuota non aveva iniziali, e questo interrompeva l'apertura del modulo. Il click è ora gestito anche con delega dal contenitore della pagina.
- Sostituiti i cantieri statici con dati salvati e azioni per creare, modificare ed eliminare.
- Aggiunta la navigazione mobile per il sito e il menu laterale della Web App.
- Aggiunti controlli di autorizzazione ai percorsi API di personale, turni, rapportini, progetti e dati HR; gli utenti non amministratori non possono esportare l'intero database.
- I backup locali vengono aggiornati in data/sam360.json.bak prima di ogni salvataggio. Il database viene scritto in modo atomico; un JSON non leggibile non viene sovrascritto.
- Il server ascolta solo su 127.0.0.1 per impostazione predefinita. È possibile scegliere PORT e HOST con variabili d'ambiente.
- L'export non include gli hash delle password.
- Il modulo “Richiedi una demo” resta non collegato: ora indica chiaramente che la richiesta non viene inviata.

AVVIO LOCALE
Eseguire AVVIA_SAM360.bat oppure `node server.mjs`.

PRIMA DELLA PUBBLICAZIONE ONLINE
Questa è ancora una versione locale, non una distribuzione pronta per Internet. Prima di usarla quotidianamente online servono almeno database di produzione con backup verificati, HTTPS/reverse proxy, limitazione dei tentativi di login, recupero/cambio password e revisione completa dei permessi e degli scope per cantiere. Non esporre direttamente il server su Internet. Le richieste demo non hanno un servizio di invio configurato.

IMPORTAZIONE EXCEL — 30/09/2026
- Conservati i dati esistenti; nuove righe riconciliate o aggiunte senza cancellare lo storico.
- Anagrafica: 75 dipendenti complessivi; 14 nuove schede rispetto ai 61 già registrati.
- Integrati registri di visite, ferie, corsi, patentini/qualifiche, rapporti ore, consegne DPI, attrezzature, costi mensili e subassembly.
- Le fonti delle ore sono mostrate separate per evitare di sommare in modo silenzioso file che possono sovrapporsi. Il workbook “Ore totale COGEI 2026” non è stato importato come fonte di transazioni perché usa collegamenti/formule con errori; i totali si devono ricalcolare dai registri validati.
- La pianificazione W40 è presente come voce da riconciliare: il foglio usa una griglia con più turni e persone affiancati e non è stata convertita automaticamente in turni individuali.
- La scheda di produzione PORTALI in “ORE ROW CP2 2026.xlsx” non è stata completata: il file è diventato non leggibile durante il passaggio finale. I dati già importati dagli altri fogli restano disponibili.
- Il database contiene informazioni personali e sanitarie. Cambiare subito la password demo prima di qualsiasi uso condiviso; non pubblicare il pacchetto su Internet. Attivare prima l'infrastruttura e i controlli di produzione descritti sopra.

