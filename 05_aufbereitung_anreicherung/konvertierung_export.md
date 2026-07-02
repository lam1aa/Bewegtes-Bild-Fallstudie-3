# Formatkonvertierungen und -exporte

Dieser Abschnitt dokumentiert, wie die Metadaten aus dem Projektkorpus aus dem primären Arbeitsformat `xlsx` in die offenen Publikationsformate `cvs`, `html` und `json` exportiert bzw. überführt wurden. Die Schritte sind so aufbereitet, dass sie für eigene Datenprojekte reproduziert werden können. Für die Ver- und Bearbeitung der Dateien kann ein kostenloser Code-Editor genutzt werden. In dieser OER nutzen wir für alle Beispiele <a href="https://code.visualstudio.com/" class="external-link" target="_blank">Visual Studio Code (VS Code)</a> von Microsoft, da die Software kostenfrei verfügbar ist und auch für Einsteiger:innen leicht zugänglich. Alternativ können ebenso andere, auch nicht kommerziell betriebene Text- oder Code-Editoren verwendet werden.

(xlsx-zu-csv)=
## XLSX zu CSV

Um die Erklärungen so überschaubar wie möglich zu halten, arbeiten wir nachfolgend mit einem [Beispieldatensatz](../assets/05_aufbereitung_anreicherung/doc_k05_beispieldatensatz.xlsx), der die ersten 50 Einträge der Korpusmetadaten enthält.

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_excel_interface_beispieldatensatz.png
---
align: center
width: 100%
name: beispieldatensatz interface
---
Interface der Excel-Oberfläche mit dem Beispieldatensatz
```

Bevor der `csv`-Export durchgeführt wird, müssen einige Punkte in der Ausgangsdatei überprüft werden:

```{admonition} Überprüfung der Ausgangsdatei
:class: keypoint
* **Spaltennamen in `snake_case`**: Alle Spaltennamen sollten in `snake_case` formatiert sein, d.h. ausschließlich Kleinbuchstaben und Unterstriche statt Leerzeichen (z.B. `object_id`, `runtime_min` usw.); Leerzeichen können bei der maschinellen Verarbeitung zu Fehlern oder Problemen führen!
* **Trennzeichen: Semikolon statt Komma**: Standardmäßig verwenden `csv`-Dateien ein Komma (`,`) als Trennzeichen (daher der Name *Comma-Separated Values*). In einem Datensatz, der Filmtitel mit Kommas enthält (z. B. *Good bye, Lenin!*), führt ein Komma als Trennzeichen jedoch zu Fehlinterpretationen, da Kommas in Titeln als Spaltentrenner erkannt werden. Wir verwenden daher durchgängig das **Semikolon (`;`)** als Trennzeichen. Dies entspricht bereits dem Standard-Exportverhalten von Excel in einer deutschsprachigen Systemumgebung.
```

### Schritt-für-Schritt: Export aus Excel

1. Die XLSX-Datei in Excel öffnen
2. Das Tabellenblatt aktivieren, das exportiert werden soll

```{admonition} Aktives Tabellenblatt
:class: hinweis
Beim `csv`-Export aus Excel wird nur das aktuell aktive Tabellenblatt exportiert. Arbeitsdateien mit mehreren Tabellenblättern müssen separat exportiert werden. Vor dem Export also sicherstellen, dass das richtige Blatt ausgewählt ist.
```

3. `Datei` → `Speichern unter` → Dateiformat **CSV UTF-8 (durch Trennzeichen getrennt) (.csv)** wählen; es gibt mehrere CSV-Varianten in Excel. Unbedingt **CSV UTF-8** wählen. Nur UTF-8 stellt sicher, dass Sonderzeichen korrekt gelesen und in anderen Tools fehlerfrei dargestellt werden.

4. Speichern; die Warnung, dass nur das aktive Blatt gespeichert wird, bestätigen

```{admonition} Leerzeichen zwischen Spaltenüberschriften
:class: caution
Beim Export aus Excel kann es vorkommen, dass sich Leerzeichen unbemerkt in Spaltenüberschriften einschleichen. Dies passiert insbesondere, wenn Felder bzw. Spalten nachträglich hinzugefügt werden. Im Tabellenblatt selbst bleiben diese Leerzeichen unsichtbar, führen aber beim Einlesen der `csv`-Datei in anderen Tools zu Problemen. Es empfiehlt sich daher, die exportierte `csv`-Datei in einem Text-Editor wie VS Code zu öffnen und die Kopfzeile manuell auf unerwünschte Leerzeichen zu überprüfen.
```

### Ergebnis

So sehen die ersten 7 Einträge aus dem Datensatz als `csv`-Export aus:

```text
title;object_id;imdb_id;classification;country;year;director;runtime_min;duration_iso8601;season_episode;episode_title;modes_intervention;annotation_data;moviebarcode
2040;f0162;tt7150512;documentary;AU;2018;Damon Gameau;92 Min.;PT1H32M;;;Escalation / de-escalation;TRUE;TRUE
2067;f0522;tt1918734;feature film;AU;2020;Seth Larney;114 Min.;PT1H54M;;;;FALSE;TRUE
Albatross;f025a;tt9914642;documentary;US;2017;Chris Jordan;97 Min.;PT1H37M;;;;FALSE;TRUE
An Inconvenient Sequel: Truth to Power;f009a;tt6322922;documentary;US;2017;"Bonni Cohen;Jon Shenk";98 Min.;PT1H38M;;;;FALSE;TRUE
An Inconvenient Truth;f020a;tt0497116;documentary;US;2006;Davis Guggenheim;96 Min.;PT1H36M;;;;FALSE;TRUE
Annihilation;f049a;tt2798920;feature film;"US;GB";2018;Alex Garland;115 Min.;PT1H55M;;;;FALSE;TRUE
Another Earth;f040a;tt1549572;feature film;US;2011;Mike Cahill;92 Min.;PT1H32M;;;;FALSE;TRUE
```
Der Beispieldatensatz als `csv`-Datei kann ebenfalls [hier](../assets/05_aufbereitung_anreicherung/doc_k05_beispieldatensatz.csv) gedownloaded werden.

Was es zu beachten gilt:
* Felder mit Mehrfachwerten (z.B. `country`, `director`) werden in Anführungszeichen gesetzt
* Leere Felder (z. B. `season_episode`, `episode_title` bei Spielfilmen) bleiben leer, die Semikolons als *Positionsmarker* bleiben aber erhalten
* `TRUE`/`FALSE` kennzeichnet, ob Annotationsdaten bzw. Moviebarcodes vorliegen

```{admonition}  Warum in leeren Feldern die Semikolons beibehalten werden müssen
:class: caution
In einer `csv`-Datei bestimmt die Position des Semikolons, welcher Wert in welche Spalte gehört. Wird ein Semikolon aus einem Leeren Feld gelöscht,verschieben sich alle nachfolgenden Werte um eine Spalte, d.h, dass die Tabelle logisch auseinanderbricht. Leere Felder dürfen also nicht einfach weggelassen werden, sondern müssen als leere Positionen (`;;`) erhalten bleiben.
```

## CSV zu HTML

Eine `html`-Version der Korpusmetadaten wird für eine bessere Durchsuchbarkeit zur Verfügung gestellt `html`-Dokumente bestehen oft aus zwei Teilen: dem eigentlichen **Inhalt** (*„was soll da rein?"*, z.B. Tabellen, Überschriften, Text) in `html`-Syntax und den **Gestaltungsregeln** (*„wie soll es aussehen?"*, z.B. Farben, Abstände, Schriftgröße) in `css`-Syntax. Beide sind im bereitgestellten Code enthalten und kommentiert.

```{admonition} Kommentare im Code
:class: hinweis
Kommentare sind in vielen Programmiersprachen sehr üblich. Sie beeinträchtigen die Code-Funktionen nicht und dienen ausschließlich der Lesbarkeit und Dokumentation des Codes. Die Syntax variiert je nach Sprache:
* Python und YAML: `# Kommentar`
* HTML: `<!-- Kommentar -->`
* CSS: `/* Kommentar */`
```

Um ein `html`-Dokument jedoch selbst zu schreiben, sind vertiefende Kenntnisse in `html` notwendig. Folgender hier bereitgestellter Code kann jedoch auch ohne vertiefende Kenntnisse als Vorlage genutzt und angepasst werden. 

Zur Weiterverarbeitung wird das `html`-Dokument ebenfalls als [Download](../assets/05_aufbereitung_anreicherung/doc_k05_beispieldatensatz.html) bereitgestellt sowie nachfolgend als Code-Block angezeigt. Wie er verwendet und angepasst werden kann, zeigen wir Schritt für Schritt.

`````{dropdown} Der HTML-Code im Detail

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <!-- Zeichensatz: UTF-8 unterstützt Sonderzeichen --> 

  <!-- Titel der Browser-Registerkarte -->
  <meta charset="utf-8" />
  <title>QUADRIGA FS3 Korpusmetadaten</title>
  <style>
    /* Grundlayout der Seite */
    body { font-family: Arial, sans-serif; margin: 30px; font-size: 14px; }

    /* Container für die Tabelle mit Scrollbars */
    #tableContainer {
      overflow-x: auto;       /* horizontales Scrollen erlauben */
      overflow-y: auto;       /* vertikales Scrollen erlauben */
      max-height: 75vh;       /* maximale Höhe (75% der Fensterhöhe) */
      margin: 20px auto;
      width: 90%;
      border: 1px solid #ccc;
    }

    /* Tabellen-Grundlayout */
    table {
      border-collapse: collapse; /* Darsellung des Gitternetzes */
      width: 100%;
      border-radius: 8px;
      background-color: white;
      white-space: nowrap; /* kein automatischer Zeilenumbruch (default) */
    }

    /* Tabellenkopf */
    th {
      background-color: #00796b;
      color: white;
      font-weight: bold;
      padding: 8px 10px;
      text-align: left;
      cursor: pointer; /* Spalten sind klickbar */
      position: sticky; /* Kopf bleibt beim Scrollen sichtbar */
      top: 0;
      z-index: 2;
    }

    /* Tabellenzellen */
    td { 
      padding: 6px 10px;
      white-space: nowrap;
    }

    /* Zellen, in denen Zeilenumbrüche erlaubt sind */
    td.breakable {
      white-space: pre; 	  /* keine automatischen Zeilenumbrüche */
      word-break: keep-all;    /* keine Worttrennungen */
    }

    /* Jede zweite Zeile leicht einfärben */
    tr:nth-child(even) { background-color: #f9f9f9; }
    
    /* Hover-Effekt */
    tr:hover { background-color: #e0f7fa; }

    /* Suchbereich */
    #searchContainer {
      text-align: center;
      margin: 20px auto;
    }

    /* Suchfeld & Dropdown */
    #searchInput, #columnSelect {
      padding: 8px;
      font-size: 14px;
      border-radius: 6px;
      border: 1px solid #ccc;
      margin: 5px;
    }
  </style>
