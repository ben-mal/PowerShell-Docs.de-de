---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 3/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4add39c09b6123aaf8c9302529346a6b1dec391
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213663"
---
# Start-Sleep

## ZUSAMMENFASSUNG
Hält die Aktivität in einem Skript oder einer Sitzung für den angegebenen Zeitraum an.

## SYNTAX

### Sekunden (Standard)

```
Start-Sleep [-Seconds] <Int32> [<CommonParameters>]
```

### Millisekunden

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## DESCRIPTION

Das- `Start-Sleep` Cmdlet hält die Aktivität in einem Skript oder einer Sitzung für den angegebenen Zeitraum an.
Sie können es für viele Aufgaben verwenden, z. B. Warten auf den Abschluss eines Vorgangs oder Anhalten, bevor ein Vorgang wiederholt wird.

## BEISPIELE

### Beispiel 1: alle Befehle für 15 Sekunden in den Standbymodus

```powershell
Start-Sleep -s 15
```

Mit diesem Befehl werden alle Befehle in der Sitzung für 15 Sekunden in den Ruhezustand versetzt.

### Beispiel 2: alle Befehle im Standbymodus

```powershell
Start-Sleep -m 500
```

Mit diesem Befehl werden alle Befehle in der Sitzung für eine halbe Sekunde (500 Millisekunden) in den Ruhezustand versetzt.

## PARAMETERS

### -Millisekunden

Gibt an, wie lange die Ressource in Millisekunden im Ruhezustand ist.
Der-Parameter kann als **m** abgekürzt werden.

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sekunden

Gibt an, wie lange die Ressource in Sekunden im Ruhezustand ist.
Sie können den Parameternamen ( **Sekunden** ) weglassen, oder Sie können ihn als **s** abkürzen.

```yaml
Type: System.Int32
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.Int32

Sie können die Anzahl der Sekunden an die Pipeline übergeben `Start-Sleep` .

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

- Sie können auch auf den `Start-Sleep` integrierten Alias verweisen `sleep` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Ctrl+C` bricht von ab `Start-Sleep` .
  - `Ctrl+C` bricht nicht aus `[Threading.Thread]::Sleep` . Weitere Informationen finden Sie unter [Thread. Sleep-Methode](/dotnet/api/system.threading.thread.sleep).

## VERWANDTE LINKS
