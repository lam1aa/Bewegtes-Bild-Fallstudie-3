# Datenmanagementplan

Um einerseits die Organisation des FDMs zu bewerkstelligen und andererseits klare, nachvollziehbare Strukturen zu etablieren, empfiehlt es sich, einen sogenannten **Datenmanagementplan** (kurz: DMP) zu erstellen. In einem DMP können die bisher weitestgehend grob bzw. abstrakt zusammengefassten Phasen des Datenlebenszyklus systematisch dokumentiert und organisiert werden. 
Der DMP muss hierbei als ein "living document", also ein lebendiges Dokument, verstanden werden, denn sowohl die eigentliche Forschung selbst als auch das FDM sind komplex und (besonders bei Langzeitprojekten) hochdynamisch; selten verlaufen diese Prozesse linear. 
Im Wesentlichen sind DMPs von Menschen lesbare Dokumente, wobei es mittlerweile auch eine Reihe von Entwicklungen hin zu automatisierten und maschinenlesbaren Formaten gibt. 

## Inhalte eines DMPs

Die konkreten Inhalte eines DMPs sind nicht normiert, es gibt sowohl eine Reihe institutioneller Handreichungen und Vorlagen als auch digitale Werkzeuge, mit denen DMPs erstellt werden können. Für einen ersten Überblick fassen wir die wichtigsten Inhalte hier kurz zusammen:

```{figure} ../assets/02_forschungsdaten_fdm/abb_k02_dmp.png
---
align: center
width: 65%
name: Datenmanagementplan
---
Datenmanagementplan
```

<style>
.table-clean {
    border-collapse: collapse;
    width: 100%;
    font-size: 15px;
}
.table-clean th {
    text-align: left;
    padding: 8px 6px;
    border-bottom: 1px solid #ccc;
    font-weight: bold;
}
.table-clean td {
    padding: 8px 6px;
    border-bottom: 1px solid #eee;
    vertical-align: top;
}
</style>

<table class="table-clean">
  <tr>
    <th>Bereich</th>
    <th>Leitfragen / Beschreibung</th>
  </tr>
  <tr>
    <td><strong>Art der Daten</strong></td>
    <td>Welche Forschungsdaten fallen an (Primär- oder Sekundärdaten, Annotationen, Transkriptionen? Metadaten, Visualisierungen uvm.); werden Daten nachgenutzt? Und wenn ja: welche Lizenzen und Bedingungen gelten dafür?</td>
  </tr>
  <tr>
    <td><strong>Datengewinnung</strong></td>
    <td>Welche Methoden werden eingesetzt? Gibt es (ggf. rechtliche) Hürden bei der Datengewinnung? Welche Softwareversionen, Tools oder Geräte werden verwendet?</td>
  </tr>
  <tr>
    <td><strong>Datentypen</strong></td>
    <td>Formate, Datenmenge, Dateigrößen; werden offene und nachhaltige Formate verwendet (FAIR-Prinzipien)? Sind Konvertierungen notwendig?</td>
  </tr>
  <tr>
    <td><strong>Speicherung &amp; Speicherlösungen</strong></td>
    <td>Speicherplatz, Datenzugang, Speicherorte und Speicherdauer; gibt es tragbare Speicher? Werden lokale Speicher oder Cloud-Dienste genutzt? Werden Backups angelegt und wenn ja: welche Backup-Strategien werden entwickelt?</td>
  </tr>
  <tr>
    <td><strong>Datensicherheit</strong></td>
    <td>Verschlüsselung von Dateien und Speichersystemen, sichere Passwörter, Festlegung von Speicherfristen und ggf. Löschung von nicht mehr benötigter Daten, Zugangsbeschränkungen und -kontrollen,Verteilung von Zugriffsrollen, Einhaltung des Datenschutzes, Speicherung personenbezogener Daten innerhalb der EU</td>
  </tr>
  <tr>
    <td><strong>Qualitätssicherung</strong></td>
    <td>Welche Maßnahmen gibt es, um die Qualitätssicherung der Daten zu gewährleisten? Gibt es Validierungsroutinen?</td>
  </tr>
  <tr>
    <td><strong>Ressourcen</strong></td>
    <td>Bearbeitungsaufwand, Zeitplan, personelle, technische und finanzielle Kapazitäten, ggf. geplante Workshops oder Schulungen für Datenkompetenzen</td>
  </tr>
  <tr>
    <td><strong>Archivierung und Veröffentlichung</strong></td>
    <td>Wo werden die Daten langfristig archiviert? Werden die Daten veröffentlicht? Wenn ja: Wo und wie werden sie veröffentlicht? Welche Lizenzen werden vergeben? Werden die Daten in einem (lokalen) Repositorium abgelegt? Erhalten die Daten einen persistenten Identifier (z. B. DOI)?</td>
  </tr>
  <tr>
    <td><strong>Datenorganisation</strong></td>
    <td>Ordnerstrukturen, Benennungskonventionen für Dateien und Ordner, Versionierung (z.B. Semantic Versioning), Konsistenzregeln</td>
  </tr>
  <tr>
    <td><strong>Nachnutzungsszenarien/Umgang nach Projektende</strong></td>
    <td>Nachvollziehbare Dokumentationen, Datenberichte, Metadaten, Kontextualisierung der Daten, Herkunft und Beschreibung der Daten; sind Daten ausreichend dokumentiert, damit Dritte sie verstehen können?</td>
  </tr>
  <tr>
    <td><strong>Rechtliche Aspekte</strong></td>
    <td>Einhaltung des Datenschutzes, Umgang mit personenbezogenen Daten, Lizenzbedingungen nachgenutzter Daten, Materialrechte (z.B. von Bildern, Videos oder Audiofiles) bzw. urheberrechtliche Aspekte, Einwilligungen für (z.B. für Interviews)</td>
  </tr>
