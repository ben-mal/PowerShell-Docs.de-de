---
description: Beschreibt, wie die Ausgabe von Remote Befehlen interpretiert und formatiert wird.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_output?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Output
ms.openlocfilehash: 476afc62089795d22002ece05c7ce2bf53994237
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597569"
---
# <a name="about-remote-output"></a><span data-ttu-id="97248-103">Informationen zur Remote Ausgabe</span><span class="sxs-lookup"><span data-stu-id="97248-103">About Remote Output</span></span>

## <a name="short-description"></a><span data-ttu-id="97248-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97248-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="97248-105">Beschreibt, wie die Ausgabe von Remote Befehlen interpretiert und formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="97248-105">Describes how to interpret and format the output of remote commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="97248-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97248-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="97248-107">Die Ausgabe eines Befehls, der auf einem Remote Computer ausgeführt wurde, könnte wie die Ausgabe desselben Befehls aussehen, der auf einem lokalen Computer ausgeführt wird. es gibt jedoch einige bedeutende Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="97248-107">The output of a command that was run on a remote computer might look like output of the same command run on a local computer, but there are some significant differences.</span></span>

<span data-ttu-id="97248-108">In diesem Thema wird erläutert, wie die Ausgabe von Befehlen interpretiert, formatiert und angezeigt wird, die auf Remote Computern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="97248-108">This topic explains how to interpret, format, and display the output of commands that are run on remote computers.</span></span>

## <a name="displaying-the-computer-name"></a><span data-ttu-id="97248-109">Anzeigen des Computer namens</span><span class="sxs-lookup"><span data-stu-id="97248-109">DISPLAYING THE COMPUTER NAME</span></span>

<span data-ttu-id="97248-110">Wenn Sie mit dem Cmdlet "Invoke-Command" einen Befehl auf einem Remote Computer ausführen, gibt der Befehl ein Objekt zurück, das den Namen des Computers enthält, von dem die Daten generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="97248-110">When you use the Invoke-Command cmdlet to run a command on a remote computer, the command returns an object that includes the name of the computer that generated the data.</span></span> <span data-ttu-id="97248-111">Der Name des Remote Computers wird in der pscomputername-Eigenschaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="97248-111">The remote computer name is stored in the PSComputerName property.</span></span>

<span data-ttu-id="97248-112">Für viele Befehle wird der pscomputername standardmäßig angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97248-112">For many commands, the PSComputerName is displayed by default.</span></span> <span data-ttu-id="97248-113">Der folgende Befehl führt z. b. einen Get-Culture Befehl auf zwei Remote Computern aus: Server01 und Server02.</span><span class="sxs-lookup"><span data-stu-id="97248-113">For example, the following command runs a Get-Culture command on two remote computers, Server01 and Server02.</span></span> <span data-ttu-id="97248-114">Die Ausgabe, die unten angezeigt wird, enthält die Namen der Remote Computer, auf denen der Befehl ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="97248-114">The output, which appears below, includes the names of the remote computers on which the command ran.</span></span>

```powershell
C:\PS> invoke-command -script {get-culture} -comp Server01, Server02

LCID  Name    DisplayName                PSComputerName
----  ----    -----------                --------------
1033  en-US   English (United States)    Server01
1033  es-AR   Spanish (Argentina)        Server02
```

<span data-ttu-id="97248-115">Sie können den hidecomputername-Parameter von Invoke-Command verwenden, um die pscomputername-Eigenschaft auszublenden.</span><span class="sxs-lookup"><span data-stu-id="97248-115">You can use the HideComputerName parameter of Invoke-Command to hide the PSComputerName property.</span></span> <span data-ttu-id="97248-116">Dieser Parameter ist für Befehle vorgesehen, die nur Daten von einem Remote Computer sammeln.</span><span class="sxs-lookup"><span data-stu-id="97248-116">This parameter is designed for commands that collect data from only one remote computer.</span></span>

<span data-ttu-id="97248-117">Der folgende Befehl führt einen Get-Culture Befehl auf dem Remote Computer "Server01" aus.</span><span class="sxs-lookup"><span data-stu-id="97248-117">The following command runs a Get-Culture command on the Server01 remote computer.</span></span> <span data-ttu-id="97248-118">Er verwendet den hidecomputername-Parameter, um die pscomputername-Eigenschaft und zugehörige Eigenschaften auszublenden.</span><span class="sxs-lookup"><span data-stu-id="97248-118">It uses the HideComputerName parameter to hide the PSComputerName property and related properties.</span></span>

