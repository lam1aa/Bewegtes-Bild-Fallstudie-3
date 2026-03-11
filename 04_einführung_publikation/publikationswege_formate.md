# Publikationswege und -formate

Es gibt zahlreiche Möglichkeiten, Forschungsdaten zu publizieren und sie für die Wissenschaftscommunity zugänglich sowie nachnutzbar zu machen. Im Folgenden stellen wir die relevantesten Publikationswege und -formate praxisnah vor und kennzeichnen jeweils das erforderliche technische Niveau. 

## Repositorien
*→ Niveau: Basis / Fortgeschritten*
<style>

.accordion-block details {
  margin-bottom: 0.6rem;
}

.accordion-block summary {
  font-weight: 600;
  font-size: 1.1rem;
  cursor: pointer;
  list-style: none;
}

.accordion-block summary::marker {
  display: none;
}

.accordion-block summary::before {
  content: "▸";
  font-size: 1.9rem;      
  margin-right: 0.6rem;
  display: inline-block;
  transform: translateY(2px);
  transition: transform 0.2s ease;
}

.accordion-block details[open] summary::before {
  transform: rotate(90deg);
}

.accordion-content {
  margin-top: 0.6rem;
}

</style>


<div class="accordion-block">


<details>
<summary>Inhalte anzeigen</summary>

<div class="accordion-content">

Sehr beliebt und niedrigschwellig in den erforderlichen Kompetenzen sind wissenschaftliche Repositorien. Repositorien sind digitale Speicherorte und Datenlager, in denen Forschungsdaten veröffentlicht, verwaltet und aufbewahrt werden können. Die in einem Repositorium publizierten Daten können Nutzer:innen, zumeist öffentlich und teils beschränkt, zugänglich gemacht werden.

```{figure} ../assets/04_einführung_publikation/abb_k04_repositorien.png
---
align: center
width: 90%
name: daten-repositorien
---
Daten publizieren in Repositorien
```

Unterschieden wird zwischen institutionellen, disziplinären oder generischen Repositorien. (z.B. <a href="https://refubium.fu-berlin.de/" class="external-link" target="_blank">Refubium</a> der FU Berlin oder der <a href="https://edoc.hu-berlin.de/home" class="external-link" target="_blank">edoc-Server</a> der HU Berlin) betrieben und ermöglichen ihren Mitgliedern die digitale Publikation wissenschaftlicher Dokumente. 

```{figure} ../assets/04_einführung_publikation/abb_k04_refubium_fu.png
---
align: center
width: 100%
name: refubium-fu
---
Exemplarische Ansicht einer Suche im <a href="https://refubium.fu-berlin.de/" class="external-link" target="_blank">Refubium</a> der FU
```

Disziplinäre Repositorien hingegen sind institutsübergreifend und Forschungsorte der Exploration der jeweiligen Fachdisziplin. Einer der wichtigsten Repositorien der Film- und Medienwissenschaft ist <a href="https://mediarep.org/" class="external-link" target="_blank">media/rep/</a>. In dem Open-Access-Fachrepositorium werden Publikationen, Aufsätze, Forschungsdaten und andere Ressourcen der Film- und Medienwissenschaft kostenfrei und ohne Zugangsbeschränkung verfügbar gemacht. Es dient als zentrales und dauerhaftes Archiv der Disziplin und fördert Wissenschaft, Austausch und Forschung.

```{figure} ../assets/04_einführung_publikation/abb_k04_media_rep.png
---
align: center
width: 100%
name: media-rep
---
Startseite des film- und medienwissenschaftlichen Repositoriums <a href="https://mediarep.org/" class="external-link" target="_blank">media/rep/</a>
```

Zu den etablierten generischen Repositorien zählen <a href="https://zenodo.org/" class="external-link" target="_blank">Zenodo</a>, <a href="https://github.com/" class="external-link" target="_blank">Github</a> und <a href="https://figshare.com/" class="external-link" target="_blank"> Figshare</a>. Sie eignen sich insbesondere für disziplinübergreifende Datensätze, Code und Projektressourcen. Für die Datenpublikation sind persistente Identifikatoren (z.B. DOI) und Versionierungsmöglichkeiten entscheidend. Über Repositorien wie Zenodo oder Figshare werden bei der Publikation DOIs vergeben. GitHub hingegen wird dafür häufig mit einem DOI-fähigen Archivierungsdienst wie Zenodo kombiniert.

