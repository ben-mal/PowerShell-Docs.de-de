---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disconnect-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-PSSession
ms.openlocfilehash: c0eed3d571cfb243c3f0ba4d0a4b7ddfaf4f04fb
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218479"
---
# <span data-ttu-id="1835c-103">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-103">Disconnect-PSSession</span></span>

## <span data-ttu-id="1835c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1835c-104">SYNOPSIS</span></span>
<span data-ttu-id="1835c-105">Trennt eine Verbindung.</span><span class="sxs-lookup"><span data-stu-id="1835c-105">Disconnects from a session.</span></span>

## <span data-ttu-id="1835c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1835c-106">SYNTAX</span></span>

### <span data-ttu-id="1835c-107">Sitzung (Standard)</span><span class="sxs-lookup"><span data-stu-id="1835c-107">Session (Default)</span></span>

```
Disconnect-PSSession [-Session] <PSSession[]> [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="1835c-108">Name</span><span class="sxs-lookup"><span data-stu-id="1835c-108">Name</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1835c-109">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1835c-109">InstanceId</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1835c-110">Id</span><span class="sxs-lookup"><span data-stu-id="1835c-110">Id</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1835c-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1835c-111">DESCRIPTION</span></span>

<span data-ttu-id="1835c-112">Das `Disconnect-PSSession` Cmdlet trennt eine PowerShell-Sitzung ("PSSession"), wie z. b. eine mit dem `New-PSSession` Cmdlet gestartete, aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="1835c-112">The `Disconnect-PSSession` cmdlet disconnects a PowerShell session ("PSSession"), such as one started by using the `New-PSSession` cmdlet, from the current session.</span></span> <span data-ttu-id="1835c-113">Dadurch befindet sich die PSSession in einem getrennten Zustand.</span><span class="sxs-lookup"><span data-stu-id="1835c-113">As a result, the PSSession is in a disconnected state.</span></span> <span data-ttu-id="1835c-114">Sie können von der aktuellen Sitzung oder einer anderen Sitzung auf dem lokalen bzw. einem anderen Computer eine Verbindung mit der getrennten PSSession herstellen.</span><span class="sxs-lookup"><span data-stu-id="1835c-114">You can connect to the disconnected PSSession from the current session or from another session on the local computer or a different computer.</span></span>

<span data-ttu-id="1835c-115">Das `Disconnect-PSSession` Cmdlet trennt nur geöffnete pssessions, die mit der aktuellen Sitzung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="1835c-115">The `Disconnect-PSSession` cmdlet disconnects only open PSSessions that are connected to the current session.</span></span> <span data-ttu-id="1835c-116">`Disconnect-PSSession` die Verbindung mit unterbrochenen oder geschlossenen pssessions oder interaktiven pssessions, die mithilfe des `Enter-PSSession` Cmdlets gestartet wurden, kann nicht getrennt werden, und es können keine pssessions getrennt werden, die mit anderen Sitzungen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="1835c-116">`Disconnect-PSSession` cannot disconnect broken or closed PSSessions, or interactive PSSessions started by using the `Enter-PSSession` cmdlet, and it cannot disconnect PSSessions that are connected to other sessions.</span></span>

<span data-ttu-id="1835c-117">Um erneut eine Verbindung mit einer getrennten PSSession herzustellen, verwenden Sie die `Connect-PSSession` `Receive-PSSession` Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="1835c-117">To reconnect to a disconnected PSSession, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span>

<span data-ttu-id="1835c-118">Wenn eine PSSession getrennt ist, werden die Befehle in der PSSession bis zum Ende ausgeführt, sofern keine Zeitüberschreitung für die PSSession eintritt oder die Befehle in der PSSession nicht durch einen vollen Ausgabepuffer blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="1835c-118">When a PSSession is disconnected, the commands in the PSSession continue to run until they complete, unless the PSSession times out or the commands in the PSSession are blocked by a full output buffer.</span></span> <span data-ttu-id="1835c-119">Um die Leerlaufzeitüberschreitung zu ändern, verwenden Sie den **IdleTimeoutSec** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1835c-119">To change the idle timeout, use the **IdleTimeoutSec** parameter.</span></span> <span data-ttu-id="1835c-120">Verwenden Sie zum Ändern des Ausgabepuffer Modus den **outputbufferingmode** -Parameter. Sie können auch den **indisconnectedsession** -Parameter des `Invoke-Command` Cmdlets verwenden, um einen Befehl in einer getrennten Sitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1835c-120">To change the output buffering mode, use the **OutputBufferingMode** parameter You can also use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet to run a command in a disconnected session.</span></span>

<span data-ttu-id="1835c-121">Weitere Informationen zum Feature „Getrennte Sitzungen“ finden Sie unter [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="1835c-121">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="1835c-122">Dieses Cmdlet wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1835c-122">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="1835c-123">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1835c-123">EXAMPLES</span></span>

### <span data-ttu-id="1835c-124">Beispiel 1: Trennen einer Sitzung nach Name</span><span class="sxs-lookup"><span data-stu-id="1835c-124">Example 1 - Disconnect a session by name</span></span>

<span data-ttu-id="1835c-125">Mit diesem Befehl wird die Verbindung der PSSession UpdateSession auf dem Computer Server01 von der aktuellen Sitzung getrennt.</span><span class="sxs-lookup"><span data-stu-id="1835c-125">This command disconnects the UpdateSession PSSession on the Server01 computer from the current session.</span></span> <span data-ttu-id="1835c-126">Der Befehl verwendet den **Name** -Parameter, um die PSSession zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1835c-126">The command uses the **Name** parameter to identify the PSSession.</span></span>

```
PS> Disconnect-PSSession -Name UpdateSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  UpdateSession   Server01        Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="1835c-127">Die Ausgabe zeigt, dass der Trennungsversuch erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="1835c-127">The output shows that the attempt to disconnect was successful.</span></span> <span data-ttu-id="1835c-128">Der Sitzungszustand ist Disconnected und die Verfügbarkeit ist None. Das weist darauf hin, dass die Sitzung nicht anderweitig verwendet wird und die Verbindung wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1835c-128">The session state is Disconnected and the Availability is None, which indicates that the session is not busy and can be reconnected.</span></span>

