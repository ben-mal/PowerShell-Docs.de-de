---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: 7e0c958201dbd1b42d1f4c4ee286b8aca1f8595a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602506"
---
# <span data-ttu-id="b53d4-102">Write-Output</span><span class="sxs-lookup"><span data-stu-id="b53d4-102">Write-Output</span></span>

## <span data-ttu-id="b53d4-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b53d4-103">SYNOPSIS</span></span>
<span data-ttu-id="b53d4-104">Sendet die angegebenen Objekte an den nächsten Befehl in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="b53d4-104">Sends the specified objects to the next command in the pipeline.</span></span> <span data-ttu-id="b53d4-105">Wenn der Befehl der letzte Befehl in der Pipeline ist, werden die Objekte in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b53d4-105">If the command is the last command in the pipeline, the objects are displayed in the console.</span></span>

## <span data-ttu-id="b53d4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b53d4-106">SYNTAX</span></span>

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="b53d4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b53d4-107">DESCRIPTION</span></span>

<span data-ttu-id="b53d4-108">Das- `Write-Output` Cmdlet sendet das angegebene Objekt über die Pipeline an den nächsten Befehl.</span><span class="sxs-lookup"><span data-stu-id="b53d4-108">The `Write-Output` cmdlet sends the specified object down the pipeline to the next command.</span></span>
<span data-ttu-id="b53d4-109">Wenn der Befehl der letzte Befehl in der Pipeline ist, wird das Objekt in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b53d4-109">If the command is the last command in the pipeline, the object is displayed in the console.</span></span>

<span data-ttu-id="b53d4-110">`Write-Output` sendet Objekte über die primäre Pipeline, auch bekannt als "Ausgabestream" oder "Erfolgs Pipeline".</span><span class="sxs-lookup"><span data-stu-id="b53d4-110">`Write-Output` sends objects down the primary pipeline, also known as the "output stream" or the "success pipeline."</span></span> <span data-ttu-id="b53d4-111">Verwenden Sie zum Senden von Fehlerobjekten über die Fehlerpipeline das Cmdlet „Write-Error“.</span><span class="sxs-lookup"><span data-stu-id="b53d4-111">To send error objects down the error pipeline, use Write-Error.</span></span>

<span data-ttu-id="b53d4-112">Dieses Cmdlet wird in der Regel in Skripts verwendet, um Zeichenfolgen und andere Objekte in der Konsole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b53d4-112">This cmdlet is typically used in scripts to display strings and other objects on the console.</span></span> <span data-ttu-id="b53d4-113">Eine der integrierten Aliase für `Write-Output` ist `echo` und ähnlich wie andere Shells `echo` , die verwenden. das Standardverhalten besteht darin, die Ausgabe am Ende einer Pipeline anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b53d4-113">One of the built-in aliases for `Write-Output` is `echo` and similar to other shells that use `echo`, the default behavior is to display the output at the end of a pipeline.</span></span> <span data-ttu-id="b53d4-114">In PowerShell ist es im Allgemeinen nicht erforderlich, das Cmdlet in Instanzen zu verwenden, in denen die Ausgabe standardmäßig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b53d4-114">In PowerShell, it is generally not necessary to use the cmdlet in instances where the output is displayed by default.</span></span> <span data-ttu-id="b53d4-115">`Get-Process | Write-Output` entspricht beispielsweise `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="b53d4-115">For example, `Get-Process | Write-Output` is equivalent to `Get-Process`.</span></span> <span data-ttu-id="b53d4-116">Oder `echo "Home directory: $HOME"` können geschrieben werden `"Home directory: $HOME"` .</span><span class="sxs-lookup"><span data-stu-id="b53d4-116">Or, `echo "Home directory: $HOME"` can be written, `"Home directory: $HOME"`.</span></span>

<span data-ttu-id="b53d4-117">Standardmäßig werden `Write-Output` für das Cmdlet bereitgestellte Auflistungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="b53d4-117">By default, `Write-Output` enumerates through collections provided to the cmdlet.</span></span> <span data-ttu-id="b53d4-118">Kann jedoch `Write-Output` auch verwendet werden, um Auflistungen in der Pipeline als einzelnes Objekt mit dem **noenumerate** -Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="b53d4-118">However, `Write-Output` can also be used to pass collections down the pipeline as a single object with the **NoEnumerate** parameter.</span></span>

## <span data-ttu-id="b53d4-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b53d4-119">EXAMPLES</span></span>

### <span data-ttu-id="b53d4-120">Beispiel 1: Objekte erhalten und in die Konsole schreiben</span><span class="sxs-lookup"><span data-stu-id="b53d4-120">Example 1: Get objects and write them to the console</span></span>

```powershell
$P = Get-Process
Write-Output $P
```

<span data-ttu-id="b53d4-121">Der erste Befehl ruft die Prozesse ab, die auf dem Computer ausgeführt werden, und speichert Sie in der `$P` Variablen.</span><span class="sxs-lookup"><span data-stu-id="b53d4-121">The first command gets processes running on the computer and stores them in the `$P` variable.</span></span>

<span data-ttu-id="b53d4-122">Mit dem zweiten und dritten Befehl werden die Prozess Objekte in `$P` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b53d4-122">The second and third commands display the process objects in `$P` on the console.</span></span>

### <span data-ttu-id="b53d4-123">Beispiel 2: übergeben der Ausgabe an ein anderes Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b53d4-123">Example 2: Pass output to another cmdlet</span></span>

