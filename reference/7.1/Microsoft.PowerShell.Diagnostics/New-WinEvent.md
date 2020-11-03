---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 8605782176a96fa1901af352ceda8b453d2f1af8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217276"
---
# New-WinEvent

## ZUSAMMENFASSUNG
Es erstellt ein neues Windows-Ereignis für den angegebenen Ereignisanbieter.

## SYNTAX

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## DESCRIPTION

Das **New-WinEvent** -Cmdlet erstellt ein ETW-Ereignis (Event Tracing for Windows, Ereignisablaufverfolgung für Windows) für einen Ereignisanbieter.
Mit diesem Cmdlet können Sie etw-Kanälen Ereignisse aus PowerShell hinzufügen.

## BEISPIELE

### Beispiel 1

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

Dieser Befehl verwendet das **New-WinEvent** -Cmdlet, um Ereignis 45090 für den Microsoft-Windows-PowerShell-Anbieter zu erstellen.

## PARAMETERS

### -Id

Gibt eine Ereignis-ID an, die über ein Instrumentationsmanifest registriert wurde.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nutzlast

Gibt die Meldung für das Ereignis an. Wenn das Ereignis in ein Ereignisprotokoll geschrieben wird, wird die Nutzlast in der **Message** -Eigenschaft des Ereignisobjekts gespeichert.

Wenn die angegebene Nutzlast nicht mit der Nutzlast in der Ereignis Definition übereinstimmt, generiert PowerShell eine Warnung, der Befehl wird jedoch trotzdem erfolgreich ausgeführt.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName

Gibt den Ereignisanbieter an, der das Ereignis in ein Ereignisprotokoll schreibt, z. B. „Microsoft-Windows-PowerShell“. Ein ETW-Ereignisanbieter ist eine logische Entität, die Ereignisse in ETW-Sitzungen schreibt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version

Gibt die Versionsnummer des Ereignisses an. Geben Sie die Ereignisnummer ein. PowerShell konvertiert die Nummer in den erforderlichen Byte-Typ.

Mit diesem Parameter können Sie ein Ereignis angeben, wenn verschiedene Versionen des gleichen Ereignisses definiert sind.

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Dieses Cmdlet nimmt keine Eingabe von der Pipeline an.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Nachdem der Anbieter das-Ereignis in ein Ereignisprotokoll geschrieben hat, können Sie mit dem Get-WinEvent-Cmdlet das Ereignis aus dem Ereignisprotokoll erhalten.

## VERWANDTE LINKS

[Get-WinEvent](Get-WinEvent.md)