### <span data-ttu-id="1835c-129">Beispiel 2: Trennen einer Sitzung von einem bestimmten Computer</span><span class="sxs-lookup"><span data-stu-id="1835c-129">Example 2 - Disconnect a session from a specific computer</span></span>

<span data-ttu-id="1835c-130">Mit diesem Befehl wird die Verbindung der PSSession ITTask auf dem Computer Server12 von der aktuellen Sitzung getrennt.</span><span class="sxs-lookup"><span data-stu-id="1835c-130">This command disconnects the ITTask PSSession on the Server12 computer from the current session.</span></span>
<span data-ttu-id="1835c-131">Die ITTask-Sitzung wurde in der aktuellen Sitzung erstellt und stellt eine Verbindung mit dem Computer Server12 her.</span><span class="sxs-lookup"><span data-stu-id="1835c-131">The ITTask session was created in the current session and connects to the Server12 computer.</span></span> <span data-ttu-id="1835c-132">Der Befehl verwendet das `Get-PSSession` Cmdlet, um die Sitzung zu erhalten `Disconnect-PSSession` , und das Cmdlet, um die Verbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="1835c-132">The command uses the `Get-PSSession` cmdlet to get the session and the `Disconnect-PSSession` cmdlet to disconnect it.</span></span>

```
PS> Get-PSSession -ComputerName Server12 -Name ITTask |
  Disconnect-PSSession -OutputBufferingMode Drop -IdleTimeoutSec 86400
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  ITTask          Server12        Disconnected  ITTasks               None
```

<span data-ttu-id="1835c-133">Der `Disconnect-PSSession` Befehl verwendet den **outputbufferingmode** -Parameter, um den Ausgabemodus auf " **Drop** " festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1835c-133">The `Disconnect-PSSession` command uses the **OutputBufferingMode** parameter to set the output mode to **Drop**.</span></span> <span data-ttu-id="1835c-134">Durch diese Einstellung wird sichergestellt, dass das in der Sitzung ausgeführte Skript auch bei vollem Ausgabepuffer weiter ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1835c-134">This setting ensures that the script that is running in the session can continue to run even if the session output buffer is full.</span></span> <span data-ttu-id="1835c-135">Da das Skript seine Ausgabedaten in einen Bericht auf einer Dateifreigabe schreibt, können andere Ausgabedaten verloren gehen, ohne dass dies Konsequenzen hätte.</span><span class="sxs-lookup"><span data-stu-id="1835c-135">Because the script writes its output to a report on a file share, other output can be lost without consequence.</span></span>

<span data-ttu-id="1835c-136">Außerdem verwendet der Befehl den **IdleTimeoutSec** -Parameter, um die Leerlaufzeitüberschreitung der Sitzung auf 24 Stunden zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="1835c-136">The command also uses the **IdleTimeoutSec** parameter to extend the idle timeout of the session to 24 hours.</span></span> <span data-ttu-id="1835c-137">Diese Einstellung gibt diesem Administrator oder anderen Administratoren Zeit, die Sitzungsverbindung wiederherzustellen, damit das Skript ausgeführt und Fehler ggf. behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="1835c-137">This setting allows time for this administrator or other administrators to reconnect to the session to verify that the script ran and troubleshoot if needed.</span></span>

### <span data-ttu-id="1835c-138">Beispiel 3: Verwenden mehrerer pssessions auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="1835c-138">Example 3 - Using multiple PSSessions on multiple computers</span></span>

<span data-ttu-id="1835c-139">Diese Reihe von Befehlen zeigt, wie das `Disconnect-PSSession` Cmdlet in einem Unternehmens Szenario verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1835c-139">This series of commands shows how the `Disconnect-PSSession` cmdlet might be used in an enterprise scenario.</span></span> <span data-ttu-id="1835c-140">In diesem Fall startet ein neuer Techniker ein Skript in einer Sitzung auf einem Remotecomputer und stößt auf ein Problem.</span><span class="sxs-lookup"><span data-stu-id="1835c-140">In this case, a new technician starts a script in a session on a remote computer and runs into a problem.</span></span> <span data-ttu-id="1835c-141">Der Techniker trennt die Verbindung mit der Sitzung, damit ein erfahrener Kollege eine Verbindung mit der Sitzung herstellen und das Problem beheben kann.</span><span class="sxs-lookup"><span data-stu-id="1835c-141">The technician disconnects from the session so that a more experienced manager can connect to the session and resolve the problem.</span></span>

```
PS> $s = New-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
PS> Invoke-Command $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Get-PSSession -Name ITTask -ComputerName Srv1 | Disconnect-PSSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1 ITTask           Srv1            Disconnected  Microsoft.PowerShell          None

PS> Get-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None
 2 ITTask          Srv2            Opened        Microsoft.PowerShell     Available
 3 ITTask          Srv30           Opened        Microsoft.PowerShell     Available

PS> Get-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None

PS> $s = Connect-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
PS> Invoke-Command -Session $s {dir $home\Scripts\PatchStatusOutput.ps1}
PS> Invoke-Command -Session $s {mkdir $home\Scripts\PatchStatusOutput}
PS> Invoke-Command -Session $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Disconnect-PSSession -Session $s
```

