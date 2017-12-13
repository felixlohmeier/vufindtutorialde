# Konfiguration der Facetten

Die Facetten innerhalb von VuFind basieren auf einzelnen Indexfeldern im Solr-Index. Die Anzeige und das Verhalten der Facetten in VuFind werden durch Einstellungen in der Datei `facets.ini` gesteuert.

## Konfigurationsdatei facets.ini

Öffnen Sie die Datei `facets.ini` aus Ihrem lokalen Konfigurationsverzeichnis mit einem Text Editor.

Der mit `[Results]` beginnende Abschnitt enthält die Facetten. Jede Zeile enthält einen Eintrag in der Form

```
SolrIndexName = Anzeigename der Facette
```

Der Anzeigename selbst ist in englischer Sprache und wird innerhalb von VuFind übersetzt.

Einträge mit einem Semikolon am Beginn der Zeile sind ausgeblendet und werden nicht dargestellt.

Die Reihenfolge innerhalb von VuFind entspricht der Reihenfolge innerhalb des Abschnitts `[Results]`. Möchten Sie die Facetten in einer anderen Reihenfolge anzeigen lassen, sortieren Sie die entsprechenden Zeilen um.

## Ausblenden von Facetten

Blenden Sie die Facetten für Institution, Gebäude, Signatur (callnumber-first), Genre, Ära und Region aus, indem Sie ein Semikolon vor den jeweiligen Eintrag schreiben:

* `;institution = Institution`
* `;building = Library`
* `;callnumber-first = "Call Number"`
* `;genre_facet = Genre`
* `;era_facet = Era`
* `;geographic_facet = Region`

## Hinzufügen von Facetten

Fügen Sie eine Facette für den Bestand als erste Facette hinzu:

* `collection = Collection`

## Zwischenstand

Die Änderungen an den Facetten werden sofort auf der Webseite wirksam:

![](media/08/image2.png)

## Übersetzung des Inhalts von Facetten

Grundsätzlich können die Inhalte aller Facetten übersetzt werden.

Zunächst müssen Sie definieren, dass eine bestimmte Facette übersetzt werden soll. Dies geschieht durch einen Eintrag weiter hinten in der Datei (etwa Zeile 176), der mit `translated_facets[] =` beginnen muss und dem der Name des Indexfeldes folgen muss, auf welchem die Facette basiert.

Für die Sprache wäre dies also

```
translated_facets[] = language
```

Nun müssen Sie alle Inhalte identifizieren, welche in der Facette erscheinen könnten. Für die Sprache sind dies die Bezeichnungen der jeweilige Sprache auf Englisch.

Gehen Sie analog zum Kapitel „Übersetzungen“ in der Anleitung für die allgemeinen Einstellungen vor und tragen Sie die gewünschten Übersetzungen in Ihre lokale Sprachdatei ein. Für die häufigsten sechs Sprachen aus den Daten des Testimportes sind diese Einträge erforderlich:

```
German = "Deutsch"
English = "Englisch"
French = "Französisch"
Spanish = "Spanisch"
Italian = "Italienisch"
Polish = "Polnisch"
```

---------

**!!!** Achten Sie unbedingt darauf, keine typographischen Anführungszeichen zu verwenden. Diese werden als Teil der Übersetzung angesehen.

--------- 

Die Facette "Sprache" sollte anschließend wie folgt aussehen:

![](media/08/image7.png)

Damit die Änderung der Sprachdatei wirksam wird, müssen Sie den Cache für die Übersetzung leeren (vgl. Kapitel Übersetzung).

## Quellen

VuFind Dokumentation: Facets (Stand: 21.12.2015)
<https://vufind.org/wiki/configuration:facets>

VuFind Dokumentation: Adding Facets. (Stand: 26.1.2016)
<https://vufind.org/wiki/indexing:adding_facets>