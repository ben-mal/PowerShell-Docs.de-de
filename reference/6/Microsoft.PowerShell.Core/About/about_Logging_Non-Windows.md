---
description: PowerShell protokolliert interne Vorgänge von der Engine, den Anbietern und den Cmdlets.
keywords: powershell
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_non-windows?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging_Non-Windows
ms.openlocfilehash: 402c59f839de4a2b16e2abde29e1e9cfa6be6fa7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221511"
---
# <a name="about-logging-non-windows"></a>Informationen zur Protokollierung nicht-Windows

## <a name="short-description"></a>Kurze Beschreibung

PowerShell protokolliert interne Vorgänge von der Engine, den Anbietern und den Cmdlets.

## <a name="long-description"></a>Lange Beschreibung

PowerShell protokolliert Details von PowerShell-Vorgängen. PowerShell protokolliert z. b. Vorgänge wie das Starten und Beenden der-Engine sowie das Starten und Beenden von Anbietern. Außerdem werden Details zu PowerShell-Befehlen protokolliert.

Der Speicherort von PowerShell-Protokollen hängt von der Zielplattform ab. Unter **Linux** können PowerShell-Protokolle für **syslog** und **rsyslog. conf** verwendet werden. Weitere Informationen finden Sie auf den lokalen Seiten des Linux-Computers `man` . Unter **macOS** wird das **os_log** Protokollierungs System verwendet. Weitere Informationen finden Sie unter [os_log Developer-Dokumentation](https://developer.apple.com/documentation/os/os_log).

## <a name="viewing-powershell-log-output-on-linux"></a>Anzeigen der PowerShell-Protokoll Ausgabe unter Linux

PowerShell-Protokolle für **syslog** unter Linux und alle Tools, die häufig zum Anzeigen von **syslog** -Inhalten verwendet werden, können verwendet werden.

Das Format der Protokolleinträge verwendet die folgende Vorlage:

```
TIMESTAMP MACHINENAME powershell[PID]: (COMMITID:TID:CID)
  [EVENTID:TASK.OPCODE.LEVEL] MESSAGE
```

|Feld        |BESCHREIBUNG                                             |
|-------------|--------------------------------------------------------|
|`TIMESTAMP`  |Ein Datum/Uhrzeit-Zeitpunkt, zu dem der Protokolleintrag erstellt wurde.            |
|`MACHINENAME`|Der Name des Systems, auf dem das Protokoll erstellt wurde.      |
|`PID`        |Die Prozess-ID des Prozesses, der den Protokolleintrag geschrieben hat. |
|`COMMITID`   |Die `git commit` ID oder das Tag, das zum Erstellen des Builds verwendet wird.   |
|`TID`        |Die Thread-ID des Threads, der den Protokolleintrag geschrieben hat.   |
|`CID`        |Der hexadezimale Kanal Bezeichner des Protokoll Eintrags.            |
|             |10 = Operational, 11 = analytische                         |
|`EVENTID`    |Der Ereignis Bezeichner des Protokoll Eintrags.                  |
|`TASK`       |Der Task Bezeichner für den Ereignis Eintrag.                 |
|`OPCODE`     |Der Opcode für den Ereignis Eintrag.                          |
|`LEVEL`      |Die Protokollebene für den Ereignis Eintrag.                       |
|`MESSAGE`    |Die Meldung, die dem Ereignis Eintrag zugeordnet ist.             |

> [!NOTE]
> `EVENTID`, `TASK` , `OPCODE` und `LEVEL` sind die gleichen Werte, die bei der Protokollierung im Windows-Ereignisprotokoll verwendet werden.

### <a name="filtering-powershell-log-entries-using-rsyslog"></a>Filtern von PowerShell-Protokoll Einträgen mithilfe von rsyslog

Normalerweise werden PowerShell-Protokolleinträge in den Standardwert `location/file` für **syslog** geschrieben. Allerdings ist es möglich, die Einträge an eine benutzerdefinierte Datei umzuleiten.

1. Erstellen Sie eine conf für die PowerShell-Protokoll Konfiguration, und geben Sie eine Zahl an, die kleiner als 50 (für `50-default.conf` ) ist, z `40-powershell.conf` . b.. Die Datei sollte unter platziert werden `/etc/rsyslog.d` .

1. Fügen Sie der Datei den folgenden Eintrag hinzu:

   ```
   :syslogtag, contains, "powershell[" /var/log/powershell.log
   & stop
   ```

1. Stellen Sie sicher, dass `/etc/rsyslog.conf` die neue Datei enthält. Häufig wird eine generische include-Anweisung verwendet, die wie folgt aussieht:

   `$IncludeConfig /etc/rsyslog.d/*.conf`

   Wenn dies nicht der Fall ist, müssen Sie eine include-Anweisung manuell hinzufügen.

1. Stellen Sie sicher, dass Attribute und Berechtigungen entsprechend festgelegt sind.

   ```
   -rw-r--r-- 1 root root   67 Nov 28 12:51 40-powershell.conf
   ```

1. Legen Sie Ownership auf **root** fest.

   ```
   chown root:root /etc/rsyslog.d/40-powershell.conf
   ```

1. Zugriffsberechtigungen festlegen: **root** hat Lese-/Schreibzugriff, **Benutzer** haben Lesezugriff.

   ```
   chmod 644 /etc/rsyslog.d/40-powershell.conf
   ```

## <a name="viewing-powershell-log-output-on-macos"></a>Anzeigen der PowerShell-Protokoll Ausgabe unter macOS

Die einfachste Methode zum Anzeigen der PowerShell-Protokoll Ausgabe unter macOS ist die Verwendung der **Konsolen** Anwendung.

1. Suchen Sie nach der **Konsolen** Anwendung, und starten Sie Sie.
1. Wählen Sie unter **Geräte** den Computernamen aus.
1. Geben Sie im **Suchfeld als Suchbegriff** `pwsh` für die Haupt-Binärdatei von PowerShell ein.
1. Ändern Sie den Suchfilter von `Any` in `Process` .
1. Führen Sie die Vorgänge aus.
1. Optional können Sie die Suche für die spätere Verwendung speichern.

Um eine bestimmte Prozess Instanz von PowerShell in der- **Konsole** zu filtern, enthält die Variable `$pid` die Prozess-ID.

1. Geben Sie die **PID** (Prozess-ID) in das **Suchfeld** ein.
1. Ändern Sie den Suchfilter in `PID` .
1. Führen Sie die Vorgänge aus.

### <a name="viewing-powershell-log-output-from-a-command-line"></a>Anzeigen der PowerShell-Protokoll Ausgabe von einer Befehlszeile aus

Der `log` Befehl kann verwendet werden, um PowerShell-Protokolleinträge von der Befehlszeile aus anzuzeigen.

```
sudo log stream --predicate 'process == "pwsh"' --info
```

### <a name="persisting-powershell-log-output"></a>Beibehalten der PowerShell-Protokoll Ausgabe

Standardmäßig verwendet PowerShell die standardmäßige reine Speicher Protokollierung unter macOS. Dieses Verhalten kann geändert werden, um die Persistenz mithilfe des Befehls zu aktivieren `log config` .

Das folgende Skript aktiviert die Protokollierung und Persistenz auf infoebene:

```
log config --subsystem com.microsoft.powershell --mode=persist:info,level:info
```

Mit dem folgenden Befehl wird die PowerShell-Protokollierung auf den Standardzustand zurückgesetzt:

```
log config --subsystem com.microsoft.powershell --mode=persist:default,level:default
```

Nachdem die Persistenz aktiviert wurde, `log show` kann der Befehl zum Exportieren von Protokoll Elementen verwendet werden. Der-Befehl stellt Optionen zum Exportieren der letzten N Elemente, Elemente seit einer bestimmten Zeit oder Elemente innerhalb einer bestimmten Zeitspanne bereit.

Beispielsweise exportiert der folgende Befehl Elemente seit `9am on April 5 of 2018` :

```
log show --info --start "2018-04-05 09:00:00" --predicate "process = 'pwsh'"
```

`log`Weitere Informationen finden Sie unter `log show --help` .

> [!TIP]
> Wenn Sie einen der Protokoll Befehle von einer PowerShell-Eingabeaufforderung oder einem Skript ausführen, verwenden Sie doppelte Anführungszeichen um die gesamte Prädikat Zeichenfolge und einfache Anführungszeichen innerhalb von. Dadurch entfällt die Notwendigkeit, doppelte Anführungszeichen in der Prädikat Zeichenfolge zu schließen.

Möglicherweise möchten Sie auch die Ereignisprotokolle an einem sichereren Speicherort speichern, z. b. in einem zentralen Ereignisprotokoll Sammler oder [Siem][] -Aggregator. Sie können Siem in Azure einrichten. Weitere Informationen finden Sie unter [generische Siem-Integration](/cloud-app-security/siem).

## <a name="configuring-logging-on-a-non-windows-system"></a>Konfigurieren der Protokollierung auf einem nicht-Windows-System

Unter Windows wird die Protokollierung durch Erstellen von etw-Ablaufverfolgungslistenern oder mithilfe der Ereignisanzeige zum Aktivieren der analytischen Protokollierung konfiguriert Unter Linux und macOS wird die Protokollierung mithilfe der-Datei konfiguriert `powershell.config.json` . Im restlichen Teil dieses Abschnitts wird die Konfiguration der PowerShell-Protokollierung auf einem nicht-Windows-System erläutert.

PowerShell ermöglicht standardmäßig eine Informations Protokollierung im Betriebskanal. Dies bedeutet, dass jede von PowerShell erzeugte Protokoll Ausgabe, die als betriebsbereit markiert ist, und eine Protokollebene (Ablauf Verfolgungs Ebene) vorhanden ist, die größer als die Information ist, protokolliert wird. Gelegentlich kann es vorkommen, dass Diagnosen eine zusätzliche Protokoll Ausgabe erfordern, z. b. eine ausführliche Protokoll Ausgabe oder die Aktivierung der analytischen Protokoll Ausgabe.

Die Datei `powershell.config.json` ist eine **JSON** -formatierte Datei, die sich im PowerShell- `$PSHOME` Verzeichnis befindet. Jede Installation von PowerShell verwendet eine eigene Kopie dieser Datei. Für den normalen Betrieb bleibt diese Datei unverändert. Dies kann nützlich sein, um einige der Einstellungen in der Datei zu ändern, um die Diagnose zu ändern oder um zwischen mehreren PowerShell-Versionen im selben System oder sogar mit mehreren Kopien derselben Version zu unterscheiden (siehe `LogIdentity` in der Tabelle unten).

Der folgende Code ist eine Beispielkonfiguration:

```json
{
  "Microsoft.PowerShell:ExecutionPolicy": "RemoteSigned",
  "PowerShellPolicies": {
    "ScriptExecution": {
      "ExecutionPolicy": "RemoteSigned",
      "EnableScripts": true
    },
    "ScriptBlockLogging": {
      "EnableScriptBlockInvocationLogging": true,
      "EnableScriptBlockLogging": true
    },
    "ModuleLogging": {
      "EnableModuleLogging": false,
      "ModuleNames": [
        "PSReadline",
        "PowerShellGet"
      ]
    },
    "ProtectedEventLogging": {
      "EnableProtectedEventLogging": false,
      "EncryptionCertificate": [
        "Joe"
      ]
    },
    "Transcription": {
      "EnableTranscripting": true,
      "EnableInvocationHeader": true,
      "OutputDirectory": "F:\\tmp\\new"
    },
    "UpdatableHelp": {
      "DefaultSourcePath": "f:\\temp"
    },
    "ConsoleSessionConfiguration": {
      "EnableConsoleSessionConfiguration": false,
      "ConsoleSessionConfigurationName": "name"
    }
  },
  "LogLevel": "verbose"
}
```

Die Eigenschaften zum Konfigurieren der PowerShell-Protokollierung sind in der folgenden Tabelle aufgeführt. Werte, die mit einem Sternchen gekennzeichnet sind (z. b.), `Operational*` geben den Standardwert an, wenn kein Wert in der Datei angegeben wird.

|Eigenschaft   |Werte        |BESCHREIBUNG                                  |
|-----------|--------------|---------------------------------------------|
|`LogIdentity`|(Zeichen folgen Name) |Der Name, der bei der Protokollierung verwendet werden soll. Standardmäßig wird von  |
|           |PowerShell   |PowerShell ist die Identität. Dieser Wert kann|
|           |              |wird verwendet, um den Unterschied zwischen zwei      |
|           |              |Instanzen einer PowerShell-Installation, z. b. |
|           |              |als Release-und Beta Version. Dieser Wert ist |
|           |              |wird auch zum Umleiten der Protokoll Ausgabe an einen verwendet.        |
|           |              |separate Datei unter Linux. Weitere Informationen finden Sie unter|
|           |              |**rsyslog** oben.                           |
|`LogChannels`|Betriebs  |Die Kanäle, die aktiviert werden sollen. Werte trennen|
|           |Analytic      |mit einem Komma, wenn mehr als eins angegeben wird.  |
|`LogLevel`   |Always        |Geben Sie einen einzelnen Wert an. Der Wert aktiviert  |
|           |Kritisch      |selbst und alle obigen Werte in der        |
|           |Fehler         |nach Links auflisten.                            |
|           |Warnung       |                                             |
|           |Ellen|                                             |
|           |Ausführlich       |                                             |
|           |Debuggen         |                                             |
|`LogKeywords`|Runspace      |Schlüsselwörter bieten die Möglichkeit, die Protokollierung einzuschränken.|
|           |Pipeline      |für bestimmte Komponenten in PowerShell. nach |
|           |Protokoll      |Standardmäßig sind alle Schlüsselwörter aktiviert und werden geändert. |
|           |Transport     |Dieser Wert ist nur für sehr nützlich.           |
|           |Host          |spezialisierte Problembehandlung.                |
|           |Cmdlets       |                                             |
|           |serializer    |                                             |
|           |Sitzung       |                                             |
|           |Managedplugin |                                             |

## <a name="see-also"></a>Weitere Informationen:

Informationen zu Linux- **syslog** -und **rsyslog. conf** -Informationen finden Sie auf den lokalen Seiten des Linux-Computers `man` .

Informationen zu macOS- **os_log** finden Sie in [os_log Entwicklerdokumentation](https://developer.apple.com/documentation/os/os_log).

[about_Logging_Windows](about_Logging_Windows.md)

[Generische SIEM-Integration](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management