<span data-ttu-id="1835c-142">Der Techniker beginnt, Sitzungen auf mehreren Remotecomputern zu erstellen und in jeder Sitzung ein Skript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1835c-142">The technician begins by creating sessions on several remote computers and running a script in each session.</span></span> <span data-ttu-id="1835c-143">Der erste Befehl verwendet das `New-PSSession` Cmdlet, um die ittask-Sitzung auf drei Remote Computern zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1835c-143">The first command uses the `New-PSSession` cmdlet to create the ITTask session on three remote computers.</span></span> <span data-ttu-id="1835c-144">Der Befehl speichert die Sitzungen in der $s-Variablen.</span><span class="sxs-lookup"><span data-stu-id="1835c-144">The command saves the sessions in the $s variable.</span></span> <span data-ttu-id="1835c-145">Der zweite Befehl verwendet den **FilePath** -Parameter des `Invoke-Command` Cmdlets, um ein Skript in den Sitzungen in der $s Variablen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1835c-145">The second command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run a script in the sessions in the $s variable.</span></span>

<span data-ttu-id="1835c-146">Das Skript, das auf dem Computer Srv1 ausgeführt wird, generiert unerwartete Fehler.</span><span class="sxs-lookup"><span data-stu-id="1835c-146">The script running on the Srv1 computer generates unexpected errors.</span></span> <span data-ttu-id="1835c-147">Der Techniker wendet sich an seinen Vorgesetzten und bittet ihn um Hilfe.</span><span class="sxs-lookup"><span data-stu-id="1835c-147">The technician contacts his manager and asks for assistance.</span></span> <span data-ttu-id="1835c-148">Der Manager weist den Techniker an, die Verbindung mit der Sitzung zu trennen, damit er untersuchen kann. Der zweite Befehl verwendet das `Get-PSSession` Cmdlet, um die ittask-Sitzung auf dem Srv1-Computer `Disconnect-PSSession` zu erhalten, und das Cmdlet, um die Verbindung zu trennen.</span><span class="sxs-lookup"><span data-stu-id="1835c-148">The manager directs the technician to disconnect from the session so he can investigate.The second command uses the `Get-PSSession` cmdlet to get the ITTask session on the Srv1 computer and the `Disconnect-PSSession` cmdlet to disconnect it.</span></span> <span data-ttu-id="1835c-149">Dieser Befehl hat keine Auswirkung auf die ittask-Sitzungen auf den anderen Computern.</span><span class="sxs-lookup"><span data-stu-id="1835c-149">This command does not affect the ITTask sessions on the other computers.</span></span>

<span data-ttu-id="1835c-150">Der dritte Befehl verwendet das `Get-PSSession` Cmdlet, um die ittask-Sitzungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1835c-150">The third command uses the `Get-PSSession` cmdlet to get the ITTask sessions.</span></span> <span data-ttu-id="1835c-151">Die Ausgabe zeigt, dass die ITTask-Sitzungen auf den Computern Srv2 und Srv30 nicht vom Trennungsbefehl betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="1835c-151">The output shows that the ITTask sessions on the Srv2 and Srv30 computers were not affected by the command to disconnect.</span></span>

<span data-ttu-id="1835c-152">Der Manager meldet sich bei seinem Heimcomputer an, stellt eine Verbindung mit dem Unternehmensnetzwerk her, startet PowerShell und verwendet das `Get-PSSession` Cmdlet, um die ittask-Sitzung auf dem Srv1-Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1835c-152">The manager logs on to his home computer, connects to his corporate network, starts PowerShell, and uses the `Get-PSSession` cmdlet to get the ITTask session on the Srv1 computer.</span></span> <span data-ttu-id="1835c-153">Er verwendet die Anmeldeinformationen des Technikers, um auf die Sitzung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1835c-153">He uses the credentials of the technician to access the session.</span></span>

<span data-ttu-id="1835c-154">Als Nächstes verwendet der Manager das- `Connect-PSSession` Cmdlet, um eine Verbindung mit der ittask-Sitzung auf dem Srv1-Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="1835c-154">Next, the manager uses the `Connect-PSSession` cmdlet to connect to the ITTask session on the Srv1 computer.</span></span> <span data-ttu-id="1835c-155">Der Befehl speichert die Sitzung in der $s-Variablen.</span><span class="sxs-lookup"><span data-stu-id="1835c-155">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="1835c-156">Der Manager verwendet das `Invoke-Command` Cmdlet, um einige Diagnose Befehle in der Sitzung in der `$s` Variablen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1835c-156">The manager uses the `Invoke-Command` cmdlet to run some diagnostic commands in the session in the `$s` variable.</span></span> <span data-ttu-id="1835c-157">Er erkennt, dass der Skriptfehler durch ein nicht gefundenes, erforderliches Verzeichnis verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="1835c-157">He recognizes that the script failed because it did not find a required directory.</span></span>
<span data-ttu-id="1835c-158">Der Manager verwendet die `MkDir` -Funktion, um das Verzeichnis zu erstellen, und dann startet er das `Get-PatchStatus.ps1` Skript neu und trennt die Verbindung mit der Sitzung. Der Manager meldet seine Ergebnisse an den Techniker, schlägt vor, dass er erneut eine Verbindung mit der Sitzung herstellt, um die Aufgaben abzuschließen, und fordert ihn auf, dem Skript einen Befehl hinzuzufügen, `Get-PatchStatus.ps1` der das erforderliche Verzeichnis erstellt, wenn es nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1835c-158">The manager uses the `MkDir` function to create the directory, and then he restarts the `Get-PatchStatus.ps1` script and disconnects from the session.The manager reports his findings to the technician, suggests that he reconnect to the session to complete the tasks, and asks him to add a command to the `Get-PatchStatus.ps1` script that creates the required directory if it does not exist.</span></span>