```powershell
C:\PS> invoke-command -scr {get-culture} -comp Server01 -HideComputerName

LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

<span data-ttu-id="97248-119">Sie können auch die pscomputername-Eigenschaft anzeigen, wenn Sie nicht standardmäßig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="97248-119">You can also display the PSComputerName property if it is not displayed by default.</span></span>

<span data-ttu-id="97248-120">Beispielsweise verwenden die folgenden Befehle das Format-Table-Cmdlet, um die pscomputername-Eigenschaft der Ausgabe eines Remote Get-Date Befehls hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="97248-120">For example, the following commands use the Format-Table cmdlet to add the PSComputerName property to the output of a remote Get-Date command.</span></span>

```powershell
$dates = invoke-command -script {get-date} -computername Server01, Server02
$dates | format-table DateTime, PSComputerName -auto

DateTime                            PSComputerName
--------                            --------------
Monday, July 21, 2008 7:16:58 PM    Server01
Monday, July 21, 2008 7:16:58 PM    Server02
```

## <a name="displaying-the-machinename-property"></a><span data-ttu-id="97248-121">Anzeigen der MachineName-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="97248-121">DISPLAYING THE MACHINENAME PROPERTY</span></span>

<span data-ttu-id="97248-122">Mehrere Cmdlets, einschließlich "Get-Process", "Get-Service" und "Get-EventLog", verfügen über einen Computername-Parameter, mit dem die Objekte auf einem Remote Computer abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="97248-122">Several cmdlets, including Get-Process, Get-Service, and Get-EventLog, have a ComputerName parameter that gets the objects on a remote computer.</span></span>
<span data-ttu-id="97248-123">Diese Cmdlets verwenden nicht PowerShell-Remoting, sodass Sie Sie auch auf Computern verwenden können, die nicht für Remoting in Windows PowerShell konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="97248-123">These cmdlets do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="97248-124">Die Objekte, die von diesen Cmdlets zurückgegeben werden, speichern den Namen des Remote Computers in der MachineName-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="97248-124">The objects that these cmdlets return store the name of the remote computer in the MachineName property.</span></span> <span data-ttu-id="97248-125">(Diese Objekte haben keine pscomputername-Eigenschaft.)</span><span class="sxs-lookup"><span data-stu-id="97248-125">(These objects do not have a PSComputerName property.)</span></span>

<span data-ttu-id="97248-126">Dieser Befehl ruft z. b. den PowerShell-Prozess auf den Remote Computern Server01 und Server02 ab.</span><span class="sxs-lookup"><span data-stu-id="97248-126">For example, this command gets the PowerShell process on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="97248-127">Die Standard Anzeige enthält nicht die MachineName-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="97248-127">The default display does not include the MachineName property.</span></span>

```powershell
C:\PS> get-process PowerShell -computername server01, server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
920      38    97524     114504   575     9.66   2648 PowerShell
194       6    24256      32384   142            3020 PowerShell
352      27    63472      63520   577     3.84   4796 PowerShell
```

<span data-ttu-id="97248-128">Sie können das Cmdlet "Format-Table" verwenden, um die "MachineName"-Eigenschaft der Prozess Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="97248-128">You can use the Format-Table cmdlet to display the MachineName property of the process objects.</span></span>

<span data-ttu-id="97248-129">Der folgende Befehl speichert beispielsweise die Prozesse in der $p-Variablen und verwendet dann einen Pipeline Operator (|), um die Prozesse in $p an den Format-Table-Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="97248-129">For example, the following command saves the processes in the $p variable and then uses a pipeline operator (|) to send the processes in $p to the Format-Table command.</span></span> <span data-ttu-id="97248-130">Der Befehl verwendet den property-Parameter von Format-Table, um die MachineName-Eigenschaft in die Anzeige einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="97248-130">The command uses the Property parameter of Format-Table to include the MachineName property in the display.</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02
C:\PS> $P | format-table -property ID, ProcessName, MachineName -auto

Id ProcessName MachineName
-- ----------- -----------
2648 PowerShell  Server02
3020 PowerShell  Server01
4796 PowerShell  Server02
```

<span data-ttu-id="97248-131">Der folgende komplexere Befehl fügt die MachineName-Eigenschaft der Standardprozess Anzeige hinzu.</span><span class="sxs-lookup"><span data-stu-id="97248-131">The following more complex command adds the MachineName property to the default process display.</span></span> <span data-ttu-id="97248-132">Sie verwendet Hash Tabellen, um berechnete Eigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="97248-132">It uses hash tables to specify calculated properties.</span></span> <span data-ttu-id="97248-133">Glücklicherweise müssen Sie es nicht verstehen, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="97248-133">Fortunately, you do not have to understand it to use it.</span></span>

