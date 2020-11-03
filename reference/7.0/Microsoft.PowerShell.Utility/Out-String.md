---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-string?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-String
ms.openlocfilehash: a64b11206a0755cedabad2894ecc330fac95a8d5
ms.sourcegitcommit: c8d1ffeab215e74e87ea1b0af8cd606c1a6a80ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "93220135"
---
# <span data-ttu-id="5c3bb-103">Out-String</span><span class="sxs-lookup"><span data-stu-id="5c3bb-103">Out-String</span></span>

## <span data-ttu-id="5c3bb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5c3bb-104">SYNOPSIS</span></span>
<span data-ttu-id="5c3bb-105">Gibt Eingabe Objekte als Zeichen folgen aus.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-105">Outputs input objects as a strings.</span></span>

## <span data-ttu-id="5c3bb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5c3bb-106">SYNTAX</span></span>

### <span data-ttu-id="5c3bb-107">Nonewlineformatierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5c3bb-107">NoNewLineFormatting (Default)</span></span>

```
Out-String [-Width <Int32>] [-NoNewline] [-InputObject <PSObject>] [<CommonParameters>]
```

### <span data-ttu-id="5c3bb-108">Streamformatierung</span><span class="sxs-lookup"><span data-stu-id="5c3bb-108">StreamFormatting</span></span>

```
Out-String [-Stream] [-Width <Int32>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="5c3bb-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c3bb-109">DESCRIPTION</span></span>

<span data-ttu-id="5c3bb-110">Mit dem- `Out-String` Cmdlet werden Eingabe Objekte in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-110">The `Out-String` cmdlet converts input objects into strings.</span></span> <span data-ttu-id="5c3bb-111">Standardmäßig `Out-String` sammelt die Zeichen folgen und gibt Sie als eine einzelne Zeichenfolge zurück. Sie können jedoch den **Stream** -Parameter verwenden, um `Out-String` eine Zeile gleichzeitig zurückzugeben oder ein Array von Zeichen folgen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-111">By default, `Out-String` accumulates the strings and returns them as a single string, but you can use the **Stream** parameter to direct `Out-String` to return one line at a time or create and array of strings.</span></span> <span data-ttu-id="5c3bb-112">Mit diesem Cmdlet können Sie die Zeichenfolgenausgabe so wie in herkömmlichen Shells durchsuchen und bearbeiten, wenn die Objektbearbeitung ungeeignet ist.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-112">This cmdlet lets you search and manipulate string output as you would in traditional shells when object manipulation is less convenient.</span></span>

## <span data-ttu-id="5c3bb-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5c3bb-113">EXAMPLES</span></span>

### <span data-ttu-id="5c3bb-114">Beispiel 1: erhalten der aktuellen Kultur und Konvertieren der Daten in Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="5c3bb-114">Example 1: Get the current culture and convert the data to strings</span></span>

<span data-ttu-id="5c3bb-115">In diesem Beispiel werden die regionalen Einstellungen für den aktuellen Benutzer abgerufen und die Objektdaten in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-115">This example gets the regional settings for the current user and converts the object data to strings.</span></span>

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

<span data-ttu-id="5c3bb-116">Die `$C` Variable speichert ein **Selected.System. Globalization. CultureInfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-116">The `$C` variable stores a **Selected.System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="5c3bb-117">Das-Objekt ist das Ergebnis des `Get-Culture` Sendens der Ausgabe in der Pipeline an `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="5c3bb-117">The object is the result of `Get-Culture` sending output down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="5c3bb-118">Der **Property** -Parameter verwendet ein Sternchen-Platzhalter Zeichen ( `*` ), um alle Eigenschaften anzugeben, die im-Objekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-118">The **Property** parameter uses an asterisk (`*`) wildcard to specify all properties are contained in the object.</span></span>

<span data-ttu-id="5c3bb-119">`Out-String` verwendet den **Inputobject** -Parameter, um das **CultureInfo** -Objekt anzugeben, das in der Variablen gespeichert ist `$C` .</span><span class="sxs-lookup"><span data-stu-id="5c3bb-119">`Out-String` uses the **InputObject** parameter to specify the **CultureInfo** object stored in the `$C` variable.</span></span> <span data-ttu-id="5c3bb-120">Die Objekte in `$C` werden in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-120">The objects in `$C` are converted to a string.</span></span>