### <span data-ttu-id="1835c-159">Beispiel 4: Ändern des Timeout Werts für eine PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-159">Example 4 - Change the timeout value for a PSSession</span></span>

<span data-ttu-id="1835c-160">In diesem Beispiel wird gezeigt, wie der Wert der **IdleTimeout** -Eigenschaft einer Sitzung korrigiert wird, damit die Verbindung getrennt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1835c-160">This example shows how to correct the value of the **IdleTimeout** property of a session so that it can be disconnected.</span></span>

<span data-ttu-id="1835c-161">Die Eigenschaft für die Leerlaufzeitüberschreitung einer Sitzung ist wichtig für getrennte Sitzungen, weil von ihr abhängt, wie lange eine getrennte Sitzung vor dem Löschen beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="1835c-161">The idle timeout property of a session is critical to disconnected sessions, because it determines how long a disconnected session is maintained before it is deleted.</span></span> <span data-ttu-id="1835c-162">Sie können die Option für die Leerlaufzeitüberschreitung festlegen, wenn Sie eine Sitzung erstellen und wenn Sie die Verbindung trennen.</span><span class="sxs-lookup"><span data-stu-id="1835c-162">You can set the idle timeout option when you create a session and when you disconnect it.</span></span> <span data-ttu-id="1835c-163">Die Standardwerte für das Leerlauf Timeout einer Sitzung werden in der `$PSSessionOption` Einstellungs Variablen auf dem lokalen Computer und in der Sitzungs Konfiguration auf dem Remote Computer festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1835c-163">The default values for the idle timeout of a session are set in the `$PSSessionOption` preference variable on the local computer and in the session configuration on the remote computer.</span></span> <span data-ttu-id="1835c-164">Die für die Sitzung festgelegten Werte haben Vorrang vor den in der Sitzungskonfiguration festgelegten Werten. Die Sitzungswerte dürfen jedoch die in der Sitzungskonfiguration festgelegten Kontingente, z. B. den **MaxIdleTimeoutMs** -Wert, nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="1835c-164">Values set for the session take precedence over values set in the session configuration, but session values cannot exceed quotas set in the session configuration, such as the **MaxIdleTimeoutMs** value.</span></span>

```
PS> $Timeout = New-PSSessionOption -IdleTimeout 172800000
PS> $s = New-PSSession -Computer Server01 -Name ITTask -SessionOption $Timeout
PS> Disconnect-PSSession -Session $s
Disconnect-PSSession : The session ITTask cannot be disconnected because the specified
idle timeout value 172800(seconds) is either greater than the server maximum allowed
43200 (seconds) or less that the minimum allowed60(seconds).  Choose an idle time out
value that is within the allowed range and try again.

PS> Invoke-Command -ComputerName Server01 {Get-PSSessionConfiguration Microsoft.PowerShell} |
 Format-List -Property *

Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/microsoft.powershell
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
SecurityDescriptorSddl        : O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GXGW;;;WD)
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 2147483647
Uri                           : http://schemas.microsoft.com/powershell/microsoft.powershell
SDKVersion                    : 2
Name                          : microsoft.powershell
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
ParentResourceUri             : http://schemas.microsoft.com/powershell/microsoft.powershell
Enabled                       : true
MaxShells                     : 25
MaxShellsPerUser              : 25
Permission                    : BUILTIN\Administrators AccessAllowed
PSComputerName                : localhost
RunspaceId                    : aea84310-6dbf-4c21-90ac-13980039925a
PSShowComputerName            : True


PS> $s.Runspace.ConnectionInfo
ConnectionUri                     : http://Server01/wsman
ComputerName                      : Server01
Scheme                            : http
Port                              : 80
AppName                           : /wsman
Credential                        :
ShellUri                          : http://schemas.microsoft.com/powershell/Microsoft.PowerShell
AuthenticationMechanism           : Default
CertificateThumbprint             :
MaximumConnectionRedirectionCount : 5
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
UseCompression                    : True
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
NoEncryption                      : False
UseUTF16                          : False
OutputBufferingMode               : Drop
IncludePortInSPN                  : False
Culture                           : en-US
UICulture                         : en-US
OpenTimeout                       : 180000
CancelTimeout                     : 60000
OperationTimeout                  : 180000
IdleTimeout                       : 172800000

PS> Disconnect-PSSession $s -IdleTimeoutSec 43200
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Disconnected  Microsoft.PowerShell          None

PS> $s.Runspace.ConnectionInfo.IdleTimeout
43200000
```

<span data-ttu-id="1835c-165">Der erste Befehl verwendet das `New-PSSessionOption` Cmdlet, um ein Sitzungs Options Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1835c-165">The first command uses the `New-PSSessionOption` cmdlet to create a session option object.</span></span> <span data-ttu-id="1835c-166">Er verwendet den **IdleTimeout** -Parameter, um eine Leerlaufzeitüberschreitung von 48 Stunden (172.800.000 Millisekunden) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1835c-166">It uses the **IdleTimeout** parameter to set an idle timeout of 48 hours (172800000 milliseconds).</span></span> <span data-ttu-id="1835c-167">Der Befehl speichert das Sitzungsoptionsobjekt in der $Timeout-Variablen.</span><span class="sxs-lookup"><span data-stu-id="1835c-167">The command saves the session option object in the $Timeout variable.</span></span>

