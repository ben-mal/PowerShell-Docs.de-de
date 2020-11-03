---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/19/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-list?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-List
ms.openlocfilehash: 6433eb5298097345d49e3e9a58e29bc299837f07
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219356"
---
# <span data-ttu-id="f50ef-103">Format-List</span><span class="sxs-lookup"><span data-stu-id="f50ef-103">Format-List</span></span>

## <span data-ttu-id="f50ef-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f50ef-104">SYNOPSIS</span></span>
<span data-ttu-id="f50ef-105">Formatiert die Ausgabe als eine Liste der Eigenschaften, in der jede Eigenschaft in einer neuen Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f50ef-105">Formats the output as a list of properties in which each property appears on a new line.</span></span>

## <span data-ttu-id="f50ef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f50ef-106">SYNTAX</span></span>

```
Format-List [[-Property] <Object[]>] [-GroupBy <Object>] [-View <string>] [-ShowError]
[-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>] [<CommonParameters>]
```

## <span data-ttu-id="f50ef-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f50ef-107">DESCRIPTION</span></span>

<span data-ttu-id="f50ef-108">Das- `Format-List` Cmdlet formatiert die Ausgabe eines Befehls als eine Liste von Eigenschaften, in der jede Eigenschaft in einer eigenen Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f50ef-108">The `Format-List` cmdlet formats the output of a command as a list of properties in which each property is displayed on a separate line.</span></span> <span data-ttu-id="f50ef-109">Sie können `Format-List` zum Formatieren und Anzeigen aller oder ausgewählter Eigenschaften eines Objekts als Liste verwenden (Format-List \*).</span><span class="sxs-lookup"><span data-stu-id="f50ef-109">You can use `Format-List` to format and display all or selected properties of an object as a list (format-list \*).</span></span>

<span data-ttu-id="f50ef-110">Da für jedes Element in einer Liste mehr Platz als in einer Tabelle verfügbar ist, zeigt PowerShell mehr Eigenschaften des Objekts in der Liste an, und die Eigenschaftswerte werden weniger wahrscheinlich abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="f50ef-110">Because more space is available for each item in a list than in a table, PowerShell displays more properties of the object in the list, and the property values are less likely to be truncated.</span></span>

## <span data-ttu-id="f50ef-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f50ef-111">EXAMPLES</span></span>

### <span data-ttu-id="f50ef-112">Beispiel 1: Formatieren von Computerdiensten</span><span class="sxs-lookup"><span data-stu-id="f50ef-112">Example 1: Format computer services</span></span>

```powershell
Get-Service | Format-List
```

