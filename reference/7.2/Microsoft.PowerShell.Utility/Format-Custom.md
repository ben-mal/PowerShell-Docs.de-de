---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-custom?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Custom
ms.openlocfilehash: ff4b2dda3f12fa34fc518c6a180f3213ba873d90
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603508"
---
# <span data-ttu-id="66d24-102">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="66d24-102">Format-Custom</span></span>

## <span data-ttu-id="66d24-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="66d24-103">SYNOPSIS</span></span>
<span data-ttu-id="66d24-104">Verwendet eine benutzerdefinierte Ansicht zur Formatierung der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="66d24-104">Uses a customized view to format the output.</span></span>

## <span data-ttu-id="66d24-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66d24-105">SYNTAX</span></span>

```
Format-Custom [[-Property] <Object[]>] [-Depth <Int32>] [-GroupBy <Object>] [-View <String>]
 [-ShowError] [-DisplayError] [-Force] [-Expand <String>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## <span data-ttu-id="66d24-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66d24-106">DESCRIPTION</span></span>

<span data-ttu-id="66d24-107">Das- `Format-Custom` Cmdlet formatiert die Ausgabe eines Befehls, wie in einer alternativen Ansicht definiert.</span><span class="sxs-lookup"><span data-stu-id="66d24-107">The `Format-Custom` cmdlet formats the output of a command as defined in an alternate view.</span></span>
<span data-ttu-id="66d24-108">`Format-Custom` dient zum Anzeigen von Sichten, bei denen es sich nicht nur um Tabellen oder nur Listen handelt.</span><span class="sxs-lookup"><span data-stu-id="66d24-108">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="66d24-109">Sie können die in PowerShell definierten Ansichten verwenden, oder Sie können eigene Sichten in einer neuen Datei erstellen `format.ps1xml` und Sie mit dem `Update-FormatData` Cmdlet PowerShell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="66d24-109">You can use the views defined in PowerShell, or you can create your own views in a new `format.ps1xml` file and use the `Update-FormatData` cmdlet to add them to PowerShell.</span></span>

## <span data-ttu-id="66d24-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="66d24-110">EXAMPLES</span></span>

### <span data-ttu-id="66d24-111">Beispiel 1: Formatieren der Ausgabe mit einer benutzerdefinierten Ansicht</span><span class="sxs-lookup"><span data-stu-id="66d24-111">Example 1: Format output with a custom view</span></span>

```powershell
Get-Command Start-Transcript | Format-Custom -View MyView
```

<span data-ttu-id="66d24-112">Dieser Befehl formatiert Informationen über das `Start-Transcript` Cmdlet in dem Format, das in der MyView-Ansicht definiert ist, einer benutzerdefinierten Ansicht, die vom Benutzer erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="66d24-112">This command formats information about the `Start-Transcript` cmdlet in the format defined by the MyView view, a custom view created by the user.</span></span> <span data-ttu-id="66d24-113">Zum erfolgreichen Ausführen dieses Befehls müssen Sie zuerst eine neue PS1XML-Datei erstellen, die Ansicht **MyView** definieren und dann den Befehl verwenden, `Update-FormatData` um die Datei PS1XML zu PowerShell hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="66d24-113">To run this command successfully, you must first create a new PS1XML file, define the **MyView** view, and then use the `Update-FormatData` command to add the PS1XML file to PowerShell.</span></span>

### <span data-ttu-id="66d24-114">Beispiel 2: Formatieren der Ausgabe mit der Standardansicht</span><span class="sxs-lookup"><span data-stu-id="66d24-114">Example 2: Format output with the default view</span></span>

```powershell
Get-Process Winlogon | Format-Custom
```

<span data-ttu-id="66d24-115">Mit diesem Befehl werden Informationen über den **Winlogon** -Prozess in einer alternativen angepassten Ansicht formatiert.</span><span class="sxs-lookup"><span data-stu-id="66d24-115">This command formats information about the **Winlogon** process in an alternate customized view.</span></span>
<span data-ttu-id="66d24-116">Da der Befehl den **View** -Parameter nicht verwendet, `Format-Custom` verwendet eine standardmäßige benutzerdefinierte Ansicht, um die Daten zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="66d24-116">Because the command does not use the **View** parameter, `Format-Custom` uses a default custom view to format the data.</span></span>

### <span data-ttu-id="66d24-117">Beispiel 3: Problembehandlung bei Format Fehlern</span><span class="sxs-lookup"><span data-stu-id="66d24-117">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="66d24-118">Die folgenden Beispiele zeigen die Ergebnisse des Hinzufügens der **displayerror** -oder **ShowError** -Parameter mit einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="66d24-118">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -DisplayError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  = #ERR
}


PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -ShowError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  =
}

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:01:04 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="66d24-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66d24-119">PARAMETERS</span></span>

### <span data-ttu-id="66d24-120">-Tiefe</span><span class="sxs-lookup"><span data-stu-id="66d24-120">-Depth</span></span>

<span data-ttu-id="66d24-121">Gibt die Anzahl der Spalten in der Anzeige an.</span><span class="sxs-lookup"><span data-stu-id="66d24-121">Specifies the number of columns in the display.</span></span>

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

### <span data-ttu-id="66d24-122">-Display Error</span><span class="sxs-lookup"><span data-stu-id="66d24-122">-DisplayError</span></span>

<span data-ttu-id="66d24-123">Zeigt Fehler in der Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="66d24-123">Displays errors at the command line.</span></span> <span data-ttu-id="66d24-124">Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Custom` und die Ausdrücke nicht zu funktionieren scheinen.</span><span class="sxs-lookup"><span data-stu-id="66d24-124">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="66d24-125">-Erweitern</span><span class="sxs-lookup"><span data-stu-id="66d24-125">-Expand</span></span>

