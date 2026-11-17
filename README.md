# AlphaTerm SLL Parser – Installation und Updates

Hier liegen die Installationspakete (MSI) des **AlphaTerm SLL Parsers**, eines Diagnose-Terminals für das
AlphaCom Simple Link Layer (SLL) Protokoll (Zenitel/Stentofon AlphaCom bzw. ICX).
Installierte Parser prüfen beim Start über dieses Repository, ob eine neuere Version verfügbar ist.

## Erstinstallation

1. Die neueste Version öffnen: **[Releases → Latest](https://github.com/Etzel1956/AlphaTerm-Releases/releases/latest)**
   (ein GitHub-Konto ist nicht nötig).
2. Unter **Assets** die Datei **`AlphaTermSLLParser-<Version>.zip`** herunterladen (empfohlen).
   Alternativ direkt das MSI `AlphaTermSLLParser-<Version>.msi` – das wird von Browsern aber häufiger
   blockiert (siehe unten).
3. ZIP entpacken (Rechtsklick → **Alle extrahieren…**), dann das enthaltene MSI per Doppelklick starten
   und dem Assistenten folgen.
   Vorgegebener Zielordner: `C:\Program Files (x86)\Scanvest\AlphaTerm SLL Parser` (änderbar).
4. Starten über das Startmenü oder die Desktop-Verknüpfung **„AlphaTerm SLL Parser“**.

### Download vom Browser blockiert?

Das Installationspaket ist (noch) nicht digital signiert und wird selten heruntergeladen. Deshalb blockieren
Browser den Download manchmal („wird nicht häufig heruntergeladen“, „könnte Ihr Gerät gefährden“).

- **Microsoft Edge:** Downloads öffnen (**Strg+J**) → beim blockierten Eintrag **„…“ → „Behalten“** →
  **„Mehr anzeigen“ → „Trotzdem behalten“**.
- **Google Chrome:** Downloads öffnen (**Strg+J**) → **„Trotzdem herunterladen“**.

Das ZIP ist davon seltener betroffen als das MSI.

### Mögliche Hinweise bei der Installation

- **Windows-SmartScreen** („Der Computer wurde durch Windows geschützt“): Das MSI ist nicht digital signiert.
  Auf **„Weitere Informationen“ → „Trotzdem ausführen“** klicken. Fragt der Browser beim Download nach,
  **„Behalten“** wählen.
- **Benutzerkontensteuerung:** Die Installation braucht Administratorrechte, weil das Programm für alle
  Benutzer des Rechners installiert wird.
- **.NET Framework 4.8** wird vorausgesetzt. Windows 10 ab Version 1903 und Windows 11 haben es bereits.
  Fehlt es, bricht das Setup mit einem Hinweis ab; dann zuerst
  [.NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48) installieren.

## Updates

- Beim Start prüft der Parser, ob hier eine neuere Version veröffentlicht wurde, und fragt nach:
  **Jetzt installieren**, **Diese Version überspringen** oder **Später**.
- Von Hand geht das über das Menü **Konfiguration → Nach Updates suchen…**.
- Bei „Jetzt installieren“ wird das MSI heruntergeladen und geprüft (SHA256), der Parser beendet sich
  (die aktuelle Konfiguration wird dabei gespeichert) und die Installation startet. Die alte Version wird
  automatisch ersetzt; Einstellungen und Konfigurationen bleiben erhalten.
- **Rechner ohne Internet:** Die Prüfung bricht still ab. Für ein Update das neue MSI wie bei der
  Erstinstallation herunterladen und ausführen – die vorhandene Version wird ersetzt.

Die automatische Update-Prüfung gibt es ab Version **2.1.3.6**. Ältere Versionen einmal von Hand aktualisieren.

## Einstellungen

Einstellungen, F-Tasten und RCI-/RCO-Beschriftungen liegen im Benutzerordner unter
`%LOCALAPPDATA%\Scanvest Deutschland GmbH\SVTerm` (z. B. `sllp_config.xml`, `FKeys.xml`). Benannte Konfigurationen
(Menü **Konfiguration → Speichern unter…**) werden standardmäßig im Unterordner `Konfigurationen` abgelegt.

## Hinweis

Das Winsock-Testfenster (`Server`) benötigt das ActiveX-Control `mswinsck.ocx`, das vom Setup nicht
registriert wird. Für alle anderen Funktionen ist es nicht erforderlich.
