---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Host
ms.openlocfilehash: 4fefb133416b3db6c19c71a916d73fe00f86f3a4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601906"
---
# <span data-ttu-id="450e1-102">Out-Host</span><span class="sxs-lookup"><span data-stu-id="450e1-102">Out-Host</span></span>

## <span data-ttu-id="450e1-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="450e1-103">SYNOPSIS</span></span>
<span data-ttu-id="450e1-104">Sendet eine Ausgabe an die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="450e1-104">Sends output to the command line.</span></span>

## <span data-ttu-id="450e1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="450e1-105">SYNTAX</span></span>

### <span data-ttu-id="450e1-106">Alle</span><span class="sxs-lookup"><span data-stu-id="450e1-106">All</span></span>

```
Out-Host [-Paging] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="450e1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="450e1-107">DESCRIPTION</span></span>

<span data-ttu-id="450e1-108">Das `Out-Host` Cmdlet sendet die Ausgabe zur Anzeige an den PowerShell-Host.</span><span class="sxs-lookup"><span data-stu-id="450e1-108">The `Out-Host` cmdlet sends output to the PowerShell host for display.</span></span> <span data-ttu-id="450e1-109">Der Host zeigt die Ausgabe in der Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="450e1-109">The host displays the output at the command line.</span></span> <span data-ttu-id="450e1-110">Da `Out-Host` der Standardwert ist, müssen Sie ihn nicht angeben, es sei denn, Sie möchten seine Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="450e1-110">Because `Out-Host` is the default, you don't have to specify it unless you want to use its parameters.</span></span>

<span data-ttu-id="450e1-111">`Out-Host` wird automatisch an jeden Befehl angehängt, der ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="450e1-111">`Out-Host` is automatically appended to every command that is executed.</span></span> <span data-ttu-id="450e1-112">Sie übergibt die Ausgabe der Pipeline an den Host, der den Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="450e1-112">It passes the output of the pipeline to the host executing the command.</span></span> <span data-ttu-id="450e1-113">`Out-Host` ignoriert ANSI-Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="450e1-113">`Out-Host` ignores ANSI escape sequences.</span></span> <span data-ttu-id="450e1-114">Die Escapesequenzen werden vom Host behandelt.</span><span class="sxs-lookup"><span data-stu-id="450e1-114">The escape sequences are handled by the host.</span></span> <span data-ttu-id="450e1-115">`Out-Host` übergibt ANSI-Escapesequenzen an den Host, ohne zu versuchen, Sie zu interpretieren oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="450e1-115">`Out-Host` passes ANSI escape sequences to the host without trying to interpret or change them.</span></span>

## <span data-ttu-id="450e1-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="450e1-116">EXAMPLES</span></span>

### <span data-ttu-id="450e1-117">Beispiel 1: Anzeigen der Ausgabeseiten Weise</span><span class="sxs-lookup"><span data-stu-id="450e1-117">Example 1: Display output one page at a time</span></span>

<span data-ttu-id="450e1-118">In diesem Beispiel werden die System Prozesse jeweils auf einer Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="450e1-118">This example displays the system processes one page at a time.</span></span>

```powershell
Get-Process | Out-Host -Paging
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     30    24.12      36.95      15.86   21004  14 ApplicationFrameHost
     55    24.33      60.48      10.80   12904  14 BCompare
<SPACE> next page; <CR> next line; Q quit
      9     4.71       8.94       0.00   16864  14 explorer
<SPACE> next page; <CR> next line; Q quit
```

<span data-ttu-id="450e1-119">`Get-Process` Ruft die System Prozesse ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="450e1-119">`Get-Process` gets the system processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="450e1-120">`Out-Host` verwendet den **Paging** -Parameter, um jeweils eine Seite mit Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="450e1-120">`Out-Host` uses the **Paging** parameter to display one page of data at a time.</span></span>

### <span data-ttu-id="450e1-121">Beispiel 2: Verwenden einer Variablen als Eingabe</span><span class="sxs-lookup"><span data-stu-id="450e1-121">Example 2: Use a variable as input</span></span>

<span data-ttu-id="450e1-122">In diesem Beispiel werden-Objekte, die in einer Variablen gespeichert sind, als Eingabe für verwendet `Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="450e1-122">This example uses objects stored in a variable as the input for `Out-Host`.</span></span>

