---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Host
ms.openlocfilehash: e3b009ae92abde371a4a6380d0ac6d491093333f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210652"
---
# <span data-ttu-id="36f87-103">Out-Host</span><span class="sxs-lookup"><span data-stu-id="36f87-103">Out-Host</span></span>

## <span data-ttu-id="36f87-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="36f87-104">SYNOPSIS</span></span>
<span data-ttu-id="36f87-105">Sendet eine Ausgabe an die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="36f87-105">Sends output to the command line.</span></span>

## <span data-ttu-id="36f87-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="36f87-106">SYNTAX</span></span>

### <span data-ttu-id="36f87-107">Alle</span><span class="sxs-lookup"><span data-stu-id="36f87-107">All</span></span>

```
Out-Host [-Paging] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="36f87-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="36f87-108">DESCRIPTION</span></span>

<span data-ttu-id="36f87-109">Das `Out-Host` Cmdlet sendet die Ausgabe zur Anzeige an den PowerShell-Host.</span><span class="sxs-lookup"><span data-stu-id="36f87-109">The `Out-Host` cmdlet sends output to the PowerShell host for display.</span></span> <span data-ttu-id="36f87-110">Der Host zeigt die Ausgabe in der Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="36f87-110">The host displays the output at the command line.</span></span> <span data-ttu-id="36f87-111">Da `Out-Host` der Standardwert ist, müssen Sie ihn nicht angeben, es sei denn, Sie möchten seine Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="36f87-111">Because `Out-Host` is the default, you don't have to specify it unless you want to use its parameters.</span></span>

<span data-ttu-id="36f87-112">`Out-Host` wird automatisch an jeden Befehl angehängt, der ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="36f87-112">`Out-Host` is automatically appended to every command that is executed.</span></span> <span data-ttu-id="36f87-113">Sie übergibt die Ausgabe der Pipeline an den Host, der den Befehl ausführt.</span><span class="sxs-lookup"><span data-stu-id="36f87-113">It passes the output of the pipeline to the host executing the command.</span></span> <span data-ttu-id="36f87-114">`Out-Host` ignoriert ANSI-Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="36f87-114">`Out-Host` ignores ANSI escape sequences.</span></span> <span data-ttu-id="36f87-115">Die Escapesequenzen werden vom Host behandelt.</span><span class="sxs-lookup"><span data-stu-id="36f87-115">The escape sequences are handled by the host.</span></span> <span data-ttu-id="36f87-116">`Out-Host` übergibt ANSI-Escapesequenzen an den Host, ohne zu versuchen, Sie zu interpretieren oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="36f87-116">`Out-Host` passes ANSI escape sequences to the host without trying to interpret or change them.</span></span>

## <span data-ttu-id="36f87-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="36f87-117">EXAMPLES</span></span>

### <span data-ttu-id="36f87-118">Beispiel 1: Anzeigen der Ausgabeseiten Weise</span><span class="sxs-lookup"><span data-stu-id="36f87-118">Example 1: Display output one page at a time</span></span>

<span data-ttu-id="36f87-119">In diesem Beispiel werden die System Prozesse jeweils auf einer Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36f87-119">This example displays the system processes one page at a time.</span></span>

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

<span data-ttu-id="36f87-120">`Get-Process` Ruft die System Prozesse ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="36f87-120">`Get-Process` gets the system processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="36f87-121">`Out-Host` verwendet den **Paging** -Parameter, um jeweils eine Seite mit Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36f87-121">`Out-Host` uses the **Paging** parameter to display one page of data at a time.</span></span>

### <span data-ttu-id="36f87-122">Beispiel 2: Verwenden einer Variablen als Eingabe</span><span class="sxs-lookup"><span data-stu-id="36f87-122">Example 2: Use a variable as input</span></span>

<span data-ttu-id="36f87-123">In diesem Beispiel werden-Objekte, die in einer Variablen gespeichert sind, als Eingabe für verwendet `Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="36f87-123">This example uses objects stored in a variable as the input for `Out-Host`.</span></span>

```powershell
$io = Get-History
Out-Host -InputObject $io
```