```{figure} ../assets/04_einführung_publikation/abb_k04_generische_repos.png
---
align: center
width: 85%
name: generische-repos
---
Startseite der etablierten generischen Repositorien <a href="https://zenodo.org/" class="external-link" target="_blank">Zenodo</a>, <a href="https://github.com/" class="external-link" target="_blank">Github</a> und <a href="https://figshare.com/" class="external-link" target="_blank"> Figshare</a>
```

```{admonition} Publikation auf Github und Zenodo
:class: hinweis
Im Kapitel [Dateninfrastrukturen](../06_publikation_repositorien/dateninfrastrukturen.md) werden die Schritte zur Publikation auf Github und Zenodo im Detail erläutert.
```

### Übersicht für Repositorien mit DOI-Vergabe
<table style="border-collapse: collapse; width: 100%; font-size: 1em;">
  <thead>
    <tr>
      <th style="text-align:left; padding:10px 8px; border-bottom:1px solid #e6e6e6;">Plattform</th>
      <th style="text-align:left; padding:10px 8px; border-bottom:1px solid #e6e6e6;">Schwerpunkt</th>
      <th style="text-align:left; padding:10px 8px; border-bottom:1px solid #e6e6e6;">DOI-Vergabe</th>
      <th style="text-align:left; padding:10px 8px; border-bottom:1px solid #e6e6e6;">Link</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;"><strong>Zenodo</strong></td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">Forschungsdaten, OER, Code, JupyterBooks</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">✅ Ja</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">
        <a href="https://zenodo.org/" target="_blank">zenodo.org</a>
      </td>
    </tr>
    <tr>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;"><strong>Figshare</strong></td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">Artikel, Datasets, Videos</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">✅ Ja</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">
        <a href="https://figshare.com/" class="external-link" target="_blank">Figshare</a>
      </td>
    </tr>
    <tr>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;"><strong>GitHub</strong></td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">Code, Versionierung, Workflows, Releases</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">⚠️ Nein (DOI i. d. R. über Zenodo-Archivierung)</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">
        <a href="https://github.com/" class="external-link" target="_blank">Github</a>
      </td>
    </tr>
    <tr>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;"><strong>Institutionelles Repositorium</strong></td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">z. B. FU Berlin, TIB Hannover</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">✅ Ja (bei Veröffentlichung)</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">via Hochschulbibliothek</td>
    </tr>
    <tr>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;"><strong>OSF.io</strong></td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">Projekte &amp; Preprints</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">✅ Ja</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">
        <a href="https://osf.io/" class="external-link" target="_blank">OSF.io</a>
      </td>
    </tr>
    <tr>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;"><strong>Dryad</strong></td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">Datensätze (v. a. begleitend zu Publikationen)</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">✅ Ja</td>
      <td style="padding:10px 8px; border-bottom:1px solid #f0f0f0;">
        <a href="https://datadryad.org/" class="external-link" target="_blank">Dryad</a>
      </td>
    </tr>
  </tbody>
</table>
<br>

Im nächsten Kapitel [Ressourcen und Entscheidungshilfen](../04_einführung_publikation/ressourcen_entscheidungshilfen.md) gibt es eine ausführliche Liste mit relevanten Repositorien und Repositorienfindern - mit Schwerpunkt auf Film-, Medien -und Geistenwissenschaften.

### Publizierte Daten in einem Repositorium: Fallbeispiel "Affektrhetoriken des Audiovisuellen"

