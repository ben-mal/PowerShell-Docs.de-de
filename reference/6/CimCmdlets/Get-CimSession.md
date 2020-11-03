---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimsession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimSession
ms.openlocfilehash: c40367d0458c3670b9d684cd0c3b4b2a3631b3e4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215159"
---
# Get-CimSession

## ZUSAMMENFASSUNG
Ruft die CIM-Sitzungs Objekte aus der aktuellen Sitzung ab.

## SYNTAX

### Computernameset (Standard)

```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### Sessionidset

```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### Instanceidset

```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### Nameset

```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## DESCRIPTION

Standardmäßig ruft das Cmdlet alle CIM-Sitzungen ab, die in der aktuellen PowerShell-Sitzung erstellt wurden. Sie können die Parameter von verwenden, `Get-CimSession` um die Sitzungen für bestimmte Computer zu erhalten, oder Sie können Sitzungen anhand ihrer Namen oder anderer Bezeichner identifizieren. `Get-CimSession` Ruft keine CIM-Sitzungen ab, die in anderen PowerShell-Sitzungen erstellt wurden oder auf anderen Computern erstellt wurden.

Weitere Informationen zu CIM-Sitzungen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

## BEISPIELE

### Beispiel 1: erhalten von CIM-Sitzungen aus der aktuellen PowerShell-Sitzung

In diesem Beispiel werden CIM-Sitzungen mithilfe von " [New-cimsession](New-CimSession.md)" erstellt, und anschließend werden die CIM-Sitzungen mit abgerufen `Get-CimSession` .

```powershell
New-CimSession -ComputerName Server01,Server02
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc3-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### Beispiel 2: beziehen der CIM-Sitzungen auf einem bestimmten Computer

In diesem Beispiel werden die CIM-Sitzungen abgerufen, die mit dem Computer namens **Server02** verbunden sind.

```powershell
Get-CimSession -ComputerName Server02
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### Beispiel 3: erhalten Sie eine Liste mit CIM-Sitzungen, und formatieren Sie dann die Liste.

In diesem Beispiel werden alle CIM-Sitzungen in der aktuellen PowerShell-Sitzung abgerufen, und es wird eine Tabelle mit nur den Eigenschaften **Computername** und **InstanceId** angezeigt.

```powershell
Get-CimSession | Format-Table -Property ComputerName,InstanceId
```

```Output
ComputerName InstanceId
------------ ----------
Server01     d1413bc3-162a-4cb8-9aec-4d2c61253d59
Server02     c0095981-52c5-4e7f-a5bb-c4c680541710
```

### Beispiel 4: alle CIM-Sitzungen mit bestimmten Namen

In diesem Beispiel werden alle CIM-Sitzungen abgerufen, deren Namen mit " **Serv** " beginnen.

```powershell
Get-CimSession -ComputerName Serv*
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### Beispiel 5: beziehen einer bestimmten CIM-Sitzung

In diesem Beispiel wird die CIM-Sitzung mit der **ID** 2 abgerufen.

```powershell
Get-CimSession -ID 2
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

## PARAMETERS

### -ComputerName

Gibt den Namen des Computers an, mit dem CIM-Sitzungen verbunden werden sollen. Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Id

Gibt den Bezeichner der zu erzurufenden CIM-Sitzung an. Verwenden Sie für mehrere IDs Kommas, um die IDs zu trennen, oder verwenden Sie den Bereichs Operator ( `..` ), um einen Bereich von IDs anzugeben. Eine **ID** ist eine Ganzzahl, die die CIM-Sitzung innerhalb der aktuellen PowerShell-Sitzung eindeutig identifiziert.

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

Gibt die Instanz-IDs der zu erzurufenden CIM-Sitzung an.

**InstanceId** ist ein global eindeutiger Bezeichner (GUID), der eine CIM-Sitzung eindeutig identifiziert. Die **InstanceId** ist eindeutig, auch wenn mehrere Sitzungen in PowerShell ausgeführt werden.

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

Ruft eine oder mehrere CIM-Sitzungen ab, die die angegebenen anzeigen Amen enthalten. Platzhalterzeichen sind zulässig.

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

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

## AUSGABEN

### Microsoft.Management.Infrastructure.CimSession

## HINWEISE

## VERWANDTE LINKS

[Format-Table](../microsoft.powershell.utility/format-table.md)

[New-CimSession](New-CimSession.md)

[Remove-CimSession](remove-cimsession.md)

[about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)