<span data-ttu-id="f50ef-113">Dieser Befehl formatiert Informationen zu Diensten auf dem Computer als Liste.</span><span class="sxs-lookup"><span data-stu-id="f50ef-113">This command formats information about services on the computer as a list.</span></span> <span data-ttu-id="f50ef-114">Standardmäßig sind die Dienste als Tabelle formatiert.</span><span class="sxs-lookup"><span data-stu-id="f50ef-114">By default, the services are formatted as a table.</span></span> <span data-ttu-id="f50ef-115">Mit dem- `Get-Service` Cmdlet werden die Objekte abgerufen, die die Dienste auf dem Computer darstellen.</span><span class="sxs-lookup"><span data-stu-id="f50ef-115">The `Get-Service` cmdlet gets objects representing the services on the computer.</span></span> <span data-ttu-id="f50ef-116">Der Pipeline Operator (|) übergibt die Ergebnisse über die Pipeline an `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="f50ef-116">The pipeline operator (|) passes the results through the pipeline to `Format-List`.</span></span>
<span data-ttu-id="f50ef-117">Anschließend `Format-List` formatiert der Befehl die Dienst Informationen in einer Liste und sendet Sie an das Standardausgabe-Cmdlet für die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="f50ef-117">Then, the `Format-List` command formats the service information in a list and sends it to the default output cmdlet for display.</span></span>

### <span data-ttu-id="f50ef-118">Beispiel 2: Formatieren von PS1XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="f50ef-118">Example 2: Format PS1XML files</span></span>

<span data-ttu-id="f50ef-119">Diese Befehle zeigen Informationen zu den PS1XML-Dateien im PowerShell-Verzeichnis als Liste an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-119">These commands display information about the PS1XML files in the PowerShell directory as a list.</span></span>

```powershell
$A = Get-ChildItem $pshome\*.ps1xml
Format-List -InputObject $A
```

<span data-ttu-id="f50ef-120">Der erste Befehl ruft die Objekte ab, die die Dateien darstellen, und speichert Sie in der `$A` Variablen.</span><span class="sxs-lookup"><span data-stu-id="f50ef-120">The first command gets the objects representing the files and stores them in the `$A` variable.</span></span>

<span data-ttu-id="f50ef-121">Der zweite Befehl verwendet `Format-List` , um Informationen zu Objekten zu formatieren, die in gespeichert sind `$A` .</span><span class="sxs-lookup"><span data-stu-id="f50ef-121">The second command uses `Format-List` to format information about objects stored in `$A`.</span></span> <span data-ttu-id="f50ef-122">Dieser Befehl verwendet den **Inputobject** -Parameter, um die Variable an zu übergeben `Format-List` , die dann die formatierte Ausgabe zur Anzeige an das Standardausgabe-Cmdlet sendet.</span><span class="sxs-lookup"><span data-stu-id="f50ef-122">This command uses the **InputObject** parameter to pass the variable to `Format-List`, which then sends the formatted output to the default output cmdlet for display.</span></span>

### <span data-ttu-id="f50ef-123">Beispiel 3: Formatieren von Prozess Eigenschaften nach Name</span><span class="sxs-lookup"><span data-stu-id="f50ef-123">Example 3: Format process properties by name</span></span>

<span data-ttu-id="f50ef-124">Dieser Befehl zeigt Name, Basispriorität und Prioritätsklasse für jeden Prozess auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-124">This command displays the name, base priority, and priority class of each process on the computer.</span></span>

```powershell
Get-Process | Format-List -Property name, basepriority, priorityclass
```

<span data-ttu-id="f50ef-125">Er verwendet das `Get-Process` Cmdlet, um ein Objekt zu erhalten, das jeden Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="f50ef-125">It uses the `Get-Process` cmdlet to get an object representing each process.</span></span> <span data-ttu-id="f50ef-126">Der Pipeline Operator (|) übergibt die Prozess Objekte über die Pipeline an `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="f50ef-126">The pipeline operator (|) passes the process objects through the pipeline to `Format-List`.</span></span> <span data-ttu-id="f50ef-127">`Format-List` formatiert die Prozesse als eine Liste mit den angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f50ef-127">`Format-List` formats the processes as a list of the specified properties.</span></span> <span data-ttu-id="f50ef-128">Der *Eigenschafts* Parameter Name ist optional, daher können Sie ihn weglassen.</span><span class="sxs-lookup"><span data-stu-id="f50ef-128">The *Property* parameter name is optional, so you can omit it.</span></span>

### <span data-ttu-id="f50ef-129">Beispiel 4: Formatieren aller Eigenschaften für einen Prozess</span><span class="sxs-lookup"><span data-stu-id="f50ef-129">Example 4: Format all properties for a process</span></span>

<span data-ttu-id="f50ef-130">Dieser Befehl zeigt alle Eigenschaften des Winlogon-Prozesses an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-130">This command displays all of the properties of the Winlogon process.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="f50ef-131">Er verwendet das Get-Process-Cmdlet zum Abrufen eines Objekts, das den Winlogon-Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="f50ef-131">It uses the Get-Process cmdlet to get an object representing the Winlogon process.</span></span> <span data-ttu-id="f50ef-132">Der Pipeline Operator (|) übergibt das Winlogon-Prozess Objekt über die Pipeline an `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="f50ef-132">The pipeline operator (|) passes the Winlogon process object through the pipeline to `Format-List`.</span></span> <span data-ttu-id="f50ef-133">Der Befehl verwendet den *Property* -Parameter, um die Eigenschaften und anzugeben \* , um alle Eigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f50ef-133">The command uses the *Property* parameter to specify the properties and the \* to indicate all properties.</span></span>
<span data-ttu-id="f50ef-134">Da der Name des *Property* -Parameters optional ist, können Sie ihn weglassen und den Befehl als eingeben `Format-List *` .</span><span class="sxs-lookup"><span data-stu-id="f50ef-134">Because the name of the *Property* parameter is optional, you can omit it and type the command as `Format-List *`.</span></span> <span data-ttu-id="f50ef-135">`Format-List` sendet die Ergebnisse automatisch an das Standardausgabe-Cmdlet für die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="f50ef-135">`Format-List` automatically sends the results to the default output cmdlet for display.</span></span>

