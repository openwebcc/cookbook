# Neues Online Repository bei github.com erstellen

## Zutaten

- Browser & Visual Studio Code
- ein Account bei <https://github.com/>
- wir nehmen `username` als Accountname im Rezept

## Ablauf

- im Browser

    - einloggen als `username` bei <https://github.com/>
    - ein neues *public* Repo `test` anlegen
    - beim *Quick setup* die HTTPS Adresse `https://github.com/username/test.git` des Repos kopieren

- in Visual Studio Code

    - *View / Command Palette* oder *F1* oder *STRG+SHIFT+P*
    - *Git: Clone* wählen, die GIT-Adresse des Repos in das Inputfeld kopieren und *ENTER* drücken
    - die Repository Location (z.B. `Desktop`) auswählen und mit *Open* öffnen
    - eine neue, minimale `index.html` Datei mit folgendem Inhalt erstellen

       ```html
        <h1>Hallo Test!</h1>
       ```

    - im Source Control Bereich *Stage Changes* für `index.html` und *Commit* ausführen
    - beim Menü im Source Control Bereich *Push* wählen
    - gegebenenfalls wird beim *Push* zum Login bei <https://github.com/> aufgefordert - einfach den Anweisungen folgen
    - nach erfolgreichem *Push* wird `index.html` an <https://github.com/> gesendet

- zurück im Browser

    - <https://github.com/username/test> ansteuern und neu laden
    - `index.html` ist jetzt im Repo `test` sichtbar
    - *Settings* / *Pages* auswählen
    - unter *Build and deployment*  bei *Branch* `main` auswählen und speichern
    - nach kurzer zeitlicher Verzögerung ist das Repo `test` unter dieser URL online zugänglich:

        ```text
        https://username.github.io/test/
        ```

___
[Inhaltsverzeichnis](https://openwebcc.github.io/cookbook/index)
