---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Error
ms.openlocfilehash: c29115a65b46d38039d78b10eee293e6944cede5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213103"
---
# Get-Error

## ZUSAMMENFASSUNG

Ruft die letzten Fehlermeldungen aus der aktuellen Sitzung ab und zeigt diese an.

## SYNTAX

### Latest (Standard)

```
Get-Error [[-Newest] <Int32>] [<CommonParameters>]
```

### Fehler

```
Get-Error [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Error` Cmdlet wird ein **psextendederror** -Objekt abgerufen, das die aktuellen Fehlerdetails aus dem letzten in der Sitzung aufgetretenen Fehler darstellt.

`Get-Error`Mithilfe des **neuesten** Parameters können Sie mithilfe von eine angegebene Anzahl von Fehlern anzeigen, die in der aktuellen Sitzung aufgetreten sind.

Das- `Get-Error` Cmdlet empfängt auch Fehler Objekte aus einer Auflistung, z `$Error` . b., um mehrere Fehler aus der aktuellen Sitzung anzuzeigen.

## BEISPIELE

### Beispiel 1: erhalten der neuesten Fehlerdetails

In diesem Beispiel werden `Get-Error` die Details des letzten Fehlers angezeigt, der in der aktuellen Sitzung aufgetreten ist.

```powershell
Get-Childitem -path /NoRealDirectory
Get-Error
```

```
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.

Exception             :
    ErrorRecord          :
        Exception             :
            Message : Cannot find path 'C:\NoRealDirectory' because it does not exist.
            HResult : -2146233087
        TargetObject          : C:\NoRealDirectory
        CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [], ParentContainsErrorRecordException
        FullyQualifiedErrorId : PathNotFound
    ItemName             : C:\NoRealDirectory
    SessionStateCategory : Drive
    TargetSite           :
        Name          : GetChildItems
        DeclaringType : System.Management.Automation.SessionStateInternal
        MemberType    : Method
        Module        : System.Management.Automation.dll
    StackTrace           :
   at System.Management.Automation.SessionStateInternal.GetChildItems(String path, Boolean recurse, UInt32 depth,
CmdletProviderContext context)
   at System.Management.Automation.ChildItemCmdletProviderIntrinsics.Get(String path, Boolean recurse, UInt32
depth, CmdletProviderContext context)
   at Microsoft.PowerShell.Commands.GetChildItemCommand.ProcessRecord()
    Message              : Cannot find path 'C:\NoRealDirectory' because it does not exist.
    Source               : System.Management.Automation
    HResult              : -2146233087
TargetObject          : C:\NoRealDirectory
CategoryInfo          : ObjectNotFound: (C:\NoRealDirectory:String) [Get-ChildItem], ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
InvocationInfo        :
    MyCommand        : Get-ChildItem
    ScriptLineNumber : 1
    OffsetInLine     : 1
    HistoryId        : 57
    Line             : Get-Childitem -path c:\NoRealDirectory
    PositionMessage  : At line:1 char:1
                       + Get-Childitem -path c:\NoRealDirectory
                       + ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    InvocationName   : Get-Childitem
    CommandOrigin    : Internal
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo :
```

### Beispiel 2: erhalten der angegebenen Anzahl von Fehlermeldungen, die in der aktuellen Sitzung aufgetreten sind

Dieses Beispiel zeigt, wie `Get-Error` mit dem **neuesten** Parameter verwendet wird. In diesem Beispiel gibt **Latest** die Details zu den drei neuesten Fehlern zurück, die in dieser Sitzung aufgetreten sind.

```powershell
Get-Error -Newest 3
```

### Beispiel 3: Senden einer Auflistung von Fehlern, um ausführliche Meldungen zu empfangen

Die `$Error` Automatische Variable enthält ein Array von Fehler Objekten in der aktuellen Sitzung. Das Array von-Objekten kann an weitergeleitet werden `Get-Error` , um ausführliche Fehlermeldungen zu empfangen.

In diesem Beispiel `$Error` wird an das `Get-Error` Cmdlet weitergeleitet. Das Ergebnis ist eine Liste detaillierter Fehlermeldungen, ähnlich wie im Ergebnis 1.

```powershell
$Error | Get-Error
```

## PARAMETERS

### -Latest

Gibt die Anzahl der anzuzeigenden Fehler an, die in der aktuellen Sitzung aufgetreten sind.

```yaml
Type: System.Int32
Parameter Sets: Newest
Aliases: Last

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Dieser Parameter wird für Pipeline Eingaben verwendet.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Error
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### PSObject

Unterstützt Eingaben aus beliebigen **psobject** , aber die Ergebnisse variieren, es sei denn, es wird ein **ErrorRecord** -oder **Exception** -Objekt bereitgestellt.

## AUSGABEN

### System. Management. Automation. ErrorRecord # psextendecoderror

Ausgabe in einem **psextendederror** -Objekt.

## HINWEISE

`Get-Error` akzeptiert Pipeline Eingaben. Beispiel: `$Error | Get-Error`.

## VERWANDTE LINKS

[about_Try_Catch_Finally](../Microsoft.PowerShell.Core/About/about_Try_Catch_Finally.md)
