---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: ccc72ac961adbcba542a7b8be55ad49df68a5ef6
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224295"
---
# <span data-ttu-id="00cad-103">Write-Output</span><span class="sxs-lookup"><span data-stu-id="00cad-103">Write-Output</span></span>

## <span data-ttu-id="00cad-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="00cad-104">SYNOPSIS</span></span>
<span data-ttu-id="00cad-105">Sendet die angegebenen Objekte an den nächsten Befehl in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="00cad-105">Sends the specified objects to the next command in the pipeline.</span></span> <span data-ttu-id="00cad-106">Wenn der Befehl der letzte Befehl in der Pipeline ist, werden die Objekte in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00cad-106">If the command is the last command in the pipeline, the objects are displayed in the console.</span></span>

## <span data-ttu-id="00cad-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="00cad-107">SYNTAX</span></span>

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="00cad-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="00cad-108">DESCRIPTION</span></span>

<span data-ttu-id="00cad-109">Das- `Write-Output` Cmdlet sendet das angegebene Objekt über die Pipeline an den nächsten Befehl.</span><span class="sxs-lookup"><span data-stu-id="00cad-109">The `Write-Output` cmdlet sends the specified object down the pipeline to the next command.</span></span>
<span data-ttu-id="00cad-110">Wenn der Befehl der letzte Befehl in der Pipeline ist, wird das Objekt in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00cad-110">If the command is the last command in the pipeline, the object is displayed in the console.</span></span>

<span data-ttu-id="00cad-111">`Write-Output` sendet Objekte über die primäre Pipeline, auch bekannt als "Ausgabestream" oder "Erfolgs Pipeline".</span><span class="sxs-lookup"><span data-stu-id="00cad-111">`Write-Output` sends objects down the primary pipeline, also known as the "output stream" or the "success pipeline."</span></span> <span data-ttu-id="00cad-112">Verwenden Sie zum Senden von Fehlerobjekten über die Fehlerpipeline das Cmdlet „Write-Error“.</span><span class="sxs-lookup"><span data-stu-id="00cad-112">To send error objects down the error pipeline, use Write-Error.</span></span>