<span data-ttu-id="36f87-124">`Get-History` Ruft den Verlauf der PowerShell-Sitzung ab und speichert die Objekte in der `$io` Variablen.</span><span class="sxs-lookup"><span data-stu-id="36f87-124">`Get-History` gets the PowerShell session's history, and stores the objects in the `$io` variable.</span></span>
<span data-ttu-id="36f87-125">`Out-Host` verwendet den **Inputobject** -Parameter, um die Variable anzugeben, `$io` und zeigt den Verlauf an.</span><span class="sxs-lookup"><span data-stu-id="36f87-125">`Out-Host` uses the **InputObject** parameter to specify the `$io` variable and displays the history.</span></span>

## <span data-ttu-id="36f87-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="36f87-126">PARAMETERS</span></span>

### <span data-ttu-id="36f87-127">-InputObject</span><span class="sxs-lookup"><span data-stu-id="36f87-127">-InputObject</span></span>

<span data-ttu-id="36f87-128">Gibt die Objekte an, die in die Konsole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="36f87-128">Specifies the objects that are written to the console.</span></span> <span data-ttu-id="36f87-129">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="36f87-129">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="36f87-130">-Paging</span><span class="sxs-lookup"><span data-stu-id="36f87-130">-Paging</span></span>

<span data-ttu-id="36f87-131">Gibt an, dass `Out-Host` eine Seite der Ausgabe gleichzeitig anzeigt und auf die Benutzereingabe wartet, bevor die verbleibenden Seiten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="36f87-131">Indicates that `Out-Host` displays one page of output at a time, and waits for user input before the remaining pages are displayed.</span></span> <span data-ttu-id="36f87-132">Standardmäßig wird die gesamte Ausgabe auf einer einzelnen Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36f87-132">By default, all the output is displayed on a single page.</span></span> <span data-ttu-id="36f87-133">Die Seitengröße wird durch die Eigenschaften des Hosts bestimmt.</span><span class="sxs-lookup"><span data-stu-id="36f87-133">The page size is determined by the characteristics of the host.</span></span>

<span data-ttu-id="36f87-134">Drücken Sie die <kbd>LEERTASTE</kbd> , um die nächste Seite der Ausgabe anzuzeigen, oder drücken <kbd>Sie die Eingabe</kbd> Taste, um die nächste Zeile der Ausgabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36f87-134">Press the <kbd>Space</kbd> bar to display the next page of output or the <kbd>Enter</kbd> key to view the next line of output.</span></span> <span data-ttu-id="36f87-135">Drücken Sie <kbd>Q</kbd> zum Beenden.</span><span class="sxs-lookup"><span data-stu-id="36f87-135">Press <kbd>Q</kbd> to quit.</span></span>

<span data-ttu-id="36f87-136">**Paging** ähnelt dem **more** -Befehl.</span><span class="sxs-lookup"><span data-stu-id="36f87-136">**Paging** is similar to the **more** command.</span></span>

> [!NOTE]
> <span data-ttu-id="36f87-137">Der **Paging** -Parameter wird vom PowerShell ISE-Host nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36f87-137">The **Paging** parameter isn't supported by the PowerShell ISE host.</span></span>

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

### <span data-ttu-id="36f87-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="36f87-138">CommonParameters</span></span>

<span data-ttu-id="36f87-139">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="36f87-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="36f87-140">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="36f87-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="36f87-141">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="36f87-141">INPUTS</span></span>

### <span data-ttu-id="36f87-142">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="36f87-142">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="36f87-143">Sie können Objekte über die Pipeline an senden `Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="36f87-143">You can send objects down the pipeline to `Out-Host`.</span></span>

## <span data-ttu-id="36f87-144">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="36f87-144">OUTPUTS</span></span>

### <span data-ttu-id="36f87-145">Keine</span><span class="sxs-lookup"><span data-stu-id="36f87-145">None</span></span>

<span data-ttu-id="36f87-146">`Out-Host` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="36f87-146">`Out-Host` doesn't generate any output.</span></span> <span data-ttu-id="36f87-147">Objekte werden zur Anzeige an den Host gesendet.</span><span class="sxs-lookup"><span data-stu-id="36f87-147">It sends objects to the host for display.</span></span>

## <span data-ttu-id="36f87-148">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="36f87-148">NOTES</span></span>

