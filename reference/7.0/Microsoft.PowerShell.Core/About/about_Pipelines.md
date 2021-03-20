---
description: Kombinieren von Befehlen in Pipelines in PowerShell
Locale: en-US
ms.date: 03/18/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pipelines?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pipelines
ms.openlocfilehash: db4fcd1cef78756bf61d849c83d5e2785af6caca
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "104726348"
---
# <a name="about-pipelines"></a><span data-ttu-id="04376-103">Informationen zu Pipelines</span><span class="sxs-lookup"><span data-stu-id="04376-103">About Pipelines</span></span>

## <a name="short-description"></a><span data-ttu-id="04376-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04376-104">Short description</span></span>

<span data-ttu-id="04376-105">Kombinieren von Befehlen in Pipelines in PowerShell</span><span class="sxs-lookup"><span data-stu-id="04376-105">Combining commands into pipelines in the PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="04376-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04376-106">Long description</span></span>

<span data-ttu-id="04376-107">Eine Pipeline ist eine Reihe von Befehlen, die durch Pipeline Operatoren ( `|` ) (ASCII 124) verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="04376-107">A pipeline is a series of commands connected by pipeline operators (`|`) (ASCII 124).</span></span> <span data-ttu-id="04376-108">Jeder Pipeline Operator sendet die Ergebnisse des vorangehenden Befehls an den nächsten Befehl.</span><span class="sxs-lookup"><span data-stu-id="04376-108">Each pipeline operator sends the results of the preceding command to the next command.</span></span>

<span data-ttu-id="04376-109">Die Ausgabe des ersten Befehls kann als Eingabe für den zweiten Befehl zur Verarbeitung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="04376-109">The output of the first command can be sent for processing as input to the second command.</span></span> <span data-ttu-id="04376-110">Und diese Ausgabe kann an einen anderen Befehl gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="04376-110">And that output can be sent to yet another command.</span></span> <span data-ttu-id="04376-111">Das Ergebnis ist eine komplexe Befehlskette oder _Pipeline_ , die aus einer Reihe einfacher Befehle besteht.</span><span class="sxs-lookup"><span data-stu-id="04376-111">The result is a complex command chain or _pipeline_ that is composed of a series of simple commands.</span></span>

<span data-ttu-id="04376-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04376-112">For example,</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="04376-113">In diesem Beispiel werden die-Objekte, die `Command-1` ausgibt, an gesendet `Command-2` .</span><span class="sxs-lookup"><span data-stu-id="04376-113">In this example, the objects that `Command-1` emits are sent to `Command-2`.</span></span>
<span data-ttu-id="04376-114">`Command-2` verarbeitet die-Objekte und sendet Sie an `Command-3` .</span><span class="sxs-lookup"><span data-stu-id="04376-114">`Command-2` processes the objects and sends them to `Command-3`.</span></span> <span data-ttu-id="04376-115">`Command-3` verarbeitet die Objekte und sendet Sie über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="04376-115">`Command-3` processes the objects and send them down the pipeline.</span></span> <span data-ttu-id="04376-116">Da in der Pipeline keine weiteren Befehle vorhanden sind, werden die Ergebnisse in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04376-116">Because there are no more commands in the pipeline, the results are displayed at the console.</span></span>

<span data-ttu-id="04376-117">In einer Pipeline werden die Befehle in der Reihenfolge von links nach rechts verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="04376-117">In a pipeline, the commands are processed in order from left to right.</span></span> <span data-ttu-id="04376-118">Die Verarbeitung wird als einzelner Vorgang behandelt, und die Ausgabe wird angezeigt, wenn Sie generiert wird.</span><span class="sxs-lookup"><span data-stu-id="04376-118">The processing is handled as a single operation and output is displayed as it's generated.</span></span>

<span data-ttu-id="04376-119">Hier ist ein einfaches Beispiel.</span><span class="sxs-lookup"><span data-stu-id="04376-119">Here is a simple example.</span></span> <span data-ttu-id="04376-120">Der folgende Befehl ruft den Notepad-Prozess ab und beendet ihn.</span><span class="sxs-lookup"><span data-stu-id="04376-120">The following command gets the Notepad process and then stops it.</span></span>

<span data-ttu-id="04376-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04376-121">For example,</span></span>

```powershell
Get-Process notepad | Stop-Process
```

<span data-ttu-id="04376-122">Der erste Befehl verwendet das `Get-Process` Cmdlet, um ein Objekt zu erhalten, das den Notepad-Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="04376-122">The first command uses the `Get-Process` cmdlet to get an object representing the Notepad process.</span></span> <span data-ttu-id="04376-123">Er verwendet einen Pipeline Operator ( `|` ), um das Process-Objekt an das `Stop-Process` Cmdlet zu senden, das den Notepad-Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="04376-123">It uses a pipeline operator (`|`) to send the process object to the `Stop-Process` cmdlet, which stops the Notepad process.</span></span> <span data-ttu-id="04376-124">Beachten Sie, dass der `Stop-Process` Befehl keinen **namens** -oder **ID** -Parameter besitzt, um den Prozess anzugeben, da der angegebene Prozess über die Pipeline übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="04376-124">Notice that the `Stop-Process` command doesn't have a **Name** or **ID** parameter to specify the process, because the specified process is submitted through the pipeline.</span></span>

