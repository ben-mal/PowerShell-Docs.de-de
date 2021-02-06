---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/20/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-string?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-String
ms.openlocfilehash: 59e5b728604ce37f27b56ebe62e1a22d6af8a966
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "99603131"
---
# <span data-ttu-id="7c206-102">Out-String</span><span class="sxs-lookup"><span data-stu-id="7c206-102">Out-String</span></span>

## <span data-ttu-id="7c206-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="7c206-103">Synopsis</span></span>
<span data-ttu-id="7c206-104">Gibt Eingabe Objekte als Zeichen folgen aus.</span><span class="sxs-lookup"><span data-stu-id="7c206-104">Outputs input objects as a strings.</span></span>

## <span data-ttu-id="7c206-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c206-105">Syntax</span></span>

### <span data-ttu-id="7c206-106">Nonewlineformatierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="7c206-106">NoNewLineFormatting (Default)</span></span>

```
Out-String [-Width <Int32>] [-NoNewline] [-InputObject <PSObject>] [<CommonParameters>]
```

### <span data-ttu-id="7c206-107">Streamformatierung</span><span class="sxs-lookup"><span data-stu-id="7c206-107">StreamFormatting</span></span>

```
Out-String [-Stream] [-Width <Int32>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="7c206-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7c206-108">Description</span></span>

<span data-ttu-id="7c206-109">Mit dem- `Out-String` Cmdlet werden Eingabe Objekte in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7c206-109">The `Out-String` cmdlet converts input objects into strings.</span></span> <span data-ttu-id="7c206-110">Standardmäßig `Out-String` sammelt die Zeichen folgen und gibt Sie als eine einzelne Zeichenfolge zurück. Sie können jedoch den **Stream** -Parameter verwenden, um `Out-String` eine Zeile gleichzeitig zurückzugeben oder ein Array von Zeichen folgen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c206-110">By default, `Out-String` accumulates the strings and returns them as a single string, but you can use the **Stream** parameter to direct `Out-String` to return one line at a time or create and array of strings.</span></span> <span data-ttu-id="7c206-111">Mit diesem Cmdlet können Sie die Zeichenfolgenausgabe so wie in herkömmlichen Shells durchsuchen und bearbeiten, wenn die Objektbearbeitung ungeeignet ist.</span><span class="sxs-lookup"><span data-stu-id="7c206-111">This cmdlet lets you search and manipulate string output as you would in traditional shells when object manipulation is less convenient.</span></span>

## <span data-ttu-id="7c206-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7c206-112">Examples</span></span>

### <span data-ttu-id="7c206-113">Beispiel 1: erhalten der aktuellen Kultur und Konvertieren der Daten in Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="7c206-113">Example 1: Get the current culture and convert the data to strings</span></span>

<span data-ttu-id="7c206-114">In diesem Beispiel werden die regionalen Einstellungen für den aktuellen Benutzer abgerufen und die Objektdaten in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7c206-114">This example gets the regional settings for the current user and converts the object data to strings.</span></span>

```powershell
$C = Get-Culture | Select-Object -Property *
Out-String -InputObject $C -Width 100
```

```Output
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - en-US
TextInfo                       : TextInfo - en-US
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar,
                                 System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False
```

<span data-ttu-id="7c206-115">Die `$C` Variable speichert ein **Selected.System. Globalization. CultureInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="7c206-115">The `$C` variable stores a **Selected.System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="7c206-116">Das-Objekt ist das Ergebnis des `Get-Culture` Sendens der Ausgabe in der Pipeline an `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="7c206-116">The object is the result of `Get-Culture` sending output down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="7c206-117">Der **Property** -Parameter verwendet ein Sternchen-Platzhalter Zeichen ( `*` ), um alle Eigenschaften anzugeben, die im-Objekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7c206-117">The **Property** parameter uses an asterisk (`*`) wildcard to specify all properties are contained in the object.</span></span>

<span data-ttu-id="7c206-118">`Out-String` verwendet den **Inputobject** -Parameter, um das **CultureInfo** -Objekt anzugeben, das in der Variablen gespeichert ist `$C` .</span><span class="sxs-lookup"><span data-stu-id="7c206-118">`Out-String` uses the **InputObject** parameter to specify the **CultureInfo** object stored in the `$C` variable.</span></span> <span data-ttu-id="7c206-119">Die Objekte in `$C` werden in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7c206-119">The objects in `$C` are converted to a string.</span></span>

> [!NOTE]
> <span data-ttu-id="7c206-120">Um das `Out-String` Array anzuzeigen, speichern Sie die Ausgabe in einer Variablen, und verwenden Sie einen Array Index, um die Elemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7c206-120">To view the `Out-String` array, store the output to a variable and use an array index to view the elements.</span></span> <span data-ttu-id="7c206-121">Weitere Informationen zum Array Index finden Sie unter [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span><span class="sxs-lookup"><span data-stu-id="7c206-121">For more information about the array index, see [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span></span>
>
> `$str = Out-String -InputObject $C -Width 100`