</table>
<br>

Das Erstellen eines DMPs hilft dabei, im Vorfeld systematisch über Erzeugung, Nutzung und Einbindung von Forschungsdaten zu reflektieren. Gleichzeitig wird Transparenz über Datenerzeugung und -verwendung geschaffen – einerseits für die Planung innerhalb des Projekts, andererseits ebenso für die Kommunikation mit der Forschungseinrichtung oder Förderinstitution 
(z.B. <a href="https://www.dfg.de/de" class="external-link" target="_blank">DFG</a> oder <a href="https://www.bmftr.bund.de/DE/Home/home_node.html" class="external-link" target="_blank">BMFTR</a>). 

Um den Einstieg zu erleichtern, hat die die HU Berlin hierzu ein kurzes Online-Video erstellt und die wichtigsten Punkte zusammengefasst.

<div style="max-width:500px; margin:2rem 0;">

  <video id="ref_91"
         controls
         preload="none"
         style="width:100%; height:auto;"
         poster="https://rs.cms.hu-berlin.de/dataman/plugins/api_resource/?ref=91&amp;key=3QUcTW8DyUNYbF_08xZQ-Q93zH0IHkE-STHwTP3S32mS2l1ZWuyPviKuHFv4tTHiZtIXZg,,&amp;preview=1&amp;skey=430ebe346ff118895412774462694765">
  </video>

  <div style="margin-top:0.6rem; font-size:0.85rem; text-align:center;">
    <a href="https://rs.cms.hu-berlin.de/dataman/pages/view.php?ref=91#"
       target="_blank" rel="noopener">
       Was sind Datenmanagementpläne?
    </a>
    von Kerstin Helbig et&nbsp;al. (HU Berlin), © CC BY 4.0
  </div>

</div>

Ein Beispiel dafür, wie ein ausgearbeiteter DMP aussehen kann, findet sich im Kapitel [Aufbereitung & Anreicherung filmwissenschaftlicher Daten](../05_aufbereitung_anreicherung/informationen_datenset.md) - exemplarisch dargestellt anhand der Daten des SFB-Teilprojekts.

```{admonition} Weiterführende Links zum Thema Datenmanagementplan, Tools & Vorlagen
:class: seealso
**Institutionelle DMP-Vorlagen** 
* <a href="https://www.fu-berlin.de/sites/forschungsdatenmanagement/materialien/handreichungen/dmp/index.html" class="external-link" target="_blank">FU Berlin</a>
* <a href="https://www.cms.hu-berlin.de/de/dl/dataman/mitdmparbeiten/dmp_erstellen/hinweise" class="external-link" target="_blank">HU Berlin</a>

**DMP-Tools**
* <a href="https://rdmo.aip.de/" class="external-link" target="_blank">RDMO</a>
* <a href="https://www.tu.berlin/ub/szf/tipps-tools/planen/tool-tub-dmp" class="external-link" target="_blank">TUB-DMP</a>
* <a href="https://argos.openaire.eu/home" class="external-link" target="_blank">ARGOS</a>
* <a href="https://ds-wizard.org/" class="external-link" target="_blank">Data Stewardship Wizard</a>

**Weiterführende Informationen**
* <a href="https://forschungsdaten.info/themen/informieren-und-planen/datenmanagementplan/" class="external-link" target="_blank">forschungsdaten.info</a>
* <a href="https://www.tu.berlin/ub/szf/nachrichtendetails/leitfaden-zur-erstellung-eines-datenmanagementplans-verfuegbar" class="external-link" target="_blank">Leitfaden TU Berlin</a>
* <a href="https://libereurope.eu/working-group/research-data-management/plans/" class="external-link" target="_blank">LIBER Research Data Management Working Group</a>
```