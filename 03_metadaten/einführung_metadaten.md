# Einführung Metadaten

```{figure} ../assets/03_metadaten/abb_k03_metadata.png
---
align: left
width: 100%
name: metadata
---
Metadata, © @Markus Winkler via Unsplash
```
Metadaten sind Daten über Daten. Oder wie Johanna Drucker es treffend formuliert: "Think of metadata as the information about a resource or digital asset". Die Bandbreite der Erscheinungsformen von Metadaten reicht von sehr einfachen Beschreibungen, wie etwa den grundlegenden "Get Info"-Angaben zu einem digitalen Objekt, bis hin zu hochkomplexen Metadatenstrukturen mit mehreren Ebenen, Feldern und Hierarchien, wie sie insbesondere in Museen, kulturellen Einrichtungen und Archiven zur Erschließung und Verwaltung von Beständen genutzt werden.

```{image} ../assets/03_metadaten/abb_k03_bandbreite_metadaten.png
---
align: center
width: 70%
name: bandbreite-metadaten
---
```
<br>

Als Bestandteil von Dateien und Dokumenten geben Metadaten im Kern zusätzliche, strukturierte Informationen an, die den eigentlichen (Forschungs-)Daten, Ressourcen oder Objekten, die sie beschreiben, beigefügt werden.  Häufig stehen die Metadaten aber auch als Platzhalter für das Objekt selbst, wie es beispielsweise in Bibliothekskatalogen der Fall ist. Hier wird das ursprüngliche Objekt (z. B. ein Buch oder Film) über Metadaten definiert und identifiziert, um Materialien zu lokalisieren und Informationen einzugrenzen. Auf diese Weise ermöglichen Metadaten die Beschreibung, Identifizierung und Klassifizierung von (digitalen) Objekten und kulturellen Artefakten.

```{figure} ../assets/03_metadaten/abb_k03_kinemathek_katalog.png
---
align: center
width: 80%
name: kinemathek-katalog
---
Ergebnisansicht eines Bestandeintrags im Katalog der <a href="https://deutsche-kinemathek.bsz-bw.de/cgi-bin/koha/opac-detail.pl?biblionumber=21039" class="external-link" target="_blank">Deutschen Kinemathek Bibliothek</a>
```
Für die Publikation von Forschungsdaten sind Metadaten unerlässlich, da erst durch die ergänzenden Informationen Daten zuverlässig auffindbar, eindeutig identifizierbar und damit zitierfähig werden. Die zentrale Bedeutung von Metadaten in der digitalen Forschungspraxis hebt auch Drucker hervor: 
> "Metadata is an essential aspect of any digital scholarship or research. Data have to be described and identified in order to be useful." 

Die Charakterisierung von Daten über Metadaten ermöglicht es Forschenden somit, Daten in ihre jeweiligen Kontexte einzuordnen, ihre Herkunft und Struktur nachzuvollziehen und ihre Qualität zu bewerten.

## Arten von Metadaten

Es gibt verschiedene Typen von Metadaten, die hinsichtlich ihrer Art und Funktion unterschieden werden:
<style>
.table-clean {
  border-collapse: collapse;
  width: 100%;
  font-size: 15px;
}
.table-clean th {
  text-align: left;
  padding: 6px 6px;
  border-bottom: 1px solid #ccc;
  font-weight: bold;
}
.table-clean td {
  padding: 6px 6px;
  border-bottom: 1px solid #eee;
  vertical-align: top;
}
</style>