```powershell
Write-Output "test output" | Get-Member
```

<span data-ttu-id="b53d4-124">Mit diesem Befehl wird die Zeichenfolge "Test Output" über die Pipeline an das `Get-Member` Cmdlet übergeben, das die Member der **System. String** -Klasse anzeigt und zeigt, dass die Zeichenfolge an der Pipeline übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b53d4-124">This command pipes the "test output" string to the `Get-Member` cmdlet, which displays the members of the **System.String** class, demonstrating that the string was passed along the pipeline.</span></span>

### <span data-ttu-id="b53d4-125">Beispiel 3: Unterdrücken der Enumeration in der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b53d4-125">Example 3: Suppress enumeration in output</span></span>

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

<span data-ttu-id="b53d4-126">Dieser Befehl fügt den **noenumerate** -Parameter hinzu, um eine Auflistung oder ein Array als ein einzelnes Objekt über die Pipeline zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="b53d4-126">This command adds the **NoEnumerate** parameter to treat a collection or array as a single object through the pipeline.</span></span>

## <span data-ttu-id="b53d4-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b53d4-127">PARAMETERS</span></span>

### <span data-ttu-id="b53d4-128">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b53d4-128">-InputObject</span></span>

<span data-ttu-id="b53d4-129">Gibt die Objekte an, die über die Pipeline gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b53d4-129">Specifies the objects to send down the pipeline.</span></span> <span data-ttu-id="b53d4-130">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b53d4-130">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="b53d4-131">-Noenumerate</span><span class="sxs-lookup"><span data-stu-id="b53d4-131">-NoEnumerate</span></span>

<span data-ttu-id="b53d4-132">Standardmäßig zählt das `Write-Output` Cmdlet seine Ausgabe immer auf.</span><span class="sxs-lookup"><span data-stu-id="b53d4-132">By default, the `Write-Output` cmdlet always enumerates its output.</span></span> <span data-ttu-id="b53d4-133">Der **noenumerate** -Parameter unterdrückt das Standardverhalten und verhindert die `Write-Output` Enumeration der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="b53d4-133">The **NoEnumerate** parameter suppresses the default behavior, and prevents `Write-Output` from enumerating output.</span></span> <span data-ttu-id="b53d4-134">Der **noenumerate** -Parameter hat keine Auswirkung, wenn der Befehl in Klammern eingeschlossen wird, da die Klammern eine Enumeration erzwingen.</span><span class="sxs-lookup"><span data-stu-id="b53d4-134">The **NoEnumerate** parameter has no effect if the command is wrapped in parentheses, because the parentheses force enumeration.</span></span> <span data-ttu-id="b53d4-135">`(Write-Output 1,2,3)`Listet z. b. immer noch das Array auf.</span><span class="sxs-lookup"><span data-stu-id="b53d4-135">For example, `(Write-Output 1,2,3)` still enumerates the array.</span></span>

> [!NOTE]
> <span data-ttu-id="b53d4-136">Dieser Switch funktioniert nur ordnungsgemäß mit PowerShell Core 6,2 und neuer.</span><span class="sxs-lookup"><span data-stu-id="b53d4-136">This switch only works correctly with PowerShell Core 6.2 and newer.</span></span> <span data-ttu-id="b53d4-137">In älteren Versionen von PowerShell Core wird die Auflistung immer noch durch die Verwendung dieses Schalters aufgezählt.</span><span class="sxs-lookup"><span data-stu-id="b53d4-137">On older versions of PowerShell Core, the collection is still enumerated even with use of this switch.</span></span>

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

### <span data-ttu-id="b53d4-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b53d4-138">CommonParameters</span></span>

<span data-ttu-id="b53d4-139">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b53d4-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b53d4-140">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b53d4-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b53d4-141">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b53d4-141">INPUTS</span></span>

### <span data-ttu-id="b53d4-142">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="b53d4-142">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b53d4-143">Sie können Objekte über die Pipeline an übergeben `Write-Output` .</span><span class="sxs-lookup"><span data-stu-id="b53d4-143">You can pipe objects to `Write-Output`.</span></span>

## <span data-ttu-id="b53d4-144">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b53d4-144">OUTPUTS</span></span>

### <span data-ttu-id="b53d4-145">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="b53d4-145">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b53d4-146">`Write-Output` Gibt die Objekte zurück, die als Eingabe übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="b53d4-146">`Write-Output` returns the objects that are submitted as input.</span></span>

## <span data-ttu-id="b53d4-147">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b53d4-147">NOTES</span></span>

## <span data-ttu-id="b53d4-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b53d4-148">RELATED LINKS</span></span>

[<span data-ttu-id="b53d4-149">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="b53d4-149">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="b53d4-150">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="b53d4-150">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="b53d4-151">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="b53d4-151">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="b53d4-152">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="b53d4-152">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="b53d4-153">Write-Error</span><span class="sxs-lookup"><span data-stu-id="b53d4-153">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="b53d4-154">Write-Host</span><span class="sxs-lookup"><span data-stu-id="b53d4-154">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="b53d4-155">Write-Information</span><span class="sxs-lookup"><span data-stu-id="b53d4-155">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="b53d4-156">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="b53d4-156">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="b53d4-157">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="b53d4-157">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="b53d4-158">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="b53d4-158">Write-Warning</span></span>](Write-Warning.md)