> [!NOTE]
> <span data-ttu-id="5c3bb-121">Um das `Out-String` Array anzuzeigen, speichern Sie die Ausgabe in einer Variablen, und verwenden Sie einen Array Index, um die Elemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-121">To view the `Out-String` array, store the output to a variable and use an array index to view the elements.</span></span> <span data-ttu-id="5c3bb-122">Weitere Informationen zum Array Index finden Sie unter [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span><span class="sxs-lookup"><span data-stu-id="5c3bb-122">For more information about the array index, see [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span></span>
>
> `$str = Out-String -InputObject $C -Width 100`

### <span data-ttu-id="5c3bb-123">Beispiel 2: Arbeiten mit Objekten</span><span class="sxs-lookup"><span data-stu-id="5c3bb-123">Example 2: Working with objects</span></span>

<span data-ttu-id="5c3bb-124">Dieses Beispiel veranschaulicht den Unterschied zwischen dem Arbeiten mit Objekten und dem Arbeiten mit Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-124">This example demonstrates the difference between working with objects and working with strings.</span></span> <span data-ttu-id="5c3bb-125">Der Befehl zeigt einen Alias an, der den Text **GCM** enthält, den Alias für `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="5c3bb-125">The command displays an alias that includes the text **gcm** , the alias for `Get-Command`.</span></span>

```powershell
Get-Alias | Out-String -Stream | Select-String -Pattern "gcm"
```

```Output
Alias           gcm -> Get-Command
```

<span data-ttu-id="5c3bb-126">`Get-Alias` Ruft die **System. Management. Automation. AliasInfo** -Objekte ab, eine für jeden Alias und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-126">`Get-Alias` gets the **System.Management.Automation.AliasInfo** objects, one for each alias, and sends the objects down the pipeline.</span></span> <span data-ttu-id="5c3bb-127">`Out-String` verwendet den **Stream** -Parameter, um jedes-Objekt in eine Zeichenfolge zu konvertieren, indem alle-Objekte in einer einzelnen Zeichenfolge verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-127">`Out-String` uses the **Stream** parameter to convert each object to a string rather concatenating all the objects into a single string.</span></span> <span data-ttu-id="5c3bb-128">Die **System. String** -Objekte werden über die Pipeline gesendet und `Select-String` verwenden den **Pattern** -Parameter, um Übereinstimmungen für den Text- **GCM** zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-128">The **System.String** objects are sent down the pipeline and `Select-String` uses the **Pattern** parameter to find matches for the text **gcm**.</span></span>

> [!NOTE]
> <span data-ttu-id="5c3bb-129">Wenn Sie den **Stream** -Parameter weglassen, zeigt der Befehl alle Aliase an, da `Select-String` den Text- **GCM** in der einzelnen Zeichenfolge findet, die `Out-String` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-129">If you omit the **Stream** parameter, the command displays all the aliases because `Select-String` finds the text **gcm** in the single string that `Out-String` returns.</span></span>

### <span data-ttu-id="5c3bb-130">Beispiel 3: Verwenden Sie den width-Parameter, um das Abschneiden zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-130">Example 3: Use the Width parameter to prevent truncation.</span></span>

<span data-ttu-id="5c3bb-131">Obwohl die meisten Ausgaben von `Out-String` in die nächste Zeile umschließt werden, gibt es Szenarien, in denen die Ausgabe vom Formatierungs System abgeschnitten wird, bevor Sie an weitergeleitet wird `Out-String` .</span><span class="sxs-lookup"><span data-stu-id="5c3bb-131">While most output from `Out-String` is wrapped to the next line, there are scenarios where the output is truncated by the formatting system before being passed to `Out-String`.</span></span> <span data-ttu-id="5c3bb-132">Sie können das Abschneiden mithilfe des **Width** -Parameters vermeiden.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-132">You can avoid truncation using the **Width** parameter.</span></span>

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

## <span data-ttu-id="5c3bb-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5c3bb-133">PARAMETERS</span></span>

### <span data-ttu-id="5c3bb-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5c3bb-134">-InputObject</span></span>

<span data-ttu-id="5c3bb-135">Gibt die Objekte an, die in eine Zeichenfolge geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-135">Specifies the objects to be written to a string.</span></span> <span data-ttu-id="5c3bb-136">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-136">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="5c3bb-137">-Nonewline</span><span class="sxs-lookup"><span data-stu-id="5c3bb-137">-NoNewline</span></span>

<span data-ttu-id="5c3bb-138">Entfernt alle Zeilenumbrüche aus der Ausgabe, die vom PowerShell-Formatierer generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-138">Removes all newlines from output generated by the PowerShell formatter.</span></span> <span data-ttu-id="5c3bb-139">Zeilenumbrüche, die Teil der Zeichen folgen Objekte sind, werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-139">Newlines that are part of the string objects are preserved.</span></span>

