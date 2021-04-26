# FritzCall
Das FritzCall-Plugin zeigt Anrufe, die auf einer FRITZ!Box Fon ankommen oder über diese rausgehen, auf dem Fernseher an.(*) Darüberhinaus bietet es noch Folgendes an:

- War die Dreambox im Standby wird optional eine Zusammenfassung der Anrufe bei Wiedereinschalten angezeigt.
- Unbekannte Nummern werden versucht über diverse Websites aufzulösen.
- Es hat ein internes Telefonbuch, in dem gefundene Nummern gespeichert werden können.
- Das Telefonbuch der FRITZ!Box Fon kann eingelesen und benutzt werden.
- Dieses interne Telefonbuch kann bearbeitet werden.
- Die Anzeige kann auf bestimmte eigene Nummern eingeschränkt werden
- Es wird ein Anruferbild angezeigt, wenn ein entsprechendes Bild (PNG mit 256 Farben) mit dem Namen oder der Nummer des Anrufers im Verzeichnis <Lokation des Telefonbuchs>/FritzCallFaces existiert

(*) Dazu muss an einem Telefon, dass direkt an der FRITZ!Box Fon angeschlossen ist, die Folge #96*5* eingeben und gewählt werden. Des weiteren muss "Zugriff für Anwendungen zulassen" in der FRITZ!Box aktiviert werden (Heimnetzübersicht/Netzwerkeinstellungen). Dokumentation und Screenshots finden sich hier.

Die ipk-Datei installiert man auf der Box mit ```opkg install <Dateiname>```.
Unter Umständen muss man vorher noch die existierende Installation entfernen mit ```opkg remove enigma2-plugin-extensions-fritzcall```.

Wenn ihr nicht wollt, dass der nächste FW-Update das Plugin überschreibt ```opkg flag hold enigma2-plugin-extensions-fritzcall```.

Ansonsten Installation eines tar-Ball. Installation (am besten über eine bestehende Installation):

- Datei auf die Dreambox nach /tmp spielen.
- Auf der Dreambox dann: "cd /; tar xvzf /tmp/FritzCall.tar.gz"
- Falls noch nicht installiert, twisted-web, python-json und python-html installieren
- Dann Enigma neu starten.
- In der Konfiguration unbedingt die Firmware-Version richtig einstellen!
- Die Rückwärtssuche wird gesteuert von der Datei reverselookup.xml im Plugin-Verzeichnis. Da sich diese meist öfter ändert als das Plugin, stelle ich sie, wenn nötig, separat zur Verfügung. Eine neue Version braucht nur in das Plugin-Verzeichnis /usr/lib/enigma2/python/Plugins/Extensions/FritzCall kopiert zu werden. Das Plugin sollte eine neue Version automatisch erkennen und diese neu einlesen. Die aktuellste Version stelle ich zukünftig hier zur Verfügung.

DrMichael

PS:
- Die aktuelle Version speichert das interne Telefonbuch nun in Phonebook.json
- Wenn Logging auf DEBUG steht, werden u.U. Dateien mit sensiblen Informationen unter "/tmp/Fritz..." angelegt.
- Die neueren Versionen speichern das Passwort verschlüsselt. Daher kann es zu Fehlermeldung bzgl. Benutzer/Passwort kommen. Dann Passwort neu eingeben in der Konfiguration.
- Um alle weiteren Fragen danach zuvorzukommen: Nein, es wird kein Timeshift/Anhalten des Bildes bei Anruf geben analog Mute.
