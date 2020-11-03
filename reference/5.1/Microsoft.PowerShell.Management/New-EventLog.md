---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-EventLog
ms.openlocfilehash: 61fafc0670a24fd6ca057e4cf0c7179d90446b07
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214620"
---
# New-EventLog

## ZUSAMMENFASSUNG
Erstellt ein neues Ereignisprotokoll und eine neue Ereignisquelle auf einem lokalen Computer oder einem Remotecomputer.

## SYNTAX

```
New-EventLog [-LogName] <string> [-Source] <string[]> [[-ComputerName] <string[]>]
  [-CategoryResourceFile <string>] [-MessageResourceFile <string>] [-ParameterResourceFile <string>]
  [<CommonParameters>]
```

## DESCRIPTION

Dieses Cmdlet erstellt ein neues klassisches Ereignisprotokoll auf einem lokalen Computer oder einem Remotecomputer. Außerdem kann eine Ereignisquelle registriert werden, die in das neue Protokoll oder in ein vorhandenes Protokoll schreibt.

Die Cmdlets, die das Substantiv %%amp;quot;EventLog%%amp;quot; enthalten (die EventLog-Cmdlets), können nur für klassische Ereignisprotokolle verwendet werden.
Verwenden Sie, um Ereignisse aus Protokollen zu erhalten, in denen die Windows-Ereignisprotokoll Technologie in Windows Vista und höheren Versionen von Windows verwendet wird `Get-WinEvent` .

## BEISPIELE

### Beispiel 1: Erstellen eines neuen Ereignis Protokolls

Mit diesem Befehl wird das Ereignisprotokoll %%amp;quot;TestLog%%amp;quot; auf dem lokalen Computer erstellt und eine neue Quelle dafür registriert.

```powershell
New-EventLog -source TestApp -LogName TestLog -MessageResourceFile C:\Test\TestApp.dll
```

### Beispiel 2: Hinzufügen einer neuen Ereignis Quelle zu einem vorhandenen Protokoll

Mit diesem Befehl wird die neue Ereignisquelle %%amp;quot;NewTestApp%%amp;quot; dem Anwendungsprotokoll auf dem Remotecomputer %%amp;quot;Server01%%amp;quot; hinzugefügt.

```powershell
$file = "C:\Program Files\TestApps\NewTestApp.dll"
New-EventLog -ComputerName Server01 -Source NewTestApp -LogName Application -MessageResourceFile $file -CategoryResourceFile $file
```

Für diesen Befehl muss sich die Datei %%amp;quot;NewTestApp.dll%%amp;quot; auf dem Computer %%amp;quot;Server01%%amp;quot; befinden.

## PARAMETERS

### -CategoryResourceFile

Gibt den Pfad zu der Datei an, die Kategoriezeichenfolgen für die Quellereignisse enthält. Diese Datei wird auch als Kategoriemeldungsdatei bezeichnet.

Die Datei muss auf dem Computer vorhanden sein, auf dem das Ereignisprotokoll erstellt wird. Dieser Parameter erstellt und verschiebt keine Dateien.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Erstellt die neuen Ereignisprotokolle auf den angegebenen Computern. Die Standardeinstellung ist der lokale Computer.

Den NetBIOS-Namen, die IP-Adresse oder den voll qualifizierten Domänen Namen eines Remote Computers.
Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt (.) oder %%amp;quot;localhost%%amp;quot; ein.

Dieser Parameter beruht nicht auf PowerShell-Remoting. Sie können den **Computername** -Parameter `Get-EventLog` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 3
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

Gibt den Namen des Ereignisprotokolls an.

Wenn das Protokoll nicht vorhanden ist, `New-EventLog` erstellt das Protokoll und verwendet diesen Wert für die Eigenschaften " **Log** " und " **LogDisplayName** " des neuen Ereignis Protokolls. Wenn das Protokoll vorhanden ist, `New-EventLog` registriert eine neue Quelle für das Ereignisprotokoll.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageResourceFile

Gibt den Pfad zu der Datei an, die Formatzeichenfolgen für Nachrichten für die Quellereignisse enthält.
Diese Datei wird auch als Ereignismeldungsdatei bezeichnet.

Die Datei muss auf dem Computer vorhanden sein, auf dem das Ereignisprotokoll erstellt wird.
Dieser Parameter erstellt und verschiebt keine Dateien.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterResourceFile

Gibt an den Pfad zu der Datei mit Zeichenfolgen an, die für die Parameterersetzungen in Ereignisbeschreibungen verwendet werden. Diese Datei wird auch als Parametermeldungsdatei bezeichnet.

Die Datei muss auf dem Computer vorhanden sein, auf dem das Ereignisprotokoll erstellt wird.
Dieser Parameter erstellt und verschiebt keine Dateien.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Gibt die Namen der Ereignisprotokollquellen an, z. B. Anwendungen, die in das Ereignisprotokoll schreiben. Dieser Parameter ist erforderlich.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Diagnostics. EventLogEntry

## HINWEISE

Wenn Sie unter `New-EventLog` Windows Vista und höheren Versionen von Windows verwenden möchten, öffnen Sie PowerShell mit der Option "als Administrator ausführen".

Zum Erstellen einer Ereignisquelle in Windows Vista, Windows XP Professional oder Windows Server 2003 müssen Sie Mitglied der Gruppe %%amp;quot;Administratoren%%amp;quot; auf dem Computer sein.

Wenn Sie ein neues Ereignisprotokoll und eine neue Ereignisquelle erstellen, registriert das System die neue Quelle für das neue Protokoll, das Protokoll wird jedoch erst erstellt, wenn der erste Eintrag darin geschrieben wird.

Das Betriebssystem speichert Ereignisprotokolle als Dateien.

Wenn Sie ein neues Ereignisprotokoll erstellen, wird die zugehörige Datei im `$env:SystemRoot\System32\Config` Verzeichnis auf dem angegebenen Computer gespeichert.

Der Dateiname ist die ersten acht Zeichen der **Log** -Eigenschaft mit der Dateinamenerweiterung ". evt".

## VERWANDTE LINKS

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