<span data-ttu-id="36f87-149">Der **Paging** -Parameter wird nicht von allen PowerShell-Hosts unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36f87-149">The **Paging** parameter isn't supported by all PowerShell hosts.</span></span> <span data-ttu-id="36f87-150">Wenn Sie z. b. den **Paging** -Parameter in der PowerShell ISE verwenden, wird der folgende Fehler angezeigt: `out-lineoutput : The method or operation is not implemented.`</span><span class="sxs-lookup"><span data-stu-id="36f87-150">For example, if you use the **Paging** parameter in the PowerShell ISE, the following error is displayed: `out-lineoutput : The method or operation is not implemented.`</span></span>

<span data-ttu-id="36f87-151">Mit den Cmdlets, die das **out** -Verb enthalten, `Out-` werden keine Objekte formatiert.</span><span class="sxs-lookup"><span data-stu-id="36f87-151">The cmdlets that contain the **Out** verb, `Out-`, don't format objects.</span></span> <span data-ttu-id="36f87-152">Sie Rendering-Objekte und senden Sie an das angegebene Anzeige Ziel.</span><span class="sxs-lookup"><span data-stu-id="36f87-152">They render objects and send them to the specified display destination.</span></span> <span data-ttu-id="36f87-153">Wenn Sie ein unformatiertes Objekt an ein `Out-` Cmdlet senden, sendet das Cmdlet es vor dem Rendern an ein Formatierungs-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="36f87-153">If you send an unformatted object to an `Out-` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="36f87-154">Die `Out-` Cmdlets enthalten keine Parameter für Namen oder Dateipfade.</span><span class="sxs-lookup"><span data-stu-id="36f87-154">The `Out-` cmdlets don't have parameters for names or file paths.</span></span> <span data-ttu-id="36f87-155">Verwenden Sie zum Senden von Daten an ein `Out-` Cmdlet die Pipeline, um die Ausgabe eines PowerShell-Befehls an das Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="36f87-155">To send data to an `Out-` cmdlet, use the pipeline to send a PowerShell command's output to the cmdlet.</span></span> <span data-ttu-id="36f87-156">Oder Sie können Daten in einer Variablen speichern und den **Inputobject** -Parameter verwenden, um die Daten an das Cmdlet zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="36f87-156">Or, you can store data in a variable and use the **InputObject** parameter to pass the data to the cmdlet.</span></span>

<span data-ttu-id="36f87-157">`Out-Host` sendet Daten, aber es werden keine Ausgabe Objekte erzeugt.</span><span class="sxs-lookup"><span data-stu-id="36f87-157">`Out-Host` sends data, but it doesn't produce any output objects.</span></span> <span data-ttu-id="36f87-158">Wenn Sie die Ausgabe von `Out-Host` an das `Get-Member` Cmdlet weitergeben, `Get-Member` meldet, dass keine Objekte angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="36f87-158">If you pipeline the output of `Out-Host` to the `Get-Member` cmdlet, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="36f87-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="36f87-159">RELATED LINKS</span></span>

[<span data-ttu-id="36f87-160">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="36f87-160">Clear-Host</span></span>](Clear-Host.md)

[<span data-ttu-id="36f87-161">Out-Default</span><span class="sxs-lookup"><span data-stu-id="36f87-161">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="36f87-162">Out-File</span><span class="sxs-lookup"><span data-stu-id="36f87-162">Out-File</span></span>](../Microsoft.PowerShell.Utility/Out-File.md)

[<span data-ttu-id="36f87-163">Out-Null</span><span class="sxs-lookup"><span data-stu-id="36f87-163">Out-Null</span></span>](Out-Null.md)

[<span data-ttu-id="36f87-164">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="36f87-164">Out-Printer</span></span>](../Microsoft.PowerShell.Utility/Out-Printer.md)

[<span data-ttu-id="36f87-165">Out-String</span><span class="sxs-lookup"><span data-stu-id="36f87-165">Out-String</span></span>](../Microsoft.PowerShell.Utility/Out-String.md)

[<span data-ttu-id="36f87-166">Write-Host</span><span class="sxs-lookup"><span data-stu-id="36f87-166">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)
