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


## 09 Juni

- Jekyll getting started [Tutorial](https://www.youtube.com/watch?v=iWowJBRMtpc) geguckt  
- Ordnerstruktur überarbeitet, alles was jekyll braucht, muss im root folder liegen  
- Libreas .css eingefügt und 'theme-base-wes' ins body tag eingefügt