### <span data-ttu-id="7c206-122">Beispiel 2: Arbeiten mit Objekten</span><span class="sxs-lookup"><span data-stu-id="7c206-122">Example 2: Working with objects</span></span>

<span data-ttu-id="7c206-123">Dieses Beispiel veranschaulicht den Unterschied zwischen dem Arbeiten mit Objekten und dem Arbeiten mit Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="7c206-123">This example demonstrates the difference between working with objects and working with strings.</span></span> <span data-ttu-id="7c206-124">Der Befehl zeigt einen Alias an, der den Text **GCM** enthält, den Alias für `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="7c206-124">The command displays an alias that includes the text **gcm**, the alias for `Get-Command`.</span></span>

```powershell
Get-Alias | Out-String -Stream | Select-String -Pattern "gcm"
```

```Output
Alias           gcm -> Get-Command
```

<span data-ttu-id="7c206-125">`Get-Alias` Ruft die **System. Management. Automation. AliasInfo** -Objekte ab, eine für jeden Alias und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="7c206-125">`Get-Alias` gets the **System.Management.Automation.AliasInfo** objects, one for each alias, and sends the objects down the pipeline.</span></span> <span data-ttu-id="7c206-126">`Out-String` verwendet den **Stream** -Parameter, um jedes-Objekt in eine Zeichenfolge zu konvertieren, indem alle-Objekte in einer einzelnen Zeichenfolge verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="7c206-126">`Out-String` uses the **Stream** parameter to convert each object to a string rather concatenating all the objects into a single string.</span></span> <span data-ttu-id="7c206-127">Die **System. String** -Objekte werden über die Pipeline gesendet und `Select-String` verwenden den **Pattern** -Parameter, um Übereinstimmungen für den Text- **GCM** zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7c206-127">The **System.String** objects are sent down the pipeline and `Select-String` uses the **Pattern** parameter to find matches for the text **gcm**.</span></span>

> [!NOTE]
> <span data-ttu-id="7c206-128">Wenn Sie den **Stream** -Parameter weglassen, zeigt der Befehl alle Aliase an, da `Select-String` den Text- **GCM** in der einzelnen Zeichenfolge findet, die `Out-String` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7c206-128">If you omit the **Stream** parameter, the command displays all the aliases because `Select-String` finds the text **gcm** in the single string that `Out-String` returns.</span></span>

### <span data-ttu-id="7c206-129">Beispiel 3: Verwenden Sie den width-Parameter, um das Abschneiden zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="7c206-129">Example 3: Use the Width parameter to prevent truncation.</span></span>

<span data-ttu-id="7c206-130">Obwohl die meisten Ausgaben von `Out-String` in die nächste Zeile umschließt werden, gibt es Szenarien, in denen die Ausgabe vom Formatierungs System abgeschnitten wird, bevor Sie an weitergeleitet wird `Out-String` .</span><span class="sxs-lookup"><span data-stu-id="7c206-130">While most output from `Out-String` is wrapped to the next line, there are scenarios where the output is truncated by the formatting system before being passed to `Out-String`.</span></span> <span data-ttu-id="7c206-131">Sie können das Abschneiden mithilfe des **Width** -Parameters vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7c206-131">You can avoid truncation using the **Width** parameter.</span></span>

```powershell
PS> @{TestKey = ('x' * 200)} | Out-String
Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx...

PS> @{TestKey = ('x' * 200)} | Out-String -Width 250

Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## <span data-ttu-id="7c206-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7c206-132">PARAMETERS</span></span>

### <span data-ttu-id="7c206-133">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7c206-133">-InputObject</span></span>

<span data-ttu-id="7c206-134">Gibt die Objekte an, die in eine Zeichenfolge geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7c206-134">Specifies the objects to be written to a string.</span></span> <span data-ttu-id="7c206-135">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7c206-135">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="7c206-136">-Nonewline</span><span class="sxs-lookup"><span data-stu-id="7c206-136">-NoNewline</span></span>

<span data-ttu-id="7c206-137">Entfernt alle Zeilenumbrüche aus der Ausgabe, die vom PowerShell-Formatierer generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7c206-137">Removes all newlines from output generated by the PowerShell formatter.</span></span> <span data-ttu-id="7c206-138">Zeilenumbrüche, die Teil der Zeichen folgen Objekte sind, werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="7c206-138">Newlines that are part of the string objects are preserved.</span></span>

<span data-ttu-id="7c206-139">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c206-139">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoNewLineFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7c206-140">-Stream</span><span class="sxs-lookup"><span data-stu-id="7c206-140">-Stream</span></span>

