---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-cimsession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimSession
ms.openlocfilehash: 4c7de7a8ad3ae2a9e69cf4a00f9b9140a4294f4e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215132"
---
# Remove-CimSession

## ZUSAMMENFASSUNG
Entfernt mindestens eine CIM-Sitzung.

## SYNTAX

### Cimsessionset (Standard)

```
Remove-CimSession [-CimSession] <CimSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Computernameset

```
Remove-CimSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Sessionidset

```
Remove-CimSession [-Id] <UInt32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Instanceidset

```
Remove-CimSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nameset

```
Remove-CimSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Remove-CimSession` Cmdlet werden ein oder mehrere CIM-Sitzungs Objekte aus der lokalen PowerShell-Sitzung entfernt.

## BEISPIELE

### Beispiel 1: Entfernen aller CIM-Sitzungen

In diesem Beispiel werden alle verfügbaren CIM-Sitzungen auf dem lokalen Computer mithilfe des Cmdlets [Get-cimsession](Get-CimSession.md) abgerufen und dann mithilfe von entfernt `Remove-CimSession` .

```powershell
Get-CimSession | Remove-CimSession
```

### Beispiel 2: Entfernen einer bestimmten CIM-Sitzung

In diesem Beispiel wird die CIM-Sitzung mit dem **ID** -Wert 5 entfernt.

```powershell
Remove-CimSession -Id 5
```

### Beispiel 3: Anzeigen der Liste der zu entfernenden CIM-Sitzungen mit dem WhatIf-Parameter

In diesem Beispiel wird der allgemeine Parameter **WhatIf** verwendet, um anzugeben, dass die Deinstallation nicht ausgeführt werden soll, sondern nur, was geschehen würde, wenn Sie ausgeführt würde.

```powershell
Remove-CimSession -Name a* -WhatIf
```

## PARAMETERS

### -CimSession

Gibt die Sitzungs Objekte der zu schließenden CIM-Sitzungen an.

Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, mit dem die CIM-Sitzung erstellt oder abgerufen wird, z [`New-CimSession`](New-CimSession.md) [`Get-CimSession`](Get-CimSession.md) . b. die Cmdlets oder.
Weitere Informationen finden Sie unter [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ComputerName

Gibt ein Array von Namen von Computern an. Entfernt die Sitzungen, die eine Verbindung zu den angegebenen Computern herstellen. Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) oder einen NetBIOS-Namen angeben.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Id

Gibt die ID der zu entfernenden CIM-Sitzung an. Geben Sie mindestens eine durch Kommas getrennte ID an, oder verwenden Sie den Bereichs Operator ( `..` ), um einen Bereich von IDs anzugeben. Eine **ID** ist eine Ganzzahl, die die CIM-Sitzung in der aktuellen PowerShell-Sitzung eindeutig identifiziert.

Weitere Informationen zum Bereichs Operator finden Sie unter [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).

```yaml
Type: System.UInt32[]
Parameter Sets: SessionIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Gibt die Instanz-ID der zu entfernenden CIM-Sitzung an. **InstanceId** ist eine GUID (Global Unique Identifier), die eine CIM-Sitzung eindeutig identifiziert. Die **InstanceId** ist eindeutig, auch wenn mehrere Sitzungen in PowerShell ausgeführt werden.

Die **InstanceId** wird in der **InstanceId-** Eigenschaft des Objekts gespeichert, das eine CIM-Sitzung darstellt.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt den anzeigen amen der zu entfernenden CIM-Sitzung an. Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.

```yaml
Type: System.String[]
Parameter Sets: NameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Dieses Cmdlet akzeptiert keine Eingabe Objekte.

## AUSGABEN

### System.Object

Dieses Cmdlet gibt ein Objekt zurück, das CIM-Sitzungsinformationen enthält.

## HINWEISE

## VERWANDTE LINKS

[Get-CimSession](Get-CimSession.md)

[New-CimSession](New-CimSession.md)

[about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)