<span data-ttu-id="66d24-126">Formatiert das Auflistungsobjekt und die Objekte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="66d24-126">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="66d24-127">Dieser Parameter dient zum Formatieren von Objekten, die die **System. Collections. ICollection** -Schnittstelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="66d24-127">This parameter is designed to format objects that support the **System.Collections.ICollection** interface.</span></span> <span data-ttu-id="66d24-128">Der Standardwert ist " **enumonly**".</span><span class="sxs-lookup"><span data-stu-id="66d24-128">The default value is **EnumOnly**.</span></span>

<span data-ttu-id="66d24-129">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="66d24-129">Valid values are:</span></span>

- <span data-ttu-id="66d24-130">Enumonly: zeigt die Eigenschaften der Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="66d24-130">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="66d24-131">Coreonly: zeigt die Eigenschaften des Auflistungs Objekts an.</span><span class="sxs-lookup"><span data-stu-id="66d24-131">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="66d24-132">Beides: zeigt die Eigenschaften des Auflistungs Objekts und die Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="66d24-132">Both: Displays the properties of the collection object and the objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: EnumOnly
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d24-133">-Force</span><span class="sxs-lookup"><span data-stu-id="66d24-133">-Force</span></span>

<span data-ttu-id="66d24-134">Weist das Cmdlet an, alle Fehlerinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="66d24-134">Directs the cmdlet to display all of the error information.</span></span> <span data-ttu-id="66d24-135">Verwenden Sie mit den Parametern **displayerror** oder **ShowError** .</span><span class="sxs-lookup"><span data-stu-id="66d24-135">Use with the **DisplayError** or **ShowError** parameters.</span></span> <span data-ttu-id="66d24-136">Wenn ein Fehlerobjekt in die Fehler- oder Anzeigedatenströme geschrieben wird, werden standardmäßig nur einige der Fehlerinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="66d24-136">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="66d24-137">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="66d24-137">-GroupBy</span></span>

<span data-ttu-id="66d24-138">Formatiert die Ausgabe basierend auf einer freigegebenen Eigenschaft bzw. einem freigegebenen Wert in Gruppen.</span><span class="sxs-lookup"><span data-stu-id="66d24-138">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="66d24-139">Geben Sie einen Ausdruck oder eine Eigenschaft der Ausgabe ein.</span><span class="sxs-lookup"><span data-stu-id="66d24-139">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="66d24-140">Der Wert des **GroupBy** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="66d24-140">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="66d24-141">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="66d24-141">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="66d24-142">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="66d24-142">Valid key-value pairs are:</span></span>

- <span data-ttu-id="66d24-143">Name (oder Bezeichnung)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="66d24-143">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="66d24-144">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="66d24-144">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="66d24-145">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="66d24-145">FormatString - `<string>`</span></span>

<span data-ttu-id="66d24-146">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="66d24-146">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d24-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="66d24-147">-InputObject</span></span>

<span data-ttu-id="66d24-148">Gibt die zu formatierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="66d24-148">Specifies the objects to be formatted.</span></span> <span data-ttu-id="66d24-149">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="66d24-149">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="66d24-150">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="66d24-150">-Property</span></span>

<span data-ttu-id="66d24-151">Gibt die in der Anzeige angezeigten Objekteigenschaften und die Reihenfolge an, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="66d24-151">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="66d24-152">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="66d24-152">Wildcards are permitted.</span></span>

<span data-ttu-id="66d24-153">Wenn Sie diesen Parameter weglassen, hängen die in der Anzeige dargestellten Eigenschaften von dem angezeigten Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="66d24-153">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="66d24-154">Die Parameter Name- **Eigenschaft** ist optional.</span><span class="sxs-lookup"><span data-stu-id="66d24-154">The parameter name **Property** is optional.</span></span> <span data-ttu-id="66d24-155">Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="66d24-155">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="66d24-156">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="66d24-156">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="66d24-157">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="66d24-157">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="66d24-158">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="66d24-158">Valid key-value pairs are:</span></span>

