---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/join-string?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-String
ms.openlocfilehash: bae6b8558a3e12bf161d8f0ec12037841a20cc04
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211196"
---
# <span data-ttu-id="667a3-102">Join-String</span><span class="sxs-lookup"><span data-stu-id="667a3-102">Join-String</span></span>

## <span data-ttu-id="667a3-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="667a3-103">SYNOPSIS</span></span>
<span data-ttu-id="667a3-104">Kombiniert Objekte aus der Pipeline zu einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="667a3-104">Combines objects from the pipeline into a single string.</span></span>

## <span data-ttu-id="667a3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="667a3-105">SYNTAX</span></span>

### <span data-ttu-id="667a3-106">Standard (Standard)</span><span class="sxs-lookup"><span data-stu-id="667a3-106">Default (Default)</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-UseCulture] [-InputObject <PSObject[]>] [<CommonParameters>]
```

### <span data-ttu-id="667a3-107">Singleanführungs Zeichen</span><span class="sxs-lookup"><span data-stu-id="667a3-107">SingleQuote</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-SingleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="667a3-108">Doppeltes Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="667a3-108">DoubleQuote</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-DoubleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="667a3-109">Format</span><span class="sxs-lookup"><span data-stu-id="667a3-109">Format</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-FormatString <String>] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="667a3-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="667a3-110">DESCRIPTION</span></span>

<span data-ttu-id="667a3-111">Das `Join-String` Cmdlet verknüpft oder kombiniert Text von Pipeline Objekten in einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="667a3-111">The `Join-String` cmdlet joins, or combines, text from pipeline objects into a single string.</span></span>

<span data-ttu-id="667a3-112">Wenn keine Parameter angegeben werden, werden die Pipeline Objekte in eine Zeichenfolge konvertiert und mit dem Standard Trennzeichen verknüpft `$OFS` .</span><span class="sxs-lookup"><span data-stu-id="667a3-112">If no parameters are specified, the pipeline objects are converted to a string and joined with the default separator `$OFS`.</span></span>

<span data-ttu-id="667a3-113">Wenn Sie einen Eigenschaftsnamen angeben, wird der Wert der Eigenschaft in eine Zeichenfolge konvertiert und in eine Zeichenfolge aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="667a3-113">By specifying a property name, the property's value is converted to a string and joined into a string.</span></span>

<span data-ttu-id="667a3-114">Anstelle eines Eigenschafts namens kann ein Skriptblock verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="667a3-114">Instead of a property name, a script block can be used.</span></span> <span data-ttu-id="667a3-115">Das Ergebnis des Skript Blocks wird in eine Zeichenfolge konvertiert, bevor es verknüpft wird, um das Ergebnis zu bilden.</span><span class="sxs-lookup"><span data-stu-id="667a3-115">The script block's result is converted to a string before it's joined to form the result.</span></span> <span data-ttu-id="667a3-116">Es kann entweder der Text der-Eigenschaft eines Objekts oder das Ergebnis des-Objekts, das in eine Zeichenfolge konvertiert wurde, kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="667a3-116">It can either combine the text of an object's property or the result of the object that was converted to a string.</span></span>

<span data-ttu-id="667a3-117">Dieses Cmdlet wurde in PowerShell 6,2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="667a3-117">This cmdlet was introduced in PowerShell 6.2.</span></span>

## <span data-ttu-id="667a3-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="667a3-118">EXAMPLES</span></span>

### <span data-ttu-id="667a3-119">Beispiel 1: Verknüpfen von Verzeichnisnamen</span><span class="sxs-lookup"><span data-stu-id="667a3-119">Example 1: Join directory names</span></span>

<!-- markdownlint-disable MD038 -->
<span data-ttu-id="667a3-120">In diesem Beispiel werden Verzeichnisnamen miteinander verbunden, die Ausgabe wird in doppelte Anführungszeichen eingeschlossen und die Verzeichnisnamen werden durch ein Komma und ein Leerzeichen ( `, ` ) getrennt.</span><span class="sxs-lookup"><span data-stu-id="667a3-120">This example joins directory names, wraps the output in double-quotes, and separates the directory names with a comma and space (`, `).</span></span> <span data-ttu-id="667a3-121">Bei der Ausgabe handelt es sich um ein Zeichen folgen Objekt.</span><span class="sxs-lookup"><span data-stu-id="667a3-121">The output is a string object.</span></span>

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property Name -DoubleQuote -Separator ', '
```

```Output
"PerfLogs", "Program Files", "Program Files (x86)", "Users", "Windows"
```

