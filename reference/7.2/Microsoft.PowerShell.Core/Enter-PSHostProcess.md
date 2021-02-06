---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 85cbc9d012781873dddaf2a7d220a0e478dcbda2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605364"
---
# <span data-ttu-id="daab8-102">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="daab8-102">Enter-PSHostProcess</span></span>

## <span data-ttu-id="daab8-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="daab8-103">SYNOPSIS</span></span>
<span data-ttu-id="daab8-104">Stellt eine Verbindung mit einer interaktiven Sitzung mit einem lokalen Prozess her und wechselt in diese.</span><span class="sxs-lookup"><span data-stu-id="daab8-104">Connects to and enters into an interactive session with a local process.</span></span>

## <span data-ttu-id="daab8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="daab8-105">SYNTAX</span></span>

### <span data-ttu-id="daab8-106">Processidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="daab8-106">ProcessIdParameterSet (Default)</span></span>

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="daab8-107">Processparameterset</span><span class="sxs-lookup"><span data-stu-id="daab8-107">ProcessParameterSet</span></span>

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="daab8-108">Processnameparameterset</span><span class="sxs-lookup"><span data-stu-id="daab8-108">ProcessNameParameterSet</span></span>

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="daab8-109">Pshostprocessinfonoparameterset</span><span class="sxs-lookup"><span data-stu-id="daab8-109">PSHostProcessInfoParameterSet</span></span>

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="daab8-110">Pipameparameterset</span><span class="sxs-lookup"><span data-stu-id="daab8-110">PipeNameParameterSet</span></span>

```
Enter-PSHostProcess -CustomPipeName <String> [<CommonParameters>]
```

## <span data-ttu-id="daab8-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="daab8-111">DESCRIPTION</span></span>

<span data-ttu-id="daab8-112">`Enter-PSHostProcess`Mit dem-Cmdlet wird eine Verbindung mit einer interaktiven Sitzung hergestellt und mit einem lokalen Prozess verknüpft.</span><span class="sxs-lookup"><span data-stu-id="daab8-112">The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process.</span></span> <span data-ttu-id="daab8-113">Ab PowerShell 6,2 wird dieses Cmdlet auf nicht-Windows-Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="daab8-113">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

<span data-ttu-id="daab8-114">Anstatt einen neuen Prozess zum Hosten von PowerShell zu erstellen und eine Remote Sitzung auszuführen, wird die interaktive Remote Sitzung in einem vorhandenen Prozess ausgeführt, auf dem bereits PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="daab8-114">Instead of creating a new process to host PowerShell and run a remote session, the remote, interactive session is run in an existing process that is already running PowerShell.</span></span> <span data-ttu-id="daab8-115">Wenn Sie mit einer Remote Sitzung für einen angegebenen Prozess interagieren, können Sie laufende Runspaces auflisten und dann einen zu debuggenden Runspace auswählen, indem Sie entweder `Debug-Runspace` oder Ausführen `Enable-RunspaceDebug` .</span><span class="sxs-lookup"><span data-stu-id="daab8-115">When you are interacting with a remote session on a specified process, you can enumerate running runspaces, and then select a runspace to debug by running either `Debug-Runspace` or `Enable-RunspaceDebug`.</span></span>

<span data-ttu-id="daab8-116">Für den Prozess, den Sie eingeben möchten, muss PowerShell (System.Management.Automation.dll) gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="daab8-116">The process that you want to enter must be hosting PowerShell (System.Management.Automation.dll).</span></span>
<span data-ttu-id="daab8-117">Sie müssen entweder Mitglied der Gruppe "Administratoren" auf dem Computer sein, auf dem der Prozess gefunden wurde, oder Sie müssen der Benutzer sein, der das Skript ausgeführt hat, das den Prozess gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="daab8-117">You must be either a member of the Administrators group on the computer on which the process is found, or you must be the user who is running the script that started the process.</span></span>

<span data-ttu-id="daab8-118">Nachdem Sie einen zu debuggenden Runspace ausgewählt haben, wird eine remotedebuggingsitzung für den Runspace geöffnet, wenn Sie entweder einen Befehl ausführen oder im Debugger angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="daab8-118">After you have selected a runspace to debug, a remote debug session is opened for the runspace if it is either currently running a command or is stopped in the debugger.</span></span> <span data-ttu-id="daab8-119">Anschließend können Sie das Runspace-Skript genauso Debuggen wie andere Remote Sitzungs Skripts.</span><span class="sxs-lookup"><span data-stu-id="daab8-119">You can then debug the runspace script in the same way you would debug other remote session scripts.</span></span>

<span data-ttu-id="daab8-120">Trennen Sie von einer Debugsitzung und dann der interaktiven Sitzung mit dem Prozess, indem Sie "beenden" zweimal ausführen, oder beenden Sie die Ausführung des Skripts, indem Sie den vorhandenen Debugger beenden-Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="daab8-120">Detach from a debugging session, and then the interactive session with the process, by running exit twice, or stop script execution by running the existing debugger quit command.</span></span>

