# Systemd.path
Beispiele für Systemd Path-Units

## Ein Path-Unit für Backups nutzen

Kopieren Sie die Dateien "backup.path" und "backup.service" in Ihr Home-Verzeichnis in den Ordner ".config/systemd/user". Passen Sie die Pfade in den Dateien für Ihre Zwecke an.

Öffnen Sie ein Terminal und führen Sie die folgenden beiden Befehlszeilen aus:
```
systemctl --user enable backup.path
systemctl --user start backup.path
```
Das Service-Unit "backup.service" muss nicht aktiviert oder gestartet werden. Systemd startet das zum Path-Unit gehörende Service-Unit mit dem gleichen Basisnamen automatisch.

Wenn Sie jetzt unter "~/Dokumente/Workdir" eine Datei neu erstellen oder ändern, erstellt rsync ein Backup des Ordners.

## Konfiguration ohne administrative Rechte ändern

Kopieren Sie die Dateien "tuxedo_keyboard.path" und "tuxedo_keyboard.service" aus dem Ordner "tuxedo_keyboard" mit root-Rechten in den Ordner "/etc/systemd/system". Die Datei "tuxedo_keyboard.sh" kopieren Sie in den Ordner "/root". Die Datei "tuxedo_keybord.ini" kopieren Sie in Ihr Home-Verzeichnis.

Aktivieren und starten Sie das Path-Unit:
```
sudo systemctl enable tuxedo_keyboard.path
sudo systemctl start tuxedo_keyboard.path
```
Sie können jetzt in der Datei "tuxedo_keybord.ini" Werte ändern, tragen Sie beispielsweise statt "color=GREEN" den Wert "color=RED" ein (Großschreibung beachten). Die Farbe der Tastatur-LEDs ändert sich sofort.

Das Beispielprogramm tuxedo_keyboard für ein Tuxedo Polaris 15 finden Sie unter https://github.com/Myria-de/tuxedo_keyboard. Laden Sie das Programm aus dem Ordner "bin" herunter.


