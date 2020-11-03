---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: 4b9b466be3d52877056b948e4cc373991784416a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214540"
---
# Remove-PSDrive

## ZUSAMMENFASSUNG
Löscht temporäre PowerShell-Laufwerke und trennt die Verbindung mit zugeordneten Netzlaufwerken.

## SYNTAX

### Name (Standard)

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### LiteralName

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Remove-PSDrive` Cmdlet werden temporäre PowerShell-Laufwerke gelöscht, die mithilfe des- `New-PSDrive` Cmdlets erstellt wurden.

Ab Windows PowerShell 3,0 werden `Remove-PSDrive` von auch zugeordnete Netzwerklaufwerke getrennt, einschließlich, aber nicht beschränkt auf Laufwerke, die mit dem- `Persist` Parameter von erstellt wurden `New-PSDrive` .

`Remove-PSDrive` physische oder logische Windows-Laufwerke können nicht gelöscht werden.

Ab Windows PowerShell 3,0 wird von PowerShell automatisch ein PSDrive zum Dateisystem hinzugefügt, das das neue Laufwerk darstellt, wenn ein externes Laufwerk mit dem Computer verbunden ist.
PowerShell muss nicht neu gestartet werden.
Ebenso wird beim Trennen eines externen Laufwerks mit dem Computer das PSDrive, das das entfernte Laufwerk darstellt, von PowerShell automatisch gelöscht.

## BEISPIELE

### Beispiel 1: Entfernen eines Dateisystem Laufwerks

Mit diesem Befehl wird ein temporäres Dateisystemlaufwerk namens %%amp;quot;smp%%amp;quot; entfernt.

```powershell
Remove-PSDrive -Name smp
```

### Beispiel 2: Entfernen von zugeordneten Netzlaufwerken

Dieser Befehl verwendet `Remove-PSDrive` , um die Verbindung zwischen den X: und S: zugeordneten Netzwerklaufwerken zu trennen.

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## PARAMETERS

### -Force

Entfernt das aktuelle PowerShell-Laufwerk.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralName

Gibt den Namen des Laufwerks an.

Der Wert von **LiteralName** wird genau so verwendet, wie er eingegeben wurde.
Es werden keine Zeichen als Platzhalter interpretiert.
Wenn der Name Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen (') einschließen.
Einfache Anführungszeichen weisen PowerShell an, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt die Namen der zu entfernenden Laufwerke an.
Geben Sie keinen Doppelpunkt (:) nach dem Laufwerknamen ein.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Psprovider

Gibt ein Array von **psprovider** -Objekten an.
Mit diesem Cmdlet werden alle Laufwerke, die dem angegebenen PowerShell-Anbieter zugeordnet sind, entfernt und getrennt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Bereich

Gibt einen Bereich für das Laufwerk an.
Die zulässigen Werte für diesen Parameter lauten: Global, local und Script oder eine Zahl relativ zum aktuellen Bereich. Bereiche mit der Zahl 0 bis zur Anzahl der Bereiche. Die aktuelle Bereichs Nummer ist 0 und das übergeordnete Element ist 1.
Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseTransaction

Schließt den Befehl in die aktive Transaktion ein.
Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.
Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.Management.Automation.PSDrivin FO

Sie können ein Laufwerks Objekt, z. b. ein vom `Get-PSDrive` Cmdlet, an das `Remove-PSDrive` Cmdlet weiterreichen.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

- Das `Remove-PSDrive` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von einem beliebigen PowerShell-Anbieter verfügbar gemacht werden. Führen Sie die Anbieter in Ihrer Sitzung mithilfe des Cmdlets `Get-PSProvider` auf. Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Get-PSDrive](Get-PSDrive.md)

[New-PSDrive](New-PSDrive.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
