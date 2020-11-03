---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-EventLog
ms.openlocfilehash: e8dbcf1aa4280c0481714a8a9fb24f2e5ef79ffe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214407"
---
# Show-EventLog

## ZUSAMMENFASSUNG
Zeigt die Ereignisprotokolle des lokalen Computers oder eines Remotecomputers in der Ereignisanzeige an.

## SYNTAX

```
Show-EventLog [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
Das Cmdlet " **Show-EventLog** " wird Ereignisanzeige auf dem lokalen Computer geöffnet und darin alle klassischen Ereignisprotokolle auf dem lokalen Computer oder einem Remote Computer angezeigt.

Zum Öffnen von Ereignisanzeige unter Windows Vista und höheren Versionen des Windows-Betriebssystems muss der aktuelle Benutzer Mitglied der Gruppe "Administratoren" auf dem lokalen Computer sein.

Die Cmdlets, die das **EventLog** -Substantiv (die **EventLog** -Cmdlets) enthalten, funktionieren nur in klassischen Ereignisprotokollen.
Verwenden Sie das Cmdlet "Get-WinEvent", um Ereignisse aus Protokollen zu erhalten, in denen die Windows-Ereignisprotokoll Technologie in Windows Vista und höheren Versionen des Windows-Betriebssystems verwendet wird.

## BEISPIELE

### Beispiel 1: Anzeigen von Ereignisprotokollen für den lokalen Computer

```
PS C:\> Show-EventLog
```

Mit diesem Befehl wird die Ereignisanzeige geöffnet, und darin werden die klassischen Ereignisprotokolle auf dem lokalen Computer angezeigt.

### Beispiel 2: Anzeigen von Ereignisprotokollen für einen Remote Computer

```
PS C:\> Show-EventLog -ComputerName "Server01"
```

Mit diesem Befehl wird die Ereignisanzeige geöffnet, und darin werden die klassischen Ereignisprotokolle auf dem Computer %%amp;quot;Server01%%amp;quot; angezeigt.

## PARAMETERS

### -ComputerName
Gibt einen Remotecomputer an.
" **Show-EventLog** " zeigt die Ereignisprotokolle auf dem angegebenen Computer in Ereignisanzeige auf dem lokalen Computer an.
Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.
Sie können den *ComputerName* -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
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

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Die Windows PowerShell-Eingabeaufforderung wird zurückgegeben, sobald die Ereignisanzeige geöffnet wird. Sie können in der aktuellen Sitzung arbeiten, während die Ereignisanzeige geöffnet ist.

  Da für dieses Cmdlet eine Benutzeroberfläche erforderlich ist, kann es nicht in Server Core-Installationen von Windows Server verwendet werden.

*

## VERWANDTE LINKS

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Write-EventLog](Write-EventLog.md)