</head>
<body>

  <!-- Hauptüberschrift -->
  <h1>QUADRIGA FS3 Korpusmetadaten</h1>

<!-- Such- und Filterbereich -->
<div id="searchContainer">
  <input type="text" id="searchInput" placeholder="Search...">
  <select id="columnSelect"></select>

  <!-- Anzeige der Eintragsanzahl -->
  <span id="entryCount" style="
    display: inline-block;
    margin-left: 15px;
    padding: 6px 10px;
    border: 1px solid #ccc;
    border-radius: 6px;
    background-color: #f9f9f9;
    font-size: 14px;
  ">Entries: 0</span>
</div>
  <!-- Tabellencontainer -->
  <div id="tableContainer">
    <table id="csvTable"></table>
  </div>

  <script>
    /*
      CSV-Daten als mehrzeiliger String.
      Trennzeichen: Semikolon (;) wegen CSV aus Excel-Export
    */
    const csvText = `title;object_id;imdb_id;classification;country;year;director;runtime_min;duration_iso8601;season_episode;episode_title;modes_intervention;annotation_data;moviebarcode
2040;f0162;tt7150512;documentary;AU;2018;Damon Gameau;92 Min.;PT1H32M;;;Escalation / de-escalation;TRUE;TRUE
2067;f0522;tt1918734;feature film;AU;2020;Seth Larney;114 Min.;PT1H54M;;;;FALSE;TRUE
Albatross;f025a;tt9914642;documentary;US;2017;Chris Jordan;97 Min.;PT1H37M;;;;FALSE;TRUE
An Inconvenient Sequel: Truth to Power;f009a;tt6322922;documentary;US;2017;"Bonni Cohen;Jon Shenk";98 Min.;PT1H38M;;;;FALSE;TRUE
An Inconvenient Truth;f020a;tt0497116;documentary;US;2006;Davis Guggenheim;96 Min.;PT1H36M;;;;FALSE;TRUE
Annihilation;f049a;tt2798920;feature film;"US;GB";2018;Alex Garland;115 Min.;PT1H55M;;;;FALSE;TRUE
Another Earth;f040a;tt1549572;feature film;US;2011;Mike Cahill;92 Min.;PT1H32M;;;;FALSE;TRUE
Anthropocene: The Human Epoch;f002a;tt8399690;documentary;CA;2018;"Jennifer Baichwal; Edward Burtynsky; Nicholas de Pencier";87 Min.;PT1H27M;;;"Unintended Consequences; Escalation / de-escalation; Unintended Consequences; Escalation / de-escalation";TRUE;TRUE
Awake: A Dream from Standing Rock;f012a;tt6691862;documentary;US;2017;"Myron Dewey; Josh Fox; James Spione";89 Min.;PT1H29M;;;"Disruptive scaling; Non-linear temporalities; Unintended Consequences; Post-anthropocentric reperspectivations";TRUE;TRUE
Beasts of the Southern Wild;f065b;tt2125435;feature film;US;2012;Benh Zeitlin;93 Min.;PT1H33M;;;Destabilization / Restabilization;TRUE;TRUE
Before the Flood;f013b;tt5929776;documentary;US;2016;Fisher Stevens;96 Min.;PT1H36M;;;Escalation / de-escalation;TRUE;TRUE
Blade Runner 2049;f063b;tt1856101;feature film;"US; CA; ES";2017;Denis Villeneuve;164 Min.;PT2H44M;;;;FALSE;TRUE
Blue Planet II;e066b;tt7473714;episode;"GB; US; CN; FR; DE";2018;James Honeyborne;51 Min.;PT51M;S01E01;One Ocean;;FALSE;TRUE
Blue Planet II;e067b;tt7579602;episode;"GB; US; CN; FR; DE";2018;James Honeyborne;54 Min.;PT54M;S01E02;The Deep;;FALSE;TRUE
Blue Planet II;e068b;tt7579754;episode;"GB; US; CN; FR; DE";2018;James Honeyborne;52 Min.;PT52M;S01E04;Big Blue;;FALSE;TRUE
Blue Planet II;e069b;tt7579776;episode;"GB; US; CN; FR; DE";2018;James Honeyborne;50 Min.;PT50M;S01E06;Coasts;;FALSE;TRUE
Blue Planet II;e070b;tt7579782;episode;"GB; US; CN; FR; DE";2018;James Honeyborne;53 Min.;PT53M;S01E07;Our Blue Planet;;FALSE;TRUE
Blue Planet II;e114t;tt7579764;episode;"GB; US; CN; FR; DE";2018;James Honeyborne;51 Min.;PT51M;S01E03;Coral Reefs;;FALSE;TRUE
Blue Planet II;e115t;tt7579758;episode;"GB; US; CN; FR; DE";2018;James Honeyborne;53 Min.;PT53M;S01E05;Green Seas;;FALSE;TRUE
Carbon Nation;f007c;tt1482991;documentary;US;2010;Peter Byck;86 Min.;PT1H26M;;;;FALSE;TRUE
Chasing Ice;f032c;tt1579361;documentary;US;2012;Jeff Orlowski-Yang;75 Min.;PT1H15M;;;;FALSE;TRUE
Children of Men;f042c;tt0206634;feature film;"US; GB; JP";2006;Alfonso Cuarón;109 Min.;PT1H49M;;;;FALSE;TRUE
Climate of Change;f022c;tt1563712;documentary;US;2010;Brian Hill;86 Min.;PT1H26M;;;;FALSE;TRUE
Dear Future Children;f005d;tt11191356;documentary;"DE; GB; AT";2021;Franz Böhm;89 Min.;PT1H29M;;;;FALSE;TRUE
Everything Will Change;f029e;tt13086274;documentary;"DE; NL";2021;Marten Persiel;93 Min.;PT1H33M;;;Post-anthropocentric reperspectivations;TRUE;TRUE
Everything's Cool;f019e;tt0810970;documentary;US;2007;"Daniel B. Gold; Judith Helfand";89 Min.;PT1H29M;;;;FALSE;TRUE
First Reformed;f059f;tt6053438;feature film;"US; GB; AU";2017;Paul Schrader;113 Min.;PT1H53M;;;"Escalation / de-escalation; Disruptive scaling";TRUE;TRUE
Frozen Planet;e213f;tt2095246;episode;"GB; US; ES; DE; GR; CA";2012;Paul Spillenger;58 Min.;PT58M;S01E01;To the Ends of the Earth;;FALSE;TRUE
Frozen Planet;e214f;tt2095243;episode;"GB; US; ES; DE; GR; CA";2012;"Mark Linfield; Paul Spillenger";58 Min.;PT58M;S01E02;Spring;;FALSE;TRUE
Frozen Planet;e215f;tt2095244;episode;"GB; US; ES; DE; GR; CA";2012;Paul Spillenger;59 Min.;PT59M;S01E03;Summer;;FALSE;TRUE
Frozen Planet;e216f;tt2095241;episode;"GB; US; ES; DE; GR; CA";2012;Paul Spillenger;58 Min.;PT58M;S01E04;Autumn;;FALSE;TRUE
Frozen Planet;e217f;tt2095247;episode;"GB; US; ES; DE; GR; CA";2012;Paul Spillenger;58 Min.;PT58M;S01E05;Winter;;FALSE;TRUE
Frozen Planet;e218f;tt2095245;episode;"GB; US; ES; DE; GR; CA";2012;Paul Spillenger;58 Min.;PT58M;S01E06;The Last Frontier;;FALSE;TRUE
Frozen Planet;e219f;tt2095242;episode;"GB; US; ES; DE; GR; CA";2012;Paul Spillenger;58 Min.;PT58M;S01E07;On Thin Ice;;FALSE;TRUE
Frozen Planet II;e220f;tt18468964;episode;GB;2023;Alex Lanchester;57 Min.;PT57M;S01E01;Frozen Worlds;;FALSE;TRUE
Frozen Planet II;e221f;tt21987364;episode;GB;2023;Rachel Scott;57 Min.;PT57M;S01E02;Frozen Ocean;;FALSE;TRUE
Frozen Planet II;e222f;tt21987366;episode;GB;2023;Alex Lanchester;58 Min.;PT58M;S01E03;Frozen Peaks;;FALSE;TRUE
Frozen Planet II;e223f;tt21987370;episode;GB;2023;Orla Doherty;58 Min.;PT58M;S01E04;Frozen South;;FALSE;TRUE
Frozen Planet II;e224f;tt21987376;episode;GB;2023;Jane Atkins;57 Min.;PT57M;S01E05;Frozen Lands;;FALSE;TRUE
Frozen Planet II;e225f;tt21987378;episode;GB;2023;James Reed;58 Min.;PT58M;S01E06;Our Frozen Planet;;FALSE;TRUE
Geostorm;f045g;tt1981128;feature film;"US; JP; AE; HK";2017;Dean Devlin;111 Min.;PT1H51M;;;;FALSE;TRUE
Greta;f018i;tt10394738;documentary;"SE; DE; GB; US";2020;Nathan Grossman;97 Min.;PT1H37M;;;;FALSE;TRUE
Guardians of the Earth;f028g;tt7214084;documentary;"DE; AT";2017;Filip Antoni Malinowski;86 Min.;PT1H26M;;;;FALSE;TRUE
Hell;f047h;tt1643222;feature film;"DE; FR";2011;Tim Fehlbaum;89 Min.;PT1H29M;;;;FALSE;TRUE
Home;f004h;tt1014762;documentary;FR;2009;Yann Arthus-Bertrand;118 Min.;PT1H58M;;;;FALSE;TRUE
How to Blow Up a Pipeline;f043h;tt21440780;feature film;US;2022;Daniel Goldhaber;104 Min.;PT1H44M;;;Escalation / de-escalation;TRUE;TRUE
How to Let Go of the World: and Love All the Things Climate Can't Change;f014h;tt5246328;documentary;US;2016;Josh Fox;127 Min.;PT2H07M;;;;FALSE;TRUE
How To Save Our Planet;v088h;;video;;;;8 Min.;PT8M;;;;FALSE;TRUE
Inuit Knowledge and Climate Change;f026i;tt4081544;documentary;CA;2010;"Zacharias Kunuk; Ian Mauro";60 Min.;PT1H00M;;;Destabilization / Restabilization;TRUE;TRUE`     
    /*
      Hauptfunktion:
      - liest CSV
      - erzeugt Tabelle
      - baut Spaltenüberschriften
      - füllt Dropdown
    */
   function parseCSV(text, delimiter = ';') {
  const rows = [];
  let row = [];
  let cell = '';
  let inQuotes = false;

  for (let i = 0; i < text.length; i++) {
    const char = text[i];
    const nextChar = text[i + 1];

    if (char === '"' && inQuotes && nextChar === '"') {
      cell += '"';
      i++;
    } else if (char === '"') {
      inQuotes = !inQuotes;
    } else if (char === delimiter && !inQuotes) {
      row.push(cell);
      cell = '';
    } else if ((char === '\n' || char === '\r') && !inQuotes) {
      if (char === '\r' && nextChar === '\n') i++;
      row.push(cell);
      rows.push(row);
      row = [];
      cell = '';
    } else {
      cell += char;
    }
  }

  row.push(cell);
  rows.push(row);

  return rows;
}
    function showCSV(csv) {

      /*
      teilt die CSV in Zeilen und Spalten auf
      ';' als Trennzeichen festlegen
      */
      const rows = parseCSV(csv.trim(), ';');
      
      // Tabelle leeren, um sie je nach Suchbegriff neu zu bauen      
      const table = document.getElementById('csvTable');
      table.innerHTML = '';

      /* ## Tabellenkopf ## */
      const headerRow = document.createElement('tr');
      rows[0].forEach((h, index) => {
        const th = document.createElement('th');
        th.textContent = h;
        
        // Ermöglicht sortieren durch Klick auf den Tabellenkopf        
        th.addEventListener('click', () => sortTable(index));
        headerRow.appendChild(th);
      });
      table.appendChild(headerRow);
      const headerNames = rows[0];

      /* ## Dropdown mit Spaltennamen ## */
      const select = document.getElementById('columnSelect');
      select.innerHTML = '';

      // Erstellt das Dropdown-Menü für die Suchfilter      
      const allOption = document.createElement('option');
      allOption.value = 'all';
      allOption.textContent = 'All Columns';
      select.appendChild(allOption);
      
      // Fügt die eizelnen Spalten als Suchfilter hinzu
      headerNames.forEach(name => {
        const opt = document.createElement('option');
        opt.value = name;
        opt.textContent = name;
        select.appendChild(opt);
      });

      /* Definiert Spalten, in denen Zeilenumbrüche erlaubt sind */
      const breakableColumns = ['title', 'episode_title'];

      /* ## Tabelleninhalt ## */
      rows.slice(1).forEach(r => {
        const tr = document.createElement('tr');
        r.forEach((cell, index) => {
          const td = document.createElement('td');

    // Für normale Spalten: Zeilenumbrüche entfernen
		if (!breakableColumns.includes(headerNames[index])) {
  cell = cell.replace(/\n/g, ' ');
} else {
  td.classList.add('breakable');

  /*
  Prüfen, ob Text zu breit ist.
  Nur dann wird ein manueller Zeilenumbruch eingefügt.
  */
  const tempSpan = document.createElement('span');
  tempSpan.style.visibility = 'hidden';
  tempSpan.style.whiteSpace = 'nowrap';
  tempSpan.textContent = cell;
  document.body.appendChild(tempSpan);

  const textWidth = tempSpan.offsetWidth;
  const columnWidth = td.offsetWidth || 200; // fallback if empty

  document.body.removeChild(tempSpan);

  if (textWidth > columnWidth * 1.1) { // force break only if too wide
    const midpoint = Math.floor(cell.length / 2);
    const breakPos = cell.indexOf(' ', midpoint);
    if (breakPos !== -1) {
      cell = cell.slice(0, breakPos) + '\n' + cell.slice(breakPos + 1);
    }
  }
}
          // Spezialfall: imdb_id 
          if (headerNames[index] === 'imdb_id') {
            const a = document.createElement('a');
            a.href = `https://www.imdb.com/title/${cell}/`; //generiert den Link zur entsprechenden imdb-Seite
            a.textContent = cell; //angezeigter Text ist nur die imdb_id
            a.target = '_blank';
            td.appendChild(a);
          } else {
            td.textContent = cell;
          }

          tr.appendChild(td);
        });
        table.appendChild(tr);
      });
	  updateEntryCount();
    }

    // CSV anzeigen
    showCSV(csvText);

    /* ## Tabellen-Sortierung ## */
    function sortTable(colIndex) {
      const tableEl = document.getElementById('csvTable');
      const rowsArray = Array.from(tableEl.querySelectorAll('tr:not(:first-child)'));
      
      // Prüfen, ob aktuell aufsteigend sortiert ist
      const isAsc = tableEl.getAttribute('data-sort-col') == colIndex &&
                    tableEl.getAttribute('data-sort-order') == 'asc';

      rowsArray.sort((a, b) => {
        const aText = a.children[colIndex].textContent;
        const bText = b.children[colIndex].textContent;
        
        /* 
        Numerische Tabellenwerte werden von String in Float umgewandelt, 
        um sie für die Sortierung vergleichbar zu machen
        */         
        const aNum = parseFloat(aText.replace(',', '.'));
        const bNum = parseFloat(bText.replace(',', '.'));
        
        /* Prüft, ob die zu sortierende Spalte Zahlen oder Text enthält */        
        if (!isNaN(aNum) && !isNaN(bNum)) {
          return isAsc ? bNum - aNum : aNum - bNum;
        } else {
          return isAsc ? bText.localeCompare(aText) : aText.localeCompare(bText);
        }
      });

      // Neue Reihenfolge ins DOM schreiben
      rowsArray.forEach(row => tableEl.appendChild(row));
      
      // Sortierstatus speichern
      tableEl.setAttribute('data-sort-col', colIndex);
      tableEl.setAttribute('data-sort-order', isAsc ? 'desc' : 'asc');
    }

    /* ## Filtern ## */
    const searchInput = document.getElementById('searchInput');
    const columnSelect = document.getElementById('columnSelect');

    searchInput.addEventListener('input', filterTable);
    columnSelect.addEventListener('change', filterTable);

    function filterTable() {
      const filter = searchInput.value.toLowerCase();
      const selectedColumn = columnSelect.value;
      const table = document.getElementById('csvTable');
      const rows = table.querySelectorAll('tr:not(:first-child)');

      rows.forEach(tr => {
        if (!filter) { /* Bei leerer Suchzeile wird die gesamte Tabelle angezeigt */
          tr.style.display = '';
          return;
        }

        let textToCheck = '';
        if (selectedColumn === 'all') { /* Alle Spalten werden durchsucht */
          textToCheck = tr.textContent.toLowerCase();
        } else { /* Ansonsten: Macht ein Array aus allen Spaltenüberschriften und ermittelt die zu dursuchende Spalte */
          const header = Array.from(table.querySelectorAll('tr:first-child th'))
          .findIndex(th => th.textContent === selectedColumn);
          /* Jetzt wird der Zeileninhalt der jeweiligen Spalte durchsucht */          
          textToCheck = tr.children[header].textContent.toLowerCase();
        }
        /* Bestimmt ob die Zeile angezeigt wird oder nicht */
        tr.style.display = textToCheck.includes(filter) ? '' : 'none';
      });
    /* Passt den Eintragszähler an */
	  updateEntryCount();
    }
    