<span data-ttu-id="7c206-141">Standardmäßig `Out-String` gibt eine einzelne Zeichenfolge aus, die so formatiert ist, wie Sie in der-Konsole angezeigt wird, einschließlich leerer Header oder nachfolgender Zeilenumbruch.</span><span class="sxs-lookup"><span data-stu-id="7c206-141">By default, `Out-String` outputs a single string formatted as you would see it in the console including any blank headers or trailing newlines.</span></span> <span data-ttu-id="7c206-142">Der **Stream** -Parameter ermöglicht `Out-String` , jede Zeile nacheinander auszugeben.</span><span class="sxs-lookup"><span data-stu-id="7c206-142">The **Stream** parameter enables `Out-String` to output each line one by one.</span></span> <span data-ttu-id="7c206-143">Die einzige Ausnahme hierbei sind mehrzeilige Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="7c206-143">The only exception to this are multiline strings.</span></span> <span data-ttu-id="7c206-144">In diesem Fall gibt `Out-String` die Zeichenfolge weiterhin als eine einzelne, mehrzeilige Zeichenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="7c206-144">In that case, `Out-String` will still output the string as a single, multiline string.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StreamFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7c206-145">-Breite</span><span class="sxs-lookup"><span data-stu-id="7c206-145">-Width</span></span>

<span data-ttu-id="7c206-146">Gibt die Anzahl der Zeichen in jeder Zeile der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="7c206-146">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="7c206-147">Alle zusätzlichen Zeichen werden je nach verwendetem Formatierer-Cmdlet in die nächste Zeile umschließt oder abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="7c206-147">Any additional characters are wrapped to the next line or truncated depending on the formatter cmdlet used.</span></span> <span data-ttu-id="7c206-148">Der **Width** -Parameter gilt nur für Objekte, die formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="7c206-148">The **Width** parameter applies only to objects that are being formatted.</span></span> <span data-ttu-id="7c206-149">Wenn Sie diesen Parameter weglassen, wird die Breite durch die Merkmale des Hostprogramms bestimmt.</span><span class="sxs-lookup"><span data-stu-id="7c206-149">If you omit this parameter, the width is determined by the characteristics of the host program.</span></span> <span data-ttu-id="7c206-150">Im Terminalfenster (Konsolenfenster) wird die aktuelle Fensterbreite als Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c206-150">In terminal (console) windows, the current window width is used as the default value.</span></span> <span data-ttu-id="7c206-151">Bei der Installation von PowerShell-Konsolen Fenstern wird standardmäßig eine Breite von 80 Zeichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7c206-151">PowerShell console windows default to a width of 80 characters on installation.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7c206-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7c206-152">CommonParameters</span></span>

<span data-ttu-id="7c206-153">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7c206-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7c206-154">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7c206-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7c206-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7c206-155">INPUTS</span></span>

### <span data-ttu-id="7c206-156">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="7c206-156">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7c206-157">Sie können Objekte über die Pipeline an senden `Out-String` .</span><span class="sxs-lookup"><span data-stu-id="7c206-157">You can send objects down the pipeline to `Out-String`.</span></span>

## <span data-ttu-id="7c206-158">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7c206-158">OUTPUTS</span></span>

### <span data-ttu-id="7c206-159">System.String</span><span class="sxs-lookup"><span data-stu-id="7c206-159">System.String</span></span>

<span data-ttu-id="7c206-160">`Out-String` Gibt die Zeichenfolge zurück, die aus dem Eingabe Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7c206-160">`Out-String` returns the string that it creates from the input object.</span></span>

## <span data-ttu-id="7c206-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7c206-161">NOTES</span></span>

<span data-ttu-id="7c206-162">Die Cmdlets, die das `Out` Verb enthalten, formatieren Objekte nicht.</span><span class="sxs-lookup"><span data-stu-id="7c206-162">The cmdlets that contain the `Out` verb don't format objects.</span></span> <span data-ttu-id="7c206-163">Die- `Out` Cmdlets senden-Objekte an das Formatierer für das angegebene Anzeige Ziel.</span><span class="sxs-lookup"><span data-stu-id="7c206-163">The `Out` cmdlets send objects to the formatter for the specified display destination.</span></span>

## <span data-ttu-id="7c206-164">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7c206-164">RELATED LINKS</span></span>

[<span data-ttu-id="7c206-165">about_Formatting</span><span class="sxs-lookup"><span data-stu-id="7c206-165">about_Formatting</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="7c206-166">Out-Default</span><span class="sxs-lookup"><span data-stu-id="7c206-166">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="7c206-167">Out-File</span><span class="sxs-lookup"><span data-stu-id="7c206-167">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="7c206-168">Out-Host</span><span class="sxs-lookup"><span data-stu-id="7c206-168">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="7c206-169">Out-Null</span><span class="sxs-lookup"><span data-stu-id="7c206-169">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="7c206-170">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="7c206-170">Out-GridView</span></span>](Out-GridView.md)

[<span data-ttu-id="7c206-171">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="7c206-171">Out-Printer</span></span>](Out-Printer.md)