### <span data-ttu-id="f50ef-136">Beispiel 5: Problembehandlung bei Format Fehlern</span><span class="sxs-lookup"><span data-stu-id="f50ef-136">Example 5: Troubleshooting format errors</span></span>

<span data-ttu-id="f50ef-137">Die folgenden Beispiele zeigen die Ergebnisse des Hinzufügens der **displayerror** -oder **ShowError** -Parameter mit einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f50ef-137">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -DisplayError

DayOfWeek    : Friday
 $_ / $null  : #ERR

PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -ShowError

DayOfWeek    : Friday
 $_ / $null  :

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 7:59:23 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="f50ef-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f50ef-138">PARAMETERS</span></span>

### <span data-ttu-id="f50ef-139">-Display Error</span><span class="sxs-lookup"><span data-stu-id="f50ef-139">-DisplayError</span></span>

<span data-ttu-id="f50ef-140">Gibt an, dass dieses Cmdlet Fehler in der Befehlszeile anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f50ef-140">Indicates that this cmdlet displays errors at the command line.</span></span> <span data-ttu-id="f50ef-141">Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-List` und die Ausdrücke nicht zu funktionieren scheinen.</span><span class="sxs-lookup"><span data-stu-id="f50ef-141">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="f50ef-142">-Erweitern</span><span class="sxs-lookup"><span data-stu-id="f50ef-142">-Expand</span></span>

<span data-ttu-id="f50ef-143">Gibt das formatierte Auflistungs Objekt sowie die Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-143">Specifies the formatted collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="f50ef-144">Dieser Parameter dient zum Formatieren der Objekte, die die ICollection (System.Collections)-Schnittstelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f50ef-144">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="f50ef-145">Der Standardwert ist „EnumOnly“.</span><span class="sxs-lookup"><span data-stu-id="f50ef-145">The default value is EnumOnly.</span></span> <span data-ttu-id="f50ef-146">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="f50ef-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f50ef-147">"Enumonly".</span><span class="sxs-lookup"><span data-stu-id="f50ef-147">EnumOnly.</span></span> <span data-ttu-id="f50ef-148">Zeigt die Eigenschaften der Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-148">Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="f50ef-149">Nur coreonly.</span><span class="sxs-lookup"><span data-stu-id="f50ef-149">CoreOnly.</span></span> <span data-ttu-id="f50ef-150">Zeigt die Eigenschaften des Auflistungsobjekts an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-150">Displays the properties of the collection object.</span></span>
- <span data-ttu-id="f50ef-151">Both (Beides):</span><span class="sxs-lookup"><span data-stu-id="f50ef-151">Both.</span></span> <span data-ttu-id="f50ef-152">Zeigt die Eigenschaften des Auflistungsobjekts und die Eigenschaften von Objekten in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-152">Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f50ef-153">-Force</span><span class="sxs-lookup"><span data-stu-id="f50ef-153">-Force</span></span>

<span data-ttu-id="f50ef-154">Gibt an, dass dieses Cmdlet alle Fehlerinformationen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f50ef-154">Indicates that this cmdlet displays all of the error information.</span></span> <span data-ttu-id="f50ef-155">Verwenden Sie mit dem **Display Error** -Parameter oder **ShowError** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="f50ef-155">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="f50ef-156">Wenn ein Fehlerobjekt in die Fehler- oder Anzeigedatenströme geschrieben wird, werden standardmäßig nur einige der Fehlerinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f50ef-156">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="f50ef-157">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="f50ef-157">-GroupBy</span></span>