- <span data-ttu-id="66d24-159">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="66d24-159">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="66d24-160">Eingeh `<int32>`</span><span class="sxs-lookup"><span data-stu-id="66d24-160">Depth - `<int32>`</span></span>

<span data-ttu-id="66d24-161">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="66d24-161">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="66d24-162">-ShowError</span><span class="sxs-lookup"><span data-stu-id="66d24-162">-ShowError</span></span>

<span data-ttu-id="66d24-163">Sendet Fehler über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="66d24-163">Sends errors through the pipeline.</span></span> <span data-ttu-id="66d24-164">Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Custom` und die Ausdrücke nicht zu funktionieren scheinen.</span><span class="sxs-lookup"><span data-stu-id="66d24-164">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="66d24-165">-Ansicht</span><span class="sxs-lookup"><span data-stu-id="66d24-165">-View</span></span>

<span data-ttu-id="66d24-166">Gibt den Namen eines alternativen Formats oder einer alternativen Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="66d24-166">Specifies the name of an alternate format or view.</span></span> <span data-ttu-id="66d24-167">Wenn Sie diesen Parameter weglassen, wird von `Format-Custom` eine standardmäßige benutzerdefinierte Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="66d24-167">If you omit this parameter, `Format-Custom` uses a default custom view.</span></span> <span data-ttu-id="66d24-168">Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="66d24-168">You cannot use the **Property** and **View** parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d24-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="66d24-169">CommonParameters</span></span>

<span data-ttu-id="66d24-170">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="66d24-170">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66d24-171">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="66d24-171">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="66d24-172">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="66d24-172">INPUTS</span></span>

### <span data-ttu-id="66d24-173">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="66d24-173">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="66d24-174">Sie können jedes beliebige Objekt an die Pipeline übergeben `Format-Custom` .</span><span class="sxs-lookup"><span data-stu-id="66d24-174">You can pipe any object to `Format-Custom`.</span></span>

## <span data-ttu-id="66d24-175">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="66d24-175">OUTPUTS</span></span>

### <span data-ttu-id="66d24-176">Microsoft. PowerShell. Commands. Internal. Format</span><span class="sxs-lookup"><span data-stu-id="66d24-176">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="66d24-177">`Format-Custom` Gibt die Format Objekte zurück, die die Anzeige darstellen.</span><span class="sxs-lookup"><span data-stu-id="66d24-177">`Format-Custom` returns the format objects that represent the display.</span></span>

## <span data-ttu-id="66d24-178">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="66d24-178">NOTES</span></span>

<span data-ttu-id="66d24-179">`Format-Custom` dient zum Anzeigen von Sichten, bei denen es sich nicht nur um Tabellen oder nur Listen handelt.</span><span class="sxs-lookup"><span data-stu-id="66d24-179">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="66d24-180">Um eine Alternative Tabellenansicht anzuzeigen, verwenden Sie `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="66d24-180">To display an alternate table view, use `Format-Table`.</span></span> <span data-ttu-id="66d24-181">Um eine Alternative Listenansicht anzuzeigen, verwenden Sie `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="66d24-181">To display an alternate list view, use `Format-List`.</span></span>

<span data-ttu-id="66d24-182">Sie können auch auf den `Format-Custom` integrierten Alias verweisen `fc` .</span><span class="sxs-lookup"><span data-stu-id="66d24-182">You can also refer to `Format-Custom` by its built-in alias, `fc`.</span></span> <span data-ttu-id="66d24-183">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="66d24-183">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="66d24-184">Beim **GroupBy** -Parameter wird davon ausgegangen, dass die Objekte sortiert sind.</span><span class="sxs-lookup"><span data-stu-id="66d24-184">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="66d24-185">Vor `Format-Custom` der Verwendung von zum Gruppieren der Objekte verwenden `Sort-Object` Sie, um diese zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="66d24-185">Before using `Format-Custom` to group the objects, use `Sort-Object` to sort them.</span></span>

## <span data-ttu-id="66d24-186">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="66d24-186">RELATED LINKS</span></span>

[<span data-ttu-id="66d24-187">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="66d24-187">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="66d24-188">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="66d24-188">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="66d24-189">Format-List</span><span class="sxs-lookup"><span data-stu-id="66d24-189">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="66d24-190">Format-Table</span><span class="sxs-lookup"><span data-stu-id="66d24-190">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="66d24-191">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="66d24-191">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="66d24-192">Get-Process</span><span class="sxs-lookup"><span data-stu-id="66d24-192">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
