---
description: Konfigurationsdateien für PowerShell Core, die die Registrierungs Konfiguration ersetzen.
keywords: powershell
Locale: en-US
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Config
ms.openlocfilehash: 88e2f5fc5eaaf3ffffd5ceb3df0632866eee705e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223087"
---
# <a name="about-powershell-config"></a>Informationen zur PowerShell-Konfiguration

## <a name="short-description"></a>KURZE BESCHREIBUNG
Konfigurationsdateien für PowerShell Core, die die Registrierungs Konfiguration ersetzen.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Die `powershell.config.json` Datei enthält Konfigurationseinstellungen für PowerShell Core. Diese Konfiguration wird von PowerShell beim Start geladen. Die Einstellungen können auch zur Laufzeit geändert werden. Zuvor wurden diese Einstellungen in der Windows-Registrierung für PowerShell gespeichert, sind aber jetzt in einer Datei enthalten, um die Konfiguration unter macOS und Linux zu aktivieren.

> [!WARNING]
> Wenn die `powershell.config.json` Datei eine ungültige JSON-Datei enthält, kann PowerShell keine interaktive Sitzung starten.
> Wenn dies der Fall ist, müssen Sie die Konfigurationsdatei korrigieren.

> [!NOTE]
> Nicht erkannte Schlüssel oder ungültige Werte in der Konfigurationsdatei werden automatisch ignoriert.

### <a name="allusers-shared-configuration"></a>Konfiguration von ALLUSERS (Shared)

Eine `powershell.config.json` Datei im `$PSHOME` Verzeichnis definiert die Konfiguration für alle PowerShell-Kern Sitzungen, die von dieser PowerShell Core-Installation ausgeführt werden.

> [!NOTE]
> Der `$PSHOME` Speicherort wird als dasselbe Verzeichnis wie die ausführende System.Management.Automation.dll Assembly definiert. Dies gilt auch für gehostete PowerShell SDK-Instanzen.

### <a name="currentuser-per-user-configurations"></a>CurrentUser-Konfigurationen (pro Benutzer)

Sie können PowerShell auch pro Benutzer konfigurieren, indem Sie die Datei im Benutzer Bereichs-Konfigurationsverzeichnis platzieren. Das Benutzer Konfigurationsverzeichnis kann mit dem Befehl plattformübergreifend gefunden werden `Split-Path $PROFILE.CurrentUserCurrentHost` .

## <a name="general-configuration-settings"></a>Allgemeine Konfigurationseinstellungen

### <a name="executionpolicy"></a>ExecutionPolicy

> [!IMPORTANT]
> Diese Konfiguration gilt nur für Windows-Plattformen.

Konfiguriert die Ausführungs Richtlinie für PowerShell-Sitzungen und bestimmt, welche Skripts ausgeführt werden können. Standardmäßig verwendet PowerShell die vorhandene Ausführungs Richtlinie.

Bei ALLUSERS-Konfigurationen wird dadurch die **LocalMachine** -Ausführungs Richtlinie festgelegt.
Bei CurrentUser-Konfigurationen wird die **CurrentUser** -Ausführungs Richtlinie festgelegt.

> [!NOTE]
> Das- [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) Cmdlet ändert diese Einstellung in der ALLUSERS-Konfigurationsdatei, wenn Sie mit aufgerufen `-Scope LocalMachine` wird, und ändert diese Einstellung in der CurrentUser-Konfigurationsdatei, wenn Sie mit aufgerufen wird `-Scope CurrentUser` .

```Schema
"<shell-id>:ExecutionPolicy": "<execution-policy>"
```

Hierbei gilt:

- `<shell-id>` bezieht sich auf die ID des aktuellen PowerShell-Hosts.
  Für den normalen PowerShell-Kern lautet der Wert `Microsoft.PowerShell` .
  In einer beliebigen PowerShell-Sitzung können Sie diese mithilfe von ermitteln `$ShellId` .
- `<execution-policy>` verweist auf einen gültigen Namen für die Ausführungs Richtlinie.

