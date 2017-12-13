# Konfiguration von Kataloganreicherungen

In VuFind lassen sich folgende Elemente der Kataloganreicherung nutzen und konfigurieren:

* Titelbilder (Book Covers)
* Rezensionen (Item Reviews)
* Auszüge (Item Excerpts)
* Buchvorschau (Book Previews)

Die Einstellungen für die Kataloganreicherungen finden Sie im Abschnitt `[Content]` der `config.ini`.

--------- 

**!!!**   Vor der Nutzung von Google Book Search sollten Sie sich mit den Nutzungsbedingungen unter <https://developers.google.com/books/branding> vertraut machen.

---------

## Titelbilder (Book Covers)

**Standardeinstellungen (deaktiviert)**

* `;coverimages = Syndetics:MySyndeticsId,Amazon:MyAccessKeyId,Booksite,LibraryThing:MyLibraryThingId,Google,OpenLibrary,Summon:MySerialsSolutionsClientKey,Contentcafe:MyContentCafeID,LocalFile:PathToFile`
* `;makeDynamicCovers = true`

**Empfohlene Einstellungen**

* `coverimages = Booksite,Google,OpenLibrary`
* `makeDynamicCovers = grid`

Ohne Anmeldung frei zur Verfügung stehen Coverbilder von Booksite, Google und Open Library. Sofern Sie über ein Konto eines der anderen unterstützen Dienste verfügen, können Sie diesen Dienst hinzufügen. Sie müssen dabei Ihre jeweilige ID angeben.

Wollen Sie beispielsweise Library Thing ergänzen, sieht die Konfiguration so aus:

```
coverimages = Booksite,Google,OpenLibrary,LibraryThing:MyLibraryThingId
```

Das Wort „MyLibraryThingId“ muss durch Ihre ID ersetzt werden.

Die Einstellung „makeDynamicCovers = grid“ ist empfehlenswert, wenn beispielsweise viel Spezialliteratur im Index verzeichnet ist. Deren Coverbilder stehen im Regelfall nicht bei den gewählten Anbietern zur Verfügung. Durch die Einstellung generiert VuFind dynamisch Titelbilder für alle Titel, deren Titelbild bei keinem der Anbieter vorhanden ist. Funktionen wie der Reiter „Ähnliche Einträge“ in der Einzeltrefferanzeige sind dadurch angenehmer zu benutzen.

Mit dem Wert „grid“ werden Titelbilder generiert, welche den Titel und den Namen des Autors enthalten. Mit dem alternativen Wert „solid“ enthalten die generierten Titel den ersten Buchstaben des Titels.

**makeDynamicCovers = grid**

![](media/09/image4.png)

**makeDynamicCovers = solid**

![](media/09/image5.png)

## Rezensionen (Item Reviews)

**Standardeinstellung (deaktiviert)**

```
;reviews = Syndetics:MySyndeticsId,SyndeticsPlus:MySyndeticsID,
AmazonEditorial:MyAccessKeyId,Amazon:MyAccessKeyId,Booksite,Guardian:MyGuardianKeyId
```

**Empfohlene Einstellung**

```
reviews = Booksite
```

Sofern Sie über ein Konto für die Amazon Web Services verfügen, können Sie dieses zusätzlich angeben. Die Konfiguration sähe dann so aus:

```
reviews = Booksite,Amazon:MyAccessKeyId
```

Das Wort „MyAccessKeyId“ muss durch Ihre ID ersetzt werden.

Die Rezensionen werden in der Einzeltrefferanzeige im Reiter „Rezensionen“ angezeigt.

## Auszüge (Item Excerpts)

**Standardeinstellung (deaktiviert)**

```
;excerpts = Syndetics:MySyndeticsId,SyndeticsPlus:MySyndeticsId
```

Auszüge stehen momentan nur von Syndetics zur Verfügung. Sofern Sie dort über ein Konto verfügen, können Sie die obenstehende Einstellung aktivieren und statt „MySyndeticsId“ Ihre ID hinterlegen.

## Buchvorschau (Book Previews)

**Standardeinstellungen (deaktiviert)**

* `;previews = Google,OpenLibrary,HathiTrust`
* `;GoogleOptions['link']  = full,partial`
* `;OpenLibraryOptions  = full,partial`

**Empfohlene Einstellung**

* `previews = Google,OpenLibrary`
* `GoogleOptions['link']  = full,partial`
* `OpenLibraryOptions  = full,partial`

Mit `GoogleOptions['link']` stellen Sie ein, dass der Link zu Google Books innerhalb der Trefferliste und der Einzeltrefferanzeige erscheint. Die Einstellung `OpenLibraryOptions` ist vergleichbar mit der für Google Books. Sofern Sie nur für vollständig beim jeweiligen Anbieter verfügbare Bücher den Link anzeigen lassen möchten, setzen Sie die Einstellung auf `full`. Mit `full,partial` wird auch für unvollständig verfügbare Bücher der Link angezeigt.

## Ergebnis

Blättern Sie ein wenig durch die Trefferliste, da nicht für alle Testdaten Cover und weitere Informationen vorhanden sind. So könnte es aussehen:

![](media/09/image6.png)

## Quellen

VuFind Dokumentation: Use of External Content (Stand: 21.12.2015)
<https://vufind.org/wiki/configuration:external_content>

VuFInd Dokumentation: Book Previews (Stand: 21.12.2015)
<https://vufind.org/wiki/configuration:book_previews>