<span data-ttu-id="667a3-122">`Get-ChildItem` verwendet den **Directory** -Parameter, um alle Verzeichnisnamen für das `C:\` Laufwerk zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="667a3-122">`Get-ChildItem` uses the **Directory** parameter to get all the directory names for the `C:\` drive.</span></span>
<span data-ttu-id="667a3-123">Die Objekte werden über die Pipeline an gesendet `Join-String` .</span><span class="sxs-lookup"><span data-stu-id="667a3-123">The objects are sent down the pipeline to `Join-String`.</span></span> <span data-ttu-id="667a3-124">Der **Property** -Parameter gibt die Verzeichnisnamen an.</span><span class="sxs-lookup"><span data-stu-id="667a3-124">The **Property** parameter specifies the directory names.</span></span> <span data-ttu-id="667a3-125">Der **Double Quote** -Parameter umschließt die Verzeichnisnamen in doppelte Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="667a3-125">The **DoubleQuote** parameter wraps the directory names with double-quote marks.</span></span>
<span data-ttu-id="667a3-126">Der **Separator** -Parameter gibt an, dass ein Komma und ein Leerzeichen ( `, ` ) zum Trennen der Verzeichnisnamen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="667a3-126">The **Separator** parameter specifies to use a comma and space (`, `) to separate the directory names.</span></span>

<span data-ttu-id="667a3-127">`Get-ChildItem`Bei den Objekten handelt es sich um **System. IO. directoriyinfo** `Join-String` , und die Objekte werden in **System. String** konvertiert.</span><span class="sxs-lookup"><span data-stu-id="667a3-127">The `Get-ChildItem` objects are **System.IO.DirectoryInfo** and `Join-String` converts the objects to **System.String** .</span></span>

### <span data-ttu-id="667a3-128">Beispiel 2: Verwenden einer Eigenschafts Teil Zeichenfolge zum Verknüpfen von Verzeichnisnamen</span><span class="sxs-lookup"><span data-stu-id="667a3-128">Example 2: Use a property substring to join directory names</span></span>

<span data-ttu-id="667a3-129">In diesem Beispiel wird eine Teil Zeichenfolge-Methode verwendet, um die ersten vier Buchstaben von Verzeichnisnamen zu erhalten, die Ausgabe in einfache Anführungszeichen umschließt und die Verzeichnisnamen durch ein Semikolon () voneinander zu trennen `;` .</span><span class="sxs-lookup"><span data-stu-id="667a3-129">This example uses a substring method to get the first four letters of directory names, wraps the output in single-quotes, and separates the directory names with a semicolon (`;`).</span></span>

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property {$_.Name.SubString(0,4)} -SingleQuote -Separator ';'
```

```Output
'Perf';'Prog';'Prog';'User';'Wind'
```

<span data-ttu-id="667a3-130">`Get-ChildItem` verwendet den **Directory** -Parameter, um alle Verzeichnisnamen für das `C:\` Laufwerk zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="667a3-130">`Get-ChildItem` uses the **Directory** parameter to get all the directory names for the `C:\` drive.</span></span>
<span data-ttu-id="667a3-131">Die Objekte werden über die Pipeline an gesendet `Join-String` .</span><span class="sxs-lookup"><span data-stu-id="667a3-131">The objects are sent down the pipeline to `Join-String`.</span></span>

<span data-ttu-id="667a3-132">Der **Property** -Parameter Skriptblock verwendet die automatische Variable ( `$_` ), um die **Name** -Eigenschafts Teil Zeichenfolge jedes Objekts anzugeben.</span><span class="sxs-lookup"><span data-stu-id="667a3-132">The **Property** parameter script block uses automatic variable (`$_`) to specify each object's **Name** property substring.</span></span> <span data-ttu-id="667a3-133">Die Teil Zeichenfolge Ruft die ersten vier Buchstaben jedes Verzeichnis namens ab.</span><span class="sxs-lookup"><span data-stu-id="667a3-133">The substring gets the first four letters of each directory name.</span></span> <span data-ttu-id="667a3-134">Die Teil Zeichenfolge gibt die Start-und Endpositionen des Zeichens an.</span><span class="sxs-lookup"><span data-stu-id="667a3-134">The substring specifies the character start and end positions.</span></span> <span data-ttu-id="667a3-135">Der **singlequote** -Parameter umschließt die Verzeichnisnamen in einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="667a3-135">The **SingleQuote** parameter wraps the directory names with single-quote marks.</span></span> <span data-ttu-id="667a3-136">Der **Separator** -Parameter gibt an, dass ein Semikolon ( `;` ) zum Trennen der Verzeichnisnamen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667a3-136">The **Separator** parameter specifies to use a semicolon (`;`) to separate the directory names.</span></span>

<span data-ttu-id="667a3-137">Weitere Informationen zu automatischen Variablen und Teil Zeichenfolgen finden Sie unter [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) und [Teil Zeichenfolge](/dotnet/api/system.string.substring).</span><span class="sxs-lookup"><span data-stu-id="667a3-137">For more information about automatic variables and substrings, see [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) and [Substring](/dotnet/api/system.string.substring).</span></span>

### <span data-ttu-id="667a3-138">Beispiel 3: Anzeigen der joinausgabe in einer separaten Zeile</span><span class="sxs-lookup"><span data-stu-id="667a3-138">Example 3: Display join output on a separate line</span></span>

<span data-ttu-id="667a3-139">In diesem Beispiel werden Dienstnamen mit den einzelnen Diensten in einer separaten Zeile und eingerückt durch eine Registerkarte verbunden.</span><span class="sxs-lookup"><span data-stu-id="667a3-139">This example joins service names with each service on a separate line and indented by a tab.</span></span>

```powershell
Get-Service -Name se* | Join-String -Property Name -Separator "`r`n`t" -OutputPrefix "Services:`n`t"
```

```Output
Services:
    seclogon
    SecurityHealthService
    SEMgrSvc
    SENS
    Sense
    SensorDataService
    SensorService
    SensrSvc
    SessionEnv