/* ## Eintragszähler ## */
function updateEntryCount() {
  const table = document.getElementById('csvTable');
  const rows = table.querySelectorAll('tr:not(:first-child)');
  const totalCount = rows.length;
  const visibleCount = Array.from(rows).filter(r => r.style.display !== 'none').length;
  document.getElementById('entryCount').textContent = `Entries: ${visibleCount} / ${totalCount} total`; 
}
  </script>
</body>
</html>
````

`````

### Nachnutzung und Anpassung

Für das eigene Projekt sind folgende Stellen anzupassen, dafür muss die Datei in einem Text- und Code-Editor (z.B. VS Code) geöffnet werden. 

1. Seitentitel (Browser-Tab): **Zeile 8**

```html
<title>QUADRIGA FS3 Korpusmetadaten</title>
```
→ Ersetzen durch den eigenen Projekttitel, z.B. `<title>Mein Datensatz</title>`

2. Hauptüberschrift (sichtbar auf der Seite): **Zeile 82**

```html
<h1>QUADRIGA FS3 Korpusmetadaten</h1>
```
→ Ersetzen durch die gewünschte Überschrift, z.B. `<h1>Titel meines Datensatzes</h1>`

3. `csv`-Daten einbetten: **Zeile 110**

```javascript
const csvText = `title;object_id;...
Zeile 1;...
Zeile 2;...
`
```
→ Den gesamten Inhalt zwischen den Backticks (`` ` ``) durch die eigenen CSV-Daten ersetzen. **Wichtig**: Die Backticks am Anfang und Ende müssen erhalten bleiben