Im folgenden Beispiel wird die Ausführungs Richtlinie von PowerShell auf festgelegt `RemoteSigned` .

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "RemoteSigned"
}
```

In Windows finden Sie die entsprechenden Registrierungsschlüssel `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` unter `HKEY_LOCAL_MACHINE` und `HKEY_CURRENT_USER` .

### <a name="psmodulepath"></a>PSModulePath

Überschreibt eine psmodulepath-Komponente für diese PowerShell-Sitzung. Wenn die Konfiguration für den aktuellen Benutzer gilt, legt den CurrentUser-Modulpfad fest. Wenn die Konfiguration für alle Benutzer gilt, wird der alluser-Modulpfad von festgelegt.

> [!WARNING]
> Wenn Sie einen AllUsers-oder CurrentUser-Modulpfad hier konfigurieren, wird der Bereichs bezogene Installationsort für PowerShellGet-Module wie " [Install-Module](/powershell/module/powershellget/install-module)" nicht geändert.
> Diese Cmdlets verwenden immer die *Standard* Modul Pfade.

Wenn kein Wert festgelegt ist, wird der Standardwert für die jeweilige Modul Pfadkomponente verwendet. Weitere Informationen zu diesen Standardeinstellungen finden Sie unter [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) .

Diese Einstellung ermöglicht die Verwendung von Umgebungsvariablen, indem Sie Sie `%` `"%HOME%\Documents\PowerShell\Modules"` auf die gleiche Weise wie cmd zwischen Zeichen einbetten. Diese Syntax gilt auch für Linux und macOS. Weiter unten finden Sie Beispiele dafür.

```Schema
"PSModulePath": "<ps-module-path>"
```

Hierbei gilt:

- `<ps-module-path>` der absolute Pfad zu einem Modul Verzeichnis. Für alle Benutzerkonfigurationen ist dies das Verzeichnis "ALLUSERS Shared Module". Bei aktuellen Benutzerkonfigurationen ist dies das CurrentUser-Modul Verzeichnis.

Dieses Beispiel zeigt eine psmodulepath-Konfiguration für eine Windows-Umgebung:

```json
{
  "PSModulePath": "C:\\Program Files\\PowerShell\\6\\Modules"
}
```

Dieses Beispiel zeigt eine psmodulepath-Konfiguration für eine macOS-oder Linux-Umgebung:

```json
{
  "PSModulePath": "/opt/powershell/6/Modules"
}
```

Dieses Beispiel zeigt das Einbetten einer Umgebungsvariablen in eine psmodulepath-Konfiguration. Beachten Sie, dass `HOME` `/` dies unter Windows, macOS und Linux funktioniert, wenn die Umgebungsvariable und das Verzeichnis Trennzeichen verwendet werden.

```json
{
  "PSModulePath": "%HOME%/Documents/PowerShell/Modules"
}
```

Dieses Beispiel zeigt das Einbetten einer Umgebungsvariablen in eine psmodulepath-Konfiguration, die nur unter macOS und Linux funktioniert:

```json
{
  "PSModulePath": "%XDG_CONFIG_HOME%/powershell/Modules"
}
```

> [!NOTE]
> PowerShell-Variablen können nicht in psmodulepath-Konfigurationen eingebettet werden.
> Bei psmodulepath-Konfigurationen unter Linux und macOS wird die Groß-/Kleinschreibung beachtet. Eine psmodulepath-Konfiguration muss gültige Verzeichnis Trennzeichen für die Plattform verwenden. Unter macOS und Linux bedeutet dies `/` . Unter Windows funktionieren sowohl `/` als auch `\` .

### <a name="experimentalfeatures"></a>Experiment Features

Die Namen der experimentellen Funktionen, die in PowerShell aktiviert werden sollen.
Standardmäßig sind keine experimentellen Funktionen aktiviert.
Der Standardwert ist ein leeres Array.

```Schema
"ExperimentalFeatures": ["<experimental-feature-name>", ...]
```

Hierbei gilt:

- `<experimental-feature-name>` der Name eines experimentellen Features, das aktiviert werden soll.

Im folgenden Beispiel werden die experimentellen Funktionen **pvereinfachcitremoting** und **psugkürzen ationexpansion** aktiviert, wenn PowerShell gestartet wird.

```json
{
  "ExperimentalFeatures": [
    "PSImplicitRemotingBatching",
    "PSUseAbbreviationExpansion"
  ]
}
```

Weitere Informationen zu experimentellen Funktionen finden Sie unter [PowerShell RFC 29][RFC0029].

## <a name="non-windows-logging-configuration"></a>Konfiguration der nicht-Windows-Protokollierung

> [!IMPORTANT]
> Die Konfigurationsoptionen in diesem Abschnitt gelten nur für macOS und Linux.
> Die Protokollierung für Windows wird von der Windows-Ereignisanzeige verwaltet.

Die PowerShell-Protokollierung unter macOS und Linux kann in der PowerShell-Konfigurationsdatei konfiguriert werden. Eine vollständige Beschreibung der PowerShell-Protokollierung für nicht-Windows-Systeme finden Sie unter [Informationen zur Protokollierung](./about_Logging_Non-Windows.md).

### <a name="logidentity"></a>Logidentity

> [!IMPORTANT]
> Diese Einstellung kann nur in macOS und Linux verwendet werden.

Legt den Identitäts Namen fest, der zum Schreiben in das System Protokoll verwendet wird. Der Standardwert ist "PowerShell".

```Schema
"LogIdentity": "<log-identity>"
```

Hierbei gilt:

- `<log-identity>` die Zeichen folgen Identität, die von PowerShell zum Schreiben in syslog verwendet werden soll.

> [!NOTE]
> Möglicherweise möchten Sie für jede andere Instanz von PowerShell, die Sie installiert haben, unterschiedliche **logidentity** -Werte haben.

In diesem Beispiel konfigurieren wir die **logidentity** für eine Vorschauversion von PowerShell.

```json
{
  "LogIdentity": "powershell-preview"
}
```

### <a name="loglevel"></a>LogLevel

> [!IMPORTANT]
> Diese Einstellung kann nur in macOS und Linux verwendet werden.

Gibt den minimalen Schweregrad an, mit dem PowerShell protokolliert werden soll.

```Schema
"LogLevel": "<log-level>|default"
```

Hierbei gilt:

- `<log-level>` ist eine von:
  - Always
  - Kritisch
  - Fehler
  - Warnung
  - Informational
  - Ausführlich
  - Debuggen

> [!NOTE]
> Durch Festlegen einer Protokollebene werden alle darüber liegenden Protokoll Ebenen aktiviert.

Wenn diese Einstellung auf **default** festgelegt wird, wird Sie als Standardwert interpretiert.
Der Standardwert ist " **Information** ".

Im folgenden Beispiel wird der Wert auf **verbose** festgelegt.

```json
{
  "LogLevel": "Verbose"
}
```

### <a name="logchannels"></a>Logchannels

> [!IMPORTANT]
> Diese Einstellung kann nur in macOS und Linux verwendet werden.

Bestimmt, welche Protokollierungs Kanäle aktiviert sind.

```Schema
"LogChannels": "<log-channel>,..."
```

Hierbei gilt:

- `<log-channel>` ist eine von:
  - Operational: protokolliert grundlegende Informationen zu PowerShell-Aktivitäten.
  - Analytisch: protokolliert ausführlichere Diagnoseinformationen

Der Standardwert ist **Operational**. Um beide Kanäle zu aktivieren, schließen Sie beide Werte als einzelne durch Trennzeichen getrennte Zeichenfolge ein. Beispiel:

```json
{
  "LogChannels": "Operational,Analytic"
}
```

### <a name="logkeywords"></a>Logschlüsselwörter

> [!IMPORTANT]
> Diese Einstellung kann nur in macOS und Linux verwendet werden.

Bestimmt, welche Teile von PowerShell protokolliert werden. Standardmäßig sind alle Protokoll Schlüsselwörter aktiviert. Um mehrere Schlüsselwörter zu aktivieren, Listen Sie die Werte in einer einzelnen durch Trennzeichen getrennten Zeichenfolge auf.

```Schema
"LogKeywords": "<log-keyword>,..."
```

Hierbei gilt:

- `<log-keyword>` ist eine von:
  - Runspace-Runspace-Verwaltung
  - Pipeline-Pipeline Vorgänge
  - Protokoll Kommunikationsprotokoll-Behandlung, z. b. PSRP
  - Transport-Transportschicht Unterstützung, z. b. ssh
  - Host-PowerShell-Host Funktionen, z. b. Konsolen Interaktion
  - Cmdlets: PowerShell-Cmdlets für Builtin
  - Serializer-Serialisierungslogik
  - Sitzung-PowerShell-Sitzungs Status
  - Managedplugin-WSMAN-Plug-in

> [!NOTE]
> Es wird im Allgemeinen empfohlen, diesen Wert nicht festzulegen, es sei denn, Sie versuchen, ein bestimmtes Verhalten in einem bekannten Bereich von PowerShell zu diagnostizieren.
> Durch Ändern dieses Werts wird nur die Menge der protokollierten Informationen verringert.

In diesem Beispiel wird die Protokollierung auf Runspace-Vorgänge, die Pipeline Logik und die Cmdlet-Verwendung beschränkt. Alle anderen Protokollierungen werden weggelassen.

```json
"LogKeywords": "Runspace,Pipeline,Cmdlets"
```

<!--

## Group policy configuration

### ScriptExecution

### ScriptBlockLogging

### ProtectedEventLogging

### Transcription

### UpdateableHelp

### ConsoleSessionConfiguration

-->

## <a name="more-example-configurations"></a>Weitere Beispielkonfigurationen

### <a name="example-windows-configuration"></a>Windows-Beispielkonfiguration

Für diese Konfiguration sind mehr Einstellungen explizit festgelegt:

- Die Ausführungs Richtlinie für diese PowerShell-Installation ist `AllSigned`
- Der CurrentUser-Modulpfad wird auf ein Modul Verzeichnis auf einem freigegebenen Laufwerk festgelegt.
- Die `PSImplicitRemotingBatching` experimentelle Funktion ist aktiviert.

> [!NOTE]
> Die `ExecutionPolicy` -und- `PSModulePath` Einstellungen können hier nur auf einer Windows-Plattform verwendet werden, da der Modulpfad `\` und `;` Trennzeichen verwendet, und die Ausführungs Richtlinie ist nicht `Unrestricted` (die einzige Richtlinie, die auf Unix-ähnlichen Plattformen zulässig ist).

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "AllSigned",
  "PSModulePath": "Z:\\Marisol's Shared Drive\\Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
}
```

### <a name="example-non-windows-configuration"></a>Beispiel für eine nicht-Windows-Konfiguration

Diese Konfiguration legt eine Reihe von Optionen fest, die nur in macOS oder Linux funktionieren:

- Der CurrentUser-Modulpfad wird auf ein benutzerdefiniertes Modul Verzeichnis in festgelegt. `$HOME`
- Das experimentelle **pvereinfachcitrefitingbatching** -Funktion ist aktiviert.
- Der PowerShell-Protokolliergrad **ist für weitere Protokollierung auf ausführlich** festgelegt.
- Diese PowerShell-Installation schreibt mithilfe der **Home-PowerShell** -Identität in die Protokolle.

```json
{
  "PSModulePath": "%HOME%/.powershell/Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
  "LogLevel": "Verbose",
  "LogIdentity": "home-powershell"
}
```

## <a name="see-also"></a>Weitere Informationen:

[Informationen zu Ausführungsrichtlinien](./about_Execution_Policies.md)

[Informationen zu automatischen Variablen](./about_Automatic_Variables.md)

[RFC0029]: https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md
