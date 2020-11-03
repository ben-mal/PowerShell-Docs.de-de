---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-String
ms.openlocfilehash: 665a0ca8332c4052b59362c7947e408ba811c5f2
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "93219796"
---
# <span data-ttu-id="a1725-103">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="a1725-103">ConvertFrom-String</span></span>

## <span data-ttu-id="a1725-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a1725-104">SYNOPSIS</span></span>
<span data-ttu-id="a1725-105">Extrahiert und analysiert strukturierte Eigenschaften aus dem Zeichen folgen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="a1725-105">Extracts and parses structured properties from string content.</span></span>

## <span data-ttu-id="a1725-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a1725-106">SYNTAX</span></span>

### <span data-ttu-id="a1725-107">Bydelimiter (Standard)</span><span class="sxs-lookup"><span data-stu-id="a1725-107">ByDelimiter (Default)</span></span>

```
ConvertFrom-String [-Delimiter <String>] [-PropertyNames <String[]>] [-InputObject] <String>
 [<CommonParameters>]
```

### <span data-ttu-id="a1725-108">Templatetesing</span><span class="sxs-lookup"><span data-stu-id="a1725-108">TemplateParsing</span></span>

```
ConvertFrom-String [-TemplateFile <String[]>] [-TemplateContent <String[]>] [-IncludeExtent] [-UpdateTemplate]
 [-InputObject] <String> [<CommonParameters>]
```

## <span data-ttu-id="a1725-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a1725-109">DESCRIPTION</span></span>

<span data-ttu-id="a1725-110">Das **ConvertFrom-String-** Cmdlet extrahiert und analysiert strukturierte Eigenschaften aus dem Zeichen folgen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="a1725-110">The **ConvertFrom-String** cmdlet extracts and parses structured properties from string content.</span></span>
<span data-ttu-id="a1725-111">Dieses Cmdlet generiert ein Objekt, indem es Text aus einem herkömmlichen Textstream verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a1725-111">This cmdlet generates an object by parsing text from a traditional text stream.</span></span>
<span data-ttu-id="a1725-112">Für jede Zeichenfolge in der Pipeline teilt das Cmdlet die Eingabe entweder durch ein Trennzeichen oder einen Analyse Ausdruck auf und weist dann jedem der resultierenden geteilten Elemente Eigenschaftsnamen zu.</span><span class="sxs-lookup"><span data-stu-id="a1725-112">For each string in the pipeline, the cmdlet splits the input by either a delimiter or a parse expression, and then assigns property names to each of the resulting split elements.</span></span>
<span data-ttu-id="a1725-113">Sie können diese Eigenschaftsnamen angeben. Wenn Sie dies nicht tun, werden Sie automatisch für Sie generiert.</span><span class="sxs-lookup"><span data-stu-id="a1725-113">You can provide these property names; if you do not, they are automatically generated for you.</span></span>

<span data-ttu-id="a1725-114">Der Standardparametersatz des Cmdlets, **bydelimiter** , wird genau für das Trennzeichen für reguläre Ausdrücke unterteilt.</span><span class="sxs-lookup"><span data-stu-id="a1725-114">The cmdlet's default parameter set, **ByDelimiter** , splits exactly on the regular expression delimiter.</span></span>
<span data-ttu-id="a1725-115">Er führt keine Anführungszeichen oder Trennzeichen aus, wie es das `Import-Csv` Cmdlet tut.</span><span class="sxs-lookup"><span data-stu-id="a1725-115">It does not perform quote matching or delimiter escaping as the `Import-Csv` cmdlet does.</span></span>

<span data-ttu-id="a1725-116">Der Alternative Parametersatz des Cmdlets, **templatearsing** , generiert Elemente aus den Gruppen, die von einem regulären Ausdruck aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="a1725-116">The cmdlet's alternate parameter set, **TemplateParsing** , generates elements from the groups that are captured by a regular expression.</span></span> <span data-ttu-id="a1725-117">Weitere Informationen zu regulären Ausdrücken finden Sie unter [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a1725-117">For more information on regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