`````{admonition} Trennzeichen anpassen (Zeile 207)
:class: hinweis
Weiter unten im Code wird das Semikolon als Trennzeichen definiert:

```javascript
const rows = parseCSV(csv.trim(), ';');
```

Falls der eigene `csv`-Datensatz ein anderes Trennzeichen verwendet (z.B. Komma), muss hier das Semikolon `';'` durch ein Komma `','` ersetzt werden.
`````
4. Leerzeichen in Spaltenüberschriften prüfen

Wenn die `html`-Tabelle nach dem Anpassen der `csv`-Daten nicht korrekt dargestellt wird oder Spalten falsch zugeordnet sind, liegt der Fehler sehr häufig an **führenden oder nachgestellten Leerzeichen in den Spaltenüberschriften** der `csv`. Diese entstehen leicht beim Export aus Excel. Die Kopfzeile der eingebetteten `csv` im `csvText`-String sollte deshalb manuell überprüft werden – am einfachsten in einem Text-Editor wie VS Code.

5. Semikolons in leeren Feldern erhalten

Wie bereits im Abschnitt {ref}`XLSX zu CSV <xlsx-zu-csv>` beschrieben: Die Semikolons zwischen leeren Feldern sind *Positionsmarker* und dürfen nicht entfernt werden. Wenn z.B. `season_episode` und `episode_title` für einen Spielfilm leer sind, muss die Zeile trotzdem so aussehen:

