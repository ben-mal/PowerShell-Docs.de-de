---
description: PowerShell protokolliert interne Vorgänge von der Engine, den Anbietern und den Cmdlets.
keywords: powershell
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logging_windows?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logging-Windows
ms.openlocfilehash: dbc11e15642673d3159d4f02a40147e68fbf1d7d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220455"
---
# <a name="about-logging-windows"></a>Informationen zu Protokollierungs Fenstern

## <a name="short-description"></a>Kurze Beschreibung

PowerShell protokolliert interne Vorgänge von der Engine, den Anbietern und den Cmdlets.

## <a name="long-description"></a>Lange Beschreibung

PowerShell protokolliert Details zu PowerShell-Vorgängen, z. b. das Starten und Beenden der Engine und Anbieter und das Ausführen von PowerShell-Befehlen.

> [!NOTE]
> Windows PowerShell-Versionen 3,0, 4,0, 5,0 und 5,1 enthalten **EventLog** -Cmdlets für die Windows-Ereignisprotokolle. Geben Sie in diesen Versionen Folgendes ein, um die Liste der **EventLog** -Cmdlets anzuzeigen: `Get-Command -Noun EventLog` . Weitere Informationen finden Sie in der Cmdlet-Dokumentation und about_EventLogs für Ihre Version von Windows PowerShell.

## <a name="viewing-the-powershell-event-log-entries-on-windows"></a>Anzeigen der PowerShell-Ereignisprotokoll Einträge unter Windows

PowerShell-Protokolle können mithilfe des Windows-Ereignisanzeige angezeigt werden. Das Ereignisprotokoll befindet sich in der Gruppe Anwendungs-und Dienst Protokolle und hat den Namen `PowerShellCore` . Der zugehörige ETW-Anbieter `GUID` ist `{f90714a8-5509-434a-bf6d-b1624c8a19a2}` .

Wenn die Protokollierung von Skript Blöcken aktiviert ist, protokolliert PowerShell die folgenden Ereignisse im `PowerShellCore/Operational` Protokoll:

|Feld| Wert|
|-|-|
|EventId|`4104` / `0x1008`|
|Channel|`Operational`|
|Ebene|`Verbose`|
|Opcode|`Create`|
|Aufgabe|`CommandStart`|
|Schlüsselwort|`Runspace`|

### <a name="registering-the-powershell-event-provider-on-windows"></a>Registrieren des PowerShell-Ereignis Anbieters unter Windows

Anders als bei Linux oder macOS muss Windows den Ereignis Anbieter registrieren, bevor Ereignisse in das Ereignisprotokoll geschrieben werden können. Führen Sie den folgenden Befehl an einer PowerShell-Eingabeaufforderung mit erhöhten Rechten aus, um den PowerShell-Ereignis Anbieter zu aktivieren.

```powershell
$PSHOME\RegisterManifest.ps1
```

### <a name="unregistering-the-powershell-event-provider-on-windows"></a>Aufheben der Registrierung des PowerShell-Ereignis Anbieters unter Windows

Durch das Registrieren des Ereignis Anbieters wird eine Sperre in der binären Bibliothek platziert, die zum Decodieren von Ereignissen verwendet wird. Um diese Bibliothek zu aktualisieren, muss die Registrierung des Anbieters aufgehoben werden, um diese Sperre freizugeben.

Um die Registrierung des PowerShell-Anbieters aufzuheben, führen Sie den folgenden Befehl an einer PowerShell-Eingabeaufforderung mit erhöhten Rechten aus.

```powershell
$PSHOME\RegisterManifest.ps1 -Unregister
```

Führen Sie nach dem Aktualisieren von PowerShell aus, `$PSHOME\RegisterManifest.ps1` um den aktualisierten Ereignis Anbieter zu registrieren.

## <a name="enabling-script-block-logging"></a>Aktivieren der Skript Block Protokollierung

Wenn Sie die Skript Block Protokollierung aktivieren, zeichnet PowerShell den Inhalt aller Skriptblöcke auf, die er verarbeitet. Nach der Aktivierung werden diese Informationen in jeder neuen PowerShell-Sitzung protokolliert.

> [!NOTE]
> Es wird empfohlen, die Protokollierung geschützter Ereignisse wie unten beschrieben zu aktivieren, wenn Sie die Skript Block Protokollierung für andere Zwecke als Diagnosezwecke verwenden.

Die Skript Block Protokollierung kann über Gruppenrichtlinie oder eine Registrierungs Einstellung aktiviert werden.

### <a name="using-group-policy"></a>Verwenden von Gruppenrichtlinien

Aktivieren Sie zum Aktivieren der automatischen Aufzeichnung die `Turn on PowerShell Script Block
Logging` Funktion in Gruppenrichtlinie `Administrative Templates -> Windows
Components -> Windows PowerShell` .

### <a name="using-the-registry"></a>Verwenden der Registrierung

Führen Sie die folgende Funktion aus:

```powershell
function Enable-PSScriptBlockLogging
{
    $basePath = 'HKLM:\Software\Policies\Microsoft\Windows' +
      '\PowerShell\ScriptBlockLogging'

    if(-not (Test-Path $basePath))
    {
        $null = New-Item $basePath -Force
    }

    Set-ItemProperty $basePath -Name EnableScriptBlockLogging -Value "1"
}
```