<span data-ttu-id="00cad-113">Dieses Cmdlet wird in der Regel in Skripts verwendet, um Zeichenfolgen und andere Objekte in der Konsole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00cad-113">This cmdlet is typically used in scripts to display strings and other objects on the console.</span></span> <span data-ttu-id="00cad-114">Eine der integrierten Aliase für `Write-Output` ist `echo` und ähnlich wie andere Shells `echo` , die verwenden. das Standardverhalten besteht darin, die Ausgabe am Ende einer Pipeline anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00cad-114">One of the built-in aliases for `Write-Output` is `echo` and similar to other shells that use `echo`, the default behavior is to display the output at the end of a pipeline.</span></span> <span data-ttu-id="00cad-115">In PowerShell ist es im Allgemeinen nicht erforderlich, das Cmdlet in Instanzen zu verwenden, in denen die Ausgabe standardmäßig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="00cad-115">In PowerShell, it is generally not necessary to use the cmdlet in instances where the output is displayed by default.</span></span> <span data-ttu-id="00cad-116">`Get-Process | Write-Output` entspricht beispielsweise `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="00cad-116">For example, `Get-Process | Write-Output` is equivalent to `Get-Process`.</span></span> <span data-ttu-id="00cad-117">Oder `echo "Home directory: $HOME"` können geschrieben werden `"Home directory: $HOME"` .</span><span class="sxs-lookup"><span data-stu-id="00cad-117">Or, `echo "Home directory: $HOME"` can be written, `"Home directory: $HOME"`.</span></span>

<span data-ttu-id="00cad-118">Standardmäßig werden `Write-Output` für das Cmdlet bereitgestellte Auflistungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="00cad-118">By default, `Write-Output` enumerates through collections provided to the cmdlet.</span></span> <span data-ttu-id="00cad-119">Kann jedoch `Write-Output` auch verwendet werden, um Auflistungen in der Pipeline als einzelnes Objekt mit dem **noenumerate** -Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="00cad-119">However, `Write-Output` can also be used to pass collections down the pipeline as a single object with the **NoEnumerate** parameter.</span></span>

## <span data-ttu-id="00cad-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="00cad-120">EXAMPLES</span></span>

### <span data-ttu-id="00cad-121">Beispiel 1: Objekte erhalten und in die Konsole schreiben</span><span class="sxs-lookup"><span data-stu-id="00cad-121">Example 1: Get objects and write them to the console</span></span>

```powershell
$P = Get-Process
Write-Output $P
```

<span data-ttu-id="00cad-122">Der erste Befehl ruft die Prozesse ab, die auf dem Computer ausgeführt werden, und speichert Sie in der `$P` Variablen.</span><span class="sxs-lookup"><span data-stu-id="00cad-122">The first command gets processes running on the computer and stores them in the `$P` variable.</span></span>

<span data-ttu-id="00cad-123">Mit dem zweiten und dritten Befehl werden die Prozess Objekte in `$P` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00cad-123">The second and third commands display the process objects in `$P` on the console.</span></span>

### <span data-ttu-id="00cad-124">Beispiel 2: übergeben der Ausgabe an ein anderes Cmdlet</span><span class="sxs-lookup"><span data-stu-id="00cad-124">Example 2: Pass output to another cmdlet</span></span>

```powershell
Write-Output "test output" | Get-Member
```

<span data-ttu-id="00cad-125">Mit diesem Befehl wird die Zeichenfolge "Test Output" über die Pipeline an das `Get-Member` Cmdlet übergeben, das die Member der **System. String** -Klasse anzeigt und zeigt, dass die Zeichenfolge an der Pipeline übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="00cad-125">This command pipes the "test output" string to the `Get-Member` cmdlet, which displays the members of the **System.String** class, demonstrating that the string was passed along the pipeline.</span></span>

### <span data-ttu-id="00cad-126">Beispiel 3: Unterdrücken der Enumeration in der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="00cad-126">Example 3: Suppress enumeration in output</span></span>

```powershell
Write-Output 1,2,3 | Measure-Object
```

```Output
Count    : 3
...
```

```powershell
Write-Output 1,2,3 -NoEnumerate | Measure-Object
```

```Output
Count    : 1
...
```

<span data-ttu-id="00cad-127">Dieser Befehl fügt den **noenumerate** -Parameter hinzu, um eine Auflistung oder ein Array als ein einzelnes Objekt über die Pipeline zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="00cad-127">This command adds the **NoEnumerate** parameter to treat a collection or array as a single object through the pipeline.</span></span>

## <span data-ttu-id="00cad-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="00cad-128">PARAMETERS</span></span>

### <span data-ttu-id="00cad-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="00cad-129">-InputObject</span></span>

<span data-ttu-id="00cad-130">Gibt die Objekte an, die über die Pipeline gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00cad-130">Specifies the objects to send down the pipeline.</span></span> <span data-ttu-id="00cad-131">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="00cad-131">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="00cad-132">-Noenumerate</span><span class="sxs-lookup"><span data-stu-id="00cad-132">-NoEnumerate</span></span>

<span data-ttu-id="00cad-133">Standardmäßig zählt das `Write-Output` Cmdlet seine Ausgabe immer auf.</span><span class="sxs-lookup"><span data-stu-id="00cad-133">By default, the `Write-Output` cmdlet always enumerates its output.</span></span> <span data-ttu-id="00cad-134">Der **noenumerate** -Parameter unterdrückt das Standardverhalten und verhindert die `Write-Output` Enumeration der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="00cad-134">The **NoEnumerate** parameter suppresses the default behavior, and prevents `Write-Output` from enumerating output.</span></span> <span data-ttu-id="00cad-135">Der **noenumerate** -Parameter hat keine Auswirkung, wenn der Befehl in Klammern eingeschlossen wird, da die Klammern eine Enumeration erzwingen.</span><span class="sxs-lookup"><span data-stu-id="00cad-135">The **NoEnumerate** parameter has no effect if the command is wrapped in parentheses, because the parentheses force enumeration.</span></span> <span data-ttu-id="00cad-136">`(Write-Output 1,2,3)`Listet z. b. immer noch das Array auf.</span><span class="sxs-lookup"><span data-stu-id="00cad-136">For example, `(Write-Output 1,2,3)` still enumerates the array.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00cad-137">Es liegt ein Problem mit diesem Switch in Windows PowerShell vor, der in PowerShell 6,2 und höher behoben ist.</span><span class="sxs-lookup"><span data-stu-id="00cad-137">There is an issue with this switch in Windows PowerShell that is fixed in PowerShell 6.2 and above.</span></span> <span data-ttu-id="00cad-138">Bei Verwendung von **noenumerate** und expliziter Verwendung des **Inputobject** -Parameters wird der Befehl trotzdem aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="00cad-138">When using **NoEnumerate** and explicitly using the **InputObject** parameter, the command still enumerates.</span></span> <span data-ttu-id="00cad-139">Um dieses Problem zu umgehen, übergeben Sie das **Inputobject** -Argument (n) Positional.</span><span class="sxs-lookup"><span data-stu-id="00cad-139">To work around this, pass the **InputObject** argument(s) positionally.</span></span>

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

### <span data-ttu-id="00cad-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="00cad-140">CommonParameters</span></span>

<span data-ttu-id="00cad-141">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="00cad-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="00cad-142">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="00cad-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="00cad-143">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="00cad-143">INPUTS</span></span>

### <span data-ttu-id="00cad-144">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="00cad-144">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="00cad-145">Sie können Objekte über die Pipeline an übergeben `Write-Output` .</span><span class="sxs-lookup"><span data-stu-id="00cad-145">You can pipe objects to `Write-Output`.</span></span>

## <span data-ttu-id="00cad-146">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="00cad-146">OUTPUTS</span></span>

### <span data-ttu-id="00cad-147">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="00cad-147">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="00cad-148">`Write-Output` Gibt die Objekte zurück, die als Eingabe übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="00cad-148">`Write-Output` returns the objects that are submitted as input.</span></span>

## <span data-ttu-id="00cad-149">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="00cad-149">NOTES</span></span>

## <span data-ttu-id="00cad-150">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="00cad-150">RELATED LINKS</span></span>

[<span data-ttu-id="00cad-151">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="00cad-151">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="00cad-152">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="00cad-152">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="00cad-153">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="00cad-153">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="00cad-154">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="00cad-154">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="00cad-155">Schreibfehler</span><span class="sxs-lookup"><span data-stu-id="00cad-155">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="00cad-156">Write-Host</span><span class="sxs-lookup"><span data-stu-id="00cad-156">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="00cad-157">Write-Information</span><span class="sxs-lookup"><span data-stu-id="00cad-157">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="00cad-158">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="00cad-158">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="00cad-159">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="00cad-159">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="00cad-160">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="00cad-160">Write-Warning</span></span>](Write-Warning.md)