<span data-ttu-id="a1725-118">Dieses Cmdlet unterstützt zwei Modi: eine einfache, durch Trennzeichen getrennte und automatisch generierte, Beispiel gesteuerte Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="a1725-118">This cmdlet supports two modes: basic delimited parsing, and automatically-generated, example-driven parsing.</span></span>

<span data-ttu-id="a1725-119">Bei der getrennten Analyse wird die Eingabe standardmäßig bei Leerzeichen getrennt, wobei den resultierenden Gruppen Eigenschaftsnamen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a1725-119">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span>

<span data-ttu-id="a1725-120">Sie können das Trennzeichen anpassen, indem Sie die `ConvertFrom-String` Ergebnisse an eines der `Format-*` Cmdlets weiterleiten, oder Sie können den **Trennzeichen** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1725-120">You can customize the delimiter by piping the `ConvertFrom-String` results into one of the `Format-*` cmdlets, or you can use the **Delimiter** parameter.</span></span>

<span data-ttu-id="a1725-121">Das Cmdlet unterstützt auch automatisch generierte, Beispiel gesteuerte Analyse basierend auf den unter [suchungen von Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).</span><span class="sxs-lookup"><span data-stu-id="a1725-121">The cmdlet also supports automatically-generated, example-driven parsing based on the [FlashExtract, research work by Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).</span></span>

## <span data-ttu-id="a1725-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a1725-122">EXAMPLES</span></span>

### <span data-ttu-id="a1725-123">Beispiel 1: Generieren eines Objekts mit Standard Eigenschaftsnamen</span><span class="sxs-lookup"><span data-stu-id="a1725-123">Example 1: Generate an object with default property names</span></span>

```powershell
"Hello World" | ConvertFrom-String
```

```Output
P1    P2
--    --
Hello World
```

<span data-ttu-id="a1725-124">Mit diesem Befehl wird ein Objekt mit den Standard Eigenschaftsnamen **P1** und **P2** generiert.</span><span class="sxs-lookup"><span data-stu-id="a1725-124">This command generates an object with default property names, **P1** and **P2**.</span></span>

### <span data-ttu-id="a1725-125">Beispiel 1a: Kennenlernen des generierten Objekts</span><span class="sxs-lookup"><span data-stu-id="a1725-125">Example 1A: Get to know the generated object</span></span>

<span data-ttu-id="a1725-126">Dieser Befehl generiert ein Objekt mit den Eigenschaften **P1** , **P2** ; beide Eigenschaften haben standardmäßig den Typ " **String** ".</span><span class="sxs-lookup"><span data-stu-id="a1725-126">This command generates one object with properties **P1** , **P2** ; both properties are of **String** type, by default.</span></span>

```powershell
"Hello World" | ConvertFrom-String | Get-Member
```

```Output

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
P1          NoteProperty string P1=Hello
P2          NoteProperty string P2=World
```

### <span data-ttu-id="a1725-127">Beispiel 2: Generieren eines Objekts mit Standard Eigenschaftsnamen mithilfe eines Trenn Zeichens</span><span class="sxs-lookup"><span data-stu-id="a1725-127">Example 2: Generate an object with default property names using a delimiter</span></span>

