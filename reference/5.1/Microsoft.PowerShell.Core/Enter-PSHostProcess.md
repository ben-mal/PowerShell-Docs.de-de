---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 56b8cef1911d1365f9568483921bfb49fbc32451
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212071"
---
# Enter-PSHostProcess

## ZUSAMMENFASSUNG
Stellt eine Verbindung mit einer interaktiven Sitzung mit einem lokalen Prozess her und wechselt in diese.

## SYNTAX

### Processidparameterset (Standard)

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### Processparameterset

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### Processnameparameterset

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### Pshostprocessinfonoparameterset

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

## DESCRIPTION

`Enter-PSHostProcess`Mit dem-Cmdlet wird eine Verbindung mit einer interaktiven Sitzung hergestellt und mit einem lokalen Prozess verknüpft.

Anstatt einen neuen Prozess zum Hosten von PowerShell zu erstellen und eine Remote Sitzung auszuführen, wird die interaktive Remote Sitzung in einem vorhandenen Prozess ausgeführt, auf dem bereits PowerShell ausgeführt wird. Wenn Sie mit einer Remote Sitzung für einen angegebenen Prozess interagieren, können Sie laufende Runspaces auflisten und dann einen zu debuggenden Runspace auswählen, indem Sie entweder `Debug-Runspace` oder Ausführen `Enable-RunspaceDebug` .

Für den Prozess, den Sie eingeben möchten, muss PowerShell (System.Management.Automation.dll) gehostet werden.
Sie müssen entweder Mitglied der Gruppe "Administratoren" auf dem Computer sein, auf dem der Prozess gefunden wurde, oder Sie müssen der Benutzer sein, der das Skript ausgeführt hat, das den Prozess gestartet hat.

Nachdem Sie einen zu debuggenden Runspace ausgewählt haben, wird eine remotedebuggingsitzung für den Runspace geöffnet, wenn Sie entweder einen Befehl ausführen oder im Debugger angehalten wird. Anschließend können Sie das Runspace-Skript genauso Debuggen wie andere Remote Sitzungs Skripts.

Trennen Sie von einer Debugsitzung und dann der interaktiven Sitzung mit dem Prozess, indem Sie "beenden" zweimal ausführen, oder beenden Sie die Ausführung des Skripts, indem Sie den vorhandenen Debugger beenden-Befehl ausführen.

Wenn Sie einen Prozess mithilfe des **Name** -Parameters angeben und nur ein Prozess mit dem angegebenen Namen gefunden wird, wird der Prozess eingegeben. Wenn mehr als ein Prozess mit dem angegebenen Namen gefunden wird, gibt PowerShell einen Fehler zurück und listet alle Prozesse mit dem angegebenen Namen auf.

Um das Anfügen an Prozesse auf Remote Computern zu unterstützen, `Enter-PSHostProcess` ist das Cmdlet auf einem angegebenen Remote Computer aktiviert, sodass Sie einen lokalen Prozess innerhalb einer PowerShell-Remote Sitzung anfügen können.

## BEISPIELE

### Beispiel 1: Starten des Debuggens eines Runspace innerhalb des PowerShell ISE-Prozesses

In diesem Beispiel führen Sie in `Enter-PSHostProcess` der PowerShell-Konsole aus, um den PowerShell ISE-Prozess einzugeben. In der sich ergebenden interaktiven Sitzung finden Sie einen Runspace, den Sie debuggen möchten, indem Sie Ausführen `Get-Runspace` und dann den Runspace Debuggen.