<span data-ttu-id="f50ef-158">Gibt die Ausgabe in Gruppen basierend auf einer freigegebenen Eigenschaft oder einem freigegebenen Wert an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-158">Specifies the output in groups based on a shared property or value.</span></span> <span data-ttu-id="f50ef-159">Geben Sie einen Ausdruck oder eine Eigenschaft der Ausgabe ein.</span><span class="sxs-lookup"><span data-stu-id="f50ef-159">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="f50ef-160">Der Wert des **GroupBy** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="f50ef-160">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="f50ef-161">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="f50ef-161">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="f50ef-162">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="f50ef-162">Valid key-value pairs are:</span></span>

- <span data-ttu-id="f50ef-163">Name (oder Bezeichnung)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="f50ef-163">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="f50ef-164">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="f50ef-164">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="f50ef-165">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="f50ef-165">FormatString - `<string>`</span></span>

<span data-ttu-id="f50ef-166">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="f50ef-166">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="f50ef-167">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f50ef-167">-InputObject</span></span>

<span data-ttu-id="f50ef-168">Gibt die zu formatierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-168">Specifies the objects to be formatted.</span></span> <span data-ttu-id="f50ef-169">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f50ef-169">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="f50ef-170">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="f50ef-170">-Property</span></span>

<span data-ttu-id="f50ef-171">Gibt die in der Anzeige angezeigten Objekteigenschaften und die Reihenfolge an, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f50ef-171">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="f50ef-172">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f50ef-172">Wildcards are permitted.</span></span>

<span data-ttu-id="f50ef-173">Wenn Sie diesen Parameter weglassen, hängen die in der Anzeige dargestellten Eigenschaften von dem angezeigten Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="f50ef-173">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="f50ef-174">Der Parameter Name "Property" ist optional.</span><span class="sxs-lookup"><span data-stu-id="f50ef-174">The parameter name "Property" is optional.</span></span> <span data-ttu-id="f50ef-175">Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="f50ef-175">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="f50ef-176">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="f50ef-176">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="f50ef-177">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="f50ef-177">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="f50ef-178">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="f50ef-178">Valid key-value pairs are:</span></span>

- <span data-ttu-id="f50ef-179">Name (oder Bezeichnung)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="f50ef-179">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="f50ef-180">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="f50ef-180">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="f50ef-181">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="f50ef-181">FormatString - `<string>`</span></span>

<span data-ttu-id="f50ef-182">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="f50ef-182">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="f50ef-183">-ShowError</span><span class="sxs-lookup"><span data-stu-id="f50ef-183">-ShowError</span></span>

<span data-ttu-id="f50ef-184">Gibt an, dass das Cmdlet Fehler über die Pipeline sendet.</span><span class="sxs-lookup"><span data-stu-id="f50ef-184">Indicates that the cmdlet sends errors through the pipeline.</span></span> <span data-ttu-id="f50ef-185">Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-List` und die Ausdrücke nicht zu funktionieren scheinen.</span><span class="sxs-lookup"><span data-stu-id="f50ef-185">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="f50ef-186">-Ansicht</span><span class="sxs-lookup"><span data-stu-id="f50ef-186">-View</span></span>

<span data-ttu-id="f50ef-187">Gibt den Namen eines alternativen Listen Formats oder einer anderen Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-187">Specifies the name of an alternate list format or view.</span></span> <span data-ttu-id="f50ef-188">Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="f50ef-188">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="f50ef-189">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f50ef-189">CommonParameters</span></span>

<span data-ttu-id="f50ef-190">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f50ef-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f50ef-191">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f50ef-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f50ef-192">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f50ef-192">INPUTS</span></span>

### <span data-ttu-id="f50ef-193">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="f50ef-193">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="f50ef-194">Sie können jedes beliebige Objekt an die Pipeline übergeben `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="f50ef-194">You can pipe any object to `Format-List`.</span></span>

## <span data-ttu-id="f50ef-195">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f50ef-195">OUTPUTS</span></span>

