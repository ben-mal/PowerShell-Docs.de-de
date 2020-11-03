---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/debug-runspace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Runspace
ms.openlocfilehash: fd1da10b3a64e0fe9b43dfec1289eebaf31ed739
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215860"
---
# Debug-Runspace

## ZUSAMMENFASSUNG
Startet eine interaktive Debugsitzung mit einem Runspace.

## SYNTAX

### Runspaceparameterset (Standard)

```
Debug-Runspace [-Runspace] <Runspace> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nameparameterset

```
Debug-Runspace [-Name] <String> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Idparameterset

```
Debug-Runspace [-Id] <Int32> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Instanceidparameterset

```
Debug-Runspace [-InstanceId] <Guid> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Debug-Runspace` Cmdlet wird eine interaktive Debugsitzung mit einem lokalen oder aktiven Remote-Runspace gestartet. Sie finden einen Runspace, den Sie debuggen möchten, indem Sie zuerst ausführen, `Get-Process` um Prozesse zu suchen, die mit PowerShell verknüpft sind, dann `Enter-PSHostProcess` mit der im **ID** -Parameter angegebenen Prozess-ID, die an den Prozess angehängt werden soll, und dann `Get-Runspace` Runspaces im PowerShell-Host Prozess auflisten.

Wenn Sie einen Runspace zum Debuggen ausgewählt haben und der Runspace aktuell einen Befehl oder ein Skript ausgeführt oder das Skript an einem Haltepunkt angehalten wurde, öffnet PowerShell eine Remotedebugsitzung für den Runspace. Sie können das Runspace-Skript genauso Debuggen, wie Remote Sitzungs Skripts debuggt werden.

Sie können nur an einen PowerShell-Host Prozess angefügt werden, wenn Sie ein Administrator auf dem Computer sind, auf dem der Prozess ausgeführt wird, oder wenn Sie das Skript ausführen, das Sie debuggen möchten. Außerdem ist es nicht möglich, den Host Prozess einzugeben, von dem die aktuelle PowerShell-Sitzung ausgeführt wird. Sie können nur einen Host Prozess eingeben, der eine andere PowerShell-Sitzung ausgeführt hat.

## BEISPIELE

### Beispiel 1: Debuggen eines Remoterunspace

```
PS C:\> Get-Process -ComputerName "WS10TestServer" -Name "*powershell*"

Handles      WS(K)   VM(M)      CPU(s)    Id  ProcessName
-------      -----   -----      ------    --  -----------
    377      69912     63     2.09      2420  powershell
    399     123396    829     4.48      1152  powershell_ise

PS C:\> Enter-PSSession -ComputerName "WS10TestServer"
[WS10TestServer]:PS C:\> Enter-PSHostProcess -Id 1152
[WS10TestServer:][Process:1152]: PS C:\Users\Test\Documents> Get-Runspace

Id Name            ComputerName    Type          State         Availability
-- ----            ------------    ----          -----         ------------
 1 Runspace1       WS10TestServer  Remote        Opened        Available
 2 RemoteHost      WS10TestServer  Remote        Opened        Busy

PS C:\> [WS10TestServer][Process:1152]: PS C:\Users\Test\Documents> Debug-Runspace -Id 2

Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'
At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Process:1152]: [RSDBG: 2]: PS C:\> >
```

In diesem Beispiel Debuggen Sie einen Runspace, der auf einem Remote Computer geöffnet ist, WS10TestServer. In der ersten Zeile des Befehls führen Sie `Get-Process` auf dem Remote Computer aus und Filtern nach Windows PowerShell-Host Prozessen. In diesem Beispiel möchten Sie die Prozess-ID 1152, den Windows PowerShell ISE Host Prozess Debuggen.

Im zweiten Befehl führen Sie aus, `Enter-PSSession` um eine Remote Sitzung auf WS10TestServer zu öffnen. Im dritten Befehl fügen Sie an den Windows PowerShell ISE Host Prozess an, der auf dem Remote Server ausgeführt wird, indem Sie Ausführen `Enter-PSHostProcess` und die ID des Host Prozesses angeben, den Sie im ersten Befehl abgerufen haben, 1152.

Im vierten Befehl Listen Sie verfügbare Runspaces für Prozess-ID 1152 auf, indem Sie Ausführen `Get-Runspace` .
Notieren Sie sich die ID des ausgelasteten Runspace. Es wird ein Skript ausgeführt, das Sie debuggen möchten.

Im letzten Befehl haben Sie mit dem Debuggen eines geöffneten Runspace begonnen, von dem ein Skript ausgeführt wird, TestWFVar1.ps1, indem ausgeführt `Debug-Runspace` wird und der Runspace mit der ID 2 identifiziert wird, indem der **ID** -Parameter hinzugefügt wird. Da es im Skript einen Haltepunkt gibt, wird der Debugger geöffnet.

## PARAMETERS

### -Id

Gibt die ID-Nummer eines Runspace an. Sie können ausführen `Get-Runspace` , um Runspace-IDs anzuzeigen.

```yaml
Type: System.Int32
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Gibt einen Runspace durch die Instanz-ID an, eine GUID, die Sie anzeigen können, indem Sie Ausführen `Get-Runspace` .

```yaml
Type: System.Guid
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt einen Runspace anhand seines Namens an. Sie können ausführen `Get-Runspace` , um die Namen der Runspaces anzuzeigen.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runspace

Gibt ein Runspace-Objekt an. Die einfachste Möglichkeit, einen Wert für diesen Parameter anzugeben, besteht darin, eine Variable anzugeben, die die Ergebnisse eines gefilterten `Get-Runspace` Befehls enthält.

```yaml
Type: System.Management.Automation.Runspaces.Runspace
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Default value: True
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
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -Breakall

{{Breakall-Beschreibung ausfüllen}}

```yaml
Type: System.Management.Automation.SwitchParameter
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

### System. Management. Automation. Runspaces. Runspace

Sie können die Ergebnisse eines Befehls über die Pipeline `Get-Runspace` an **Debug-Runspace übergeben.**

## AUSGABEN

## HINWEISE

`Debug-Runspace` funktioniert für Runspaces, die sich im geöffneten Zustand befinden. Wenn sich der Zustand eines Runspace von geöffnet in einen anderen Status ändert, wird der Runspace automatisch aus der Liste wird ausgeführt entfernt. Der Liste wird nur dann ein Runspace hinzugefügt, wenn die folgenden Kriterien erfüllt sind.

- Wenn Sie von "aufrufen-Command;" stammt. Das heißt, Sie verfügt über eine `Invoke-Command` GUID-ID.
- Wenn Sie von stammt, d `Debug-Runspace` . h., Sie verfügt über eine `Debug-Runspace` GUID-ID.
- Wenn Sie von einem PowerShell-Workflow stammt, und die zugehörige Workflow Auftrags-ID mit der aktuellen aktiven Debugger-Workflow Auftrags-ID übereinstimmt.

## VERWANDTE LINKS

[about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md)

[Debug-Job](../Microsoft.PowerShell.Core/Debug-Job.md)

[Get-Runspace](Get-Runspace.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)

[Enter-PSHostProcess](../Microsoft.PowerShell.Core/Enter-PSHostProcess.md)

[Enter-PSSession](../Microsoft.PowerShell.Core/Enter-PSSession.md)