<span data-ttu-id="a1725-128">Mit diesem Befehl wird ein Objekt mit einer Domäne und einem Benutzernamen generiert, wobei der umgekehrte Schrägstrich ( `\` ) als Trennzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a1725-128">This command generates an object with a domain and username using the backslash (`\`) as the delimiter.</span></span> <span data-ttu-id="a1725-129">Der umgekehrte Schrägstrich muss bei Verwendung regulärer Ausdrücke mit einem anderen umgekehrten Schrägstrich versehen werden.</span><span class="sxs-lookup"><span data-stu-id="a1725-129">The backslash character must be escaped with another backslash when using regular expressions.</span></span>

```powershell
"Contoso\Administrator" | ConvertFrom-String -Delimiter "\\"
```

```Output
P1      P2
--      --
Contoso Administrator
```

### <span data-ttu-id="a1725-130">Beispiel 3: Generieren eines Objekts, das zwei benannte Eigenschaften enthält</span><span class="sxs-lookup"><span data-stu-id="a1725-130">Example 3: Generate an object that contains two named properties</span></span>

<span data-ttu-id="a1725-131">Im folgenden Beispiel werden-Objekte aus Windows Hosts-Datei Einträge erstellt.</span><span class="sxs-lookup"><span data-stu-id="a1725-131">The following example creates objects from Windows hosts file entries.</span></span>

```powershell
$content = Get-Content C:\Windows\System32\drivers\etc\hosts
$content = $content -match "^[^#]"
$content | ConvertFrom-String -PropertyNames IP, Server
```

```Output
IP             Server
--             ------
192.168.7.10   W2012R2
192.168.7.20   W2016
192.168.7.101  WIN8
192.168.7.102  WIN10
```

<span data-ttu-id="a1725-132">Das- `Get-Content` Cmdlet speichert den Inhalt einer Windows-Hostdatei in `$content` .</span><span class="sxs-lookup"><span data-stu-id="a1725-132">The `Get-Content` cmdlet stores the content of a Windows hosts file in `$content`.</span></span> <span data-ttu-id="a1725-133">Mit dem zweiten Befehl werden alle Kommentare am Anfang der Hosts-Datei mit einem regulären Ausdruck entfernt, der mit einer beliebigen Zeile übereinstimmt, die nicht mit ( `#` ) beginnt.</span><span class="sxs-lookup"><span data-stu-id="a1725-133">The second command removes any comments at the beginning of the hosts file using a regular expression that matches any line that does not start with (`#`).</span></span> <span data-ttu-id="a1725-134">Mit dem letzten Befehl wird der verbleibende Text in Objekte mit **Server** -und **IP-** Eigenschaften konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a1725-134">The last command converts the remaining text into objects with **Server** and **IP** properties.</span></span>

### <span data-ttu-id="a1725-135">Beispiel 4: Verwenden Sie einen Ausdruck als Wert des TemplateContent-Parameters, und speichern Sie die Ergebnisse in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="a1725-135">Example 4: Use an expression as the value of the TemplateContent parameter, save the results in a variable.</span></span>

<span data-ttu-id="a1725-136">Dieser Befehl verwendet einen Ausdruck als Wert des **TemplateContent** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="a1725-136">This command uses an expression as the value of the **TemplateContent** parameter.</span></span>
<span data-ttu-id="a1725-137">Der Ausdruck wird aus Gründen der Einfachheit in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a1725-137">The expression is saved in a variable for simplicity.</span></span>
<span data-ttu-id="a1725-138">Windows PowerShell versteht nun, dass die Zeichenfolge, die in der Pipeline verwendet wird, über `ConvertFrom-String` drei Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="a1725-138">Windows PowerShell understands now that the string that is used on the pipeline to `ConvertFrom-String` has three properties:</span></span>

- <span data-ttu-id="a1725-139">**Name**</span><span class="sxs-lookup"><span data-stu-id="a1725-139">**Name**</span></span>
- <span data-ttu-id="a1725-140">**Smartphone**</span><span class="sxs-lookup"><span data-stu-id="a1725-140">**phone**</span></span>
- <span data-ttu-id="a1725-141">**Eder**</span><span class="sxs-lookup"><span data-stu-id="a1725-141">**age**</span></span>

```powershell
$template = @'
{Name*:Phoebe Cat}, {phone:425-123-6789}, {age:6}
{Name*:Lucky Shot}, {phone:(206) 987-4321}, {age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789    6
Lucky Shot    (206) 987-4321  12
Elephant Wise 425-888-7766    87
Wild Shrimp   (111)  222-3333 1
```

<span data-ttu-id="a1725-142">Jede Zeile in der Eingabe wird von den Beispiel Übereinstimmungen ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="a1725-142">Each line in the input is evaluated by the sample matches.</span></span> <span data-ttu-id="a1725-143">Wenn die Zeile mit den im Muster angegebenen Beispielen übereinstimmt, werden die Werte extrahiert und an die OUTPUT-Variable übergeben.</span><span class="sxs-lookup"><span data-stu-id="a1725-143">If the line matches the examples given in the pattern, values are extracted and passed to the output variable.</span></span>

<span data-ttu-id="a1725-144">Die Beispiel Daten, `$template` , bieten zwei verschiedene Telefon Formate:</span><span class="sxs-lookup"><span data-stu-id="a1725-144">The sample data, `$template`, provides two different phone formats:</span></span>

- `425-123-6789`
- `(206) 987-4321`

<span data-ttu-id="a1725-145">Die Beispiel Daten stellen auch zwei verschiedene Alters Formate bereit:</span><span class="sxs-lookup"><span data-stu-id="a1725-145">The sample data also provides two different age formats:</span></span>

- `6`
- `12`

<span data-ttu-id="a1725-146">Dies impliziert, dass Telefone wie `(206) 987 4321` nicht erkannt werden, weil es keine Stichprobendaten gibt, die diesem Muster entsprechen, da keine Bindestriche vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a1725-146">This implies that phones like `(206) 987 4321` will not be recognized, because there's no sample data that matches that pattern because there are no hyphens.</span></span>

### <span data-ttu-id="a1725-147">Beispiel 5: Angeben von Datentypen für die generierten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a1725-147">Example 5: Specifying data types to the generated properties</span></span>

<span data-ttu-id="a1725-148">Dies ist das gleiche Beispiel wie Beispiel 4 oben.</span><span class="sxs-lookup"><span data-stu-id="a1725-148">This is the same example as Example 4, above.</span></span>
<span data-ttu-id="a1725-149">Der Unterschied besteht darin, dass die Muster Zeichenfolge einen Datentyp für jede gewünschte Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="a1725-149">The difference is that the pattern string includes a data type for each desired property.</span></span>

```powershell
$template = @'
{[string]Name*:Phoebe Cat}, {[string]phone:425-123-6789}, {[int]age:6}
{[string]Name*:Lucky Shot}, {[string]phone:(206) 987-4321}, {[int]age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789      6
Lucky Shot    (206) 987-4321   12
Elephant Wise 425-888-7766     87
Wild Shrimp   (111)  222-3333   1
```

```powershell
$PersonalData | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
age         NoteProperty int age=6
Name        NoteProperty string Name=Phoebe Cat
phone       NoteProperty string phone=425-123-6789
```

<span data-ttu-id="a1725-150">Das- `Get-Member` Cmdlet wird verwendet, um anzuzeigen, dass die **Age** -Eigenschaft eine ganze Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="a1725-150">The `Get-Member` cmdlet is used to show that the **age** property is an integer.</span></span>

## <span data-ttu-id="a1725-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a1725-151">PARAMETERS</span></span>

### <span data-ttu-id="a1725-152">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="a1725-152">-Delimiter</span></span>

<span data-ttu-id="a1725-153">Gibt einen regulären Ausdruck an, der die Grenze zwischen Elementen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a1725-153">Specifies a regular expression that identifies the boundary between elements.</span></span>
<span data-ttu-id="a1725-154">Elemente, die von der Teilung erstellt werden, werden im resultierenden Objekt zu Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a1725-154">Elements that are created by the split become properties in the resulting object.</span></span>
<span data-ttu-id="a1725-155">Das Trennzeichen wird letztendlich in einem Aufrufe der **Split** -Methode des Typs verwendet `[System.Text.RegularExpressions.RegularExpression]` .</span><span class="sxs-lookup"><span data-stu-id="a1725-155">The delimiter is ultimately used in a call to the **Split** method of the type `[System.Text.RegularExpressions.RegularExpression]`.</span></span>

```yaml
Type: System.String
Parameter Sets: ByDelimiter
Aliases: DEL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a1725-156">-Includezblock</span><span class="sxs-lookup"><span data-stu-id="a1725-156">-IncludeExtent</span></span>

<span data-ttu-id="a1725-157">Gibt an, dass dieses Cmdlet eine standardmäßige Text Eigenschaft enthält, die standardmäßig entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="a1725-157">Indicates that this cmdlet includes an extent text property that is removed by default.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: IE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a1725-158">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a1725-158">-InputObject</span></span>

<span data-ttu-id="a1725-159">Gibt von der Pipeline empfangene Zeichen folgen oder eine Variable an, die ein Zeichen folgen Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="a1725-159">Specifies strings received from the pipeline, or a variable that contains a string object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a1725-160">-PropertyNames</span><span class="sxs-lookup"><span data-stu-id="a1725-160">-PropertyNames</span></span>

<span data-ttu-id="a1725-161">Gibt ein Array von Eigenschaften Namen an, denen im resultierenden-Objekt geteilte Werte zugewiesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a1725-161">Specifies an array of property names to which to assign split values in the resulting object.</span></span>
<span data-ttu-id="a1725-162">Jede Textzeile, die Sie teilen oder analysieren, generiert Elemente, die Eigenschaftswerte darstellen.</span><span class="sxs-lookup"><span data-stu-id="a1725-162">Every line of text that you split or parse generates elements that represent property values.</span></span>
<span data-ttu-id="a1725-163">Wenn das-Element das Ergebnis einer Erfassungs Gruppe ist und diese Erfassungs Gruppe benannt ist (z. b. `(?<name>)` oder `(?'name')` ), wird der Name dieser Erfassungs Gruppe der-Eigenschaft zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a1725-163">If the element is the result of a capture group, and that capture group is named (for example, `(?<name>)` or `(?'name')` ), then the name of that capture group is assigned to the property.</span></span>

<span data-ttu-id="a1725-164">Wenn Sie Elemente im **propertyName** -Array bereitstellen, werden diese Namen Eigenschaften zugewiesen, die noch nicht benannt wurden.</span><span class="sxs-lookup"><span data-stu-id="a1725-164">If you provide any elements in the **PropertyName** array, those names are assigned to properties that have not yet been named.</span></span>

<span data-ttu-id="a1725-165">Wenn Sie weitere Eigenschaften Namen bereitstellen, als Felder vorhanden sind, ignoriert PowerShell die zusätzlichen Eigenschaftsnamen.</span><span class="sxs-lookup"><span data-stu-id="a1725-165">If you provide more property names than there are fields, PowerShell ignores the extra property names.</span></span> <span data-ttu-id="a1725-166">Wenn Sie nicht genug Eigenschaftsnamen angeben, um alle Felder zu benennen, weist PowerShell alle Eigenschaften, die nicht den Namen **P1** , **P2** usw. aufweisen, automatisch numerischen Eigenschaftsnamen zu.</span><span class="sxs-lookup"><span data-stu-id="a1725-166">If you do not specify enough property names to name all fields, PowerShell automatically assigns numerical property names to any properties that are not named: **P1** , **P2** , etc.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByDelimiter
Aliases: PN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a1725-167">-TemplateContent</span><span class="sxs-lookup"><span data-stu-id="a1725-167">-TemplateContent</span></span>

<span data-ttu-id="a1725-168">Gibt einen Ausdruck oder einen als Variable gespeicherten Ausdruck an, der die Eigenschaften beschreibt, denen dieses Cmdlet Zeichen folgen zuweist.</span><span class="sxs-lookup"><span data-stu-id="a1725-168">Specifies an expression, or an expression saved as a variable, that describes the properties to which this cmdlet assigns strings.</span></span> <span data-ttu-id="a1725-169">Die Syntax einer Vorlagen Feld Spezifikation lautet wie folgt: `{[optional-typecast]<name>:<example-value>}` .</span><span class="sxs-lookup"><span data-stu-id="a1725-169">The syntax of a template field specification is the following: `{[optional-typecast]<name>:<example-value>}`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a1725-170">-TemplateFile</span><span class="sxs-lookup"><span data-stu-id="a1725-170">-TemplateFile</span></span>

<span data-ttu-id="a1725-171">Gibt eine Datei als Array an, die eine Vorlage für die gewünschte Analyse der Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="a1725-171">Specifies a file, as an array, that contains a template for the desired parsing of the string.</span></span>
<span data-ttu-id="a1725-172">In der Vorlagen Datei werden Eigenschaften und deren Werte in eckige Klammern eingeschlossen, wie unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1725-172">In the template file, properties and their values are enclosed in brackets, as shown below.</span></span>
<span data-ttu-id="a1725-173">Wenn eine Eigenschaft, z. b. die **Name** -Eigenschaft und die zugehörigen anderen Eigenschaften, mehrmals angezeigt wird, können Sie ein Sternchen () hinzufügen, `*` um anzugeben, dass dies zu mehreren Datensätzen führt.</span><span class="sxs-lookup"><span data-stu-id="a1725-173">If a property, such as the **Name** property and its associated other properties, appears multiple times, you can add an asterisk (`*`) to indicate that this results in multiple records.</span></span> <span data-ttu-id="a1725-174">Dadurch wird vermieden, dass mehrere Eigenschaften in einen einzelnen Datensatz extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="a1725-174">This avoids extracting multiple properties into a single record.</span></span>

```
{Name*:David Chew}
{City:Redmond}, {State:WA}
{Name*:Evan Narvaez}    {Name*:Antonio Moreno}
{City:Issaquah}, {State:WA}
```

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a1725-175">-Updatetemplate</span><span class="sxs-lookup"><span data-stu-id="a1725-175">-UpdateTemplate</span></span>

<span data-ttu-id="a1725-176">Gibt an, dass dieses Cmdlet die Ergebnisse eines Lernalgorithmus in einem Kommentar in der Vorlagen Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="a1725-176">Indicates that this cmdlet saves the results of a learning algorithm into a comment in the template file.</span></span>
<span data-ttu-id="a1725-177">Dadurch wird der algorithmuslernprozess schneller.</span><span class="sxs-lookup"><span data-stu-id="a1725-177">This makes the algorithm learning process faster.</span></span>
<span data-ttu-id="a1725-178">Um diesen Parameter zu verwenden, müssen Sie auch eine Vorlagen Datei mit dem Parameter **TemplateFile** angeben.</span><span class="sxs-lookup"><span data-stu-id="a1725-178">To use this parameter, you must also specify a template file with the **TemplateFile** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: UT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a1725-179">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a1725-179">CommonParameters</span></span>

<span data-ttu-id="a1725-180">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="a1725-180">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="a1725-181">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a1725-181">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a1725-182">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a1725-182">INPUTS</span></span>

### <span data-ttu-id="a1725-183">System.String</span><span class="sxs-lookup"><span data-stu-id="a1725-183">System.String</span></span>

## <span data-ttu-id="a1725-184">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a1725-184">OUTPUTS</span></span>

## <span data-ttu-id="a1725-185">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a1725-185">NOTES</span></span>

## <span data-ttu-id="a1725-186">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a1725-186">RELATED LINKS</span></span>

[<span data-ttu-id="a1725-187">ConvertFrom-String: Beispiel basierte Textverarbeitung</span><span class="sxs-lookup"><span data-stu-id="a1725-187">ConvertFrom-String: Example-based text parsing</span></span>](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)

[<span data-ttu-id="a1725-188">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="a1725-188">ConvertFrom-StringData</span></span>](ConvertFrom-StringData.md)

[<span data-ttu-id="a1725-189">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="a1725-189">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="a1725-190">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="a1725-190">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)