<span data-ttu-id="1835c-168">Der zweite Befehl verwendet das `New-PSSession` Cmdlet, um die ittask-Sitzung auf dem Server01-Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1835c-168">The second command uses the `New-PSSession` cmdlet to create the ITTask session on the Server01 computer.</span></span> <span data-ttu-id="1835c-169">Der Befehl speichert die Sitzung in der $s-Variablen.</span><span class="sxs-lookup"><span data-stu-id="1835c-169">The command save the session in the $s variable.</span></span> <span data-ttu-id="1835c-170">Der Wert des **SessionOption** -Parameters entspricht der Leerlaufzeitüberschreitung von 48 Stunden in der $Timeout-Variablen.</span><span class="sxs-lookup"><span data-stu-id="1835c-170">The value of the **SessionOption** parameter is the 48-hour idle timeout in the $Timeout variable.</span></span>

<span data-ttu-id="1835c-171">Der dritte Befehl trennt die Verbindung der in der $s-Variablen enthaltenen ITTask-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="1835c-171">The third command disconnects the ITTask session in the $s variable.</span></span> <span data-ttu-id="1835c-172">Der Befehl verursacht einen Fehler, weil der Wert für die Leerlaufzeitüberschreitung der Sitzung das **MaxIdleTimeoutMs** -Kontingent in der Sitzungskonfiguration überschreitet.</span><span class="sxs-lookup"><span data-stu-id="1835c-172">The command fails because the idle timeout value of the session exceeds the **MaxIdleTimeoutMs** quota in the session configuration.</span></span> <span data-ttu-id="1835c-173">Da die Leerlaufzeitüberschreitung erst verwendet wird, wenn die Sitzung getrennt ist, bleibt dieser Verstoß während der laufenden Sitzung unentdeckt.</span><span class="sxs-lookup"><span data-stu-id="1835c-173">Because the idle timeout is not used until the session is disconnected, this violation can go undetected while the session is in use.</span></span>

<span data-ttu-id="1835c-174">Der vierte Befehl verwendet das `Invoke-Command` Cmdlet, um einen `Get-PSSessionConfiguration` Befehl für die Microsoft. PowerShell-Sitzungs Konfiguration auf dem Server01-Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1835c-174">The fourth command uses the `Invoke-Command` cmdlet to run a `Get-PSSessionConfiguration` command for the Microsoft.PowerShell session configuration on the Server01 computer.</span></span> <span data-ttu-id="1835c-175">Der Befehl verwendet das `Format-List` Cmdlet, um alle Eigenschaften der Sitzungs Konfiguration in einer Liste anzuzeigen. Die Ausgabe zeigt, dass die **maxidletimeoutms** -Eigenschaft, die den maximal zulässigen **IdleTimeout** -Wert für Sitzungen festlegt, die die Sitzungs Konfiguration verwenden, 43,2 Millionen Millisekunden (12 Stunden) beträgt.</span><span class="sxs-lookup"><span data-stu-id="1835c-175">The command uses the `Format-List` cmdlet to display all properties of the session configuration in a list.The output shows that the **MaxIdleTimeoutMS** property, which establishes the maximum permitted **IdleTimeout** value for sessions that use the session configuration, is 43200000 milliseconds (12 hours).</span></span>

<span data-ttu-id="1835c-176">Der fünfte Befehl ruft die Sitzungsoptionswerte der Sitzung in der $s-Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="1835c-176">The fifth command gets the session option values of the session in the $s variable.</span></span> <span data-ttu-id="1835c-177">Die Werte vieler Sitzungs Optionen sind Eigenschaften der **ConnectionInfo** -Eigenschaft der **Runspace** -Eigenschaft der Sitzung. Die Ausgabe zeigt, dass der Wert der **IdleTimeout** -Eigenschaft der Sitzung 172,8 Millionen Millisekunden (48 Stunden) beträgt, wodurch das **maxidletimeoutms** -Kontingent von 12 Stunden in der Sitzungs Konfiguration verletzt wird. Um diesen Konflikt zu lösen, können Sie mit dem **ConfigurationName** -Parameter eine andere Sitzungs Konfiguration auswählen oder den **IdleTimeout** -Parameter verwenden, um das Leerlauf Timeout der Sitzung zu verringern.</span><span class="sxs-lookup"><span data-stu-id="1835c-177">The values of many session options are properties of the **ConnectionInfo** property of the **Runspace** property of the session.The output shows that the value of the **IdleTimeout** property of the session is 172800000 milliseconds (48 hours), which violates the **MaxIdleTimeoutMs** quota of 12 hours in the session configuration.To resolve this conflict, you can use the **ConfigurationName** parameter to select a different session configuration or use the **IdleTimeout** parameter to reduce the idle timeout of the session.</span></span>

<span data-ttu-id="1835c-178">Der sechste Befehl trennt die Sitzungsverbindung.</span><span class="sxs-lookup"><span data-stu-id="1835c-178">The sixth command disconnects the session.</span></span> <span data-ttu-id="1835c-179">Er verwendet den **IdleTimeoutSec** -Parameter, um die Leerlaufzeitüberschreitung auf den Maximalwert von 12 Stunden festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1835c-179">It uses the **IdleTimeoutSec** parameter to set the idle timeout to the 12-hour maximum.</span></span>

<span data-ttu-id="1835c-180">Der siebte Befehl ruft den Wert der **IdleTimeout** -Eigenschaft der getrennten Sitzung ab, der in Millisekunden gemessen wird.</span><span class="sxs-lookup"><span data-stu-id="1835c-180">The seventh command gets the value of the **IdleTimeout** property of the disconnected session, which is measured in milliseconds.</span></span> <span data-ttu-id="1835c-181">Die Ausgabe bestätigt, dass der Befehl erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1835c-181">The output confirms that the command was successful.</span></span>

