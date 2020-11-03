---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: 535cad057db406eaa48259288e34da6da4ed1cbb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210148"
---
# Start-Sleep

## ZUSAMMENFASSUNG
Hält die Aktivität in einem Skript oder einer Sitzung für den angegebenen Zeitraum an.

## SYNTAX

### Sekunden (Standard)

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### Millisekunden

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## DESCRIPTION

Das- `Start-Sleep` Cmdlet hält die Aktivität in einem Skript oder einer Sitzung für den angegebenen Zeitraum an. Sie können es für viele Aufgaben verwenden, z. B. Warten auf den Abschluss eines Vorgangs oder Anhalten, bevor ein Vorgang wiederholt wird.

## BEISPIELE

### Beispiel 1: alle Befehle für 15 Sekunden in den Standbymodus

```powershell
Start-Sleep -s 15
```

### Beispiel 2: Standbymodus für alle Befehle für 1,5 Sekunden

In diesem Beispiel werden alle Befehle in der Sitzung für eine und eine halbe Sekunde in den Standbymodus versetzt.

```powershell
Start-Sleep -Seconds 1.5
```

## PARAMETERS

### -Millisekunden

Gibt an, wie lange die Ressource in Millisekunden im Ruhezustand ist. Der-Parameter kann als **m** abgekürzt werden.

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases: ms

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sekunden

Gibt an, wie lange die Ressource in Sekunden im Ruhezustand ist. Sie können den Parameternamen weglassen, oder Sie können ihn als **s** abkürzen. Beginnend mit der PowerShell-6.2.0 akzeptiert dieser Parameter nun Bruchzahlen.

```yaml
Type: System.Double
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