Das Forschungsprojekt <a href="https://www.ada.cinepoetics.fu-berlin.de/ " class="external-link" target="_blank">"Affektrhetoriken des Audiovisuellen"</a> (kurz: AdA) stellt seine filmanalytischen Annotationsdaten als ein öffentlich zugängliches Datenpaket zur Nachnutzung in einem <a href="https://github.com/ProjectAdA/public" class="external-link" target="_blank"> Github-Repositorum</a> zur Verfügung. Die Projektergebnisse und Forschungsartefakte umfassen: eine Filmontologie und das Vokabular <a href="https://github.com/ProjectAdA/public/tree/master/manuals" class="external-link" target="_blank">(AdA-Filmontology)</a>, ein projektspezifisches Template für die Annotation mit dem Tool Advene sowie die <a href="https://github.com/ProjectAdA/public/tree/master/annotations" class="external-link" target="_blank">Annotationsdatensätze</a> selbst. 

```{figure} ../assets/04_einführung_publikation/abb_k04_ada_github.png
---
align: center
width: 100%
name: ada-github
---
<a href="https://github.com/ProjectAdA/public" class="external-link" target="_blank">Öffentliches Repositorium</a>  des AdA-Projekts
```

Der Datensatz umfasst über 92.000 feingranulare, timecode-basierte Annotationen und wird durch Korpus-Metadaten ergänzt. 

Das AdA-Projekt ist ein gutes Beispiel dafür, wie ein Repositorium nicht einzig als Ablage genutzt wird, sondern durch ausführliche Dokumentation, Versionierung und Distribution die Weiterverwendung der Daten einerseits, sowie die eigenständige Reproduktion der Datenerhebung andererseits sichergestellt werden kann.

```{admonition} Weiterführende Links
:class: seealso
* <a href="https://quadriga-dk.github.io/Bewegtes-Bild-Fallstudie-1/intro.html" class="external-link" target="_blank">QUADRIGA Fallstudie: "Affektrhetorik in Online-Videos zur Klimakrise. Datengestützte Analysen audiovisueller Muster"</a>
* <a href="https://www.cinepoetics.fu-berlin.de/en/methods/3_Tools/3_Documentation_AdA_Toolkit/index.html" class="external-link" target="_blank">AdA-Toolkit & Videotutorials</a>
* <a href="https://zenodo.org/records/8328663" class="external-link" target="_blank">AdA-Zenodo</a>
```
</div>
</details>

## Data Paper / Data Jounal
*→ Niveau: Basis*
<style>

.accordion-block details {
  margin-bottom: 0.6rem;
}

.accordion-block summary {
  font-weight: 600;
  font-size: 1.1rem;
  cursor: pointer;
  list-style: none;
}

.accordion-block summary::marker {
  display: none;
}

.accordion-block summary::before {
  content: "▸";
  font-size: 1.9rem;      
  margin-right: 0.6rem;
  display: inline-block;
  transform: translateY(2px);
  transition: transform 0.2s ease;
}

.accordion-block details[open] summary::before {
  transform: rotate(90deg);
}

.accordion-content {
  margin-top: 0.6rem;
}

</style>


<div class="accordion-block">


<details>
<summary>Inhalte anzeigen</summary>

<div class="accordion-content">

Ein Data Paper ist eine publizierte Dokumentation zu einem Datensatz, welcher umfangreiche Informationen über verschiedene Komponenten der Forschungsdaten enthält. In der Dokumentation wird beschrieben, wie, wann und warum die Daten erhoben wurden und was der Datensatz umfasst. Im Vordergrund eines Data Papers steht die Beschreibung des selbst generierten oder nachgenutzten Forschungsmaterials. Die Behandlung der wissenschaftlichen Fragestellung selbst ist nicht zentral.

Ähnlich wie bei wissenschaftlichen Artikeln, gibt es bei Data Papers ebenfalls Peer-Reviews.

Folgende Inhalte sollte ein Data Paper enthalten:
* Informationen zur Datenerhebung und -verarbeitung
* Informationen zur Datenqualität und -struktur 
* Potentielle Anwendungsfälle für die Nachnutzung
* Metadaten und Zugangsbedingungen 

```{figure} ../assets/04_einführung_publikation/abb_k04_data_paper_tu.png
---
align: center
width: 90%
name: data-paper-tu
---
Infografik Data Paper und Data Journals, © <a href="https://www.tu.berlin/ub/szf/tipps-tools/veroeffentlichen/data-paper-data-journals" class="external-link" target="_blank">TU Berlin</a> CC0
```
In fachspezifischen Data Journals können Data Paper eingereicht werden. Etablierte Journals für die Film- und Medienwissenschaft bzw. Digital Humanities sind <a href="https://necsus-ejms.org/" class="external-link" target="_blank">NECSUS</a> oder das <a href="https://openhumanitiesdata.metajnl.com/" class="external-link" target="_blank">Journal of Open Humanities Data</a>.

