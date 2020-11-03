---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-psprovider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSProvider
ms.openlocfilehash: e11a62163f70615f33825c46999d37077b1c3d93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211876"
---
# Get-PSProvider

## ZUSAMMENFASSUNG
Ruft Informationen zum angegebenen PowerShell-Anbieter ab.

## SYNTAX

```
Get-PSProvider [[-PSProvider] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-PSProvider` Cmdlet werden die PowerShell-Anbieter in der aktuellen Sitzung abgerufen.
Sie können ein bestimmtes Laufwerk oder alle Laufwerke in der Sitzung abrufen.

Mit PowerShell-Anbietern können Sie auf eine Vielzahl von Daten speichern zugreifen, als wären es Dateisystem Laufwerke.
Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## BEISPIELE

### Beispiel 1: Anzeigen einer Liste aller verfügbaren Anbieter

```powershell
Get-PSProvider
```

Mit diesem Befehl wird eine Liste aller verfügbaren PowerShell-Anbieter angezeigt.

### Beispiel 2: Anzeigen einer Liste aller PowerShell-Anbieter, die mit angegebenen Buchstaben beginnen

```powershell
Get-PSProvider f*, r* | Format-List
```

Mit diesem Befehl wird eine Liste aller PowerShell-Anbieter angezeigt, deren Namen mit dem Buchstaben f oder r beginnen.

### Beispiel 3: Suchen von Snap-Ins oder Modulen, die ihrer Sitzung Anbieter hinzugefügt haben

```powershell
Get-PSProvider | Format-Table name, module, pssnapin -auto
```

```Output
Name        Module       PSSnapIn
----        ------       --------
Test        TestModule
WSMan                    Microsoft.WSMan.Management
Alias                    Microsoft.PowerShell.Core
Environment              Microsoft.PowerShell.Core
FileSystem               Microsoft.PowerShell.Core
Function                 Microsoft.PowerShell.Core
Registry                 Microsoft.PowerShell.Core
Variable                 Microsoft.PowerShell.Core
Certificate              Microsoft.PowerShell.Security
```

```powershell
Get-PSProvider | Where {$_.pssnapin -eq "Microsoft.PowerShell.Security"}
```

```Output
Name            Capabilities      Drives
----            ------------      ------
Certificate     ShouldProcess     {cert}
```

Diese Befehle suchen die PowerShell-Snap-Ins oder-Module, die ihrer Sitzung Anbieter hinzugefügt haben.
Alle PowerShell-Elemente, einschließlich Anbieter, stammen aus einem Snap-in oder einem Modul.

Diese Befehle verwenden die PSSnapIn-Eigenschaft und die Module-Eigenschaft des **ProviderInfo** -Objekts, das `Get-PSProvider` zurückgibt.
Die Werte dieser Eigenschaften enthalten den Namen des Snap-Ins oder Moduls, das den Anbieter hinzufügt.

Der erste Befehl ruft alle Anbieter in der Sitzung ab und formatiert sie in einer Tabelle mit den Werten der Eigenschaften %%amp;quot;Name%%amp;quot;, %%amp;quot;Module%%amp;quot; und %%amp;quot;PSSnapin%%amp;quot;.

Der zweite Befehl verwendet das `Where-Object` Cmdlet, um die Anbieter zu erhalten, die vom **Microsoft. PowerShell. Security** -Snap-in stammen.

### Beispiel 4: Auflösen des Pfads der Eigenschaft "Home" des Dateisystem Anbieters

```powershell
C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

```powershell
PS C:\> (get-psprovider FileSystem).home
```

```Output
C:\Users\User01
```

Dieses Beispiel zeigt, dass das tildesymbol (~) den Wert der **Home** -Eigenschaft des File System-Anbieters darstellt.
Der **Home** -Eigenschafts Wert ist optional, aber für den **File System** -Anbieter ist er als `$env:homedrive\$env:homepath` oder definiert `$home` .

## PARAMETERS

### -Psprovider

Gibt die Namen der PowerShell-Anbieter an, über die dieses Cmdlet Informationen abruft.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### String[]

Sie können eine oder mehrere Anbieter namens Zeichenfolgen über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### System. Management. Automation. ProviderInfo

Dieses Cmdlet gibt Objekte zurück, die die PowerShell-Anbieter in der Sitzung darstellen.

## HINWEISE

## VERWANDTE LINKS