## <span data-ttu-id="1835c-182">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1835c-182">PARAMETERS</span></span>

### <span data-ttu-id="1835c-183">-Id</span><span class="sxs-lookup"><span data-stu-id="1835c-183">-Id</span></span>

<span data-ttu-id="1835c-184">Trennt die Verbindung von Sitzungen mit der angegebenen Sitzungs-ID.</span><span class="sxs-lookup"><span data-stu-id="1835c-184">Disconnects from sessions with the specified session ID.</span></span> <span data-ttu-id="1835c-185">Geben Sie eine oder mehrere IDs (durch Kommas getrennt) ein, oder verwenden Sie den Bereichsoperator (..), um einen Bereich von IDs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1835c-185">Type one or more IDs (separated by commas), or use the range operator (..) to specify a range of IDs.</span></span>

<span data-ttu-id="1835c-186">Verwenden Sie das-Cmdlet, um die ID einer Sitzung zu erhalten `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="1835c-186">To get the ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="1835c-187">Die Instanz-ID wird in der **ID** -Eigenschaft der Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1835c-187">The instance ID is stored in the **ID** property of the session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1835c-188">-Idletimeoutsec</span><span class="sxs-lookup"><span data-stu-id="1835c-188">-IdleTimeoutSec</span></span>

<span data-ttu-id="1835c-189">Ändert den Wert für die Leerlaufzeitüberschreitung der getrennten PSSession.</span><span class="sxs-lookup"><span data-stu-id="1835c-189">Changes the idle timeout value of the disconnected PSSession.</span></span> <span data-ttu-id="1835c-190">Geben Sie einen Wert in Sekunden ein.</span><span class="sxs-lookup"><span data-stu-id="1835c-190">Enter a value in seconds.</span></span> <span data-ttu-id="1835c-191">Der minimale Wert beträgt 60 Sekunden (1 Minute).</span><span class="sxs-lookup"><span data-stu-id="1835c-191">The minimum value is 60 (1 minute).</span></span>

<span data-ttu-id="1835c-192">Die Leerlaufzeitüberschreitung bestimmt, wie lange die getrennte PSSession auf dem Remotecomputer beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="1835c-192">The idle timeout determines how long the disconnected PSSession is maintained on the remote computer.</span></span> <span data-ttu-id="1835c-193">Wenn der Wert abläuft, wird die PSSession gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1835c-193">When the timeout expires, the PSSession is deleted.</span></span>

<span data-ttu-id="1835c-194">Ab dem Zeitpunkt der Trennung befinden sich getrennte PSSessions im Leerlauf, selbst wenn die Befehle in der getrennten Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1835c-194">Disconnected PSSessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

<span data-ttu-id="1835c-195">Der Standardwert für die Leerlaufzeitüberschreitung einer Sitzung wird durch den Wert der **IdleTimeoutMs** -Eigenschaft der Sitzungskonfiguration festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1835c-195">The default value for the idle timeout of a session is set by the value of the **IdleTimeoutMs** property of the session configuration.</span></span> <span data-ttu-id="1835c-196">Der Standardwert beträgt 7.200.000 Millisekunden (2 Stunden).</span><span class="sxs-lookup"><span data-stu-id="1835c-196">The default value is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="1835c-197">Der Wert dieses Parameters hat Vorrang vor dem Wert der **IdleTimeout** -Eigenschaft der $PSSessionOption-Einstellungsvariablen und dem Standardwert für die Leerlaufzeitüberschreitung in der Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="1835c-197">The value of this parameter takes precedence over the value of the **IdleTimeout** property of the $PSSessionOption preference variable and the default idle timeout value in the session configuration.</span></span> <span data-ttu-id="1835c-198">Allerdings darf dieser Wert nicht den Wert der **MaxIdleTimeoutMs** -Eigenschaft der Sitzungskonfiguration überschreiten.</span><span class="sxs-lookup"><span data-stu-id="1835c-198">However, this value cannot exceed the value of the **MaxIdleTimeoutMs** property of the session configuration.</span></span> <span data-ttu-id="1835c-199">Der Standardwert von **MaxIdleTimeoutMs** beträgt 12 Stunden (43.200.000 Millisekunden).</span><span class="sxs-lookup"><span data-stu-id="1835c-199">The default value of **MaxIdleTimeoutMs** is 12 hours (43200000 milliseconds).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1835c-200">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="1835c-200">-InstanceId</span></span>

<span data-ttu-id="1835c-201">Trennt die Verbindung von Sitzungen mit den angegebenen Instanz-IDs.</span><span class="sxs-lookup"><span data-stu-id="1835c-201">Disconnects from sessions with the specified instance IDs.</span></span>

<span data-ttu-id="1835c-202">Die Instanz-ID ist eine GUID, die eine Sitzung auf einem lokalen oder Remotecomputer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1835c-202">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="1835c-203">Die Instanz-ID ist eindeutig, sogar über mehrere Sitzungen auf mehreren Computern.</span><span class="sxs-lookup"><span data-stu-id="1835c-203">The instance ID is unique, even across multiple sessions on multiple computers.</span></span>

<span data-ttu-id="1835c-204">Verwenden Sie das-Cmdlet, um die Instanz-ID einer Sitzung zu erhalten `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="1835c-204">To get the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="1835c-205">Die Instanz-ID wird in der **InstanceId-** Eigenschaft der Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1835c-205">The instance ID is stored in the **InstanceID** property of the session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1835c-206">-Name</span><span class="sxs-lookup"><span data-stu-id="1835c-206">-Name</span></span>