<table class="table-clean">
  <tr>
    <th>Metadatentyp</th>
    <th>Eigenschaften und Funktionen</th>
    <th>Beispiele</th>
  </tr>

  <tr>
    <td><strong>Deskriptive (inhaltliche) bzw. bibliographische Metadaten</strong></td>
    <td>Helfen beim Auffinden oder Verstehen einer Ressource und bieten inhaltliche Eingrenzung </td>
    <td>Titel, Autor, Beschreibung, Keywords, Publikationsdatum uvm. </td>
  </tr>

  <tr>
    <td><strong>Administrative Metadaten</strong></td>
    <td>
      Helfen bei der Verwaltung und langfristigen Sicherung der Daten<br><br>
      Unterarten:
      <ul>
        <li>Technische Metadaten</li>
        <li>Metadaten zur Erhaltung</li>
        <li>Rechtliche Metadaten</li>
      </ul>
    </td>
    <td>Dateityp und -größe, Speicherort, Erstellungsdatum, Provenance, Zugriffsrechte, Lizenzen uvm.</td>
  </tr>

  <tr>
    <td><strong>Strukturelle Metadaten</strong></td>
    <td>Beschreiben die Anordnung  und Hierarchie eines Objekts oder einer Sammlung, d. h. die Beziehung der einzelnen Teile zueinander </td>
    <td>Kapitelstruktur eines Buchs, sequentielle Abfolge eines Films, Verlinkungsstrukturen einer Website, Codelisten uvm.</td>
  </tr>

  <tr>
    <td><strong>Prozessmetadaten</strong></td>
    <td>Dokumentieren die Schritte und Methoden, die zur Entstehung und Verwendung von Daten angewendet werden</td>
    <td>Verarbeitungsschritte, Tools, Transformationen, Workflows, Versionsverlauf uvm.</td>
  </tr>
</table>
<br>

Nicht immer sind die einzelnen Metadaten-Kategorien klar voneinander zu trennen. So kann es beispielsweise Überlappungen zwischen Prozessmetadaten und administrativen Metadaten geben, wenn es um technische Beschreibungen wie Dateiformat, Erstellungsdatum oder Migration geht. Nichtsdestotrotz ist eine grundlegende Charakterisierung der Funktionen und Eigenschaften verschiedener Metadatentypen im Forschungsprozess sehr hilfreich.

(markup-sprachen)=
## Exkurs: Markup-Sprachen

Metadaten liegen oft in maschinenlesbarer Form vor – in sogenannten Markup-Sprachen. Dies unterstützt die Interoperabilität der Daten hinsichtlich Weiterverwendung und Austausch. 

```{admonition} Was sind Markup-Sprachen?
:class: hinweis
Markup-Sprachen (dt. Auszeichnungssprache) sind maschinenlesbare Sprachen. Sie strukturieren und formatieren Texte und Dateien, indem sie ihnen Eigenschaften - sogenannte `tags` - hinzufügen. Die bekannteste Markup-Sprache ist `HTML`.
```
Am häufigsten wird dabei die Markup-Sprache `XML` verwendet. Metadaten liegen dann als Datensatz in einem `XML`-Dokument vor.

```{figure} ../assets/03_metadaten/abb_k03_xml_beispiel.png
---
align: center
width: 90%
name: xml-beispiel
---
XML-Beispiel, © NISO
```

```{admonition} Wie funktioniert XML?
:class: hinweis, dropdown
XML nutzt definierte Elemente bzw. Tags, um anzugeben, welche Bedeutung den jeweils enthaltenen Werten zukommt. Elemente können auch andere Elemente enthalten. Ein XML-Dokument ist ähnlich aufgebaut wie eine Baumstruktur, beginnend mit einem Stammelement.
```
In den Digital Humanities hat sich die auf `XML` basierte Markup-Sprache `TEI` als gängiger Standard etabliert. `TEI` wurde gezielt an die Bedürfnisse geisteswissenschaftlicher Forschung angepasst.

```{admonition} Mehr Informationen zu XML & TEI
:class: seealso
* <a href="https://docs.nfdi4culture.de/lido-schulung/modul-xml-grundlagen" class="external-link" target="_blank">NFDI4Culture</a>
* <a href="https://libguides.exeter.ac.uk/digitalhumanities/tei" class="external-link" target="_blank">University of Exeter LibGuides</a>
* <a href="https://programminghistorian.org/en/lessons/encoding-texts-tei-1" class="external-link" target="_blank">Programming Historian</a>
```
Neben solchen spezifischen, auf Markup-Sprachen basierenden Strukturierungen von Metadaten, die in erster Linie für die Auszeichnung von Texten genutzt werden, spielen auch **allgemeine Metadatenstandards** eine wichtige Rolle. Im nächsten Kapitel gehen wir auf zwei gängige Standards ein. 





