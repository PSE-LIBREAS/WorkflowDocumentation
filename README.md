# WorkflowDocumentation

## 5 Mai 2021

- Organisation PSE-LIBREAS erstellt
- LIBREAS Repo geforked
- erste Durchsicht des Repos
- Lagebesprechung zu den Themen:
  - [Problemaufriss](Problemaufriss.md)
  - Anforderungsanalyse
  - [Zielstellung](Zielstellung.md)

## 12 Mai 2021

Frage: Lässt sich die Aktualisierung der Bibliographie automatisieren? Sprich: dynamisches Laden der Seite zum aktuell halten.  
Frage: Wie können wir lokal entwickeln? Müssen wir einen Server (localhost), evtl node script, schreiben oder wie läuft es?  
Frage: Existiert ein html Grundgerüst resp. Template?  
Frage: Kompartibilität von jekyll und ruby in Erfahrung bringen.

- [Linksammlung](LinkSammlung.md) erstellt
- Libreas Website erfolgreich geklont und via pages veröffentlicht unter: https://pse-libreas.github.io
- CNAME file umbenannt in CNAME_ignore -- Achtung rückgängig machen!!!
  - Grund: Warning Mail durch GitHub:
    > The page build completed successfully, but returned the following warning for the `master` branch: 

    > The CNAME `libreas.eu` is already taken. Check out https://docs.github.com/articles/troubleshooting-custom-domains#cname-errors for more information. 

    > For information on troubleshooting Jekyll see:

    > https://docs.github.com/articles/troubleshooting-jekyll-builds

    > If you have any questions you can submit a request at https://support.github.com/contact?repo_id=364520188&page_build_id=252739119
- Ordner für die Bibliografie anlegen und erste Schritte
- config.yml Datei in source gefunden: Ist das der richtige Ort um jekyll-scholar plugin zu laden?

## 19 Mai 2021

Folie für den [Pitch](https://docs.google.com/presentation/d/1a3fzjT55lzHuVVqnqHDQkSbnFN5oSHKIMs2XqHMaNs4/edit?usp=sharing
) erstellen  
BrainStorming zur Anforderungsanalyse:  
  
- Wo soll die Bibliographie in der Seitenleiste (Navigation) platziert sein?  
- Welche Funktionalitäten bietet uns jekyll-scholar und was können wir an Funktionalitäten zusätzlich implementieren?

## 26 Mai 2021

Erste Versuche die Bibliographie zu integrieren:

- jekyll-scholar als plugin integrieren (config.yml)
- _bibliography Ordner in source angelegt

Erste Begegnung mit GitHub Actions:

- [Martino Pilia](https://martinopilia.com/posts/2020/02/22/migration.html)


Frage: Wie würde CI/CD Sinn machen... in welchen Intervallen könnten die Runner arbeiten?

## 27 Mai 2021 (Treffen mit Najko und Michaela)

Die navbar findet sich unter: source/includes/custom  
ruby Abhängigkeiten finden sich in gemfile.lock  
  
Aufgabe: neues jekyll (upgrade) aufstetzen und an Libreas (fonts und colors; lanyon) anpassen, scholar installieren und erste Versuche bzügl github action unternehmen.

## 02 Juni 2021

Fragen:
1) Wie groß ist das Repo (Speicherplatz für lokale Instanz)? 
2) Dependencies und Kompatibilität?
3) Dokumentation des Gesamtsystems?
4) Wo liegt der GitHub pages Gem file?


## 09 Juni 2021

- Jekyll getting started [Tutorial](https://www.youtube.com/watch?v=iWowJBRMtpc) geguckt  
- Ordnerstruktur überarbeitet, alles was jekyll braucht, muss im root folder liegen  
- Libreas .css eingefügt und 'theme-base-wes' ins body tag eingefügt

## 16 Juni 2021

- Versuch der Anpassung der Sidebar, vorerst hard gecoded - muss später als Template angepasst werden  
- Versuch der Anpassung der config.yml  
- Versuch der Übernahme des Headers  
- Versuch der Übernahme des Footers  
- Übernahme des Impressums  
- Erster Versuch eine gh-action zu implementieren, hierbei sind alle unsere Dateien verloren gegangen...  
  
Aufgabe: Verstehen wie der build, den Naiko auf seiner Maschine macht, funktioniert.

## 23 Juni 2021

- UNDO: wir holen unsere Dateien über 'git reset --hard <commit>' zurück.
- Neuer Versuch eine gh-action zu implementieren
  - Erfolgreich aufgesetzt!  
  - Auf gh-pages dürfen keine Dokumente/Dateien liegen die im weiteren noch benötigt werden.  
  - Die action/source muss auf main liegen, sonst sind diese nach einem push nicht mehr vorhanden.  
  - Die css Dateien werden noch nicht eingebunden
  
Aufgabe: Das Repo visualisieren, um verständlich zu machen was wo liegt und wie gearbeitet wird.  
Frage: Wie muss die Ordnerstruktur beschaffen sein, wo müssen die Quelldateien liegen, wo müssen die css Dateien liegen??  
  
## 30 Juni 2021
  
- Versuche der Integration diverser Inhalte (Autorinnen etc)  
- Einbinden der css Datei
- Versuch jekyll-scholar einzubinden
- Versuch ein theme einzubinden
- löschen von `| absolute_url` in `_includes/head.html`
- Theme einbinden nach Löschvorgang erfolgreich
  
## 02 Juli 2021

- Löschen des gh-pages gems aus dem Gemfile
- upgrade auf Jekyll v 4.2 und jekyll-scholar v 7.0
- Erstellen eines `_plugins` Verzeichnisses
- Erstellen einer jekyll-scholar.rb plugin Datei
- kopieren von Code zur Darstellung von URLs und DOIs als klickbare Links in der Bibliographie
- Action läuft und Links werden dargestellt, allerdings DOI nicht richtig
- evtl. Regex anpassen oder csl?

## 07 Juli 2021
  
- Einbindung diverser plugins im Gemfile (pygments.rb, rubypants, octopress-quote-tag, titlecase) 
- Überlegungen zur Ordnerstruktur im Repo resp. der Website (alle vergangenen Ausgaben sollen in einem Archiv-Ordner abgelegt werden usw.)
- Wir beginnen mit der Dokumentations für die Übergabe des Repos
  
## 10 Juli 2021
  - Styling der Bibliographie
  - über html template und Javascript in Anlehnung an [sbryngelson](https://github.com/sbryngelson/sbryngelson.github.io) und einige der [issues](https://github.com/inukshuk/jekyll-scholar/issues?page=1&q=is%3Aissue+is%3Aclosed+bib) auf dem jekyll-scholar repo, toggable Buttons für Abstract und BibTeX erstellt
  - dazu Javascript im template eingefügt und im lanyon css unter `/* Bibliography */` noch ein paar sachen eingefügt
  - evtl. könnten wir auch folgendes nochmal für die DOIs ausprobieren, anstatt die im url feld zu hinterlegen [issue330](https://github.com/inukshuk/jekyll-scholar/issues/330)
  
## 11. Juli 2021 
  
  - Icons werden über zusätzliche scss files eingebunden, müssen wir unsere css files in scss ändern? 

## 12. Juli 21
  
  - ordered lists numerierung unterdrückt (list-style: none) in poole
  -scss ordner eingefügt und versucht zu verlinken
  