<span data-ttu-id="04376-125">Dieses Pipeline Beispiel ruft die Textdateien im aktuellen Verzeichnis ab, wählt nur die Dateien aus, die mehr als 10.000 Bytes lang sind, sortiert sie nach Länge und zeigt den Namen und die Länge jeder Datei in einer Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="04376-125">This pipeline example gets the text files in the current directory, selects only the files that are more than 10,000 bytes long, sorts them by length, and displays the name and length of each file in a table.</span></span>

```powershell
Get-ChildItem -Path *.txt |
  Where-Object {$_.length -gt 10000} |
    Sort-Object -Property length |
      Format-Table -Property name, length
```

<span data-ttu-id="04376-126">Diese Pipeline besteht aus vier Befehlen in der angegebenen Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="04376-126">This pipeline consists of four commands in the specified order.</span></span> <span data-ttu-id="04376-127">Die folgende Abbildung zeigt die Ausgabe der einzelnen Befehle, wenn Sie an den nächsten Befehl in der Pipeline weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="04376-127">The following illustration shows the output from each command as it's passed to the next command in the pipeline.</span></span>

```
Get-ChildItem -Path *.txt
| (FileInfo objects for *.txt)
V
Where-Object {$_.length -gt 10000}
| (FileInfo objects for *.txt)
| (      Length > 10000      )
V
Sort-Object -Property Length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
V
Format-Table -Property name, length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
| (   Formatted in a table   )
V

Name                       Length
----                       ------
tmp1.txt                    82920
tmp2.txt                   114000
tmp3.txt                   114000
```

## <a name="using-pipelines"></a><span data-ttu-id="04376-128">Verwenden von Pipelines</span><span class="sxs-lookup"><span data-stu-id="04376-128">Using pipelines</span></span>

<span data-ttu-id="04376-129">Die meisten PowerShell-Cmdlets sind für die Unterstützung von Pipelines konzipiert.</span><span class="sxs-lookup"><span data-stu-id="04376-129">Most PowerShell cmdlets are designed to support pipelines.</span></span> <span data-ttu-id="04376-130">In den meisten Fällen können Sie die Ergebnisse eines **Get** -Cmdlets über die _Pipeline_ an ein anderes Cmdlet desselben Substantivs übergeben.</span><span class="sxs-lookup"><span data-stu-id="04376-130">In most cases, you can _pipe_ the results of a **Get** cmdlet to another cmdlet of the same noun.</span></span>
<span data-ttu-id="04376-131">Beispielsweise können Sie die Ausgabe des- `Get-Service` Cmdlets an das- `Start-Service` Cmdlet oder das- `Stop-Service` Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="04376-131">For example, you can pipe the output of the `Get-Service` cmdlet to the `Start-Service` or `Stop-Service` cmdlets.</span></span>

<span data-ttu-id="04376-132">Diese Beispiel Pipeline startet den WMI-Dienst auf dem Computer:</span><span class="sxs-lookup"><span data-stu-id="04376-132">This example pipeline starts the WMI service on the computer:</span></span>

```powershell
Get-Service wmi | Start-Service
```

<span data-ttu-id="04376-133">Ein weiteres Beispiel: Sie können die Ausgabe von `Get-Item` oder `Get-ChildItem` innerhalb des PowerShell-Registrierungs Anbieters an das- `New-ItemProperty` Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="04376-133">For another example, you can pipe the output of `Get-Item` or `Get-ChildItem` within the PowerShell registry provider to the `New-ItemProperty` cmdlet.</span></span> <span data-ttu-id="04376-134">In diesem Beispiel wird dem Registrierungsschlüssel **MyCompany** ein neuer Registrierungs Eintrag, **noofemployees**, mit dem Wert **8124** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="04376-134">This example adds a new registry entry, **NoOfEmployees**, with a value of **8124**, to the **MyCompany** registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany |
  New-ItemProperty -Name NoOfEmployees -Value 8124
```

<span data-ttu-id="04376-135">Viele der hilfsprogrammcmdlets, z. b. `Get-Member` , `Where-Object` , `Sort-Object` , `Group-Object` und, `Measure-Object` werden nahezu exklusiv in Pipelines verwendet.</span><span class="sxs-lookup"><span data-stu-id="04376-135">Many of the utility cmdlets, such as `Get-Member`, `Where-Object`, `Sort-Object`, `Group-Object`, and `Measure-Object` are used almost exclusively in pipelines.</span></span> <span data-ttu-id="04376-136">Sie können einen beliebigen Objekttyp an diese Cmdlets übergeben.</span><span class="sxs-lookup"><span data-stu-id="04376-136">You can pipe any object type to these cmdlets.</span></span> <span data-ttu-id="04376-137">Dieses Beispiel zeigt, wie alle Prozesse auf dem Computer nach der Anzahl der geöffneten Handles in jedem Prozess sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="04376-137">This example shows how to sort all the processes on the computer by the number of open handles in each process.</span></span>

```powershell
Get-Process | Sort-Object -Property handles
```

<span data-ttu-id="04376-138">Sie können Objekte über die Pipeline an die Formatierungs-, Export-und Ausgabe-Cmdlets übergeben, z `Format-List` `Format-Table` . b.,, `Export-Clixml` , `Export-CSV` und `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="04376-138">You can pipe objects to the formatting, export, and output cmdlets, such as `Format-List`, `Format-Table`, `Export-Clixml`, `Export-CSV`, and `Out-File`.</span></span>