```
PS C:\> Enter-PSHostProcess -Name powershell_ise
[Process:1520]: PS C:\Test\Documents>

Next, get available runspaces within the process you have entered.
PS C:\> [Process:1520]: PS C:\>  Get-Runspace
Id    Name          InstanceId                               State           Availability
--    -------       -----------                              ------          -------------
1     Runspace1     2d91211d-9cce-42f0-ab0e-71ac258b32b5     Opened          Available
2     Runspace2     a3855043-cb16-424a-a616-685360c3763b     Opened          RemoteDebug
3     MyLocalRS     2236dbd8-2105-4dec-a15a-a27d0bfaacb5     Opened          LocalDebug
4     MyRunspace    771356e9-8c44-4b70-9de5-dd17cb41e48e     Opened          Busy
5     Runspace8     3e517382-a97a-49ba-9c3c-fd21f6664288     Broken          None

The runspace objects returned by Get-Runspace also have a NoteProperty called ScriptStackTrace of
the running command stack, if available.Next, debug runspace ID 4, that is running another user's
long-running script. From the list returned from Get-Runspace, note that the runspace state is
Opened, and Availability is Busy, meaning that the runspace is still running the long-running
script.

PS C:\> [Process:1520]: PS C:\>  (Get-Runspace -Id 4).ScriptStackTrace
Command                    Arguments                           Location
-------                    ---------                           --------
MyModuleWorkflowF1         {}                                  TestNoFile3.psm1: line 6
WFTest1                    {}                                  TestNoFile2.ps1: line 14
TestNoFile2.ps1            {}                                  TestNoFile2.ps1: line 22
<ScriptBlock>              {}                                  <No file>

Start an interactive debugging session with this runspace by running the Debug-Runspace cmdlet.

PS C:\> [Process: 1520]: PS C:\>  Debug-Runspace -Id 4
Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'

At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

[Process: 1520]: [RSDBG: 4]: PS C:\> >

After you are finished debugging, allow the script to continue running without the debugger attached
by running the exit debugger command. Alternatively, you can quit the debugger with the q or Stop
commands.

PS C:\> [Process:346]: [RSDBG: 3]: PS C:\> > exit
[Process:1520]: PS C:\>

When you are finished working in the process, exit the process by running the Exit-PSHostProcess
cmdlet. This returns you to the PS C:\> prompt.

PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

## PARAMETERS

### -Appdomainname

Gibt einen Anwendungs **Domänen Namen** an, mit dem eine Verbindung hergestellt werden soll, wenn dieser nicht angegeben wird. Verwenden `Get-PSHostProcessInfo` Sie, um die Anwendungs Domänen Namen anzuzeigen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### -Hostprocessinfo

Gibt ein **pshostprocessinfo** -Objekt an, das mit PowerShell verbunden werden kann. Verwenden `Get-PSHostProcessInfo` Sie, um das-Objekt zu erhalten.

```yaml
Type: Microsoft.PowerShell.Commands.PSHostProcessInfo
Parameter Sets: PSHostProcessInfoParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id

Gibt einen Prozess mit der Prozess-ID an. Führen Sie das-Cmdlet aus, um eine Prozess-ID zu erhalten `Get-Process` .

```yaml
Type: System.Int32
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt einen Prozess anhand des Prozess namens an. Um einen Prozessnamen zu erhalten, führen Sie das- `Get-Process` Cmdlet aus. Sie können Prozessnamen auch aus dem Dialogfeld Eigenschaften eines Prozesses im Task-Manager erhalten.

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prozess

Gibt einen Prozess vom Prozess Objekt an. Die einfachste Möglichkeit, diesen Parameter zu verwenden, besteht darin, die Ergebnisse eines Befehls zu speichern, der den `Get-Process` Prozess zurückgibt, den Sie in eine Variable eingeben möchten, und dann die Variable als Wert dieses Parameters anzugeben.

```yaml
Type: System.Diagnostics.Process
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.Diagnostics.Process

## AUSGABEN

## HINWEISE

`Enter-PSHostProcess` der Vorgang kann nicht in die PowerShell-Sitzung eingegeben werden, in der Sie den Befehl ausführen. Sie können jedoch den Prozess einer anderen PowerShell-Sitzung oder eine PowerShell ISE-Sitzung eingeben, die zur gleichen Zeit wie die Sitzung ausgeführt wird, in der Sie ausgeführt werden `Enter-PSHostProcess` .

`Enter-PSHostProcess` Es können nur die Prozesse eingegeben werden, von denen PowerShell gehostet wird. Das heißt, Sie haben das PowerShell-Modul geladen.

Um einen Prozess innerhalb des Prozesses zu beenden, geben Sie **Exit** ein, und drücken Sie dann die <kbd>Eingabe</kbd>Taste.

## VERWANDTE LINKS

[Exit-PSHostProcess](Exit-PSHostProcess.md)

[Get-PSHostProcessInfo](Get-PSHostProcessInfo.md)