<span data-ttu-id="daab8-121">Wenn Sie einen Prozess mithilfe des **Name** -Parameters angeben und nur ein Prozess mit dem angegebenen Namen gefunden wird, wird der Prozess eingegeben.</span><span class="sxs-lookup"><span data-stu-id="daab8-121">If you specify a process by using the **Name** parameter, and there is only one process found with the specified name, the process is entered.</span></span> <span data-ttu-id="daab8-122">Wenn mehr als ein Prozess mit dem angegebenen Namen gefunden wird, gibt PowerShell einen Fehler zurück und listet alle Prozesse mit dem angegebenen Namen auf.</span><span class="sxs-lookup"><span data-stu-id="daab8-122">If more than one process with the specified name is found, PowerShell returns an error, and lists all processes found with the specified name.</span></span>

<span data-ttu-id="daab8-123">Um das Anfügen an Prozesse auf Remote Computern zu unterstützen, `Enter-PSHostProcess` ist das Cmdlet auf einem angegebenen Remote Computer aktiviert, sodass Sie einen lokalen Prozess innerhalb einer PowerShell-Remote Sitzung anfügen können.</span><span class="sxs-lookup"><span data-stu-id="daab8-123">To support attaching to processes on remote computers, the `Enter-PSHostProcess` cmdlet is enabled in a specified remote computer, so that you can attach to a local process within a remote PowerShell session.</span></span>

## <span data-ttu-id="daab8-124">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="daab8-124">EXAMPLES</span></span>

### <span data-ttu-id="daab8-125">Beispiel 1: Starten des Debuggens eines Runspace innerhalb des PowerShell ISE-Prozesses</span><span class="sxs-lookup"><span data-stu-id="daab8-125">Example 1: Start debugging a runspace within the PowerShell ISE process</span></span>

<span data-ttu-id="daab8-126">In diesem Beispiel führen Sie in `Enter-PSHostProcess` der PowerShell-Konsole aus, um den PowerShell ISE-Prozess einzugeben.</span><span class="sxs-lookup"><span data-stu-id="daab8-126">In this example, you run `Enter-PSHostProcess` from within the PowerShell console to enter the PowerShell ISE process.</span></span> <span data-ttu-id="daab8-127">In der sich ergebenden interaktiven Sitzung finden Sie einen Runspace, den Sie debuggen möchten, indem Sie Ausführen `Get-Runspace` und dann den Runspace Debuggen.</span><span class="sxs-lookup"><span data-stu-id="daab8-127">In the resulting interactive session, you can find a runspace that you want to debug by running `Get-Runspace`, and then debug the runspace.</span></span>

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

## <span data-ttu-id="daab8-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="daab8-128">PARAMETERS</span></span>

### <span data-ttu-id="daab8-129">-Appdomainname</span><span class="sxs-lookup"><span data-stu-id="daab8-129">-AppDomainName</span></span>

<span data-ttu-id="daab8-130">Gibt einen Anwendungs **Domänen Namen** an, mit dem eine Verbindung hergestellt werden soll, wenn dieser nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="daab8-130">Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain**.</span></span> <span data-ttu-id="daab8-131">Verwenden `Get-PSHostProcessInfo` Sie, um die Anwendungs Domänen Namen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="daab8-131">Use `Get-PSHostProcessInfo` to display the application domain names.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessIdParameterSet, ProcessParameterSet, ProcessNameParameterSet, PSHostProcessInfoParameterSet
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="daab8-132">-Hostprocessinfo</span><span class="sxs-lookup"><span data-stu-id="daab8-132">-HostProcessInfo</span></span>

<span data-ttu-id="daab8-133">Gibt ein **pshostprocessinfo** -Objekt an, das mit PowerShell verbunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="daab8-133">Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell.</span></span> <span data-ttu-id="daab8-134">Verwenden `Get-PSHostProcessInfo` Sie, um das-Objekt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="daab8-134">Use `Get-PSHostProcessInfo` to get the object.</span></span>

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

### <span data-ttu-id="daab8-135">-Id</span><span class="sxs-lookup"><span data-stu-id="daab8-135">-Id</span></span>