<span data-ttu-id="1835c-207">Trennt die Verbindung von Sitzungen mit den angegebenen Anzeigenamen.</span><span class="sxs-lookup"><span data-stu-id="1835c-207">Disconnects from sessions with the specified friendly names.</span></span> <span data-ttu-id="1835c-208">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="1835c-208">Wildcards are permitted.</span></span>

<span data-ttu-id="1835c-209">Verwenden Sie das-Cmdlet, um den anzeigen Amen einer Sitzung zu erhalten `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="1835c-209">To get the friendly name of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="1835c-210">Der Anzeigename wird in der **Name** -Eigenschaft der Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1835c-210">The friendly name is stored in the **Name** property of the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="1835c-211">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="1835c-211">-Session</span></span>

<span data-ttu-id="1835c-212">Trennt die Verbindung der angegebenen PSSessions.</span><span class="sxs-lookup"><span data-stu-id="1835c-212">Disconnects from the specified PSSessions.</span></span> <span data-ttu-id="1835c-213">Geben Sie PSSession-Objekte ein, z. b. die vom `New-PSSession` Cmdlet zurückgegebenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="1835c-213">Enter PSSession objects, such as those that the `New-PSSession` cmdlet returns.</span></span> <span data-ttu-id="1835c-214">Sie können ein PSSession-Objekt auch über die Pipeline an weiterleiten `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="1835c-214">You can also pipe a PSSession object to `Disconnect-PSSession`.</span></span>

<span data-ttu-id="1835c-215">Mit dem `Get-PSSession` -Cmdlet können alle pssessions, die auf einem Remote Computer beendet werden, einschließlich pssessions, die getrennt sind, und pssessions, die mit anderen Sitzungen auf anderen Computern verbunden sind, erhalten.</span><span class="sxs-lookup"><span data-stu-id="1835c-215">The `Get-PSSession` cmdlet can get all PSSessions that terminate at a remote computer, including PSSessions that are disconnected and PSSessions that are connected to other sessions on other computers.</span></span> <span data-ttu-id="1835c-216">`Disconnect-PSSession` trennt nur die PSSession, die mit der aktuellen Sitzung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="1835c-216">`Disconnect-PSSession` disconnects only PSSession that are connected to the current session.</span></span> <span data-ttu-id="1835c-217">Wenn Sie andere pssessions an weiterleiten `Disconnect-PSSession` , `Disconnect-PSSession` schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="1835c-217">If you pipe other PSSessions to `Disconnect-PSSession`, the `Disconnect-PSSession` command fails.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1835c-218">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="1835c-218">-ThrottleLimit</span></span>

<span data-ttu-id="1835c-219">Legt die Drosselungs Grenze für den `Disconnect-PSSession` Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="1835c-219">Sets the throttle limit for the `Disconnect-PSSession` command.</span></span>

<span data-ttu-id="1835c-220">Die Drosselungsgrenze ist die maximale Anzahl gleichzeitiger Verbindungen, die zum Ausführen dieses Befehls hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="1835c-220">The throttle limit is the maximum number of concurrent connections that can be established to run this command.</span></span> <span data-ttu-id="1835c-221">Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.</span><span class="sxs-lookup"><span data-stu-id="1835c-221">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="1835c-222">Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.</span><span class="sxs-lookup"><span data-stu-id="1835c-222">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1835c-223">-Outputbufferingmode</span><span class="sxs-lookup"><span data-stu-id="1835c-223">-OutputBufferingMode</span></span>

<span data-ttu-id="1835c-224">Bestimmt, wie die Befehlsausgabe in der getrennten Sitzung verwaltet wird, wenn der Ausgabepuffer voll ist.</span><span class="sxs-lookup"><span data-stu-id="1835c-224">Determines how command output is managed in the disconnected session when the output buffer is full.</span></span> <span data-ttu-id="1835c-225">Der Standardwert ist **Block**.</span><span class="sxs-lookup"><span data-stu-id="1835c-225">The default value is **Block**.</span></span>

<span data-ttu-id="1835c-226">Wenn der Befehl in der getrennten Sitzung Ausgabedaten zurückgibt und sich der Ausgabepuffer füllt, legt der Wert dieses Parameters tatsächlich fest, ob der Befehl weiter ausgeführt wird, während die Sitzung getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="1835c-226">If the command in the disconnected session is returning output and the output buffer fills, the value of this parameter effectively determines whether the command continues to run while the session is disconnected.</span></span> <span data-ttu-id="1835c-227">Durch den Wert **Block** wird der Befehl angehalten, bis die Sitzungsverbindung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1835c-227">A value of **Block** suspends the command until the session is reconnected.</span></span> <span data-ttu-id="1835c-228">Beim Wert **Drop** kann der Befehl abgeschlossen werden, obwohl Daten verloren gehen können.</span><span class="sxs-lookup"><span data-stu-id="1835c-228">A value of **Drop** allows the command to complete, although data might be lost.</span></span> <span data-ttu-id="1835c-229">Bei Verwendung des **Drop** -Werts wird die Befehlsausgabe an eine Datei auf dem Datenträger umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="1835c-229">When using the **Drop** value, redirect the command output to a file on disk.</span></span>

<span data-ttu-id="1835c-230">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="1835c-230">Valid values are:</span></span>