### <span data-ttu-id="f50ef-196">Microsoft. PowerShell. Commands. Internal. Format</span><span class="sxs-lookup"><span data-stu-id="f50ef-196">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="f50ef-197">`Format-List` Gibt die Format Objekte zurück, die die Liste darstellen.</span><span class="sxs-lookup"><span data-stu-id="f50ef-197">`Format-List` returns the format objects that represent the list.</span></span>

## <span data-ttu-id="f50ef-198">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f50ef-198">NOTES</span></span>

<span data-ttu-id="f50ef-199">Sie können auch über den integrierten Alias FL auf Format-List verweisen.</span><span class="sxs-lookup"><span data-stu-id="f50ef-199">You can also refer to Format-List by its built-in alias, FL.</span></span> <span data-ttu-id="f50ef-200">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="f50ef-200">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="f50ef-201">Die Format-Cmdlets, wie z `Format-List` . b., ordnen die anzuzeigenden Daten an, zeigen Sie aber nicht an.</span><span class="sxs-lookup"><span data-stu-id="f50ef-201">The format cmdlets, such as `Format-List`, arrange the data to be displayed but do not display it.</span></span>
<span data-ttu-id="f50ef-202">Die Daten werden durch die Ausgabe Features von PowerShell und durch die Cmdlets angezeigt, die das out-Verb (die Out-Cmdlets) enthalten, z `Out-Host` `Out-File` . b. oder.</span><span class="sxs-lookup"><span data-stu-id="f50ef-202">The data is displayed by the output features of PowerShell and by the cmdlets that contain the Out verb (the Out cmdlets), such as `Out-Host` or `Out-File`.</span></span>

<span data-ttu-id="f50ef-203">Wenn Sie kein Format-Cmdlet verwenden, wendet PowerShell dieses Standardformat auf jedes Objekt an, das angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f50ef-203">If you do not use a format cmdlet, PowerShell applies that default format for each object that it displays.</span></span>

<span data-ttu-id="f50ef-204">Beim **GroupBy** -Parameter wird davon ausgegangen, dass die Objekte sortiert sind.</span><span class="sxs-lookup"><span data-stu-id="f50ef-204">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="f50ef-205">Verwenden Sie Sort-Object, bevor Sie `Format-List` zum Gruppieren der Objekte verwenden.</span><span class="sxs-lookup"><span data-stu-id="f50ef-205">Use Sort-Object before using `Format-List` to group the objects.</span></span>

<span data-ttu-id="f50ef-206">Mit dem **View** -Parameter können Sie ein alternatives Format für die Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="f50ef-206">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="f50ef-207">Sie können die in den `*.format.PS1XML` Dateien im PowerShell-Verzeichnis definierten Ansichten verwenden oder Ihre eigenen Ansichten in neuen PS1XML-Dateien erstellen und das Cmdlet "Update-FormatData" verwenden, um Sie in PowerShell einzubinden.</span><span class="sxs-lookup"><span data-stu-id="f50ef-207">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory, or you can create your own views in new PS1XML files and use the Update-FormatData cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="f50ef-208">Die Alternative Ansicht für den **View** -Parameter muss das Listenformat verwenden. andernfalls schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="f50ef-208">The alternate view for the **View** parameter must use the list format, otherwise, the command fails.</span></span> <span data-ttu-id="f50ef-209">Wenn die Alternative Ansicht eine Tabelle ist, verwenden Sie `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="f50ef-209">If the alternate view is a table, use `Format-Table`.</span></span> <span data-ttu-id="f50ef-210">Wenn die Alternative Ansicht weder eine Liste noch eine Tabelle ist, verwenden Sie `Format-Custom` .</span><span class="sxs-lookup"><span data-stu-id="f50ef-210">If the alternate view is not a list or a table, use `Format-Custom`.</span></span>

## <span data-ttu-id="f50ef-211">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f50ef-211">RELATED LINKS</span></span>

[<span data-ttu-id="f50ef-212">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="f50ef-212">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="f50ef-213">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="f50ef-213">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="f50ef-214">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="f50ef-214">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="f50ef-215">Format-Table</span><span class="sxs-lookup"><span data-stu-id="f50ef-215">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="f50ef-216">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="f50ef-216">Format-Wide</span></span>](Format-Wide.md)
