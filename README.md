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

- Libreas Website erfolgreich geklont und via pages veröffentlicht unter: https://pse-libreas.github.io
- CNAME file umbenannt in CNAME_ignore -- Achtung rückgängig machen!!!
  - Grund: Warning Mail durch GitHub:
    > The page build completed successfully, but returned the following warning for the `master` branch: 

    > The CNAME `libreas.eu` is already taken. Check out https://docs.github.com/articles/troubleshooting-custom-domains#cname-errors for more information. 

    > For information on troubleshooting Jekyll see:

    > https://docs.github.com/articles/troubleshooting-jekyll-builds

    > If you have any questions you can submit a request at https://support.github.com/contact?repo_id=364520188&page_build_id=252739119