Ein Beispiel für ein Data Paper aus der Fimwissenschaft ist der Aufsatz <a href="https://necsus-ejms.org/how-to-capture-the-festival-network-reflections-on-the-film-circulation-datasets/ " class="external-link" target="_blank">"How to capture the festival network: Reflections on the Film Circulation datasets"</a> publiziert auf NECSUS von Skadi Loist und Evgenia (Zhenya) Samoilova. Darin dokumentieren die Autor:innen Kontext, Struktur, Aufbereitung und Auswertung ihres <a href="https://zenodo.org/records/7887672" class="external-link" target="_blank">Film Circulation Project Datensatzes</a> mit entsprechenden Berechnungen, Logiken und Visualisierungen. Als Necsus-Datapaper wird der Datensatz somit zugleich als eigenständiges Forschungsergebnis sichtbar. 

```{figure} ../assets/04_einführung_publikation/abb_k04_ausschnitt_necsus.png
---
align: center
width: 90%
name: necsus-datapaper
---
Ausschnitt aus dem <a href="https://necsus-ejms.org/how-to-capture-the-festival-network-reflections-on-the-film-circulation-datasets/ " class="external-link" target="_blank">Data Paper</a> von Skadi Loist und Evgenia (Zhenya) Samoilova auf NECSUS
```

```{admonition} Weiterführende Links
:class: seealso
* <a href="https://www.tu.berlin/ub/szf/tipps-tools/veroeffentlichen/data-paper-data-journals" class="external-link" target="_blank">Data Paper & Data Journals TU Berlin</a>
* <a href="https://www.cms.hu-berlin.de/de/dl/dataman/teilen/dokumentation/datajournal/datajournal" class="external-link" target="_blank">Auswahl an Data Journals HU Berlin</a>
* <a href="https://www.forschungsdaten.org/index.php/Data_Journals" class="external-link" target="_blank">Auswahl an Data Journals forschungsdaten.org</a>
* <a href="https://zenodo.org/records/7082126" class="external-link" target="_blank">List of data journals re3data</a>
```


</div>
</details>

## GLAM und interaktive Websiten
*→ Niveau: Fortgeschritten / Expert:in*
<style>

.accordion-block details {
  margin-bottom: 0.6rem;
}

.accordion-block summary {
  font-weight: 600;
  font-size: 1.1rem;
  cursor: pointer;
  list-style: none;
}

.accordion-block summary::marker {
  display: none;
}

.accordion-block summary::before {
  content: "▸";
  font-size: 1.9rem;      
  margin-right: 0.6rem;
  display: inline-block;
  transform: translateY(2px);
  transition: transform 0.2s ease;
}

.accordion-block details[open] summary::before {
  transform: rotate(90deg);
}

.accordion-content {
  margin-top: 0.6rem;
}

</style>


<div class="accordion-block">


<details>
<summary>Inhalte anzeigen</summary>

<div class="accordion-content">

Inhalte einfügen

</div>
</details>


## APIs
*→ Niveau: Expert:in*

<style>

.accordion-block details {
  margin-bottom: 0.6rem;
}

.accordion-block summary {
  font-weight: 600;
  font-size: 1.1rem;
  cursor: pointer;
  list-style: none;
}

.accordion-block summary::marker {
  display: none;
}

.accordion-block summary::before {
  content: "▸";
  font-size: 1.9rem;      
  margin-right: 0.6rem;
  display: inline-block;
  transform: translateY(2px);
  transition: transform 0.2s ease;
}

.accordion-block details[open] summary::before {
  transform: rotate(90deg);
}

.accordion-content {
  margin-top: 0.6rem;
}

</style>


<div class="accordion-block">


<details>
<summary>Inhalte anzeigen</summary>

<div class="accordion-content">

Inhalte einfügen

</div>
</details>