<span data-ttu-id="5c3bb-140">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-140">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="5c3bb-141">-Stream</span><span class="sxs-lookup"><span data-stu-id="5c3bb-141">-Stream</span></span>

<span data-ttu-id="5c3bb-142">Gibt an, dass das Cmdlet für jede Zeile eines Eingabe Objekts eine separate Zeichenfolge sendet.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-142">Indicates that the cmdlet sends a separate string for each line of an input object.</span></span> <span data-ttu-id="5c3bb-143">Standardmäßig werden die Zeichenfolgen für die einzelnen Objekte gesammelt und als eine Zeichenfolge gesendet.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-143">By default, the strings for each object are accumulated and sent as a single string.</span></span>

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

### <span data-ttu-id="5c3bb-144">-Breite</span><span class="sxs-lookup"><span data-stu-id="5c3bb-144">-Width</span></span>

<span data-ttu-id="5c3bb-145">Gibt die Anzahl der Zeichen in jeder Zeile der Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-145">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="5c3bb-146">Alle zusätzlichen Zeichen werden je nach verwendetem Formatierer-Cmdlet in die nächste Zeile umschließt oder abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-146">Any additional characters are wrapped to the next line or truncated depending on the formatter cmdlet used.</span></span> <span data-ttu-id="5c3bb-147">Der **Width** -Parameter gilt nur für Objekte, die formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-147">The **Width** parameter applies only to objects that are being formatted.</span></span> <span data-ttu-id="5c3bb-148">Wenn Sie diesen Parameter weglassen, wird die Breite durch die Merkmale des Hostprogramms bestimmt.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-148">If you omit this parameter, the width is determined by the characteristics of the host program.</span></span> <span data-ttu-id="5c3bb-149">Im Terminalfenster (Konsolenfenster) wird die aktuelle Fensterbreite als Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-149">In terminal (console) windows, the current window width is used as the default value.</span></span> <span data-ttu-id="5c3bb-150">Bei der Installation von PowerShell-Konsolen Fenstern wird standardmäßig eine Breite von 80 Zeichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-150">PowerShell console windows default to a width of 80 characters on installation.</span></span>

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

### <span data-ttu-id="5c3bb-151">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5c3bb-151">CommonParameters</span></span>

<span data-ttu-id="5c3bb-152">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5c3bb-153">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5c3bb-153">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5c3bb-154">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5c3bb-154">INPUTS</span></span>

### <span data-ttu-id="5c3bb-155">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="5c3bb-155">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="5c3bb-156">Sie können Objekte über die Pipeline an senden `Out-String` .</span><span class="sxs-lookup"><span data-stu-id="5c3bb-156">You can send objects down the pipeline to `Out-String`.</span></span>

## <span data-ttu-id="5c3bb-157">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5c3bb-157">OUTPUTS</span></span>

### <span data-ttu-id="5c3bb-158">System.String</span><span class="sxs-lookup"><span data-stu-id="5c3bb-158">System.String</span></span>

<span data-ttu-id="5c3bb-159">`Out-String` Gibt die Zeichenfolge zurück, die aus dem Eingabe Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-159">`Out-String` returns the string that it creates from the input object.</span></span>

## <span data-ttu-id="5c3bb-160">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5c3bb-160">NOTES</span></span>

<span data-ttu-id="5c3bb-161">Die Cmdlets, die das `Out` Verb enthalten, formatieren Objekte nicht.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-161">The cmdlets that contain the `Out` verb don't format objects.</span></span> <span data-ttu-id="5c3bb-162">Die- `Out` Cmdlets senden-Objekte an das Formatierer für das angegebene Anzeige Ziel.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-162">The `Out` cmdlets send objects to the formatter for the specified display destination.</span></span>

## <span data-ttu-id="5c3bb-163">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5c3bb-163">RELATED LINKS</span></span>

[<span data-ttu-id="5c3bb-164">about_Formatting</span><span class="sxs-lookup"><span data-stu-id="5c3bb-164">about_Formatting</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="5c3bb-165">Out-Default</span><span class="sxs-lookup"><span data-stu-id="5c3bb-165">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="5c3bb-166">Out-File</span><span class="sxs-lookup"><span data-stu-id="5c3bb-166">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="5c3bb-167">Out-Host</span><span class="sxs-lookup"><span data-stu-id="5c3bb-167">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="5c3bb-168">Out-Null</span><span class="sxs-lookup"><span data-stu-id="5c3bb-168">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="5c3bb-169">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="5c3bb-169">Out-GridView</span></span>](Out-GridView.md)

[<span data-ttu-id="5c3bb-170">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="5c3bb-170">Out-Printer</span></span>](Out-Printer.md)