- <span data-ttu-id="1835c-231">**Block** : Wenn der Ausgabepuffer voll ist, wird die Ausführung angehalten, bis der Puffer gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="1835c-231">**Block** : When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="1835c-232">**Drop** : Wenn der Ausgabepuffer voll ist, wird die Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="1835c-232">**Drop** : When the output buffer is full, execution continues.</span></span> <span data-ttu-id="1835c-233">Sobald neue Ausgabedaten gespeichert werden, wird die älteste Ausgabe verworfen.</span><span class="sxs-lookup"><span data-stu-id="1835c-233">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="1835c-234">**None** : Es wurde kein Ausgabepuffer Modus angegeben.</span><span class="sxs-lookup"><span data-stu-id="1835c-234">**None** : No output buffering mode is specified.</span></span> <span data-ttu-id="1835c-235">Der Wert der **OutputBufferingMode** -Eigenschaft der Sitzungskonfiguration wird für die getrennte Sitzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="1835c-235">The value of the **OutputBufferingMode** property of the session configuration is used for the disconnected session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Block
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1835c-236">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1835c-236">-Confirm</span></span>

<span data-ttu-id="1835c-237">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="1835c-237">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1835c-238">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1835c-238">-WhatIf</span></span>

<span data-ttu-id="1835c-239">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1835c-239">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1835c-240">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1835c-240">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1835c-241">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1835c-241">CommonParameters</span></span>

<span data-ttu-id="1835c-242">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1835c-242">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1835c-243">Weitere Informationen findest du unter [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="1835c-243">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="1835c-244">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1835c-244">INPUTS</span></span>

### <span data-ttu-id="1835c-245">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-245">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="1835c-246">Sie können eine Sitzung an die Pipeline übergeben `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="1835c-246">You can pipe a session to `Disconnect-PSSession`.</span></span>

## <span data-ttu-id="1835c-247">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1835c-247">OUTPUTS</span></span>

### <span data-ttu-id="1835c-248">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-248">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="1835c-249">`Disconnect-PSSession` Gibt ein-Objekt zurück, das die getrennte Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="1835c-249">`Disconnect-PSSession` returns an object that represents the session that it disconnected.</span></span>

## <span data-ttu-id="1835c-250">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1835c-250">NOTES</span></span>

- <span data-ttu-id="1835c-251">Das- `Disconnect-PSSession` Cmdlet funktioniert nur, wenn auf dem lokalen Computer und dem Remote Computer PowerShell 3,0 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1835c-251">The `Disconnect-PSSession` cmdlet works only when the local and remote computers are running PowerShell 3.0 or later.</span></span>
- <span data-ttu-id="1835c-252">Wenn Sie das `Disconnect-PSSession` Cmdlet in einer getrennten Sitzung verwenden, hat der Befehl keine Auswirkungen auf die Sitzung und generiert keine Fehler.</span><span class="sxs-lookup"><span data-stu-id="1835c-252">If you use the `Disconnect-PSSession` cmdlet on a disconnected session, the command has no effect on the session and it does not generate errors.</span></span>
- <span data-ttu-id="1835c-253">Die Verbindung getrennter Loopbacksitzungen mit interaktiven Sicherheitstoken (die mit dem **EnableNetworkAccess** -Parameter erstellt werden) kann nur von dem Computer wiederhergestellt werden, auf dem die Sitzung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1835c-253">Disconnected loopback sessions with interactive security tokens (those created with the **EnableNetworkAccess** parameter) can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="1835c-254">Diese Einschränkung schützt den Computer vor böswilligem Zugriff.</span><span class="sxs-lookup"><span data-stu-id="1835c-254">This restriction protects the computer from malicious access.</span></span>
- <span data-ttu-id="1835c-255">Wenn Sie eine PSSession trennen, nimmt sie den Sitzungszustand **Disconnected** und die Verfügbarkeit **None** an.</span><span class="sxs-lookup"><span data-stu-id="1835c-255">When you disconnect a PSSession, the session state is **Disconnected** and the availability is **None**.</span></span>

  <span data-ttu-id="1835c-256">Der Wert der **State** Eigenschaft bezieht sich auf die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="1835c-256">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="1835c-257">Folglich bedeutet der Wert **Disconnected** , dass die PSSession nicht mit der aktuellen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="1835c-257">Therefore, a value of **Disconnected** means that the PSSession is not connected to the current session.</span></span> <span data-ttu-id="1835c-258">Er bedeutet jedoch nicht, dass die PSSession von allen Sitzungen getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="1835c-258">However, it does not mean that the PSSession is disconnected from all sessions.</span></span> <span data-ttu-id="1835c-259">Sie kann mit einer anderen Sitzung verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="1835c-259">It might be connected to a different session.</span></span> <span data-ttu-id="1835c-260">Um festzustellen, ob Sie eine Sitzungsverbindung herstellen bzw. wiederherstellen können, verwenden Sie die **Availability** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1835c-260">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="1835c-261">Ein **Availability** -Wert von **None** gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1835c-261">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="1835c-262">Der Wert **Busy** gibt an, dass Sie keine Verbindung mit der PSSession herstellen können, weil sie mit einer anderen Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="1835c-262">A value of **Busy** indicates that you cannot connect to the PSSession because it is connected to another session.</span></span>

  <span data-ttu-id="1835c-263">Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate-Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="1835c-263">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span>

  <span data-ttu-id="1835c-264">Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability-Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="1835c-264">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="1835c-265">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1835c-265">RELATED LINKS</span></span>

[<span data-ttu-id="1835c-266">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-266">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="1835c-267">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-267">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="1835c-268">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-268">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="1835c-269">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-269">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="1835c-270">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="1835c-270">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="1835c-271">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-271">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="1835c-272">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="1835c-272">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="1835c-273">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="1835c-273">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="1835c-274">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-274">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="1835c-275">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="1835c-275">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="1835c-276">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="1835c-276">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="1835c-277">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="1835c-277">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="1835c-278">about_Remote</span><span class="sxs-lookup"><span data-stu-id="1835c-278">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="1835c-279">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="1835c-279">about_Remote_Disconnected_Sessions</span></span>](About/about_Remote_Disconnected_Sessions.md)