## <a name="protected-event-logging"></a>Protokollierung geschützter Ereignisse

Das Erhöhen der Protokollierungsebene auf einem System erhöht die Wahrscheinlichkeit, dass protokollierte Inhalte vertrauliche Daten enthalten können. Wenn z. b. die Skript Protokollierung aktiviert ist, können Anmelde Informationen oder andere sensible Daten, die von einem Skript verwendet werden, in das Ereignisprotokoll geschrieben werden. Wenn ein Computer, auf dem sensible Daten protokolliert wurden, kompromittiert ist, können die Protokolle einem Angreifer Informationen zur Verfügung stellen, die zum Erweitern der Reichweite benötigt werden.

Um diese Informationen zu schützen, führt Windows 10 die Protokollierung geschützter Ereignisse ein.
Durch die Protokollierung geschützter Ereignisse können beteiligte Anwendungen vertrauliche Daten verschlüsseln, die in das Ereignisprotokoll geschrieben werden. Später können Sie diese Protokolle auf einem sichereren und zentralisierten Protokoll Sammler entschlüsseln und verarbeiten.

Der Inhalt des Ereignis Protokolls wird mithilfe des IETF Cryptographic Message Syntax (CMS)-Standards geschützt. CMS verwendet Kryptografie mit öffentlichem Schlüssel. Die Schlüssel, die zum Verschlüsseln von Inhalten und Entschlüsseln von Inhalten verwendet werden, werden separat aufbewahrt.

Der öffentliche Schlüssel kann umfassend freigegeben werden, und es handelt sich nicht um vertrauliche Daten. Alle Inhalte, die mit diesem öffentlichen Schlüssel verschlüsselt sind, können nur mit dem privaten Schlüssel entschlüsselt werden. Weitere Informationen zur Kryptografie mit öffentlichem Schlüssel finden Sie unter [Kryptografie mit Wikipedia (Public Key](https://en.wikipedia.org/wiki/Public-key_cryptography)).

Um eine Richtlinie für die Protokollierung geschützter Ereignisse zu aktivieren, stellen Sie einen öffentlichen Schlüssel für alle Computer bereit, die zu schützende Ereignisprotokoll Daten aufweisen. Der entsprechende private Schlüssel wird verwendet, um die Ereignisprotokolle an einem sichereren Speicherort, z. b. einem zentralen Ereignisprotokoll Sammler oder einem [Siem][] -Aggregator, zu verarbeiten. Sie können Siem in Azure einrichten. Weitere Informationen finden Sie unter [generische Siem-Integration](/cloud-app-security/siem).

### <a name="enabling-protected-event-logging-via-group-policy"></a>Aktivieren der Protokollierung geschützter Ereignisse über Gruppenrichtlinie

Um die Protokollierung geschützter Ereignisse zu aktivieren, aktivieren Sie die `Enable Protected Event Logging` Funktion in Gruppenrichtlinie `Administrative Templates -> Windows Components
-> Event Logging` . Diese Einstellung erfordert ein Verschlüsselungs Zertifikat, das Sie in einer von mehreren Formularen bereitstellen können:

- Der Inhalt eines Base64-codierten X. 509 64-Zertifikats (z. b., wie von der- `Export` Option im Zertifikat-Manager angeboten).
- Der Fingerabdruck eines Zertifikats, das sich im Zertifikat Speicher des lokalen Computers befindet (kann von der PKI-Infrastruktur bereitgestellt werden).
- Der vollständige Pfad zu einem Zertifikat (kann lokal oder eine Remote Freigabe sein).
- Der Pfad zu einem Verzeichnis, das ein Zertifikat oder Zertifikate enthält (kann lokal oder eine Remote Freigabe sein).
- Der Antragsteller Name eines Zertifikats, das sich im Zertifikat Speicher des lokalen Computers befindet (kann von der PKI-Infrastruktur bereitgestellt werden).

Das resultierende Zertifikat muss `Document Encryption` als erweiterte Schlüssel Verwendung () verwendet `1.3.6.1.4.1.311.80.1` werden, und entweder die- `Data Encipherment` oder- `Key
Encipherment` Schlüssel Verwendungen sind aktiviert.

> [!WARNING]
> Der private Schlüssel sollte nicht für die Protokollierungs Ereignisse der Computer bereitgestellt werden. Er sollte an einem sicheren Ort aufbewahrt werden, an dem die Nachrichten entschlüsselt werden.

### <a name="decrypting-protected-event-logging-messages"></a>Entschlüsseln von Meldungen zur Protokollierung geschützter Ereignisse

Das folgende Skript ruft ab und entschlüsselt Sie, wobei angenommen wird, dass Sie über den privaten Schlüssel verfügen:

```powershell
Get-WinEvent Microsoft-Windows-PowerShell/Operational |
  Where-Object Id -eq 4104 | Unprotect-CmsMessage
```

## <a name="see-also"></a>Weitere Informationen:

[about_Logging_Non-Windows](about_Logging_Non-Windows.md)

[PowerShell-Blue Team](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)

[Generische SIEM-Integration](/cloud-app-security/siem)

<!-- link references -->
[SIEM]: https://wikipedia.org/wiki/Security_information_and_event_management