```

<span data-ttu-id="667a3-140">`Get-Service` verwendet den **Name** -Parameter mit, um Dienste anzugeben, die mit beginnen `se*` .</span><span class="sxs-lookup"><span data-stu-id="667a3-140">`Get-Service` uses the **Name** parameter with to specify services that begin with `se*`.</span></span> <span data-ttu-id="667a3-141">Das Sternchen ( `*` ) ist ein Platzhalter für ein beliebiges Zeichen.</span><span class="sxs-lookup"><span data-stu-id="667a3-141">The asterisk (`*`) is a wildcard for any character.</span></span>

<span data-ttu-id="667a3-142">Die Objekte werden an die Pipeline gesendet, die den `Join-String` **Property** -Parameter verwendet, um die Dienstnamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="667a3-142">The objects are sent down the pipeline to `Join-String` that uses the **Property** parameter to specify the service names.</span></span> <span data-ttu-id="667a3-143">Der **Separator** -Parameter gibt drei Sonderzeichen an, die ein Wagen Rücklauf Zeichen (), Zeilenumbruch Zeichen `` `r `` ( `` `n `` ) und Tabulator Zeichen () darstellen `` `t `` .</span><span class="sxs-lookup"><span data-stu-id="667a3-143">The **Separator** parameter specifies three special characters that represent a carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span> <span data-ttu-id="667a3-144">**Outputprefix** fügt einen Label- **Dienst ein:** eine neue Zeile und eine neue Registerkarte vor der ersten Zeile der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="667a3-144">The **OutputPrefix** inserts a label **Services:** with a new line and tab before the first line of output.</span></span>

<span data-ttu-id="667a3-145">Weitere Informationen zu Sonderzeichen finden Sie unter [about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md).</span><span class="sxs-lookup"><span data-stu-id="667a3-145">For more information about special characters, see [about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md).</span></span>

### <span data-ttu-id="667a3-146">Beispiel 4: Erstellen einer Klassendefinition aus einem Objekt</span><span class="sxs-lookup"><span data-stu-id="667a3-146">Example 4: Create a class definition from an object</span></span>

<span data-ttu-id="667a3-147">In diesem Beispiel wird eine PowerShell-Klassendefinition mit einem vorhandenen-Objekt als Vorlage generiert.</span><span class="sxs-lookup"><span data-stu-id="667a3-147">This example generates a PowerShell class definition using an existing object as a template.</span></span>

<span data-ttu-id="667a3-148">Dieses Codebeispiel verwendet Verteilung, um die Zeilenlänge zu verringern und die Lesbarkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="667a3-148">This code sample uses splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="667a3-149">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="667a3-149">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

```powershell
$obj = [pscustomobject] @{Name = "Joe"; Age = 42}
$parms = @{
  Property = "Name"
  FormatString = '  ${0}'
  OutputPrefix = "class {`n"
  OutputSuffix = "`n}`n"
  Separator = "`n"
}
$obj.PSObject.Properties | Join-String @parms
```

```Output
class {
  $Name
  $Age
}
```

## <span data-ttu-id="667a3-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="667a3-150">PARAMETERS</span></span>

### <span data-ttu-id="667a3-151">-Doubleanführungs Zeichen</span><span class="sxs-lookup"><span data-stu-id="667a3-151">-DoubleQuote</span></span>

<span data-ttu-id="667a3-152">Umschließt den Zeichen folgen Wert jedes Pipeline Objekts in doppelten Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="667a3-152">Wraps the string value of each pipeline object in double-quotes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DoubleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="667a3-153">-Format Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="667a3-153">-FormatString</span></span>

<span data-ttu-id="667a3-154">Eine Format Zeichenfolge, die angibt, wie die einzelnen Elemente formatiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="667a3-154">A format string that specifies how each item should be formatted.</span></span>

```yaml
Type: System.String
Parameter Sets: Format
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="667a3-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="667a3-155">-InputObject</span></span>