```powershell
$io = Get-History
Out-Host -InputObject $io
```

<span data-ttu-id="450e1-123">`Get-History` Ruft den Verlauf der PowerShell-Sitzung ab und speichert die Objekte in der `$io` Variablen.</span><span class="sxs-lookup"><span data-stu-id="450e1-123">`Get-History` gets the PowerShell session's history, and stores the objects in the `$io` variable.</span></span>
<span data-ttu-id="450e1-124">`Out-Host` verwendet den **Inputobject** -Parameter, um die Variable anzugeben, `$io` und zeigt den Verlauf an.</span><span class="sxs-lookup"><span data-stu-id="450e1-124">`Out-Host` uses the **InputObject** parameter to specify the `$io` variable and displays the history.</span></span>

## <span data-ttu-id="450e1-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="450e1-125">PARAMETERS</span></span>

### <span data-ttu-id="450e1-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="450e1-126">-InputObject</span></span>

<span data-ttu-id="450e1-127">Gibt die Objekte an, die in die Konsole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="450e1-127">Specifies the objects that are written to the console.</span></span> <span data-ttu-id="450e1-128">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="450e1-128">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="450e1-129">-Paging</span><span class="sxs-lookup"><span data-stu-id="450e1-129">-Paging</span></span>

<span data-ttu-id="450e1-130">Gibt an, dass `Out-Host` eine Seite der Ausgabe gleichzeitig anzeigt und auf die Benutzereingabe wartet, bevor die verbleibenden Seiten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="450e1-130">Indicates that `Out-Host` displays one page of output at a time, and waits for user input before the remaining pages are displayed.</span></span> <span data-ttu-id="450e1-131">Standardmäßig wird die gesamte Ausgabe auf einer einzelnen Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="450e1-131">By default, all the output is displayed on a single page.</span></span> <span data-ttu-id="450e1-132">Die Seitengröße wird durch die Eigenschaften des Hosts bestimmt.</span><span class="sxs-lookup"><span data-stu-id="450e1-132">The page size is determined by the characteristics of the host.</span></span>

<span data-ttu-id="450e1-133">Drücken Sie die <kbd>LEERTASTE</kbd> , um die nächste Seite der Ausgabe anzuzeigen, oder drücken <kbd>Sie die Eingabe</kbd> Taste, um die nächste Zeile der Ausgabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="450e1-133">Press the <kbd>Space</kbd> bar to display the next page of output or the <kbd>Enter</kbd> key to view the next line of output.</span></span> <span data-ttu-id="450e1-134">Drücken Sie <kbd>Q</kbd> zum Beenden.</span><span class="sxs-lookup"><span data-stu-id="450e1-134">Press <kbd>Q</kbd> to quit.</span></span>

<span data-ttu-id="450e1-135">**Paging** ähnelt dem **more** -Befehl.</span><span class="sxs-lookup"><span data-stu-id="450e1-135">**Paging** is similar to the **more** command.</span></span>

> [!NOTE]
> <span data-ttu-id="450e1-136">Der **Paging** -Parameter wird vom PowerShell ISE-Host nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="450e1-136">The **Paging** parameter isn't supported by the PowerShell ISE host.</span></span>

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

### <span data-ttu-id="450e1-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="450e1-137">CommonParameters</span></span>

<span data-ttu-id="450e1-138">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="450e1-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="450e1-139">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="450e1-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="450e1-140">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="450e1-140">INPUTS</span></span>

### <span data-ttu-id="450e1-141">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="450e1-141">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="450e1-142">Sie können Objekte über die Pipeline an senden `Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="450e1-142">You can send objects down the pipeline to `Out-Host`.</span></span>

## <span data-ttu-id="450e1-143">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="450e1-143">OUTPUTS</span></span>

### <span data-ttu-id="450e1-144">Keine</span><span class="sxs-lookup"><span data-stu-id="450e1-144">None</span></span>

<span data-ttu-id="450e1-145">`Out-Host` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="450e1-145">`Out-Host` doesn't generate any output.</span></span> <span data-ttu-id="450e1-146">Objekte werden zur Anzeige an den Host gesendet.</span><span class="sxs-lookup"><span data-stu-id="450e1-146">It sends objects to the host for display.</span></span>