<span data-ttu-id="daab8-136">Gibt einen Prozess mit der Prozess-ID an.</span><span class="sxs-lookup"><span data-stu-id="daab8-136">Specifies a process by the process ID.</span></span> <span data-ttu-id="daab8-137">Führen Sie das-Cmdlet aus, um eine Prozess-ID zu erhalten `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="daab8-137">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="daab8-138">-Name</span><span class="sxs-lookup"><span data-stu-id="daab8-138">-Name</span></span>

<span data-ttu-id="daab8-139">Gibt einen Prozess anhand des Prozess namens an.</span><span class="sxs-lookup"><span data-stu-id="daab8-139">Specifies a process by the process name.</span></span> <span data-ttu-id="daab8-140">Um einen Prozessnamen zu erhalten, führen Sie das- `Get-Process` Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="daab8-140">To get a process name, run the `Get-Process` cmdlet.</span></span> <span data-ttu-id="daab8-141">Sie können Prozessnamen auch aus dem Dialogfeld Eigenschaften eines Prozesses im Task-Manager erhalten.</span><span class="sxs-lookup"><span data-stu-id="daab8-141">You can also get process names from the Properties dialog box of a process in Task Manager.</span></span>

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

### <span data-ttu-id="daab8-142">-Prozess</span><span class="sxs-lookup"><span data-stu-id="daab8-142">-Process</span></span>

<span data-ttu-id="daab8-143">Gibt einen Prozess vom Prozess Objekt an.</span><span class="sxs-lookup"><span data-stu-id="daab8-143">Specifies a process by the process object.</span></span> <span data-ttu-id="daab8-144">Die einfachste Möglichkeit, diesen Parameter zu verwenden, besteht darin, die Ergebnisse eines Befehls zu speichern, der den `Get-Process` Prozess zurückgibt, den Sie in eine Variable eingeben möchten, und dann die Variable als Wert dieses Parameters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="daab8-144">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="daab8-145">-Custompipame</span><span class="sxs-lookup"><span data-stu-id="daab8-145">-CustomPipeName</span></span>

<span data-ttu-id="daab8-146">Ruft den Namen des benutzerdefinierten Named Pipe für die Verbindung ab oder legt ihn fest.</span><span class="sxs-lookup"><span data-stu-id="daab8-146">Gets or sets the custom named pipe name to connect to.</span></span> <span data-ttu-id="daab8-147">Dies wird in der Regel in Verbindung mit verwendet `pwsh -CustomPipeName` .</span><span class="sxs-lookup"><span data-stu-id="daab8-147">This is usually used in conjunction with `pwsh -CustomPipeName`.</span></span>

<span data-ttu-id="daab8-148">Dieser Parameter wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="daab8-148">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.String
Parameter Sets: PipeNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="daab8-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="daab8-149">CommonParameters</span></span>

<span data-ttu-id="daab8-150">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="daab8-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="daab8-151">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="daab8-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="daab8-152">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="daab8-152">INPUTS</span></span>

### <span data-ttu-id="daab8-153">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="daab8-153">System.Diagnostics.Process</span></span>

## <span data-ttu-id="daab8-154">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="daab8-154">OUTPUTS</span></span>

## <span data-ttu-id="daab8-155">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="daab8-155">NOTES</span></span>

<span data-ttu-id="daab8-156">`Enter-PSHostProcess` der Vorgang kann nicht in die PowerShell-Sitzung eingegeben werden, in der Sie den Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="daab8-156">`Enter-PSHostProcess` cannot enter the process of the PowerShell session in which you are running the command.</span></span> <span data-ttu-id="daab8-157">Sie können jedoch den Prozess einer anderen PowerShell-Sitzung oder eine PowerShell ISE-Sitzung eingeben, die zur gleichen Zeit wie die Sitzung ausgeführt wird, in der Sie ausgeführt werden `Enter-PSHostProcess` .</span><span class="sxs-lookup"><span data-stu-id="daab8-157">You can, however, enter the process of another PowerShell session, or a PowerShell ISE session that is running at the same time as the session in which you are running `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="daab8-158">`Enter-PSHostProcess` Es können nur die Prozesse eingegeben werden, von denen PowerShell gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="daab8-158">`Enter-PSHostProcess` can enter only those processes that are hosting PowerShell.</span></span> <span data-ttu-id="daab8-159">Das heißt, Sie haben das PowerShell-Modul geladen.</span><span class="sxs-lookup"><span data-stu-id="daab8-159">That is, they have loaded the PowerShell engine.</span></span>

<span data-ttu-id="daab8-160">Um einen Prozess innerhalb des Prozesses zu beenden, geben Sie **Exit** ein, und drücken Sie dann die <kbd>Eingabe</kbd>Taste.</span><span class="sxs-lookup"><span data-stu-id="daab8-160">To exit a process from within the process, type **exit**, and then press <kbd>Enter</kbd>.</span></span>

<span data-ttu-id="daab8-161">Vor PowerShell 7.1 unterstützte das Remoting über SSH keine Remotesitzungen über einen zweiten Hop.</span><span class="sxs-lookup"><span data-stu-id="daab8-161">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="daab8-162">Diese Funktion war auf Sitzungen beschränkt, die WinRM verwendeten.</span><span class="sxs-lookup"><span data-stu-id="daab8-162">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="daab8-163">PowerShell 7.1 ermöglicht, dass `Enter-PSSession` und `Enter-PSHostProcess` in jeder interaktiven Remotesitzung funktionieren.</span><span class="sxs-lookup"><span data-stu-id="daab8-163">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <span data-ttu-id="daab8-164">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="daab8-164">RELATED LINKS</span></span>

[<span data-ttu-id="daab8-165">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="daab8-165">Exit-PSHostProcess</span></span>](Exit-PSHostProcess.md)

[<span data-ttu-id="daab8-166">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="daab8-166">Get-PSHostProcessInfo</span></span>](Get-PSHostProcessInfo.md)