<span data-ttu-id="667a3-156">Gibt den Text an, der verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="667a3-156">Specifies the text to be joined.</span></span> <span data-ttu-id="667a3-157">Geben Sie eine Variable ein, die den Text enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden, die in Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="667a3-157">Enter a variable that contains the text, or type a command or expression that gets the objects to join into strings.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="667a3-158">-Outputprefix</span><span class="sxs-lookup"><span data-stu-id="667a3-158">-OutputPrefix</span></span>

<span data-ttu-id="667a3-159">Text, der vor der Ausgabe Zeichenfolge eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="667a3-159">Text that's inserted before the output string.</span></span> <span data-ttu-id="667a3-160">Die Zeichenfolge kann Sonderzeichen wie z. b. Wagen Rücklauf ( `` `r `` ), Zeilenumbruch ( `` `n `` ) und Tab ( `` `t `` ) enthalten.</span><span class="sxs-lookup"><span data-stu-id="667a3-160">The string can contain special characters such as carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: op

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="667a3-161">-Outputsuffix</span><span class="sxs-lookup"><span data-stu-id="667a3-161">-OutputSuffix</span></span>

<span data-ttu-id="667a3-162">Text, der an die Ausgabe Zeichenfolge angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="667a3-162">Text that's appended to the output string.</span></span> <span data-ttu-id="667a3-163">Die Zeichenfolge kann Sonderzeichen wie z. b. Wagen Rücklauf ( `` `r `` ), Zeilenumbruch ( `` `n `` ) und Tab ( `` `t `` ) enthalten.</span><span class="sxs-lookup"><span data-stu-id="667a3-163">The string can contain special characters such as carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="667a3-164">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="667a3-164">-Property</span></span>

<span data-ttu-id="667a3-165">Der Name einer Eigenschaft oder ein Eigenschafts Ausdruck, der das Pipeline Objekt in Text projizieren soll.</span><span class="sxs-lookup"><span data-stu-id="667a3-165">The name of a property, or a property expression, that will project the pipeline object to text.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="667a3-166">-Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="667a3-166">-Separator</span></span>

<span data-ttu-id="667a3-167">Text oder Zeichen, z. b. ein Komma oder Semikolon, das zwischen dem Text für jedes Pipeline Objekt eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="667a3-167">Text or characters such as a comma or semicolon that's inserted between the text for each pipeline object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="667a3-168">-Singleanführungs Zeichen</span><span class="sxs-lookup"><span data-stu-id="667a3-168">-SingleQuote</span></span>

<span data-ttu-id="667a3-169">Umschließt den Zeichen folgen Wert jedes Pipeline Objekts in einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="667a3-169">Wraps the string value of each pipeline object in single quotes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SingleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="667a3-170">-Useculture</span><span class="sxs-lookup"><span data-stu-id="667a3-170">-UseCulture</span></span>

<span data-ttu-id="667a3-171">Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="667a3-171">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="667a3-172">Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="667a3-172">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="667a3-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="667a3-173">CommonParameters</span></span>

<span data-ttu-id="667a3-174">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="667a3-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="667a3-175">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="667a3-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="667a3-176">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="667a3-176">INPUTS</span></span>

### <span data-ttu-id="667a3-177">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="667a3-177">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="667a3-178">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="667a3-178">OUTPUTS</span></span>

### <span data-ttu-id="667a3-179">System.String</span><span class="sxs-lookup"><span data-stu-id="667a3-179">System.String</span></span>

## <span data-ttu-id="667a3-180">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="667a3-180">NOTES</span></span>

## <span data-ttu-id="667a3-181">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="667a3-181">RELATED LINKS</span></span>

[<span data-ttu-id="667a3-182">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="667a3-182">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="667a3-183">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="667a3-183">about_Special_Characters</span></span>](..//microsoft.powershell.core/about/about_special_characters.md)

[<span data-ttu-id="667a3-184">Teil Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="667a3-184">Substring</span></span>](/dotnet/api/system.string.substring)