## <span data-ttu-id="450e1-147">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="450e1-147">NOTES</span></span>

<span data-ttu-id="450e1-148">Der **Paging** -Parameter wird nicht von allen PowerShell-Hosts unterstützt.</span><span class="sxs-lookup"><span data-stu-id="450e1-148">The **Paging** parameter isn't supported by all PowerShell hosts.</span></span> <span data-ttu-id="450e1-149">Wenn Sie z. b. den **Paging** -Parameter in der PowerShell ISE verwenden, wird der folgende Fehler angezeigt: `out-lineoutput : The method or operation is not implemented.`</span><span class="sxs-lookup"><span data-stu-id="450e1-149">For example, if you use the **Paging** parameter in the PowerShell ISE, the following error is displayed: `out-lineoutput : The method or operation is not implemented.`</span></span>

<span data-ttu-id="450e1-150">Mit den Cmdlets, die das **out** -Verb enthalten, `Out-` werden keine Objekte formatiert.</span><span class="sxs-lookup"><span data-stu-id="450e1-150">The cmdlets that contain the **Out** verb, `Out-`, don't format objects.</span></span> <span data-ttu-id="450e1-151">Sie Rendering-Objekte und senden Sie an das angegebene Anzeige Ziel.</span><span class="sxs-lookup"><span data-stu-id="450e1-151">They render objects and send them to the specified display destination.</span></span> <span data-ttu-id="450e1-152">Wenn Sie ein unformatiertes Objekt an ein `Out-` Cmdlet senden, sendet das Cmdlet es vor dem Rendern an ein Formatierungs-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="450e1-152">If you send an unformatted object to an `Out-` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="450e1-153">Die `Out-` Cmdlets enthalten keine Parameter für Namen oder Dateipfade.</span><span class="sxs-lookup"><span data-stu-id="450e1-153">The `Out-` cmdlets don't have parameters for names or file paths.</span></span> <span data-ttu-id="450e1-154">Verwenden Sie zum Senden von Daten an ein `Out-` Cmdlet die Pipeline, um die Ausgabe eines PowerShell-Befehls an das Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="450e1-154">To send data to an `Out-` cmdlet, use the pipeline to send a PowerShell command's output to the cmdlet.</span></span> <span data-ttu-id="450e1-155">Oder Sie können Daten in einer Variablen speichern und den **Inputobject** -Parameter verwenden, um die Daten an das Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="450e1-155">Or, you can store data in a variable and use the **InputObject** parameter to pass the data to the cmdlet.</span></span>

<span data-ttu-id="450e1-156">`Out-Host` sendet Daten, aber es werden keine Ausgabe Objekte erzeugt.</span><span class="sxs-lookup"><span data-stu-id="450e1-156">`Out-Host` sends data, but it doesn't produce any output objects.</span></span> <span data-ttu-id="450e1-157">Wenn Sie die Ausgabe von `Out-Host` an das `Get-Member` Cmdlet weitergeben, `Get-Member` meldet, dass keine Objekte angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="450e1-157">If you pipeline the output of `Out-Host` to the `Get-Member` cmdlet, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="450e1-158">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="450e1-158">RELATED LINKS</span></span>

[<span data-ttu-id="450e1-159">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="450e1-159">Clear-Host</span></span>](Clear-Host.md)

[<span data-ttu-id="450e1-160">Out-Default</span><span class="sxs-lookup"><span data-stu-id="450e1-160">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="450e1-161">Out-File</span><span class="sxs-lookup"><span data-stu-id="450e1-161">Out-File</span></span>](../Microsoft.PowerShell.Utility/Out-File.md)

[<span data-ttu-id="450e1-162">Out-Null</span><span class="sxs-lookup"><span data-stu-id="450e1-162">Out-Null</span></span>](Out-Null.md)

[<span data-ttu-id="450e1-163">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="450e1-163">Out-Printer</span></span>](../Microsoft.PowerShell.Utility/Out-Printer.md)

[<span data-ttu-id="450e1-164">Out-String</span><span class="sxs-lookup"><span data-stu-id="450e1-164">Out-String</span></span>](../Microsoft.PowerShell.Utility/Out-String.md)

[<span data-ttu-id="450e1-165">Write-Host</span><span class="sxs-lookup"><span data-stu-id="450e1-165">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)

