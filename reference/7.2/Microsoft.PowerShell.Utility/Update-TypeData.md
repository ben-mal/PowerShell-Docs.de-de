---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-typedata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-TypeData
ms.openlocfilehash: 1314d388bff5a46bcf335f3da7908a65233aa46e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603126"
---
# <span data-ttu-id="7d406-102">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="7d406-102">Update-TypeData</span></span>

## <span data-ttu-id="7d406-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="7d406-103">Synopsis</span></span>
<span data-ttu-id="7d406-104">Aktualisiert die erweiterten Typdaten in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7d406-104">Updates the extended type data in the session.</span></span>

## <span data-ttu-id="7d406-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d406-105">Syntax</span></span>

### <span data-ttu-id="7d406-106">Fileset (Standard)</span><span class="sxs-lookup"><span data-stu-id="7d406-106">FileSet (Default)</span></span>

```
Update-TypeData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="7d406-107">Dynamictypeset</span><span class="sxs-lookup"><span data-stu-id="7d406-107">DynamicTypeSet</span></span>

```
Update-TypeData [-MemberType <PSMemberTypes>] [-MemberName <String>] [-Value <Object>]
 [-SecondValue <Object>] [-TypeConverter <Type>] [-TypeAdapter <Type>]
 [-SerializationMethod <String>] [-TargetTypeForDeserialization <Type>]
 [-SerializationDepth <Int32>] [-DefaultDisplayProperty <String>]
 [-InheritPropertySerializationSet <Nullable`1>] [-StringSerializationSource <String>]
 [-DefaultDisplayPropertySet <String[]>] [-DefaultKeyPropertySet <String[]>]
 [-PropertySerializationSet <String[]>] -TypeName <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="7d406-108">Typedataset</span><span class="sxs-lookup"><span data-stu-id="7d406-108">TypeDataSet</span></span>

```
Update-TypeData [-Force] [-TypeData] <TypeData[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7d406-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7d406-109">Description</span></span>

<span data-ttu-id="7d406-110">`Update-TypeData`Mit dem-Cmdlet werden die erweiterten Typdaten in der Sitzung aktualisiert, indem die Dateien erneut in den Arbeits `Types.ps1xml` Speicher geladen und neue erweiterte Typdaten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-110">The `Update-TypeData` cmdlet updates the extended type data in the session by reloading the `Types.ps1xml` files into memory and adding new extended type data.</span></span>

<span data-ttu-id="7d406-111">Standardmäßig lädt PowerShell erweiterte Typdaten nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="7d406-111">By default, PowerShell loads extended type data as it is needed.</span></span> <span data-ttu-id="7d406-112">Ohne Parameter `Update-TypeData` lädt alle Dateien, die Sie `Types.ps1xml` in die Sitzung geladen hat, einschließlich aller von Ihnen hinzugefügten Typdateien neu.</span><span class="sxs-lookup"><span data-stu-id="7d406-112">Without parameters, `Update-TypeData` reloads all of the `Types.ps1xml` files that it has loaded in the session, including any type files that you added.</span></span> <span data-ttu-id="7d406-113">Sie können die Parameter von verwenden `Update-TypeData` , um neue Typdateien hinzuzufügen und erweiterte Typdaten hinzuzufügen und zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="7d406-113">You can use the parameters of `Update-TypeData` to add new type files and add and replace extended type data.</span></span>

<span data-ttu-id="7d406-114">Das- `Update-TypeData` Cmdlet kann verwendet werden, um alle Typdaten vorab zu laden.</span><span class="sxs-lookup"><span data-stu-id="7d406-114">The `Update-TypeData` cmdlet can be used to preload all type data.</span></span> <span data-ttu-id="7d406-115">Diese Funktion ist besonders nützlich, wenn Sie Typen entwickeln und diese neuen Typen zu Testzwecken laden möchten.</span><span class="sxs-lookup"><span data-stu-id="7d406-115">This feature is particularly useful when you are developing types and want to load those new types for testing purposes.</span></span>

<span data-ttu-id="7d406-116">Ab Windows PowerShell 3,0 können Sie verwenden, `Update-TypeData` um erweiterte Typdaten in der Sitzung hinzuzufügen und zu ersetzen, ohne eine Datei zu verwenden `Types.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="7d406-116">Beginning in Windows PowerShell 3.0, you can use `Update-TypeData` to add and replace extended type data in the session without using a `Types.ps1xml` file.</span></span> <span data-ttu-id="7d406-117">Typdaten die dynamisch, d. h. ohne Datei, hinzugefügt werden, werden nur zur aktuellen Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7d406-117">Type data that is added dynamically, that is, without a file, is added only to the current session.</span></span> <span data-ttu-id="7d406-118">Fügen Sie Ihrem PowerShell-Profil einen Befehl hinzu, um die Typdaten zu allen Sitzungen hinzuzufügen `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7d406-118">To add the type data to all sessions, add an `Update-TypeData` command to your PowerShell profile.</span></span> <span data-ttu-id="7d406-119">Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7d406-119">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="7d406-120">Außerdem können Sie ab Windows PowerShell 3,0 das `Get-TypeData` Cmdlet verwenden, um die erweiterten Typen in der aktuellen Sitzung zu erhalten, und das `Remove-TypeData` Cmdlet, um erweiterte Typen aus der aktuellen Sitzung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="7d406-120">Also, beginning in Windows PowerShell 3.0, you can use the `Get-TypeData` cmdlet to get the extended types in the current session and the `Remove-TypeData` cmdlet to delete extended types from the current session.</span></span>

<span data-ttu-id="7d406-121">Ausnahmen, die in Eigenschaften auftreten, oder das Hinzufügen von Eigenschaften zu einem `Update-TypeData` Befehl, melden keine Fehler.</span><span class="sxs-lookup"><span data-stu-id="7d406-121">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors.</span></span> <span data-ttu-id="7d406-122">Dadurch werden Ausnahmen unterdrückt, die während der Formatierung und Ausgabe in vielen gängigen Typen auftreten würden.</span><span class="sxs-lookup"><span data-stu-id="7d406-122">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="7d406-123">Wenn Sie .net-Eigenschaften erhalten, können Sie die Unterdrückung von Ausnahmen umgehen, indem Sie stattdessen die Methoden Syntax verwenden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7d406-123">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

`"hello".get_Length()`

<span data-ttu-id="7d406-124">Beachten Sie, dass die Methoden Syntax nur mit .net-Eigenschaften verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d406-124">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="7d406-125">Eigenschaften, die durch das Ausführen des `Update-TypeData` Cmdlets hinzugefügt werden, können keine Methoden Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d406-125">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

<span data-ttu-id="7d406-126">Weitere Informationen zu den `Types.ps1xml` Dateien in PowerShell finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="7d406-126">For more information about the `Types.ps1xml` files in PowerShell, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

## <span data-ttu-id="7d406-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7d406-127">Examples</span></span>

### <span data-ttu-id="7d406-128">Beispiel 1: Aktualisieren erweiterter Typen</span><span class="sxs-lookup"><span data-stu-id="7d406-128">Example 1: Update extended types</span></span>

```powershell
Update-TypeData
```

<span data-ttu-id="7d406-129">Dieser Befehl aktualisiert die Konfiguration des erweiterten Typs aus den `Types.ps1xml` Dateien, die bereits in der Sitzung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="7d406-129">This command updates the extended type configuration from the `Types.ps1xml` files that have already been used in the session.</span></span>

### <span data-ttu-id="7d406-130">Beispiel 2: mehrmals Aktualisieren von Typen</span><span class="sxs-lookup"><span data-stu-id="7d406-130">Example 2: Update types multiple times</span></span>

<span data-ttu-id="7d406-131">In diesem Beispiel wird gezeigt, wie die Typen in einer Typdatei mehrmals in der gleichen Sitzung aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-131">This example shows how to update the types in a type file multiple times in the same session.</span></span>

<span data-ttu-id="7d406-132">Der erste Befehl aktualisiert die Konfiguration des erweiterten Typs aus den `Types.ps1xml` Dateien, wobei `TypesA.types.ps1xml` die `TypesB.types.ps1xml` Dateien und zuerst verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-132">The first command updates the extended type configuration from the `Types.ps1xml` files, processing the `TypesA.types.ps1xml` and `TypesB.types.ps1xml` files first.</span></span>

<span data-ttu-id="7d406-133">Der zweite Befehl zeigt, wie Sie den `TypesA.types.ps1xml` erneut aktualisieren können, z. b. Wenn Sie einen Typ in der Datei hinzugefügt oder geändert haben.</span><span class="sxs-lookup"><span data-stu-id="7d406-133">The second command shows how to update the `TypesA.types.ps1xml` again, such as you might do if you added or changed a type in the file.</span></span> <span data-ttu-id="7d406-134">Sie können entweder den vorherigen Befehl für die Datei wiederholen `TypesA.types.ps1xml` oder einen `Update-TypeData` Befehl ohne Parameter ausführen, da `TypesA.types.ps1xml` bereits in der Liste der Typdateien für die aktuelle Sitzung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7d406-134">You can either repeat the previous command for the `TypesA.types.ps1xml` file, or run an `Update-TypeData` command without parameters, because `TypesA.types.ps1xml` is already in the type file list for the current session.</span></span>

```powershell
Update-TypeData -PrependPath TypesA.types.ps1xml, TypesB.types.ps1xml
Update-TypeData -PrependPath TypesA.types.ps1xml
```

### <span data-ttu-id="7d406-135">Beispiel 3: Hinzufügen einer Skript Eigenschaft zu DateTime-Objekten</span><span class="sxs-lookup"><span data-stu-id="7d406-135">Example 3: Add a script property to DateTime objects</span></span>

<span data-ttu-id="7d406-136">In diesem Beispiel `Update-TypeData` wird verwendet, um die **Quarter** -Skript Eigenschaft zu **System. DateTime** -Objekten in der aktuellen Sitzung hinzuzufügen, z. b. die vom `Get-Date` Cmdlet zurückgegebenen.</span><span class="sxs-lookup"><span data-stu-id="7d406-136">This example uses `Update-TypeData` to add the **Quarter** script property to **System.DateTime** objects in the current session, such as those returned by the `Get-Date` cmdlet.</span></span>

```powershell
Update-TypeData -TypeName "System.DateTime" -MemberType ScriptProperty -MemberName "Quarter" -Value {
  if ($this.Month -in @(1,2,3)) {"Q1"}
  elseif ($this.Month -in @(4,5,6)) {"Q2"}
  elseif ($this.Month -in @(7,8,9)) {"Q3"}
  else {"Q4"}
}
(Get-Date).Quarter
```

```Output
Q1
```

<span data-ttu-id="7d406-137">Der `Update-TypeData` Befehl verwendet den **tykame** -Parameter, um **den System. DateTime** -Typ anzugeben, den **Mitgliedschafts Namen** Parameter, um einen Namen für die neue Eigenschaft anzugeben, die Eigenschaft " **mitgliedschaftentyp** ", um den **scriptproperty** -Typ anzugeben, und den **value** -Parameter, um das Skript anzugeben, das das jährliche Quartal bestimmt.</span><span class="sxs-lookup"><span data-stu-id="7d406-137">The `Update-TypeData` command uses the **TypeName** parameter to specify **the System.DateTime** type, the **MemberName** parameter to specify a name for the new property, the **MemberType** property to specify the **ScriptProperty** type, and the **Value** parameter to specify the script that determines the annual quarter.</span></span>

<span data-ttu-id="7d406-138">Der Wert der **Value**-Eigenschaft ist ein Skript, das das aktuelle Quartal berechnet.</span><span class="sxs-lookup"><span data-stu-id="7d406-138">The value of the **Value** property is a script that calculates the current annual quarter.</span></span> <span data-ttu-id="7d406-139">Der Skriptblock verwendet die `$this` Automatische Variable zur Darstellung der aktuellen Instanz des Objekts und den in-Operator, um zu bestimmen, ob der Monatswert in jedem ganzzahligen Array angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7d406-139">The script block uses the `$this` automatic variable to represent the current instance of the object and the In operator to determine whether the month value appears in each integer array.</span></span> <span data-ttu-id="7d406-140">Weitere Informationen zum- `-in` Operator finden Sie unter [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="7d406-140">For more information about the `-in` operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).</span></span>

<span data-ttu-id="7d406-141">Der zweite Befehl ruft die neue Quarter-Eigenschaft des aktuellen Datums ab.</span><span class="sxs-lookup"><span data-stu-id="7d406-141">The second command gets the new Quarter property of the current date.</span></span>

### <span data-ttu-id="7d406-142">Beispiel 4: Aktualisieren eines Typs, der standardmäßig in Listen angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="7d406-142">Example 4: Update a type that displays in lists by default</span></span>

<span data-ttu-id="7d406-143">In diesem Beispiel wird gezeigt, wie die Eigenschaften eines Typs festgelegt werden, der standardmäßig in Listen angezeigt wird, d. h., wenn keine Eigenschaften angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="7d406-143">This example shows how to set the properties of a type that displays in lists by default, that is, when no properties are specified.</span></span> <span data-ttu-id="7d406-144">Da die Typdaten nicht in einer Datei angegeben sind `Types.ps1xml` , sind Sie nur in der aktuellen Sitzung gültig.</span><span class="sxs-lookup"><span data-stu-id="7d406-144">Because the type data is not specified in a `Types.ps1xml` file, it is effective only in the current session.</span></span>

```powershell
Update-TypeData -TypeName "System.DateTime" -DefaultDisplayPropertySet "DateTime, DayOfYear, Quarter"
Get-Date | Format-List
```

```Output
Thursday, March 15, 2012 12:00:00 AM
DayOfYear : 75
Quarter   : Q1
```

<span data-ttu-id="7d406-145">Der erste Befehl verwendet das `Update-TypeData` Cmdlet, um die Standard Listen Eigenschaften für den **System. DateTime** -Typ festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7d406-145">The first command uses the `Update-TypeData` cmdlet to set the default list properties for the **System.DateTime** type.</span></span> <span data-ttu-id="7d406-146">Der Befehl verwendet den **TypeName**-Parameter, um den Typ anzugeben, und den **DefaultDisplayPropertySet**-Parameter, um die Standardeigenschaften für eine Liste anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7d406-146">The command uses the **TypeName** parameter to specify the type and the **DefaultDisplayPropertySet** parameter to specify the default properties for a list.</span></span> <span data-ttu-id="7d406-147">Die ausgewählten Eigenschaften enthalten die neue **Quarter** -Skript Eigenschaft, die in einem vorherigen Beispiel hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d406-147">The selected properties include the new **Quarter** script property that was added in a previous example.</span></span>

<span data-ttu-id="7d406-148">Der zweite Befehl verwendet das `Get-Date` Cmdlet, um ein **System. DateTime** -Objekt zu erhalten, das das aktuelle Datum darstellt.</span><span class="sxs-lookup"><span data-stu-id="7d406-148">The second command uses the `Get-Date` cmdlet to get a **System.DateTime** object that represents the current date.</span></span> <span data-ttu-id="7d406-149">Der Befehl verwendet einen Pipeline Operator ( `|` ), um das **DateTime** -Objekt an das `Format-List` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="7d406-149">The command uses a pipeline operator (`|`) to send the **DateTime** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="7d406-150">Da der `Format-List` Befehl nicht die Eigenschaften angibt, die in der Liste angezeigt werden sollen, verwendet PowerShell die Standardwerte, die vom Befehl festgelegt wurden `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7d406-150">Because the `Format-List` command does not specify the properties to display in the list, PowerShell uses the default values that were established by the `Update-TypeData` command.</span></span>

### <span data-ttu-id="7d406-151">Beispiel 5: Aktualisieren von Typdaten für ein weitergeleitete Objekt</span><span class="sxs-lookup"><span data-stu-id="7d406-151">Example 5: Update type data for a piped object</span></span>

```powershell
Get-Module | Update-TypeData -MemberType ScriptProperty -MemberName "SupportsUpdatableHelp" -Value {
  if ($this.HelpInfoUri) {$True} else {$False}
}
Get-Module -ListAvailable | Format-Table Name, SupportsUpdatableHelp
```

```Output
Name                             SupportsUpdatableHelp
----                             ---------------------
Microsoft.PowerShell.Diagnostics                  True
Microsoft.PowerShell.Host                         True
Microsoft.PowerShell.Management                   True
Microsoft.PowerShell.Security                     True
Microsoft.PowerShell.Utility                      True
Microsoft.WSMan.Management                        True
PSDiagnostics                                    False
PSScheduledJob                                    True
PSWorkflow                                        True
ServerManager                                     True
TroubleshootingPack                              False
```

<span data-ttu-id="7d406-152">In diesem Beispiel wird veranschaulicht, dass beim Übergeben eines Objekts an `Update-TypeData` `Update-TypeData` Erweiterte Typdaten für den Objekttyp hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="7d406-152">This example demonstrates that when you pipe an object to `Update-TypeData`, `Update-TypeData` adds extended type data for the object type.</span></span>

<span data-ttu-id="7d406-153">Diese Technik ist schneller als die Verwendung des- `Get-Member` Cmdlets oder der- `Get-Type` Methode, um den Objekttyp zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7d406-153">This technique is quicker than using the `Get-Member` cmdlet or the `Get-Type` method to get the object type.</span></span> <span data-ttu-id="7d406-154">Wenn Sie jedoch eine Auflistung von Objekten an weiterleiten `Update-TypeData` , aktualisiert Sie die Typdaten des ersten Objekt Typs und gibt dann einen Fehler für alle anderen Objekte in der Auflistung zurück, da der Member bereits für den Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7d406-154">However, if you pipe a collection of objects to `Update-TypeData`, it updates the type data of the first object type and then returns an error for all other objects in the collection because the member is already defined on the type.</span></span>

<span data-ttu-id="7d406-155">Der erste Befehl verwendet das `Get-Module` Cmdlet, um das psscheduledjob-Modul abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7d406-155">The first command uses the `Get-Module` cmdlet to get the PSScheduledJob module.</span></span> <span data-ttu-id="7d406-156">Der Befehl übergibt das Modul Objekt an das `Update-TypeData` Cmdlet, das die Typdaten für den **System. Management. Automation. psmoduleinfo** -Typ und die von ihm abgeleiteten Typen aktualisiert, wie z. b. den moduleinfogruppierung-Typ, der `Get-Module` zurückgibt, wenn Sie den **listavailable** -Parameter im Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d406-156">The command pipes the module object to the `Update-TypeData` cmdlet, which updates the type data for the **System.Management.Automation.PSModuleInfo** type and the types derived from it, such as the ModuleInfoGrouping type that `Get-Module` returns when you use the **ListAvailable** parameter in the command.</span></span>

<span data-ttu-id="7d406-157">Die `Update-TypeData` Befehle fügen der **supportsupdatablehelp** -Skript Eigenschaft alle importierten Module hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d406-157">The `Update-TypeData` commands adds the **SupportsUpdatableHelp** script property to all imported modules.</span></span> <span data-ttu-id="7d406-158">Der Wert des **value** -Parameters ist ein Skript, das zurückgibt, `$True` Wenn die **helpinfouri** -Eigenschaft des Moduls aufgefüllt ist, und `$False` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="7d406-158">The value of the **Value** parameter is a script that returns `$True` if the **HelpInfoUri** property of the module is populated and `$False` otherwise.</span></span>

<span data-ttu-id="7d406-159">Mit dem zweiten Befehl werden die Modul Objekte `Get-Module` an das `Format-Table` Cmdlet weitergeleitet, das die Eigenschaften " **Name** " und " **supportsupdatablehelp** " aller Module in einer Liste anzeigt.</span><span class="sxs-lookup"><span data-stu-id="7d406-159">The second command pipes the module objects from `Get-Module` to the `Format-Table` cmdlet, which displays the **Name** and **SupportsUpdatableHelp** properties of all modules in a list.</span></span>

## <span data-ttu-id="7d406-160">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d406-160">Parameters</span></span>

### <span data-ttu-id="7d406-161">-Appendpath</span><span class="sxs-lookup"><span data-stu-id="7d406-161">-AppendPath</span></span>

<span data-ttu-id="7d406-162">Gibt den Pfad zu optionalen `.ps1xml` Dateien an.</span><span class="sxs-lookup"><span data-stu-id="7d406-162">Specifies the path to optional `.ps1xml` files.</span></span> <span data-ttu-id="7d406-163">Die angegebenen Dateien werden in der Reihenfolge geladen, in der sie nach dem Laden der integrierten Dateien aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="7d406-163">The specified files are loaded in the order that they are listed after the built-in files are loaded.</span></span> <span data-ttu-id="7d406-164">Sie können einen **appendpath** -Wert auch über die Pipeline an senden `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7d406-164">You can also pipe an **AppendPath** value to `Update-TypeData`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-165">-Defaultdisplayproperty</span><span class="sxs-lookup"><span data-stu-id="7d406-165">-DefaultDisplayProperty</span></span>

<span data-ttu-id="7d406-166">Gibt die Eigenschaft des Typs an, der vom `Format-Wide` Cmdlet angezeigt wird, wenn keine anderen Eigenschaften angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="7d406-166">Specifies the property of the type that is displayed by the `Format-Wide` cmdlet when no other properties are specified.</span></span>

<span data-ttu-id="7d406-167">Geben Sie den Namen einer Standardeigenschaft oder erweiterten Eigenschaft des Typs ein.</span><span class="sxs-lookup"><span data-stu-id="7d406-167">Type the name of a standard or extended property of the type.</span></span> <span data-ttu-id="7d406-168">Der Wert dieses Parameters kann der Name eines Typs sein, der im selben Befehl hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7d406-168">The value of this parameter can be the name of a type that is added in the same command.</span></span>

<span data-ttu-id="7d406-169">Dieser Wert ist nur wirksam, wenn keine breiten Ansichten für den Typ in einer Datei definiert sind `Format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="7d406-169">This value is effective only when there are no wide views defined for the type in a `Format.ps1xml` file.</span></span>

<span data-ttu-id="7d406-170">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-170">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-171">-Defaultdisplaypropertyset</span><span class="sxs-lookup"><span data-stu-id="7d406-171">-DefaultDisplayPropertySet</span></span>

<span data-ttu-id="7d406-172">Gibt eine oder mehrere Eigenschaften des Typs an.</span><span class="sxs-lookup"><span data-stu-id="7d406-172">Specifies one or more properties of the type.</span></span> <span data-ttu-id="7d406-173">Diese Eigenschaften werden durch das `Format-List` Cmdlet angezeigt, wenn keine anderen Eigenschaften angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-173">These properties are displayed by the `Format-List` cmdlet when no other properties are specified.</span></span>

<span data-ttu-id="7d406-174">Geben Sie die Namen der Standardeigenschaften oder erweiterten Eigenschaften des Typs ein.</span><span class="sxs-lookup"><span data-stu-id="7d406-174">Type the names of standard or extended properties of the type.</span></span> <span data-ttu-id="7d406-175">Der Wert dieses Parameters kann der Name von Typen sein, die im selben Befehl hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-175">The value of this parameter can be the names of types that are added in the same command.</span></span>

<span data-ttu-id="7d406-176">Dieser Wert ist nur wirksam, wenn keine Listenansichten für den Typ in einer Datei definiert sind `Format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="7d406-176">This value is effective only when there are no list views defined for the type in a `Format.ps1xml` file.</span></span>

<span data-ttu-id="7d406-177">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-177">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-178">-Defaultkeypropertyset</span><span class="sxs-lookup"><span data-stu-id="7d406-178">-DefaultKeyPropertySet</span></span>

<span data-ttu-id="7d406-179">Gibt eine oder mehrere Eigenschaften des Typs an.</span><span class="sxs-lookup"><span data-stu-id="7d406-179">Specifies one or more properties of the type.</span></span> <span data-ttu-id="7d406-180">Diese Eigenschaften werden von den `Group-Object` -und- `Sort-Object` Cmdlets verwendet, wenn keine anderen Eigenschaften angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-180">These properties are used by the `Group-Object` and `Sort-Object` cmdlets when no other properties are specified.</span></span>

<span data-ttu-id="7d406-181">Geben Sie die Namen der Standardeigenschaften oder erweiterten Eigenschaften des Typs ein.</span><span class="sxs-lookup"><span data-stu-id="7d406-181">Type the names of standard or extended properties of the type.</span></span> <span data-ttu-id="7d406-182">Der Wert dieses Parameters kann der Name von Typen sein, die im selben Befehl hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-182">The value of this parameter can be the names of types that are added in the same command.</span></span>

<span data-ttu-id="7d406-183">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-183">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-184">-Force</span><span class="sxs-lookup"><span data-stu-id="7d406-184">-Force</span></span>

<span data-ttu-id="7d406-185">Gibt an, dass das Cmdlet die angegebenen Typdaten verwendet, auch wenn für diesen Typ bereits Typdaten angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="7d406-185">Indicates that the cmdlet uses the specified type data, even if type data has already been specified for that type.</span></span>

<span data-ttu-id="7d406-186">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-186">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DynamicTypeSet, TypeDataSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-187">-Vererpropertyserializationset</span><span class="sxs-lookup"><span data-stu-id="7d406-187">-InheritPropertySerializationSet</span></span>

<span data-ttu-id="7d406-188">Gibt an, ob der Satz von Eigenschaften, die serialisiert werden, geerbt wird.</span><span class="sxs-lookup"><span data-stu-id="7d406-188">Indicates whether the set of properties that are serialized is inherited.</span></span> <span data-ttu-id="7d406-189">Der Standardwert ist `$Null`.</span><span class="sxs-lookup"><span data-stu-id="7d406-189">The default value is `$Null`.</span></span> <span data-ttu-id="7d406-190">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="7d406-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7d406-191">`$True`.</span><span class="sxs-lookup"><span data-stu-id="7d406-191">`$True`.</span></span> <span data-ttu-id="7d406-192">Der Eigenschaftensatz wird geerbt.</span><span class="sxs-lookup"><span data-stu-id="7d406-192">The property set is inherited.</span></span>
- <span data-ttu-id="7d406-193">`$False`.</span><span class="sxs-lookup"><span data-stu-id="7d406-193">`$False`.</span></span> <span data-ttu-id="7d406-194">Der Eigenschaftensatz wird nicht geerbt.</span><span class="sxs-lookup"><span data-stu-id="7d406-194">The property set is not inherited.</span></span>
- <span data-ttu-id="7d406-195">`$Null`.</span><span class="sxs-lookup"><span data-stu-id="7d406-195">`$Null`.</span></span> <span data-ttu-id="7d406-196">Die Vererbung ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="7d406-196">Inheritance is not defined.</span></span>

<span data-ttu-id="7d406-197">Dieser Parameter ist nur gültig, wenn der Wert des **serializationmethod** -Parameters ist `SpecificProperties` .</span><span class="sxs-lookup"><span data-stu-id="7d406-197">This parameter is valid only when the value of the **SerializationMethod** parameter is `SpecificProperties`.</span></span> <span data-ttu-id="7d406-198">Wenn der Wert dieses Parameters ist `$False` , ist der **propertyserializationset** -Parameter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d406-198">When the value of this parameter is `$False`, the **PropertySerializationSet** parameter is required.</span></span>

<span data-ttu-id="7d406-199">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-199">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-200">-Mitgliedsname</span><span class="sxs-lookup"><span data-stu-id="7d406-200">-MemberName</span></span>

<span data-ttu-id="7d406-201">Gibt den Namen einer Eigenschaft oder Methode an.</span><span class="sxs-lookup"><span data-stu-id="7d406-201">Specifies the name of a property or method.</span></span>

<span data-ttu-id="7d406-202">Verwenden Sie diesen Parameter mit den Parametern **TypeName**, **MemberType**, **Value** und **SecondValue**, um eine Eigenschaft oder Methode eines Typs hinzuzufügen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7d406-202">Use this parameter with the **TypeName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="7d406-203">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-204">-Mitgliedstyp</span><span class="sxs-lookup"><span data-stu-id="7d406-204">-MemberType</span></span>

<span data-ttu-id="7d406-205">Gibt den Typ des Members an, der hinzugefügt oder geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7d406-205">Specifies the type of the member to add or change.</span></span>

<span data-ttu-id="7d406-206">Verwenden Sie diesen Parameter mit den Parametern **TypeName**, **MemberType**, **Value** und **SecondValue**, um eine Eigenschaft oder Methode eines Typs hinzuzufügen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7d406-206">Use this parameter with the **TypeName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span> <span data-ttu-id="7d406-207">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="7d406-207">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7d406-208">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="7d406-208">AliasProperty</span></span>
- <span data-ttu-id="7d406-209">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="7d406-209">CodeMethod</span></span>
- <span data-ttu-id="7d406-210">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="7d406-210">CodeProperty</span></span>
- <span data-ttu-id="7d406-211">NoteProperty</span><span class="sxs-lookup"><span data-stu-id="7d406-211">Noteproperty</span></span>
- <span data-ttu-id="7d406-212">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="7d406-212">ScriptMethod</span></span>
- <span data-ttu-id="7d406-213">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="7d406-213">ScriptProperty</span></span>

<span data-ttu-id="7d406-214">Weitere Informationen zu diesen Werten finden Sie unter [psmembership types-Enumeration](/dotnet/api/system.management.automation.psmembertypes).</span><span class="sxs-lookup"><span data-stu-id="7d406-214">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes).</span></span>

<span data-ttu-id="7d406-215">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: DynamicTypeSet
Aliases:
Accepted values: NoteProperty, AliasProperty, ScriptProperty, CodeProperty, ScriptMethod, CodeMethod

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-216">-Prepdpath</span><span class="sxs-lookup"><span data-stu-id="7d406-216">-PrependPath</span></span>

<span data-ttu-id="7d406-217">Gibt den Pfad zu den optionalen `.ps1xml` Dateien an.</span><span class="sxs-lookup"><span data-stu-id="7d406-217">Specifies the path to the optional `.ps1xml` files.</span></span> <span data-ttu-id="7d406-218">Die angegebenen Dateien werden in der Reihenfolge geladen, in der sie vor dem Laden der integrierten Dateien aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="7d406-218">The specified files are loaded in the order that they are listed before the built-in files are loaded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-219">-Propertyserializationset</span><span class="sxs-lookup"><span data-stu-id="7d406-219">-PropertySerializationSet</span></span>

<span data-ttu-id="7d406-220">Gibt die Namen der Eigenschaften an, die serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-220">Specifies the names of properties that are serialized.</span></span> <span data-ttu-id="7d406-221">Verwenden Sie diesen Parameter, wenn der Wert des **SerializationMethod**-Parameters **SpecificProperties** ist.</span><span class="sxs-lookup"><span data-stu-id="7d406-221">Use this parameter when the value of the **SerializationMethod** parameter is **SpecificProperties**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-222">-SecondValue</span><span class="sxs-lookup"><span data-stu-id="7d406-222">-SecondValue</span></span>

<span data-ttu-id="7d406-223">Gibt zusätzliche Werte für die Member **AliasProperty**, **ScriptProperty**, **CodeProperty** oder **CodeMethod** an.</span><span class="sxs-lookup"><span data-stu-id="7d406-223">Specifies additional values for **AliasProperty**, **ScriptProperty**, **CodeProperty**, or **CodeMethod** members.</span></span>

<span data-ttu-id="7d406-224">Verwenden Sie diesen Parameter mit den Parametern **tykame**, **Membership Type**, **value** und **SecondValue** , um eine Eigenschaft oder Methode eines Typs hinzuzufügen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7d406-224">Use this parameter with the **TypeName**, **MemberType**, **Value**, and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="7d406-225">Wenn der Wert des **Membership Type** -Parameters ist `AliasProperty` , muss der Wert des **SecondValue** -Parameters ein-Datentyp sein.</span><span class="sxs-lookup"><span data-stu-id="7d406-225">When the value of the **MemberType** parameter is `AliasProperty`, the value of the **SecondValue** parameter must be a data type.</span></span> <span data-ttu-id="7d406-226">PowerShell konvertiert (d. h. Umwandlungen) den Wert der Alias Eigenschaft in den angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="7d406-226">PowerShell converts (that is, casts) the value of the alias property to the specified type.</span></span> <span data-ttu-id="7d406-227">Wenn Sie z. b. eine Alias Eigenschaft hinzufügen, die einen alternativen Namen für eine Zeichen folgen Eigenschaft bereitstellt, können Sie auch einen **SecondValue** von **System. Int32** angeben, um den Alias-Zeichen folgen Wert in eine ganze Zahl zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7d406-227">For example, if you add an alias property that provides an alternate name for a string property, you can also specify a **SecondValue** of **System.Int32** to convert the aliased string value to an integer.</span></span>

<span data-ttu-id="7d406-228">Wenn der Wert des **Membership Type** -Parameters ist `ScriptProperty` , können Sie den **SecondValue** -Parameter verwenden, um einen zusätzlichen Skriptblock anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7d406-228">When the value of the **MemberType** parameter is `ScriptProperty`, you can use the **SecondValue** parameter to specify an additional script block.</span></span> <span data-ttu-id="7d406-229">Der Skriptblock im Wert des **Value**-Parameters ruft den Wert einer Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="7d406-229">The script block in the value of the **Value** parameter gets the value of a variable.</span></span> <span data-ttu-id="7d406-230">Der Skriptblock im Wert des **SecondValue**-Parameters legt den Wert der Variablen fest.</span><span class="sxs-lookup"><span data-stu-id="7d406-230">The script block in the value of the **SecondValue** parameter set the value of the variable.</span></span>

<span data-ttu-id="7d406-231">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-231">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-232">-Serializationtiefe</span><span class="sxs-lookup"><span data-stu-id="7d406-232">-SerializationDepth</span></span>

<span data-ttu-id="7d406-233">Gibt an, wie viele Ebenen von Objekten des Typs als Zeichenfolgen serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-233">Specifies how many levels of type objects are serialized as strings.</span></span> <span data-ttu-id="7d406-234">Der Standardwert `1` serialisiert das Objekt und seine Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7d406-234">The default value `1` serializes the object and its properties.</span></span> <span data-ttu-id="7d406-235">`0`Der Wert serialisiert das Objekt, aber nicht seine Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7d406-235">A value of `0` serializes the object, but not its properties.</span></span> <span data-ttu-id="7d406-236">`2`Der Wert serialisiert das Objekt, dessen Eigenschaften und alle Objekte in den Eigenschafts Werten.</span><span class="sxs-lookup"><span data-stu-id="7d406-236">A value of `2` serializes the object, its properties, and any objects in property values.</span></span>

<span data-ttu-id="7d406-237">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-237">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-238">-Serializationmethod</span><span class="sxs-lookup"><span data-stu-id="7d406-238">-SerializationMethod</span></span>

<span data-ttu-id="7d406-239">Gibt eine Serialisierungsmethode für den Typ an.</span><span class="sxs-lookup"><span data-stu-id="7d406-239">Specifies a serialization method for the type.</span></span> <span data-ttu-id="7d406-240">Eine Serialisierungsmethode bestimmt, welche Eigenschaften des Typs serialisiert werden und mit welchem Verfahren sie serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-240">A serialization method determines which properties of the type are serialized and the technique that is used to serialize them.</span></span> <span data-ttu-id="7d406-241">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="7d406-241">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7d406-242">`AllPublicProperties`.</span><span class="sxs-lookup"><span data-stu-id="7d406-242">`AllPublicProperties`.</span></span> <span data-ttu-id="7d406-243">Serialisieren alle öffentlichen Eigenschaften des Typs.</span><span class="sxs-lookup"><span data-stu-id="7d406-243">Serialize all public properties of the type.</span></span> <span data-ttu-id="7d406-244">Sie können den **SerializationDepth**-Parameter verwenden, um zu bestimmen, ob die untergeordneten Eigenschaften serialisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7d406-244">You can use the **SerializationDepth** parameter to determine whether child properties are serialized.</span></span>
- <span data-ttu-id="7d406-245">`String`.</span><span class="sxs-lookup"><span data-stu-id="7d406-245">`String`.</span></span> <span data-ttu-id="7d406-246">Serialisieren den Typ als eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7d406-246">Serialize the type as a string.</span></span> <span data-ttu-id="7d406-247">Sie können **StringSerializationSource** verwenden, um eine Eigenschaft des Typs anzugeben, die als das Ergebnis der Serialisierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7d406-247">You can use the **StringSerializationSource** to specify a property of the type to use as the serialization result.</span></span> <span data-ttu-id="7d406-248">Andernfalls wird der Typ mit der **ToString**-Methode des Objekts serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7d406-248">Otherwise, the type is serialized by using the **ToString** method of the object.</span></span>
- <span data-ttu-id="7d406-249">`SpecificProperties`.</span><span class="sxs-lookup"><span data-stu-id="7d406-249">`SpecificProperties`.</span></span> <span data-ttu-id="7d406-250">Serialisiert nur die angegebenen Eigenschaften dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="7d406-250">Serialize only the specified properties of this type.</span></span> <span data-ttu-id="7d406-251">Verwenden Sie den **PropertySerializationSet**-Parameter, um die Eigenschaften des Typs anzugeben, die serialisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7d406-251">Use the **PropertySerializationSet** parameter to specify the properties of the type that are serialized.</span></span>
  <span data-ttu-id="7d406-252">Sie können auch den **InheritPropertySerializationSet**-Parameter verwenden, um zu bestimmen, ob der Eigenschaftensatz geerbt werden soll, sowie den **SerializationDepth**-Parameter, um zu bestimmen, ob die untergeordneten Eigenschaften serialisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7d406-252">You can also use the **InheritPropertySerializationSet** parameter to determine whether the property set is inherited and the **SerializationDepth** parameter to determine whether child properties are serialized.</span></span>

<span data-ttu-id="7d406-253">In PowerShell werden Serialisierungsmethoden in internen **psstandardmembers** -Objekten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7d406-253">In PowerShell, serialization methods are stored in **PSStandardMembers** internal objects.</span></span>

<span data-ttu-id="7d406-254">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-254">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-255">-Stringserializationsource</span><span class="sxs-lookup"><span data-stu-id="7d406-255">-StringSerializationSource</span></span>

<span data-ttu-id="7d406-256">Gibt den Namen einer Eigenschaft des Typs an.</span><span class="sxs-lookup"><span data-stu-id="7d406-256">Specifies the name of a property of the type.</span></span> <span data-ttu-id="7d406-257">Der Wert der angegebenen Eigenschaft wird als das Ergebnis der Serialisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d406-257">The value of specified property is used as the serialization result.</span></span> <span data-ttu-id="7d406-258">Dieser Parameter ist nur gültig, wenn der Wert des **serializationmethod** -Parameters String ist.</span><span class="sxs-lookup"><span data-stu-id="7d406-258">This parameter is valid only when the value of the **SerializationMethod** parameter is String.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-259">-Targettypeer fordeserialization</span><span class="sxs-lookup"><span data-stu-id="7d406-259">-TargetTypeForDeserialization</span></span>

<span data-ttu-id="7d406-260">Gibt den Typ an, in den Objekte dieses Typs konvertiert werden, wenn sie deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d406-260">Specifies the type to which object of this type are converted when they are deserialized.</span></span>

<span data-ttu-id="7d406-261">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-262">-Typeadapter</span><span class="sxs-lookup"><span data-stu-id="7d406-262">-TypeAdapter</span></span>

<span data-ttu-id="7d406-263">Gibt den Typ eines typadapters an, z. b. **Microsoft. PowerShell. CIM. ciminstanceadapter**.</span><span class="sxs-lookup"><span data-stu-id="7d406-263">Specifies the type of a type adapter, such as **Microsoft.PowerShell.Cim.CimInstanceAdapter**.</span></span> <span data-ttu-id="7d406-264">Ein Typadapter ermöglicht es PowerShell, die Member eines Typs zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7d406-264">A type adapter enables PowerShell to get the members of a type.</span></span>

<span data-ttu-id="7d406-265">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-265">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-266">-TypeConverter</span><span class="sxs-lookup"><span data-stu-id="7d406-266">-TypeConverter</span></span>

<span data-ttu-id="7d406-267">Gibt einen Typkonverter zum Konvertieren von Werten zwischen verschiedenen Typen an.</span><span class="sxs-lookup"><span data-stu-id="7d406-267">Specifies a type converter to convert values between different types.</span></span> <span data-ttu-id="7d406-268">Wenn ein Typkonverter für einen Typ definiert ist, wird eine Instanz des Typkonverters für die Konvertierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d406-268">If a type converter is defined for a type, an instance of the type converter is used for the conversion.</span></span>

<span data-ttu-id="7d406-269">Geben Sie einen **System.Type**-Wert ein, der von den **System.ComponentModel.TypeConverter**- oder **System.Management.Automation.PSTypeConverter**-Klassen abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="7d406-269">Enter a **System.Type** value that is derived from the **System.ComponentModel.TypeConverter** or **System.Management.Automation.PSTypeConverter** classes.</span></span>

<span data-ttu-id="7d406-270">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-270">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-271">-Typedata</span><span class="sxs-lookup"><span data-stu-id="7d406-271">-TypeData</span></span>

<span data-ttu-id="7d406-272">Gibt ein Array vom Typ Daten an, das von diesem Cmdlet der Sitzung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7d406-272">Specifies an array of type data that this cmdlet adds to the session.</span></span> <span data-ttu-id="7d406-273">Geben Sie eine Variable ein, die ein **typedata** -Objekt oder einen Befehl enthält, der ein **typedata** -Objekt abruft, z `Get-TypeData` . b. einen Befehl.</span><span class="sxs-lookup"><span data-stu-id="7d406-273">Enter a variable that contains a **TypeData** object or a command that gets a **TypeData** object, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="7d406-274">Sie können ein **typedata** -Objekt auch über die Pipeline an senden `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7d406-274">You can also pipe a **TypeData** object to `Update-TypeData`.</span></span>

<span data-ttu-id="7d406-275">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-275">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.TypeData[]
Parameter Sets: TypeDataSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-276">-Typname</span><span class="sxs-lookup"><span data-stu-id="7d406-276">-TypeName</span></span>

<span data-ttu-id="7d406-277">Gibt den Namen des zu erweiternden Typs an.</span><span class="sxs-lookup"><span data-stu-id="7d406-277">Specifies the name of the type to extend.</span></span>

<span data-ttu-id="7d406-278">Geben Sie für Typen im **System**-Namespace den Kurznamen ein.</span><span class="sxs-lookup"><span data-stu-id="7d406-278">For types in the **System** namespace, enter the short name.</span></span> <span data-ttu-id="7d406-279">Für andere Typen ist der vollständige Typname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d406-279">Otherwise, the full type name is required.</span></span> <span data-ttu-id="7d406-280">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d406-280">Wildcards are not supported.</span></span>

<span data-ttu-id="7d406-281">Sie können Typnamen an übergeben `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7d406-281">You can pipe type names to `Update-TypeData`.</span></span> <span data-ttu-id="7d406-282">Wenn Sie ein Objekt an die Pipeline übergeben `Update-TypeData` , ruft `Update-TypeData` den Typnamen des Objekts ab, und geben Sie Daten in den Objekttyp ein.</span><span class="sxs-lookup"><span data-stu-id="7d406-282">When you pipe an object to `Update-TypeData`, `Update-TypeData` gets the type name of the object and type data to the object type.</span></span>

<span data-ttu-id="7d406-283">Verwenden Sie diesen Parameter mit den Parametern " **Membership Name**", " **Membership Type**", " **value** " und " **SecondValue** " zum Hinzufügen oder Ändern einer Eigenschaft oder Methode eines Typs.</span><span class="sxs-lookup"><span data-stu-id="7d406-283">Use this parameter with the **MemberName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="7d406-284">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-284">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-285">-Value</span><span class="sxs-lookup"><span data-stu-id="7d406-285">-Value</span></span>

<span data-ttu-id="7d406-286">Gibt den Wert der Eigenschaft oder Methode an.</span><span class="sxs-lookup"><span data-stu-id="7d406-286">Specifies the value of the property or method.</span></span>

<span data-ttu-id="7d406-287">Wenn Sie ein-,-,-oder-Element hinzufügen `AliasProperty` `CodeProperty` `ScriptProperty` `CodeMethod` , können Sie den **SecondValue** -Parameter verwenden, um zusätzliche Informationen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7d406-287">If you add an `AliasProperty`, `CodeProperty`, `ScriptProperty`, or `CodeMethod` member, you can use the **SecondValue** parameter to add additional information.</span></span>

<span data-ttu-id="7d406-288">Verwenden Sie diesen Parameter mit den Parametern " **Membership Name**", " **Membership Type**", " **value** " und " **SecondValue** " zum Hinzufügen oder Ändern einer Eigenschaft oder Methode eines Typs.</span><span class="sxs-lookup"><span data-stu-id="7d406-288">Use this parameter with the **MemberName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="7d406-289">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-289">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-290">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7d406-290">-Confirm</span></span>

<span data-ttu-id="7d406-291">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7d406-291">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-292">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7d406-292">-WhatIf</span></span>

<span data-ttu-id="7d406-293">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7d406-293">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7d406-294">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7d406-294">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d406-295">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7d406-295">CommonParameters</span></span>

<span data-ttu-id="7d406-296">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7d406-296">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7d406-297">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7d406-297">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7d406-298">Eingaben</span><span class="sxs-lookup"><span data-stu-id="7d406-298">Inputs</span></span>

### <span data-ttu-id="7d406-299">System.String</span><span class="sxs-lookup"><span data-stu-id="7d406-299">System.String</span></span>

<span data-ttu-id="7d406-300">Sie können eine Zeichenfolge, die die Werte der Parameter **appendpath**, **TypeName** oder **typedata** enthält, über die Pipeline an übergeben `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="7d406-300">You can pipe a string that contains the values of the **AppendPath**, **TypeName**, or **TypeData** parameters to `Update-TypeData`.</span></span>

## <span data-ttu-id="7d406-301">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="7d406-301">Outputs</span></span>

### <span data-ttu-id="7d406-302">Keine</span><span class="sxs-lookup"><span data-stu-id="7d406-302">None</span></span>

<span data-ttu-id="7d406-303">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="7d406-303">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="7d406-304">Notizen</span><span class="sxs-lookup"><span data-stu-id="7d406-304">Notes</span></span>

## <span data-ttu-id="7d406-305">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="7d406-305">Related links</span></span>

[<span data-ttu-id="7d406-306">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="7d406-306">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="7d406-307">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="7d406-307">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="7d406-308">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="7d406-308">Remove-TypeData</span></span>](Remove-TypeData.md)