<span data-ttu-id="97248-134">(Beachten Sie, dass das Graviszeichen ['] das Fortsetzungs Zeichen ist.)</span><span class="sxs-lookup"><span data-stu-id="97248-134">(Note that the backtick [\`] is the continuation character.)</span></span>

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02

C:\PS> $p | format-table -property Handles, `
@{Label="NPM(K)";Expression={int}}, `
@{Label="PM(K)";Expression={int}}, `
@{Label="WS(K)";Expression={int}}, `
@{Label="VM(M)";Expression={int}}, `
@{Label="CPU(s)";Expression={if ($.CPU -ne $()){ $.CPU.ToString("N")}}}, `
Id, ProcessName, MachineName -auto

Handles NPM(K) PM(K)  WS(K) VM(M) CPU(s)   Id ProcessName MachineName
------- ------ -----  ----- ----- ------   -- ----------- -----------
920     38 97560 114532   576        2648 PowerShell  Server02
192      6 24132  32028   140        3020 PowerShell  Server01
438     26 48436  59132   565        4796 PowerShell  Server02

```

## <a name="deserialized-objects"></a><span data-ttu-id="97248-135">deserialisierte Objekte</span><span class="sxs-lookup"><span data-stu-id="97248-135">DESERIALIZED OBJECTS</span></span>

<span data-ttu-id="97248-136">Wenn Sie Remote Befehle ausführen, die die Ausgabe generieren, wird die Befehlsausgabe über das Netzwerk zurück an den lokalen Computer übertragen.</span><span class="sxs-lookup"><span data-stu-id="97248-136">When you run remote commands that generate output, the command output is transmitted across the network back to the local computer.</span></span>

<span data-ttu-id="97248-137">Da die meisten Live Microsoft .NET Framework-Objekte (z. b. die von PowerShell-Cmdlets zurückgegebenen Objekte) nicht über das Netzwerk übertragen werden können, werden die Live-Objekte "serialisiert".</span><span class="sxs-lookup"><span data-stu-id="97248-137">Because most live Microsoft .NET Framework objects (such as the objects that PowerShell cmdlets return) cannot be transmitted over the network, the live objects are "serialized".</span></span> <span data-ttu-id="97248-138">Das heißt, die Live-Objekte werden in XML-Darstellungen des-Objekts und der zugehörigen Eigenschaften konvertiert.</span><span class="sxs-lookup"><span data-stu-id="97248-138">In other words, the live objects are converted into XML representations of the object and its properties.</span></span> <span data-ttu-id="97248-139">Anschließend wird das XML-basierte serialisierte Objekt über das Netzwerk übertragen.</span><span class="sxs-lookup"><span data-stu-id="97248-139">Then, the XML-based serialized object is transmitted across the network.</span></span>

<span data-ttu-id="97248-140">Auf dem lokalen Computer empfängt PowerShell das XML-basierte serialisierte Objekt und deserialisiert es, indem das XML-basierte Objekt in ein Standard-.NET Framework Objekt umgewandelt wird.</span><span class="sxs-lookup"><span data-stu-id="97248-140">On the local computer, PowerShell receives the XML-based serialized object and "deserializes" it by converting the XML-based object into a standard .NET Framework object.</span></span>

<span data-ttu-id="97248-141">Das deserialisierte Objekt ist jedoch kein Live Objekt.</span><span class="sxs-lookup"><span data-stu-id="97248-141">However, the deserialized object is not a live object.</span></span> <span data-ttu-id="97248-142">Es handelt sich um eine Momentaufnahme des-Objekts zum Zeitpunkt der Serialisierung und enthält Eigenschaften, aber keine-Methoden.</span><span class="sxs-lookup"><span data-stu-id="97248-142">It is a snapshot of the object at the time that it was serialized, and it includes properties but no methods.</span></span> <span data-ttu-id="97248-143">Sie können diese Objekte in PowerShell verwenden und verwalten, indem Sie Sie an Pipelines übergeben, ausgewählte Eigenschaften anzeigen und formatieren.</span><span class="sxs-lookup"><span data-stu-id="97248-143">You can use and manage these objects in PowerShell, including passing them in pipelines, displaying selected properties, and formatting them.</span></span>

<span data-ttu-id="97248-144">Die meisten deserialisierten Objekte werden automatisch für die Anzeige durch Einträge in den Types.ps1XML-oder Format.ps1XML-Dateien formatiert.</span><span class="sxs-lookup"><span data-stu-id="97248-144">Most deserialized objects are automatically formatted for display by entries in the Types.ps1xml or Format.ps1xml files.</span></span> <span data-ttu-id="97248-145">Allerdings verfügt der lokale Computer möglicherweise nicht über Formatierungs Dateien für alle deserialisierten Objekte, die auf einem Remote Computer generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="97248-145">However, the local computer might not have formatting files for all of the deserialized objects that were generated on a remote computer.</span></span> <span data-ttu-id="97248-146">Wenn Objekte nicht formatiert sind, werden alle Eigenschaften der einzelnen Objekte in der Konsole in einer streamingliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97248-146">When objects are not formatted, all of the properties of each object appear in the console in a streaming list.</span></span>

<span data-ttu-id="97248-147">Wenn Objekte nicht automatisch formatiert werden, können Sie die Formatierungs-Cmdlets wie Format-Table oder Format-List verwenden, um die ausgewählten Eigenschaften zu formatieren und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="97248-147">When objects are not formatted automatically, you can use the formatting cmdlets, such as Format-Table or Format-List, to format and display selected properties.</span></span> <span data-ttu-id="97248-148">Oder Sie können das Cmdlet "Out-GridView" verwenden, um die Objekte in einer Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="97248-148">Or, you can use the Out-GridView cmdlet to display the objects in a table.</span></span>

<span data-ttu-id="97248-149">Wenn Sie außerdem einen Befehl auf einem Remote Computer ausführen, der-Cmdlets verwendet, die nicht auf dem lokalen Computer vorhanden sind, werden die Objekte, die der Befehl zurückgibt, möglicherweise nicht ordnungsgemäß formatiert, da Sie nicht über die Formatierungs Dateien für diese Objekte auf dem Computer verfügen.</span><span class="sxs-lookup"><span data-stu-id="97248-149">Also, if you run a command on a remote computer that uses cmdlets that you do not have on your local computer, the objects that the command returns might not be formatted properly because you do not have the formatting files for those objects on your computer.</span></span> <span data-ttu-id="97248-150">Um Formatierungsdaten von einem anderen Computer zu erhalten, verwenden Sie die Cmdlets Get-FormatData und Export-FormatData.</span><span class="sxs-lookup"><span data-stu-id="97248-150">To get formatting data from another computer, use the Get-FormatData and Export-FormatData cmdlets.</span></span>

<span data-ttu-id="97248-151">Einige Objekttypen, z. b. DirectoryInfo-Objekte und GUIDs, werden wieder in Live Objekte konvertiert, wenn Sie empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="97248-151">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="97248-152">Diese Objekte benötigen keine besondere Behandlung oder Formatierung.</span><span class="sxs-lookup"><span data-stu-id="97248-152">These objects do not need any special handling or formatting.</span></span>

## <a name="ordering-the-results"></a><span data-ttu-id="97248-153">Reihenfolge der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="97248-153">ORDERING THE RESULTS</span></span>

<span data-ttu-id="97248-154">Die Reihenfolge der Computernamen im Computername-Parameter von Cmdlets legt die Reihenfolge fest, in der PowerShell eine Verbindung mit den Remote Computern herstellt.</span><span class="sxs-lookup"><span data-stu-id="97248-154">The order of the computer names in the ComputerName parameter of cmdlets determines the order in which PowerShell connects to the remote computers.</span></span> <span data-ttu-id="97248-155">Die Ergebnisse werden jedoch in der Reihenfolge angezeigt, in der Sie vom lokalen Computer empfangen werden. Dies kann eine andere Reihenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="97248-155">However, the results appear in the order in which the local computer receives them, which might be a different order.</span></span>

<span data-ttu-id="97248-156">Verwenden Sie das Cmdlet "Sort-Object", um die Reihenfolge der Ergebnisse zu ändern.</span><span class="sxs-lookup"><span data-stu-id="97248-156">To change the order of the results, use the Sort-Object cmdlet.</span></span> <span data-ttu-id="97248-157">Sie können nach der pscomputername-Eigenschaft oder der MachineName-Eigenschaft sortieren.</span><span class="sxs-lookup"><span data-stu-id="97248-157">You can sort on the PSComputerName or MachineName property.</span></span> <span data-ttu-id="97248-158">Sie können auch nach einer anderen Eigenschaft des Objekts sortieren, sodass die Ergebnisse von verschiedenen Computern miteinander vermischt werden.</span><span class="sxs-lookup"><span data-stu-id="97248-158">You can also sort on another property of the object so that the results from different computers are interspersed.</span></span>

## <a name="see-also"></a><span data-ttu-id="97248-159">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="97248-159">SEE ALSO</span></span>

[<span data-ttu-id="97248-160">about_Remote</span><span class="sxs-lookup"><span data-stu-id="97248-160">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="97248-161">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="97248-161">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="97248-162">Format-Table</span><span class="sxs-lookup"><span data-stu-id="97248-162">Format-Table</span></span>](xref:Microsoft.PowerShell.Utility.Format-Table)

[<span data-ttu-id="97248-163">Get-Process</span><span class="sxs-lookup"><span data-stu-id="97248-163">Get-Process</span></span>](xref:Microsoft.PowerShell.Management.Get-Process)

[<span data-ttu-id="97248-164">Get-Service</span><span class="sxs-lookup"><span data-stu-id="97248-164">Get-Service</span></span>](xref:Microsoft.PowerShell.Management.Get-Service)

[<span data-ttu-id="97248-165">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="97248-165">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="97248-166">Select-Object</span><span class="sxs-lookup"><span data-stu-id="97248-166">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