```text
Annihilation;f049a;tt2798920;feature film;"US;GB";2018;Alex Garland;115 Min.;PT1H55M;;;;FALSE;TRUE
```

Die vier aufeinanderfolgenden Semikolons (`;;;;`) sichern, dass `annotation_data` und `moviebarcode` in den richtigen Spalten stehen.

```{admonition} Nutzung des Skripts
:class: keypoint
Das `hmtl`-Skript kann auch für andere Datensätze mit abweichenden Feldern übernommen werden. Voraussetzungen hierfür sind:
1. Die eingebunden `csv`-Daten haben eine Kopfzeile mit Spaltennamen
2. Mit Semikolon getrennte Werte verwenden; andernfalls (wie oben beschrieben) das Trennzeichen anpassen
```

Alternativ gibt es auch die Möglichkeit, sich mit Generativen-KI-Tools `html`-Skripte generieren zu lassen und diese dann zu bearbeiten oder anzupassen. Dies ist in den Digital Humanities aus heutiger Perspektive gängige Praxis und erleichtert die Arbeitsprozesse. Grundlegende `html`- und `JavaScript`-Kenntnisse (bzw. auch `css`) sind dafür sehr hilfreich, um den Code zu verstehen und entsprechend bearbeiten zu können.

## CSV zu JSON