<span data-ttu-id="04376-139">Dieses Beispiel zeigt, wie das `Format-List` Cmdlet verwendet wird, um eine Liste von Eigenschaften für ein Prozess Objekt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04376-139">This example shows how to use the `Format-List` cmdlet to display a list of properties for a process object.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="04376-140">Sie können die Ausgabe der systemeigenen Befehle auch über die Pipeline an PowerShell-Cmdlets übergeben.</span><span class="sxs-lookup"><span data-stu-id="04376-140">You can also pipe the output of native commands to PowerShell cmdlets.</span></span> <span data-ttu-id="04376-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04376-141">For example:</span></span>

```powershell
PS> ipconfig.exe | Select-String -Pattern 'IPv4'

   IPv4 Address. . . . . . . . . . . : 172.24.80.1
   IPv4 Address. . . . . . . . . . . : 192.168.1.45
   IPv4 Address. . . . . . . . . . . : 100.64.108.37
```

> [!IMPORTANT]
> <span data-ttu-id="04376-142">Die **Erfolgs** -und **Fehler** Datenströme ähneln den stdin-und stderr-Datenströmen anderer Shells.</span><span class="sxs-lookup"><span data-stu-id="04376-142">The **Success** and **Error** streams are similar to the stdin and stderr streams of other shells.</span></span> <span data-ttu-id="04376-143">Stdin ist jedoch nicht für die Eingabe mit der PowerShell-Pipeline verbunden.</span><span class="sxs-lookup"><span data-stu-id="04376-143">However, stdin is not connected to the PowerShell pipeline for input.</span></span> <span data-ttu-id="04376-144">Weitere Informationen finden Sie unter [about_Redirection](about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="04376-144">For more information, see [about_Redirection](about_Redirection.md).</span></span>

<span data-ttu-id="04376-145">In der Praxis werden Sie feststellen, dass die Kombination einfacher Befehle in Pipelines Zeit und Eingabe spart und die Skripterstellung effizienter macht.</span><span class="sxs-lookup"><span data-stu-id="04376-145">With a bit of practice, you'll find that combining simple commands into pipelines saves time and typing, and makes your scripting more efficient.</span></span>

## <a name="how-pipelines-work"></a><span data-ttu-id="04376-146">Funktionsweise von Pipelines</span><span class="sxs-lookup"><span data-stu-id="04376-146">How pipelines work</span></span>

<span data-ttu-id="04376-147">In diesem Abschnitt wird erläutert, wie Eingabe Objekte an Cmdlet-Parameter gebunden und während der Pipeline Ausführung verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="04376-147">This section explains how input objects are bound to cmdlet parameters and processed during pipeline execution.</span></span>

### <a name="accepts-pipeline-input"></a><span data-ttu-id="04376-148">Akzeptiert Pipeline Eingaben</span><span class="sxs-lookup"><span data-stu-id="04376-148">Accepts pipeline input</span></span>

<span data-ttu-id="04376-149">Um Pipelining zu unterstützen, muss das empfangende Cmdlet über einen Parameter verfügen, der Pipeline Eingaben akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="04376-149">To support pipelining, the receiving cmdlet must have a parameter that accepts pipeline input.</span></span> <span data-ttu-id="04376-150">Verwenden Sie den- `Get-Help` Befehl mit den Optionen **Full** oder **Parameter** , um zu bestimmen, welche Parameter eines Cmdlets Pipeline Eingaben akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="04376-150">Use the `Get-Help` command with the **Full** or **Parameter** options to determine which parameters of a cmdlet accept pipeline input.</span></span>

<span data-ttu-id="04376-151">Geben Sie z. b. Folgendes ein, um zu bestimmen, welcher der Parameter des `Start-Service` Cmdlets Pipeline Eingaben akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="04376-151">For example, to determine which of the parameters of the `Start-Service` cmdlet accepts pipeline input, type:</span></span>

```powershell
Get-Help Start-Service -Full
```

<span data-ttu-id="04376-152">oder</span><span class="sxs-lookup"><span data-stu-id="04376-152">or</span></span>

```powershell
Get-Help Start-Service -Parameter *
```

<span data-ttu-id="04376-153">Die Hilfe für das `Start-Service` Cmdlet zeigt, dass nur der **Inputobject** -Parameter und der **Name** -Parameter Pipeline Eingaben akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="04376-153">The help for the `Start-Service` cmdlet shows that only the **InputObject** and **Name** parameters accept pipeline input.</span></span>

```Output
-InputObject <ServiceController[]>
Specifies ServiceController objects representing the services to be started.
Enter a variable that contains the objects, or type a command or expression
that gets the objects.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByValue)
Accept wildcard characters?  false

-Name <String[]>
Specifies the service names for the service to be started.

The parameter name is optional. You can use Name or its alias, ServiceName,
or you can omit the parameter name.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByPropertyName, ByValue)
Accept wildcard characters?  false
```

<span data-ttu-id="04376-154">Wenn Sie Objekte über die Pipeline an senden `Start-Service` , versucht PowerShell, die Objekte den **Inputobject** -und **Name** -Parametern zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="04376-154">When you send objects through the pipeline to `Start-Service`, PowerShell attempts to associate the objects with the **InputObject** and **Name** parameters.</span></span>

### <a name="methods-of-accepting-pipeline-input"></a><span data-ttu-id="04376-155">Methoden zum Akzeptieren von Pipeline Eingaben</span><span class="sxs-lookup"><span data-stu-id="04376-155">Methods of accepting pipeline input</span></span>

<span data-ttu-id="04376-156">Cmdlets-Parameter können eine Pipeline Eingabe auf zwei verschiedene Arten akzeptieren:</span><span class="sxs-lookup"><span data-stu-id="04376-156">Cmdlets parameters can accept pipeline input in one of two different ways:</span></span>

- <span data-ttu-id="04376-157">**Byvalue**: der Parameter akzeptiert Werte, die dem erwarteten .NET-Typ entsprechen oder in diesen Typ konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="04376-157">**ByValue**: The parameter accepts values that match the expected .NET type or that can be converted to that type.</span></span>

  <span data-ttu-id="04376-158">Der **Name** -Parameter von akzeptiert beispielsweise `Start-Service` Pipeline Eingaben nach Wert.</span><span class="sxs-lookup"><span data-stu-id="04376-158">For example, the **Name** parameter of `Start-Service` accepts pipeline input by value.</span></span> <span data-ttu-id="04376-159">Sie kann Zeichen folgen Objekte oder-Objekte akzeptieren, die in Zeichen folgen konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="04376-159">It can accept string objects or objects that can be converted to strings.</span></span>

- <span data-ttu-id="04376-160">**Bypropertyname**: der-Parameter akzeptiert nur Eingaben, wenn das Eingabe Objekt eine Eigenschaft mit dem gleichen Namen wie der-Parameter aufweist.</span><span class="sxs-lookup"><span data-stu-id="04376-160">**ByPropertyName**: The parameter accepts input only when the input object has a property of the same name as the parameter.</span></span>

  <span data-ttu-id="04376-161">Der Name-Parameter von kann z `Start-Service` . b.-Objekte akzeptieren, die über eine **Name** -Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="04376-161">For example, the Name parameter of `Start-Service` can accept objects that have a **Name** property.</span></span> <span data-ttu-id="04376-162">Um die Eigenschaften eines Objekts aufzulisten, übergeben Sie es an `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="04376-162">To list the properties of an object, pipe it to `Get-Member`.</span></span>

<span data-ttu-id="04376-163">Einige Parameter können Objekte sowohl nach Wert als auch nach Eigenschaftsname akzeptieren, sodass Sie die Eingabe von der Pipeline vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="04376-163">Some parameters can accept objects by both value or property name, making it easier to take input from the pipeline.</span></span>

### <a name="parameter-binding"></a><span data-ttu-id="04376-164">Parameterbindung</span><span class="sxs-lookup"><span data-stu-id="04376-164">Parameter binding</span></span>

<span data-ttu-id="04376-165">Wenn Sie Objekte von einem Befehl an einen anderen Befehl übergeben, versucht PowerShell, die weitergeleiteten Objekte einem Parameter des empfangenden Cmdlets zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="04376-165">When you pipe objects from one command to another command, PowerShell attempts to associate the piped objects with a parameter of the receiving cmdlet.</span></span>

<span data-ttu-id="04376-166">Die Parameter bindungskomponente von PowerShell ordnet die Eingabe Objekte den Cmdlet-Parametern gemäß den folgenden Kriterien zu:</span><span class="sxs-lookup"><span data-stu-id="04376-166">PowerShell's parameter binding component associates the input objects with cmdlet parameters according to the following criteria:</span></span>

- <span data-ttu-id="04376-167">Der-Parameter muss Eingaben aus einer Pipeline akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="04376-167">The parameter must accept input from a pipeline.</span></span>
- <span data-ttu-id="04376-168">Der-Parameter muss den Typ des gesendeten Objekts oder einen Typ akzeptieren, der in den erwarteten Typ konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="04376-168">The parameter must accept the type of object being sent or a type that can be converted to the expected type.</span></span>
- <span data-ttu-id="04376-169">Der-Parameter wurde im Befehl nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="04376-169">The parameter wasn't used in the command.</span></span>

<span data-ttu-id="04376-170">Beispielsweise hat das `Start-Service` Cmdlet viele Parameter, aber nur zwei von Ihnen, **Name** und **Inputobject** akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="04376-170">For example, the `Start-Service` cmdlet has many parameters, but only two of them, **Name** and **InputObject** accept pipeline input.</span></span> <span data-ttu-id="04376-171">Der **Name** -Parameter nimmt Zeichen folgen an, und der **Inputobject** -Parameter übernimmt Dienst Objekte.</span><span class="sxs-lookup"><span data-stu-id="04376-171">The **Name** parameter takes strings and the **InputObject** parameter takes service objects.</span></span> <span data-ttu-id="04376-172">Daher können Sie Zeichen folgen, Dienst Objekte und Objekte mit Eigenschaften übergeben, die in Zeichen folgen-oder Dienst Objekte konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="04376-172">Therefore, you can pipe strings, service objects, and objects with properties that can be converted to string or service objects.</span></span>

<span data-ttu-id="04376-173">PowerShell verwaltet die Parameter Bindung so effizient wie möglich.</span><span class="sxs-lookup"><span data-stu-id="04376-173">PowerShell manages parameter binding as efficiently as possible.</span></span> <span data-ttu-id="04376-174">Sie können nicht vorschlagen oder erzwingen, dass PowerShell an einen bestimmten Parameter gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="04376-174">You can't suggest or force the PowerShell to bind to a specific parameter.</span></span> <span data-ttu-id="04376-175">Der Befehl schlägt fehl, wenn die weitergeleiteten Objekte von PowerShell nicht gebunden werden können.</span><span class="sxs-lookup"><span data-stu-id="04376-175">The command fails if PowerShell can't bind the piped objects.</span></span>

<span data-ttu-id="04376-176">Weitere Informationen zur Problembehandlung bei Bindungs Fehlern finden Sie unter unter [Suchen von Pipeline Fehlern](#investigating-pipeline-errors) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="04376-176">For more information about troubleshooting binding errors, see [Investigating Pipeline Errors](#investigating-pipeline-errors) later in this article.</span></span>

### <a name="one-at-a-time-processing"></a><span data-ttu-id="04376-177">Uni-at-a-Time-Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="04376-177">One-at-a-time processing</span></span>

<span data-ttu-id="04376-178">Das Weiterleiten von Objekten an einen Befehl ähnelt dem Verwenden eines Parameters des Befehls, um die Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="04376-178">Piping objects to a command is much like using a parameter of the command to submit the objects.</span></span> <span data-ttu-id="04376-179">Sehen wir uns ein Beispiel für eine Pipeline an.</span><span class="sxs-lookup"><span data-stu-id="04376-179">Let's look at a pipeline example.</span></span> <span data-ttu-id="04376-180">In diesem Beispiel verwenden wir eine Pipeline, um eine Tabelle mit Dienst Objekten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04376-180">In this example, we use a pipeline to display a table of service objects.</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="04376-181">Funktionell ist dies die Verwendung des **Inputobject** -Parameters von `Format-Table` zum übermitteln der Objekt Auflistung.</span><span class="sxs-lookup"><span data-stu-id="04376-181">Functionally, this is like using the **InputObject** parameter of `Format-Table` to submit the object collection.</span></span>

<span data-ttu-id="04376-182">Beispielsweise können wir die Auflistung der Dienste in einer Variablen speichern, die mithilfe des **Inputobject** -Parameters übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="04376-182">For example, we can save the collection of services to a variable that is passed using the **InputObject** parameter.</span></span>

```powershell
$services = Get-Service
Format-Table -InputObject $services -Property Name, DependentServices
```

<span data-ttu-id="04376-183">Oder Sie können den Befehl in den **Inputobject-Parameter einbetten** .</span><span class="sxs-lookup"><span data-stu-id="04376-183">Or we can embed the command in the **InputObject** parameter.</span></span>

```powershell
Format-Table -InputObject (Get-Service) -Property Name, DependentServices
```

<span data-ttu-id="04376-184">Es gibt jedoch einen wichtigen Unterschied.</span><span class="sxs-lookup"><span data-stu-id="04376-184">However, there's an important difference.</span></span> <span data-ttu-id="04376-185">Wenn Sie mehrere Objekte an einen Befehl übergeben, sendet PowerShell die Objekte nacheinander an den Befehl.</span><span class="sxs-lookup"><span data-stu-id="04376-185">When you pipe multiple objects to a command, PowerShell sends the objects to the command one at a time.</span></span> <span data-ttu-id="04376-186">Wenn Sie einen Command-Parameter verwenden, werden die-Objekte als einzelnes Array Objekt gesendet.</span><span class="sxs-lookup"><span data-stu-id="04376-186">When you use a command parameter, the objects are sent as a single array object.</span></span> <span data-ttu-id="04376-187">Dieser geringfügige Unterschied hat bedeutende Konsequenzen.</span><span class="sxs-lookup"><span data-stu-id="04376-187">This minor difference has significant consequences.</span></span>

<span data-ttu-id="04376-188">Beim Ausführen einer Pipeline listet PowerShell automatisch jeden Typ auf, der die- `IEnumerable` Schnittstelle implementiert, und sendet die Elemente nacheinander über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="04376-188">When executing a pipeline, PowerShell automatically enumerates any type that implements the `IEnumerable` interface and sends the members through the pipeline one at a time.</span></span> <span data-ttu-id="04376-189">Die Ausnahme ist `[hashtable]` , was einen aufzurufenden- `GetEnumerator()` Methode erfordert.</span><span class="sxs-lookup"><span data-stu-id="04376-189">The exception is `[hashtable]`, which requires a call to the `GetEnumerator()` method.</span></span>

<span data-ttu-id="04376-190">In den folgenden Beispielen werden ein Array und eine Hash Tabelle an das `Measure-Object` Cmdlet weitergeleitet, um die Anzahl der Objekte zu zählen, die von der Pipeline empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="04376-190">In the following examples, an array and a hashtable are piped to the `Measure-Object` cmdlet to count the number of objects received from the pipeline.</span></span> <span data-ttu-id="04376-191">Das Array verfügt über mehrere Member, und die Hash Tabelle verfügt über mehrere Schlüssel-Wert-Paare.</span><span class="sxs-lookup"><span data-stu-id="04376-191">The array has multiple members, and the hashtable has multiple key-value pairs.</span></span> <span data-ttu-id="04376-192">Nur das Array wird nacheinander aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="04376-192">Only the array is enumerated one at a time.</span></span>

```powershell
@(1,2,3) | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

```powershell
@{"One"=1;"Two"=2} | Measure-Object
```

```Output
Count    : 1
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

<span data-ttu-id="04376-193">Wenn Sie mehrere Prozess Objekte aus dem `Get-Process` Cmdlet an das `Get-Member` Cmdlet weiterreichen, sendet PowerShell jedes Prozess Objekt einzeln an `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="04376-193">Similarly, if you pipe multiple process objects from the `Get-Process` cmdlet to the `Get-Member` cmdlet, PowerShell sends each process object, one at a time, to `Get-Member`.</span></span> <span data-ttu-id="04376-194">`Get-Member` zeigt die .NET-Klasse (Typ) der Prozess Objekte und ihre Eigenschaften und Methoden an.</span><span class="sxs-lookup"><span data-stu-id="04376-194">`Get-Member` displays the .NET class (type) of the process objects, and their properties and methods.</span></span>

```powershell
Get-Process | Get-Member
```

```Output
TypeName: System.Diagnostics.Process

Name      MemberType     Definition
----      ----------     ----------
Handles   AliasProperty  Handles = Handlecount
Name      AliasProperty  Name = ProcessName
NPM       AliasProperty  NPM = NonpagedSystemMemorySize
...
```

> [!NOTE]
> <span data-ttu-id="04376-195">`Get-Member` entfernt Duplikate, sodass nur ein Objekttyp angezeigt wird, wenn die Objekte alle denselben Typ haben.</span><span class="sxs-lookup"><span data-stu-id="04376-195">`Get-Member` eliminates duplicates, so if the objects are all of the same type, it only displays one object type.</span></span>

<span data-ttu-id="04376-196">Wenn Sie jedoch den **Inputobject** -Parameter von verwenden `Get-Member` , `Get-Member` empfängt ein Array von **System. Diagnostics. Process** -Objekten als einzelne Einheit.</span><span class="sxs-lookup"><span data-stu-id="04376-196">However, if you use the **InputObject** parameter of `Get-Member`, then `Get-Member` receives an array of **System.Diagnostics.Process** objects as a single unit.</span></span> <span data-ttu-id="04376-197">Es zeigt die Eigenschaften eines Arrays von-Objekten an.</span><span class="sxs-lookup"><span data-stu-id="04376-197">It displays the properties of an array of objects.</span></span> <span data-ttu-id="04376-198">(Beachten Sie das Array Symbol ( `[]` ) nach dem **System. Object** -Typnamen.)</span><span class="sxs-lookup"><span data-stu-id="04376-198">(Note the array symbol (`[]`) after the **System.Object** type name.)</span></span>

<span data-ttu-id="04376-199">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04376-199">For example,</span></span>

```powershell
Get-Member -InputObject (Get-Process)
```

```Output
TypeName: System.Object[]

Name               MemberType    Definition
----               ----------    ----------
Count              AliasProperty Count = Length
Address            Method        System.Object& Address(Int32 )
Clone              Method        System.Object Clone()
...
```

<span data-ttu-id="04376-200">Das Ergebnis ist möglicherweise nicht das, was Sie beabsichtigt haben.</span><span class="sxs-lookup"><span data-stu-id="04376-200">This result might not be what you intended.</span></span> <span data-ttu-id="04376-201">Aber nachdem Sie es verstanden haben, können Sie es verwenden.</span><span class="sxs-lookup"><span data-stu-id="04376-201">But after you understand it, you can use it.</span></span> <span data-ttu-id="04376-202">Beispielsweise verfügen alle Array Objekte über eine **count** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="04376-202">For example, all array objects have a **Count** property.</span></span> <span data-ttu-id="04376-203">Damit können Sie die Anzahl der Prozesse zählen, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="04376-203">You can use that to count the number of processes running on the computer.</span></span>

<span data-ttu-id="04376-204">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04376-204">For example,</span></span>

```powershell
(Get-Process).count
```

<span data-ttu-id="04376-205">Beachten Sie, dass Objekte, die über die Pipeline gesendet werden, nacheinander zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="04376-205">It's important to remember that objects sent down the pipeline are delivered one at a time.</span></span>

## <a name="investigating-pipeline-errors"></a><span data-ttu-id="04376-206">Untersuchen von Pipeline Fehlern</span><span class="sxs-lookup"><span data-stu-id="04376-206">Investigating pipeline errors</span></span>

<span data-ttu-id="04376-207">Wenn PowerShell die weitergeleiteten Objekte keinem Parameter des empfangenden Cmdlets zuordnen kann, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="04376-207">When PowerShell can't associate the piped objects with a parameter of the receiving cmdlet, the command fails.</span></span>

<span data-ttu-id="04376-208">Im folgenden Beispiel wird versucht, einen Registrierungs Eintrag aus einem Registrierungsschlüssel in einen anderen zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="04376-208">In the following example, we try to move a registry entry from one registry key to another.</span></span> <span data-ttu-id="04376-209">Mit dem- `Get-Item` Cmdlet wird der Zielpfad abgerufen, der dann an das `Move-ItemProperty` Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="04376-209">The `Get-Item` cmdlet gets the destination path, which is then piped to the `Move-ItemProperty` cmdlet.</span></span> <span data-ttu-id="04376-210">Der `Move-ItemProperty` Befehl gibt den aktuellen Pfad und Namen des Registrierungs Eintrags an, der verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="04376-210">The `Move-ItemProperty` command specifies the current path and name of the registry entry to be moved.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales |
Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
```

<span data-ttu-id="04376-211">Der Befehl schlägt fehl, und PowerShell zeigt die folgende Fehlermeldung an:</span><span class="sxs-lookup"><span data-stu-id="04376-211">The command fails and PowerShell displays the following error message:</span></span>

```Output
Move-ItemProperty : The input object can't be bound to any parameters for
the command either because the command doesn't take pipeline input or the
input and its properties do not match any of the parameters that take
pipeline input.
At line:1 char:23
+ $a | Move-ItemProperty <<<<  -Path HKLM:\Software\MyCompany\design -Name p
```

<span data-ttu-id="04376-212">Um dies zu untersuchen, verwenden Sie das- `Trace-Command` Cmdlet, um die Parameter bindungskomponente von PowerShell zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="04376-212">To investigate, use the `Trace-Command` cmdlet to trace the parameter binding component of PowerShell.</span></span> <span data-ttu-id="04376-213">Im folgenden Beispiel wird die Parameter Bindung nachverfolgt, während die Pipeline ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="04376-213">The following example traces parameter binding while the pipeline is executing.</span></span> <span data-ttu-id="04376-214">Der **pshost** -Parameter zeigt die Ablauf Verfolgungs Ergebnisse in der-Konsole an, und der **FilePath** -Parameter sendet die Ablauf Verfolgungs Ergebnisse zur `debug.txt` späteren Referenz an die Datei.</span><span class="sxs-lookup"><span data-stu-id="04376-214">The **PSHost** parameter displays the trace results in the console and the **FilePath** parameter send the trace results to the `debug.txt` file for later reference.</span></span>

```powershell
Trace-Command -Name ParameterBinding -PSHost -FilePath debug.txt -Expression {
  Get-Item -Path HKLM:\Software\MyCompany\sales |
    Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
}
```

<span data-ttu-id="04376-215">Die Ergebnisse der Ablauf Verfolgung sind langwierig, aber Sie zeigen die Werte an, die an das `Get-Item` Cmdlet gebunden werden, und dann die benannten Werte, die an das `Move-ItemProperty` Cmdlet gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="04376-215">The results of the trace are lengthy, but they show the values being bound to the `Get-Item` cmdlet and then the named values being bound to the `Move-ItemProperty` cmdlet.</span></span>

```Output
...
BIND NAMED cmd line args [`Move-ItemProperty`]
BIND arg [HKLM:\Software\MyCompany\design] to parameter [Path]
...
BIND arg [product] to parameter [Name]
...
BIND POSITIONAL cmd line args [`Move-ItemProperty`]
...
```

<span data-ttu-id="04376-216">Schließlich wird angezeigt, dass der Versuch, den Pfad an den **Ziel** Parameter von zu binden, `Move-ItemProperty` fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="04376-216">Finally, it shows that the attempt to bind the path to the **Destination** parameter of `Move-ItemProperty` failed.</span></span>

```Output
...
BIND PIPELINE object to parameters: [`Move-ItemProperty`]
PIPELINE object TYPE = [Microsoft.Win32.RegistryKey]
RESTORING pipeline parameter's original values
Parameter [Destination] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
Parameter [Credential] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
...
```

<span data-ttu-id="04376-217">Verwenden Sie das- `Get-Help` Cmdlet, um die Attribute des **Destination** -Parameters anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04376-217">Use the `Get-Help` cmdlet to view the attributes of the **Destination** parameter.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Destination

-Destination <String>
    Specifies the path to the destination location.

    Required?                    true
    Position?                    1
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  false
```

<span data-ttu-id="04376-218">Die Ergebnisse zeigen an, dass das **Ziel** nur Pipeline Eingaben "by Property Name" annimmt.</span><span class="sxs-lookup"><span data-stu-id="04376-218">The results show that **Destination** takes pipeline input only "by property name".</span></span> <span data-ttu-id="04376-219">Daher muss das weitergeleitete Objekt über eine Eigenschaft mit dem Namen " **Destination**" verfügen.</span><span class="sxs-lookup"><span data-stu-id="04376-219">Therefore, the piped object must have a property named **Destination**.</span></span>

<span data-ttu-id="04376-220">Verwenden `Get-Member` Sie, um die Eigenschaften des Objekts anzuzeigen, das aus stammt `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="04376-220">Use `Get-Member` to see the properties of the object coming from `Get-Item`.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales | Get-Member
```

<span data-ttu-id="04376-221">Die Ausgabe zeigt, dass es sich bei dem Element um ein **Microsoft. Win32. RegistryKey** -Objekt handelt, das nicht über eine **Ziel** Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="04376-221">The output shows that the item is a **Microsoft.Win32.RegistryKey** object that doesn't have a **Destination** property.</span></span> <span data-ttu-id="04376-222">Dies erläutert, warum der Befehl fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="04376-222">That explains why the command failed.</span></span>

<span data-ttu-id="04376-223">Der **path** -Parameter akzeptiert Pipeline Eingaben nach Namen oder Wert.</span><span class="sxs-lookup"><span data-stu-id="04376-223">The **Path** parameter accepts pipeline input by name or by value.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Path

-Path <String[]>
    Specifies the path to the current location of the property. Wildcard
    characters are permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  true
```

<span data-ttu-id="04376-224">Zum Beheben des Befehls müssen wir das Ziel im `Move-ItemProperty` Cmdlet angeben und verwenden `Get-Item` , um den **Pfad** des Elements zu erhalten, das verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="04376-224">To fix the command, we must specify the destination in the `Move-ItemProperty` cmdlet and use `Get-Item` to get the **Path** of the item we want to move.</span></span>

<span data-ttu-id="04376-225">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04376-225">For example,</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\design |
Move-ItemProperty -Destination HKLM:\Software\MyCompany\sales -Name product
```

## <a name="intrinsic-line-continuation"></a><span data-ttu-id="04376-226">Intrinsische Zeilen Fortsetzung</span><span class="sxs-lookup"><span data-stu-id="04376-226">Intrinsic line continuation</span></span>

<span data-ttu-id="04376-227">Wie bereits erwähnt, besteht eine Pipeline aus einer Reihe von Befehlen, die durch Pipeline Operatoren ( `|` ) verbunden sind, die in der Regel in einer einzelnen Zeile geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="04376-227">As already discussed, a pipeline is a series of commands connected by pipeline operators (`|`), usually written on a single line.</span></span> <span data-ttu-id="04376-228">Zur besseren Lesbarkeit ermöglicht Ihnen PowerShell jedoch, die Pipeline über mehrere Zeilen hinweg aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="04376-228">However, for readability, PowerShell allows you to split the pipeline across multiple lines.</span></span>
<span data-ttu-id="04376-229">Wenn ein Pipeoperator das letzte Token in der Zeile ist, fügt der PowerShell-Parser den Befehl nächste Zeile zum aktuellen Befehl ein, um die Erstellung der Pipeline fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="04376-229">When a pipe operator is the last token on the line, the PowerShell parser joins the next line to current command to continue the construction of the pipeline.</span></span>

<span data-ttu-id="04376-230">Beispielsweise die folgende einzeilige Pipeline:</span><span class="sxs-lookup"><span data-stu-id="04376-230">For example, the following single-line pipeline:</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="04376-231">kann wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="04376-231">can be written as:</span></span>

```powershell
Command-1 |
  Command-2 |
    Command-3
```

<span data-ttu-id="04376-232">Die führenden Leerzeichen in den nachfolgenden Zeilen sind nicht von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="04376-232">The leading spaces on the subsequent lines are not significant.</span></span> <span data-ttu-id="04376-233">Der Einzug verbessert die Lesbarkeit.</span><span class="sxs-lookup"><span data-stu-id="04376-233">The indentation enhances readability.</span></span>

<span data-ttu-id="04376-234">PowerShell 7 fügt Unterstützung für die Fortsetzung von Pipelines mit dem Pipeline Zeichen am Anfang einer Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="04376-234">PowerShell 7 adds support for continuation of pipelines with the pipeline character at the beginning of a line.</span></span> <span data-ttu-id="04376-235">In den folgenden Beispielen wird gezeigt, wie Sie diese neue Funktion verwenden können.</span><span class="sxs-lookup"><span data-stu-id="04376-235">The following examples show how you could use this new functionality.</span></span>

```powershell
# Wrapping with a pipe at the beginning of a line (no backtick required)
Get-Process | Where-Object CPU | Where-Object Path
    | Get-Item | Where-Object FullName -match "AppData"
    | Sort-Object FullName -Unique

# Wrapping with a pipe on a line by itself
Get-Process | Where-Object CPU | Where-Object Path
    |
    Get-Item | Where-Object FullName -match "AppData"
    |
    Sort-Object FullName -Unique
```

> [!IMPORTANT]
> <span data-ttu-id="04376-236">Wenn Sie in der Shell interaktiv arbeiten, fügen Sie Code nur am Anfang einer Zeile mit Pipelines ein, wenn <kbd></kbd>Sie + zum Einfügen Strg<kbd>V</kbd> verwenden.</span><span class="sxs-lookup"><span data-stu-id="04376-236">When working interactively in the shell, pasting code with pipelines at the beginning of a line only when using <kbd>Ctrl</kbd>+<kbd>V</kbd> to paste.</span></span>
> <span data-ttu-id="04376-237">Klicken Sie mit der rechten Maustaste auf Einfügevorgänge, um die Zeilen einzeln einzufügen.</span><span class="sxs-lookup"><span data-stu-id="04376-237">Right-click paste operations insert the lines one at a time.</span></span> <span data-ttu-id="04376-238">Da die Zeile nicht mit einem Pipeline Zeichen endet, betrachtet PowerShell die Eingabe als abgeschlossen und führt diese Zeile wie eingegeben aus.</span><span class="sxs-lookup"><span data-stu-id="04376-238">Since the line does not end with a pipeline character, PowerShell considers the input to be complete and executes that line as entered.</span></span>

## <a name="see-also"></a><span data-ttu-id="04376-239">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04376-239">See Also</span></span>

[<span data-ttu-id="04376-240">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="04376-240">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="04376-241">about_Objects</span><span class="sxs-lookup"><span data-stu-id="04376-241">about_Objects</span></span>](about_objects.md)

[<span data-ttu-id="04376-242">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="04376-242">about_Parameters</span></span>](about_parameters.md)

[<span data-ttu-id="04376-243">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="04376-243">about_Command_Syntax</span></span>](about_command_syntax.md)

[<span data-ttu-id="04376-244">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="04376-244">about_ForEach</span></span>](about_foreach.md)