`json` wird häufig für den Datenaustausch genutzt und kann, im Gegensatz zu `csv`, **Datentypen** abbilden. Das macht `json` maschinenlesbarer und für viele Weiterverarbeitungsszenarien attraktiver. 

```{admonition} Welche grundlegenden Datentypen gibt es?
:class: hinweis
Datentypen in Programmiersprachen legen fest, welche Art von Wert in einem Feld steht und wie der Wert verarbeitet werden kann. Die Grundtypen sind:

* String (Text) – z.B. `"Anthropocene"`, immer in Anführungszeichen
* Integer (Ganzzahl) – z.B. `2018`, ohne Anführungszeichen und ohne Nachkommastellen
* Float (Gleitkommazahl) – z.B. `1.5`, für Werte mit Nachkommastellen
* Boolean (Wahrheitswert) – nur `true` oder `false`, z.B. ob eine Annotation vorhanden ist

`csv` kennt diese Unterscheidung nicht. Rein technisch gesehen ist dort alles Text – auch Zahlen oder Wahrheitswerte. 
```

Um den Beispieldatensatz, der als `csv`-Datei voliegt, auch in `json` zu konvertieren, wird ein Python-Skript verwendet. Der folgende Code arbeitet mit einigen zentralen Python-Konzepten, kann jedoch auch ohne Vorwissen ausgeführt werden. Wer noch keine Python-Erfahrung hat, findet hier kurze Erklärungen sowie Tutorials zum Vertiefen. Zum Schreiben eines eigenen Python-Skript werden allerdings vertiefende Kenntnisse benötigt.

`````{dropdown} Python-Grundkonzepte im Detail und weiterführende Links
Neben den oben genannten Datentypen gibt es noch folgende Grundkonzepte, die für das Verständnis des Codes hilfreich sein können:
* Bibliotheken (`import`): Python selbst stellt in der Standardinstallation nur wenige Funktionen zur Verfügung; zusätzliche Funktionen werden beispielsweise über Bibliotheken wie `pandas` (Tabellenverarbeitung) oder `json` (`json`-Verarbeitung) eingebunden
* Funktionen (`def`): Funktionen sind wiederverwendbare Codeblöcke, die eine bestimmte Aufgabe erfüllen. `def konvertiere_wert(wert):` definiert eine Funktion, die einen Wert entgegennimmt und einen umgewandelten Wert zurückgibt (`return`)
* Bedingungen (`if`): Prüfen, ob etwas zutrifft, und führen je nach Ergebnis unterschiedlichen Code aus. Im Beispiel: "Wenn der Wert `TRUE` ist, gib `True` zurück."
* DataFrame: `DataFrame` ist die zentrale Datenstruktur der `pandas`-Bibliothek, vergleichbar mit einer Tabelle aus Zeilen und Spalten, mit der programmatisch gearbeitet werden kann

```{admonition} Tutorials: Python für Anfänger 
:class: seealso
* <a href="https://www.python.org/about/gettingstarted/" class="external-link" target="_blank">Offizielle Python-Seite</a>
* <a href="https://www.w3schools.com/python/python_intro.asp" class="external-link" target="_blank">W3Schools Python Tutorial</a>
* <a href="https://en.wikibooks.org/wiki/Non-Programmer's_Tutorial_for_Python_3" class="external-link" target="_blank">Wikibooks Non-Programmer's Tutorial for Python 3</a>
```
`````
### Schritt-für-Schritt: CSV zu JSON

(python-umgebung)=
#### Python-Umgebung einrichten

Um das folgende Skript auszuführen, wird eine funktionierende Python-Umgebung mit der Bibliothek `pandas` benötigt. Nachfolgend wird die Variante vorgestellt, die für Einsteiger:innen am freundlichsten ist. Denn es gibt die Möglichkeit Python (und alle benötigten Bibliotheken und Editoren) über die Distribution (Zusammenstellung verschiedener Pakete und Software) <a href="https://www.anaconda.com/download" class="external-link" target="_blank">Anaconda</a> herunterzuladen. Für den Download bitte den Anweisungen auf der Seite folgen.

1. Anaconda Distribution herunterladen und installieren (**Achtung: die Installation benötigt mehrere GB Speicherplatz!**)
2. Anaconda Navigator öffnen
3. Bei → `Jupyter Notebook` auf → `Launch` klicken – es öffnet sich ein neuer Tab im Browser; parallel öffnet sich das Terminal, dieser kann vorerst einfach ignoriert werden

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_anaconda_launch_notebook.png
---
align: center
width: 85%
name: anaconda-launch-jb
---
Anaconda-Interface
```

4. Im Dateibrowser zu dem Ordner navigieren, in dem die `csv`-Datei liegt (durch Klicken auf die Ordnersymbole)

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_notebook_ordner.png
---
align: center
width: 90%
name: ordnernavigation
---
Ordnernavigation
```

5. Über `New` → `Notebook` ein neues Notebook in diesem Ordner erstellen; der Python-Kernel wird automatisch ausgewählt, es sollte der Kernel `Python 3` erscheinen

```{figure} ../assets/05_aufbereitung_anreicherung/abb_k05_notebook_kernel_python.png
---
align: center
width: 90%
name: select-python-kernel
---
Python-Kernel wählen
```

6. Jetzt öffnet sich ein neues Notebook und die Umgebung ist eingerichtet; das neue Notebook wird in dem Ordnerverzeichnis gespeichert

#### Python-Skript ausführen

```{admonition} Installation der Pandas-Bibliothek
:class: danger
In der Regel ist `pandas` über Anaconda bereits vorinstalliert. Sollte beim Ausführen des Codes ein Fehler wie `ModuleNotFoundError: No module named 'pandas'` erscheinen, dann direkt in der Notebook-Zelle folgenden Befehl ausführen: `!pip install pandas`
```
Dieses Skript kann in dem geöffneten Notebook ausgeführt werden, die mit `#` gekennzeichneten Kommentare beeinträchtigen die Code-Funktionen nicht.

Es müssen lediglich die Dateinamen, wie oben angemerkt, unter `input_datei = "annotation_metadata.csv"` (Eingabedatei), 
`output_datei = "annotation_metadata.json"` (Ausgabedatei) für den eigenen Datensatz angepasst werden. Für den Beispieldatensatz kann folgender Titel der Eingabedatei eingegeben werden: `doc_k05_beispieldatensatz.csv`. Die Ausgabedatei kann entsprechend so benannt werden: `doc_k05_beispieldatensatz.json`. Der Rest des Codes funktioniert für jeden semikolon-getrennten CSV-Datensatz mit `TRUE`/`FALSE`-Werten und numerischen Feldern. Nach dem Ausführen sollte in dem gewählten Ordnerverzeichnis ein `json`-Export der `csv`-Datei vorliegen.

```python
import pandas as pd
import json
import re

# 1) Dateinamen festlegen
input_datei = "annotation_metadata.csv"   # 1. Name der Eingabedatei anpassen
output_datei = "annotation_metadata.json" # 2. Name der Ausgabedatei anpassen

# 2) CSV einlesen
# sep=";" → wichtig, weil Datei semikolon-getrennt ist
# dtype=str Hiermit werden alle Werte erstmal als Text eingelesen 
# die Typkonvertierung erfolgt erst im nächsten Schritt kontrolliert
df = pd.read_csv(input_datei, sep=";", dtype=str)

# 3) Leere Zellen als leere Strings statt NaN behandeln
# pandas füllt leere Felder standardmäßig mit NaN (Not a Number),
# in JSON wird das zu "null"-Werten, daher werden sie als "" gesetzt
df = df.fillna("")

# 4) Funktion zum Umwandeln einzelner Werte
def konvertiere_wert(wert):
    # Falls der Wert kein String ist, direkt zurückgeben
    if not isinstance(wert, str):
        return wert
    # Leerzeichen am Anfang und Ende entfernen
    wert = wert.strip()
    # TRUE / FALSE in echte JSON-Booleans umwandeln
    # (in CSV sind das Strings, in JSON sollten es true/false sein)
    if wert == "TRUE":
        return True
    if wert == "FALSE":
        return False
    # Ganzzahlen in int umwandeln (z.B. Jahreszahlen, Laufzeiten)
    if re.fullmatch(r"-?\d+", wert):
        return int(wert)
    # Alles andere bleibt Text
    return wert

# 5) Alle Zellen der Tabelle durch die Funktion laufen lassen
df = df.map(konvertiere_wert)

# 6) Tabelle in eine Liste von Datensätzen (Dictionaries) umwandeln
# orient="records" bedeutet: jede Zeile wird ein eigenes JSON-Objekt
daten = df.to_dict(orient="records")

# 7) Als JSON-Datei speichern
# ensure_ascii=False bedeutet: Sonderzeichen (Umlaute etc.) bleiben lesbar
# indent=2 sorgt für ein eingerücktes, menschenlesbares Format
with open(output_datei, "w", encoding="utf-8") as f:
    json.dump(daten, f, ensure_ascii=False, indent=2)

print(f"Fertig. JSON gespeichert als: {output_datei}")
```
Es müssen lediglich die Dateinamen, wie oben angemerkt, unter `input_datei = "annotation_metadata.csv"` (Eingabedatei), 
`output_datei = "annotation_metadata.json"` (Ausgabedatei) für den eigenen Datensatz angepasst werden. Der Rest des Codes funktioniert für jeden semikolon-getrennten CSV-Datensatz mit `TRUE`/`FALSE`-Werten und numerischen Feldern. Nach dem Ausführen sollte in dem gewählten Ordnerverzeichnis ein `json`-Export der `csv`-Datei vorliegen.

Anschließend kann der Browsertab geschlossen werden. Um den Jupyter Server sauber zu beenden, empfiehlt es sich in dem zuvor sich öffnendem Terminalfenster durch eingabe von `Control + C` bzw. `Strg + C` die Prozesse zu beenden.


### Das Ergebnis

Die `json`-Datei enthält eine Liste von Objekten, eines pro Zeile der ursprünglichen `csv`. Ein einzelner Eintrag sieht beispielsweise so aus:

```json
{
  "title": "2040",
  "object_id": "f0162",
  "imdb_id": "tt7150512",
  "classification": "documentary",
  "country": "AU",
  "year": 2018,
  "director": "Damon Gameau",
  "runtime_min": "92 Min.",
  "duration_iso8601": "PT1H32M",
  "season_episode": "",
  "episode_title": "",
  "modes_intervention": "Escalation / de-escalation",
  "annotation_data": true,
  "moviebarcode": true
}
```

Leere Felder wurden beim Export bewusst als leere Zeichenketten ("") beibehalten und nicht als `null`-Werte, um die tabellarische Struktur der Metadaten zu erhalten. Wahrheitswerte wie `TRUE` und `FALSE` wurden dagegen in die `json`-Booleans `true` und `false` überführt. `year` wird ebenfalls als Ganzzahl `2018` gespeichert und nicht als String `"2018"`. Der Beispieldatensatz kann zum Abgleich [hier](../assets/05_aufbereitung_anreicherung/doc_k05_beispieldatensatz.json) gespeichert werden.