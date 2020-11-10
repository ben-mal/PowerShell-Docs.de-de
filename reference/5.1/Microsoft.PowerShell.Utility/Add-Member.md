---
external help file: Microsoft.PowerShell.Commands.Utility.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-member?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Member
ms.openlocfilehash: 4d251a558d1623e2e0573812921f0e1f273356cf
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388143"
---
# <span data-ttu-id="d5b7c-103">Add-Member</span><span class="sxs-lookup"><span data-stu-id="d5b7c-103">Add-Member</span></span>

## <span data-ttu-id="d5b7c-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d5b7c-104">SYNOPSIS</span></span>
<span data-ttu-id="d5b7c-105">Fügt einer Instanz eines PowerShell-Objekts benutzerdefinierte Eigenschaften und Methoden hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-105">Adds custom properties and methods to an instance of a PowerShell object.</span></span>

## <span data-ttu-id="d5b7c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d5b7c-106">SYNTAX</span></span>

### <span data-ttu-id="d5b7c-107">Tytzameset (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5b7c-107">TypeNameSet (Default)</span></span>

```
Add-Member -InputObject <PSObject> -TypeName <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="d5b7c-108">Notepropertymultimembership Set</span><span class="sxs-lookup"><span data-stu-id="d5b7c-108">NotePropertyMultiMemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru]
 [-NotePropertyMembers] <IDictionary> [<CommonParameters>]
```

### <span data-ttu-id="d5b7c-109">Notepropertysinglemembership Set</span><span class="sxs-lookup"><span data-stu-id="d5b7c-109">NotePropertySingleMemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru] [-NotePropertyName] <String>
 [-NotePropertyValue] <Object> [<CommonParameters>]
```

### <span data-ttu-id="d5b7c-110">MemberSet</span><span class="sxs-lookup"><span data-stu-id="d5b7c-110">MemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-MemberType] <PSMemberTypes> [-Name] <String> [[-Value] <Object>]
 [[-SecondValue] <Object>] [-TypeName <String>] [-Force] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="d5b7c-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d5b7c-111">DESCRIPTION</span></span>

<span data-ttu-id="d5b7c-112">Mit dem- `Add-Member` Cmdlet können Sie einer Instanz eines PowerShell-Objekts Elemente (Eigenschaften und Methoden) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-112">The `Add-Member` cmdlet lets you add members (properties and methods) to an instance of a PowerShell object.</span></span> <span data-ttu-id="d5b7c-113">Beispielsweise können Sie ein NoteProperty-Element hinzufügen, das eine Beschreibung des Objekts enthält, oder ein **ScriptMethod** -Element, das ein Skript zum Ändern des Objekts ausführt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-113">For instance, you can add a NoteProperty member that contains a description of the object or a **ScriptMethod** member that runs a script to change the object.</span></span>

<span data-ttu-id="d5b7c-114">Um zu verwenden `Add-Member` , übergeben Sie das-Objekt an `Add-Member` , oder verwenden Sie den **Inputobject** -Parameter, um das-Objekt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-114">To use `Add-Member`, pipe the object to `Add-Member`, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="d5b7c-115">Der Parameter " **Membership Type** " gibt den Typ des Members an, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-115">The **MemberType** parameter indicates the type of member that you want to add.</span></span> <span data-ttu-id="d5b7c-116">Der **Name** -Parameter weist dem neuen Member einen Namen zu, und der **value** -Parameter legt den Wert des Members fest.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-116">The **Name** parameter assigns a name to the new member, and the **Value** parameter sets the value of the member.</span></span>

<span data-ttu-id="d5b7c-117">Die Eigenschaften und Methoden, die Sie hinzufügen, werden nur der angegebenen bestimmten Instanz des Objekts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-117">The properties and methods that you add are added only to the particular instance of the object that you specify.</span></span> <span data-ttu-id="d5b7c-118">`Add-Member` der Objekttyp wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-118">`Add-Member` does not change the object type.</span></span> <span data-ttu-id="d5b7c-119">Um einen neuen Objekttyp zu erstellen, verwenden Sie das- `Add-Type` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-119">To create a new object type, use the `Add-Type` cmdlet.</span></span>

<span data-ttu-id="d5b7c-120">Sie können auch das- `Export-Clixml` Cmdlet verwenden, um die Instanz des Objekts, einschließlich der zusätzlichen Elemente, in einer Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-120">You can also use the `Export-Clixml` cmdlet to save the instance of the object, including the additional members, in a file.</span></span> <span data-ttu-id="d5b7c-121">Anschließend können Sie mit dem `Import-Clixml` Cmdlet die Instanz des Objekts aus den Informationen, die in der exportierten Datei gespeichert sind, neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-121">Then you can use the `Import-Clixml` cmdlet to re-create the instance of the object from the information that is stored in the exported file.</span></span>

<span data-ttu-id="d5b7c-122">Ab Windows PowerShell 3,0 `Add-Member` verfügt über neue Funktionen, die das Hinzufügen von Hinweis Eigenschaften zu Objekten vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-122">Beginning in Windows PowerShell 3.0, `Add-Member` has new features that make it easier to add note properties to objects.</span></span>
<span data-ttu-id="d5b7c-123">Sie können die Parameter **NotePropertyName** und **NotePropertyValue** verwenden, um eine Hinweiseigenschaft zu definieren, oder aber den **NotePropertyMembers** -Parameter verwenden, der eine Hashtabelle mit Hinweiseigenschaftsnamen und -werten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-123">You can use the **NotePropertyName** and **NotePropertyValue** parameters to define a note property or use the **NotePropertyMembers** parameter, which takes a hash table of note property names and values.</span></span>

<span data-ttu-id="d5b7c-124">Ab Windows PowerShell 3.0 wird außerdem der **PassThru** -Parameter zum Generieren eines Ausgabeobjekts seltener benötigt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-124">Also, beginning in Windows PowerShell 3.0, the **PassThru** parameter, which generates an output object, is needed less frequently.</span></span> <span data-ttu-id="d5b7c-125">`Add-Member` fügt jetzt die neuen Elemente direkt dem Eingabe Objekt anderer Typen hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-125">`Add-Member` now adds the new members directly to the input object of more types.</span></span> <span data-ttu-id="d5b7c-126">Weitere Informationen finden Sie in der Beschreibung zum **PassThru** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-126">For more information, see the **PassThru** parameter description.</span></span>

## <span data-ttu-id="d5b7c-127">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d5b7c-127">EXAMPLES</span></span>

### <span data-ttu-id="d5b7c-128">Beispiel 1: Hinzufügen einer Note-Eigenschaft zu einem psobject</span><span class="sxs-lookup"><span data-stu-id="d5b7c-128">Example 1: Add a note property to a PSObject</span></span>

<span data-ttu-id="d5b7c-129">Im folgenden Beispiel wird dem **FileInfo** -Objekt, das die Datei darstellt, eine **Status** Hinweis Eigenschaft mit dem Wert "Done" hinzugefügt `Test.txt` .</span><span class="sxs-lookup"><span data-stu-id="d5b7c-129">The following example adds a **Status** note property with a value of "Done" to the **FileInfo** object that represents the `Test.txt` file.</span></span>

<span data-ttu-id="d5b7c-130">Der erste Befehl verwendet das `Get-ChildItem` Cmdlet, um ein **FileInfo** -Objekt zu erhalten, das die `Test.txt` Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-130">The first command uses the `Get-ChildItem` cmdlet to get a **FileInfo** object representing the `Test.txt` file.</span></span> <span data-ttu-id="d5b7c-131">Sie speichert Sie in der `$a` Variablen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-131">It saves it in the `$a` variable.</span></span>

<span data-ttu-id="d5b7c-132">Mit dem zweiten Befehl wird die Note-Eigenschaft dem-Objekt in hinzugefügt `$a` .</span><span class="sxs-lookup"><span data-stu-id="d5b7c-132">The second command adds the note property to the object in `$a`.</span></span>

<span data-ttu-id="d5b7c-133">Der dritte Befehl verwendet die Punkt Notation, um den Wert der **Status** -Eigenschaft des Objekts in zu erhalten `$a` .</span><span class="sxs-lookup"><span data-stu-id="d5b7c-133">The third command uses dot notation to get the value of the **Status** property of the object in `$a`.</span></span> <span data-ttu-id="d5b7c-134">Wie die Ausgabe zeigt, lautet der Wert "Done".</span><span class="sxs-lookup"><span data-stu-id="d5b7c-134">As the output shows, the value is "Done".</span></span>

```powershell
$A = Get-ChildItem c:\ps-test\test.txt
$A | Add-Member -NotePropertyName Status -NotePropertyValue Done
$A.Status
```

```Output
Done
```

### <span data-ttu-id="d5b7c-135">Beispiel 2: Hinzufügen einer Alias Eigenschaft zu einem psobject</span><span class="sxs-lookup"><span data-stu-id="d5b7c-135">Example 2: Add an alias property to a PSObject</span></span>

<span data-ttu-id="d5b7c-136">Im folgenden Beispiel wird dem-Objekt, das die Datei darstellt, eine **size** -Alias Eigenschaft hinzugefügt `Test.txt` .</span><span class="sxs-lookup"><span data-stu-id="d5b7c-136">The following example adds a **Size** alias property to the object that represents the `Test.txt` file.</span></span> <span data-ttu-id="d5b7c-137">Die neue Eigenschaft ist ein Alias für die **length** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-137">The new property is an alias for the **Length** property.</span></span>

<span data-ttu-id="d5b7c-138">Der erste Befehl verwendet das `Get-ChildItem` Cmdlet, um das `Test.txt` **FileInfo** -Objekt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-138">The first command uses the `Get-ChildItem` cmdlet to get the `Test.txt` **FileInfo** object.</span></span>

<span data-ttu-id="d5b7c-139">Mit dem zweiten Befehl wird die **size** -Alias Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-139">The second command adds the **Size** alias property.</span></span>
<span data-ttu-id="d5b7c-140">Der dritte Befehl verwendet die Punkt Notation, um den Wert der neuen **size** -Eigenschaft zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-140">The third command uses dot notation to get the value of the new **Size** property.</span></span>

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$A | Add-Member -MemberType AliasProperty -Name Size -Value Length
$A.Size
```

```Output
2394
```

### <span data-ttu-id="d5b7c-141">Beispiel 3: Hinzufügen einer stringuse-Notiz Eigenschaft zu einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5b7c-141">Example 3: Add a StringUse note property to a string</span></span>

<span data-ttu-id="d5b7c-142">In diesem Beispiel wird eine Zeichenfolge der Eigenschaft " **stringuse** Note" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-142">This example adds the **StringUse** note property to a string.</span></span>
<span data-ttu-id="d5b7c-143">Da `Add-Member` Typen zu **Zeichen** folgen Eingabe Objekten keine Typen hinzufügen können, können Sie den **passthru** -Parameter angeben, um ein Ausgabe Objekt zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-143">Because `Add-Member` cannot add types to **String** input objects, you can specify the **PassThru** parameter to generate an output object.</span></span> <span data-ttu-id="d5b7c-144">Der letzte Befehl im Beispiel zeigt die neue Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-144">The last command in the example displays the new property.</span></span>

<span data-ttu-id="d5b7c-145">In diesem Beispiel wird der **notepropertymembers** -Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-145">This example uses the **NotePropertyMembers** parameter.</span></span> <span data-ttu-id="d5b7c-146">Der Wert des **NotePropertyMembers** -Parameters ist eine Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-146">The value of the **NotePropertyMembers** parameter is a hash table.</span></span> <span data-ttu-id="d5b7c-147">Der Schlüssel ist der Name der Hinweis Eigenschaft ( **stringuse** ), und der Wert ist der Wert der Note-Eigenschaft, **Display**.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-147">The key is the note property name, **StringUse** , and the value is the note property value, **Display**.</span></span>

```powershell
$A = "A string"
$A = $A | Add-Member -NotePropertyMembers @{StringUse="Display"} -PassThru
$A.StringUse
```

```Output
Display
```

### <span data-ttu-id="d5b7c-148">Beispiel 4: Hinzufügen einer Skript Methode zu einem FileInfo-Objekt</span><span class="sxs-lookup"><span data-stu-id="d5b7c-148">Example 4: Add a script method to a FileInfo object</span></span>

<span data-ttu-id="d5b7c-149">In diesem Beispiel wird die **sizeinmb** -Skript Methode einem **FileInfo** -Objekt hinzugefügt, das die Dateigröße auf das nächste Megabyte berechnet.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-149">This example adds the **SizeInMB** script method to a **FileInfo** object which calculates the file size to the nearest MegaByte.</span></span> <span data-ttu-id="d5b7c-150">Mit dem zweiten Befehl wird ein **ScriptBlock** erstellt, der die statische Methode " **Round** " vom `[math]` Typ verwendet, um die Dateigröße auf die zweite Dezimalstelle zu runden.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-150">The second command creates a **ScriptBlock** that uses the **Round** static method from the `[math]` type to round the file size to the second decimal place.</span></span>

<span data-ttu-id="d5b7c-151">Der **value** -Parameter verwendet auch die `$This` Automatische Variable, die das aktuelle Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-151">The **Value** parameter also uses the `$This` automatic variable, which represents the current object.</span></span> <span data-ttu-id="d5b7c-152">Die `$This` Variable ist nur in Skript Blöcken gültig, die neue Eigenschaften und Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-152">The `$This` variable is valid only in script blocks that define new properties and methods.</span></span>

<span data-ttu-id="d5b7c-153">Der letzte Befehl verwendet die Punkt Notation, um die neue **sizeinmb** -Skript Methode für das Objekt in der Variablen aufzurufen `$A` .</span><span class="sxs-lookup"><span data-stu-id="d5b7c-153">The last command uses dot notation to call the new **SizeInMB** script method on the object in the `$A` variable.</span></span>

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$S = {[math]::Round(($this.Length / 1MB), 2)}
$A | Add-Member -MemberType ScriptMethod -Name "SizeInMB" -Value $S
$A.SizeInMB()
```

```Output
0.43
```

### <span data-ttu-id="d5b7c-154">Beispiel 5: Kopieren aller Eigenschaften eines Objekts in ein anderes</span><span class="sxs-lookup"><span data-stu-id="d5b7c-154">Example 5: Copy all properties of an object to another</span></span>

<span data-ttu-id="d5b7c-155">Diese Funktion kopiert alle Eigenschaften eines Objekts in ein anderes Objekt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-155">This function copies all of the properties of one object to another object.</span></span>

<span data-ttu-id="d5b7c-156">Die- `foreach` Schleife verwendet das- `Get-Member` Cmdlet, um alle Eigenschaften des **from** -Objekts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-156">The `foreach` loop uses the `Get-Member` cmdlet to get each of the properties of the **From** object.</span></span> <span data-ttu-id="d5b7c-157">Die Befehle in der `foreach` Schleife werden in Reihen für jede der Eigenschaften ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-157">The commands within the `foreach` loop are performed in series on each of the properties.</span></span>

<span data-ttu-id="d5b7c-158">Der- `Add-Member` Befehl fügt die-Eigenschaft des **from** -Objekts dem **to** -Objekt als **NoteProperty** hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-158">The `Add-Member` command adds the property of the **From** object to the **To** object as a **NoteProperty**.</span></span> <span data-ttu-id="d5b7c-159">Der Wert wird mithilfe des **value** -Parameters kopiert.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-159">The value is copied using the **Value** parameter.</span></span> <span data-ttu-id="d5b7c-160">Er verwendet den **Force** -Parameter, um Member mit demselben Elementnamen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-160">It uses the **Force** parameter to add members with the same member name.</span></span>

```powershell
function Copy-Property ($From, $To)
{
    $properties = Get-Member -InputObject $From -MemberType Property
    foreach ($p in $properties)
    {
        $To | Add-Member -MemberType NoteProperty -Name $p.Name -Value $From.$($p.Name) -Force
    }
}
```

### <span data-ttu-id="d5b7c-161">Beispiel 6: Erstellen eines benutzerdefinierten Objekts</span><span class="sxs-lookup"><span data-stu-id="d5b7c-161">Example 6: Create a custom object</span></span>

<span data-ttu-id="d5b7c-162">In diesem Beispiel wird **ein Benutzer** definiertes Medienobjekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-162">This example creates an **Asset** custom object.</span></span>

<span data-ttu-id="d5b7c-163">Mit dem- `New-Object` Cmdlet wird ein **psobject-Objekt** erstellt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-163">The `New-Object` cmdlet creates a **PSObject**.</span></span> <span data-ttu-id="d5b7c-164">Im Beispiel wird das **psobject** in der `$Asset` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-164">The example saves the **PSObject** in the `$Asset` variable.</span></span>

<span data-ttu-id="d5b7c-165">Mit dem zweiten Befehl wird die `[ordered]` typbeschleunigung verwendet, um ein geordnetes Wörterbuch mit Namen und Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-165">The second command uses the `[ordered]` type accelerator to create an ordered dictionary of names and values.</span></span> <span data-ttu-id="d5b7c-166">Der Befehl speichert das Ergebnis in der `$D` Variablen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-166">The command saves the result in the `$D` variable.</span></span>

<span data-ttu-id="d5b7c-167">Der dritte Befehl verwendet den **notepropertymembers** -Parameter des `Add-Member` Cmdlets, um das Wörterbuch in der `$D` Variablen dem **psobject** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-167">The third command uses the **NotePropertyMembers** parameter of the `Add-Member` cmdlet to add the dictionary in the `$D` variable to the **PSObject**.</span></span>
<span data-ttu-id="d5b7c-168">Die **typame** -Eigenschaft weist dem **psobject** einen neuen Namen, **Asset** , zu.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-168">The **TypeName** property assigns a new name, **Asset** , to the **PSObject**.</span></span>

<span data-ttu-id="d5b7c-169">Mit dem letzten Befehl wird das neue **Asset** -Objekt an das `Get-Member` Cmdlet weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-169">The last command pipes the new **Asset** object to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="d5b7c-170">Die Ausgabe zeigt, dass das Objekt den Typnamen **Asset** und die im geordneten Wörterbuch definierten Hinweis Eigenschaften aufweist.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-170">The output shows that the object has a type name of **Asset** and the note properties that we defined in the ordered dictionary.</span></span>

```powershell
$Asset = New-Object -TypeName PSObject
$d = [ordered]@{Name="Server30";System="Server Core";PSVersion="4.0"}
$Asset | Add-Member -NotePropertyMembers $d -TypeName Asset
$Asset | Get-Member
```

```Output
   TypeName: Asset

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty System.String Name=Server30
PSVersion   NoteProperty System.String PSVersion=4.0
System      NoteProperty System.String System=Server Core
```

## <span data-ttu-id="d5b7c-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d5b7c-171">PARAMETERS</span></span>

### <span data-ttu-id="d5b7c-172">-Force</span><span class="sxs-lookup"><span data-stu-id="d5b7c-172">-Force</span></span>

<span data-ttu-id="d5b7c-173">Gibt an, dass dieses Cmdlet ein neues Element hinzufügt, auch wenn das Objekt über einen benutzerdefinierten Member mit demselben Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-173">Indicates that this cmdlet adds a new member even the object has a custom member with the same name.</span></span>
<span data-ttu-id="d5b7c-174">Der **Force** -Parameter kann nicht verwendet werden, um einen Standardmember eines Typs zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-174">You cannot use the **Force** parameter to replace a standard member of a type.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MemberSet, NotePropertySingleMemberSet, NotePropertyMultiMemberSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5b7c-175">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d5b7c-175">-InputObject</span></span>

<span data-ttu-id="d5b7c-176">Gibt das Objekt an, dem das neue Element hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-176">Specifies the object to which the new member is added.</span></span>
<span data-ttu-id="d5b7c-177">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-177">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d5b7c-178">-Mitgliedstyp</span><span class="sxs-lookup"><span data-stu-id="d5b7c-178">-MemberType</span></span>

<span data-ttu-id="d5b7c-179">Gibt den Typ des hinzu zufügenden Members an.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-179">Specifies the type of the member to add.</span></span>
<span data-ttu-id="d5b7c-180">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-180">This parameter is required.</span></span>
<span data-ttu-id="d5b7c-181">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="d5b7c-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d5b7c-182">NoteProperty</span><span class="sxs-lookup"><span data-stu-id="d5b7c-182">NoteProperty</span></span>
- <span data-ttu-id="d5b7c-183">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="d5b7c-183">AliasProperty</span></span>
- <span data-ttu-id="d5b7c-184">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="d5b7c-184">ScriptProperty</span></span>
- <span data-ttu-id="d5b7c-185">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="d5b7c-185">CodeProperty</span></span>
- <span data-ttu-id="d5b7c-186">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="d5b7c-186">ScriptMethod</span></span>
- <span data-ttu-id="d5b7c-187">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="d5b7c-187">CodeMethod</span></span>

<span data-ttu-id="d5b7c-188">Weitere Informationen zu diesen Werten finden Sie unter [psmembership types-Enumeration](/dotnet/api/system.management.automation.psmembertypes) im PowerShell SDK.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-188">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes) in the PowerShell SDK.</span></span>

<span data-ttu-id="d5b7c-189">Nicht alle Objekte verfügen über jeden Membertyp.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-189">Not all objects have every type of member.</span></span>
<span data-ttu-id="d5b7c-190">Wenn Sie einen Elementtyp angeben, der für das Objekt nicht vorhanden ist, gibt PowerShell einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-190">If you specify a member type that the object does not have, PowerShell returns an error.</span></span>

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: MemberSet
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5b7c-191">-Name</span><span class="sxs-lookup"><span data-stu-id="d5b7c-191">-Name</span></span>

<span data-ttu-id="d5b7c-192">Gibt den Namen des Members an, den dieses Cmdlet hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-192">Specifies the name of the member that this cmdlet adds.</span></span>

```yaml
Type: System.String
Parameter Sets: MemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5b7c-193">-Notepropertymembers</span><span class="sxs-lookup"><span data-stu-id="d5b7c-193">-NotePropertyMembers</span></span>

<span data-ttu-id="d5b7c-194">Gibt eine Hashtabelle oder ein sortiertes Wörterbuch mit Hinweiseigenschaftsnamen und -werten an.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-194">Specifies a hash table or ordered dictionary of note property names and values.</span></span>
<span data-ttu-id="d5b7c-195">Geben Sie eine Hashtabelle oder ein Wörterbuch ein, in dem die Schlüssel Hinweiseigenschaftsnamen und die Werte Hinweiseigenschaftswerte sind.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-195">Type a hash table or dictionary in which the keys are note property names and the values are note property values.</span></span>

<span data-ttu-id="d5b7c-196">Weitere Informationen zu Hash Tabellen und geordneten Wörterbüchern in PowerShell finden Sie unter [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="d5b7c-196">For more information about hash tables and ordered dictionaries in PowerShell, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="d5b7c-197">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-197">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: NotePropertyMultiMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5b7c-198">-Notepropertyname</span><span class="sxs-lookup"><span data-stu-id="d5b7c-198">-NotePropertyName</span></span>

<span data-ttu-id="d5b7c-199">Gibt den Hinweis Eigenschaftsnamen an.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-199">Specifies the note property name.</span></span>

<span data-ttu-id="d5b7c-200">Verwenden Sie diesen Parameter mit dem **NotePropertyValue** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-200">Use this parameter with the **NotePropertyValue** parameter.</span></span>
<span data-ttu-id="d5b7c-201">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-201">This parameter is optional.</span></span>

<span data-ttu-id="d5b7c-202">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5b7c-203">-Notepropertyvalue</span><span class="sxs-lookup"><span data-stu-id="d5b7c-203">-NotePropertyValue</span></span>

<span data-ttu-id="d5b7c-204">Gibt den Wert der Note-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-204">Specifies the note property value.</span></span>

<span data-ttu-id="d5b7c-205">Verwenden Sie diesen Parameter mit dem **notepropertyname** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-205">Use this parameter with the **NotePropertyName** parameter.</span></span>
<span data-ttu-id="d5b7c-206">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-206">This parameter is optional.</span></span>

<span data-ttu-id="d5b7c-207">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-207">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5b7c-208">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d5b7c-208">-PassThru</span></span>

<span data-ttu-id="d5b7c-209">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-209">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="d5b7c-210">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-210">By default, this cmdlet does not generate any output.</span></span>

<span data-ttu-id="d5b7c-211">Bei den meisten-Objekten werden `Add-Member` die neuen Elemente dem Eingabe Objekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-211">For most objects, `Add-Member` adds the new members to the input object.</span></span>
<span data-ttu-id="d5b7c-212">Wenn das Eingabe Objekt jedoch eine Zeichenfolge ist, `Add-Member` kann das Element nicht dem Eingabe Objekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-212">However, when the input object is a string, `Add-Member` cannot add the member to the input object.</span></span>
<span data-ttu-id="d5b7c-213">Verwenden Sie für diese den **PassThru** -Parameter, um ein Ausgabeobjekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-213">For these objects, use the **PassThru** parameter to create an output object.</span></span>

<span data-ttu-id="d5b7c-214">In Windows PowerShell 2,0 wurden Elemente `Add-Member` nur dem **psobject** -Wrapper von Objekten, nicht dem Objekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-214">In Windows PowerShell 2.0, `Add-Member` added members only to the **PSObject** wrapper of objects, not to the object.</span></span>
<span data-ttu-id="d5b7c-215">Verwenden Sie den **passthru** -Parameter, um ein Ausgabe Objekt für ein Objekt zu erstellen, das über einen **psobject** -Wrapper verfügt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-215">Use the **PassThru** parameter to create an output object for any object that has a **PSObject** wrapper.</span></span>

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

### <span data-ttu-id="d5b7c-216">-SecondValue</span><span class="sxs-lookup"><span data-stu-id="d5b7c-216">-SecondValue</span></span>

<span data-ttu-id="d5b7c-217">Gibt optionale weitere Informationen zu **AliasProperty** -, **ScriptProperty** -, **CodeProperty** - oder **CodeMethod** -Elementen an.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-217">Specifies optional additional information about **AliasProperty** , **ScriptProperty** , **CodeProperty** , or **CodeMethod** members.</span></span>

<span data-ttu-id="d5b7c-218">Wenn Sie beim Hinzufügen einer **aliasproperty** verwendet wird, muss dieser Parameter ein-Datentyp sein.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-218">If used when adding an **AliasProperty** , this parameter must be a data type.</span></span>
<span data-ttu-id="d5b7c-219">Eine Konvertierung in den angegebenen Datentyp wird dem Wert der **aliasproperty** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-219">A conversion to the specified data type is added to the value of the **AliasProperty**.</span></span>

<span data-ttu-id="d5b7c-220">Wenn Sie z. b. eine **aliasproperty** hinzufügen, die einen alternativen Namen für eine Zeichen folgen Eigenschaft bereitstellt, können Sie auch einen **SecondValue** -Parameter von **System. Int32** angeben, um anzugeben, dass der Wert dieser Zeichen folgen Eigenschaft in eine ganze Zahl konvertiert werden soll, wenn über die entsprechende **aliasproperty** darauf zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-220">For example, if you add an **AliasProperty** that provides an alternate name for a string property, you can also specify a **SecondValue** parameter of **System.Int32** to indicate that the value of that string property should be converted to an integer when accessed by using the corresponding **AliasProperty**.</span></span>

<span data-ttu-id="d5b7c-221">Mit dem **SecondValue** -Parameter können Sie einen zusätzlichen **ScriptBlock** angeben, wenn Sie ein **scriptproperty** -Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-221">You can use the **SecondValue** parameter to specify an additional **ScriptBlock** when adding a **ScriptProperty** member.</span></span> <span data-ttu-id="d5b7c-222">Der erste **ScriptBlock** , der im **value** -Parameter angegeben wird, wird verwendet, um den Wert einer Variablen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-222">The first **ScriptBlock** , specified in the **Value** parameter, is used to get the value of a variable.</span></span> <span data-ttu-id="d5b7c-223">Der zweite **ScriptBlock** , der im **SecondValue** -Parameter angegeben wird, wird verwendet, um den Wert einer Variablen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-223">The second **ScriptBlock** , specified in the **SecondValue** parameter, is used to set the value of a variable.</span></span>

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5b7c-224">-Value</span><span class="sxs-lookup"><span data-stu-id="d5b7c-224">-Value</span></span>

<span data-ttu-id="d5b7c-225">Gibt den Anfangswert des hinzugefügten Elements an.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-225">Specifies the initial value of the added member.</span></span>
<span data-ttu-id="d5b7c-226">Wenn Sie einen **aliasproperty** -, **CodeProperty** -, **scriptproperty** -oder **codemethod** -Member hinzufügen, können Sie optionale, zusätzliche Informationen mithilfe des **SecondValue** -Parameters angeben.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-226">If you add an **AliasProperty** , **CodeProperty** , **ScriptProperty** or **CodeMethod** member, you can supply optional, additional information by using the **SecondValue** parameter.</span></span>

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5b7c-227">-Typname</span><span class="sxs-lookup"><span data-stu-id="d5b7c-227">-TypeName</span></span>

<span data-ttu-id="d5b7c-228">Gibt einen Namen für den Typ an.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-228">Specifies a name for the type.</span></span>

<span data-ttu-id="d5b7c-229">Wenn der Typ eine Klasse im **System** -Namespace oder ein Typ mit einer typbeschleunigung ist, können Sie den Kurznamen des Typs eingeben.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-229">When the type is a class in the **System** namespace or a type that has a type accelerator, you can enter the short name of the type.</span></span> <span data-ttu-id="d5b7c-230">Für andere Typen ist der vollständige Typname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-230">Otherwise, the full type name is required.</span></span>
<span data-ttu-id="d5b7c-231">Dieser Parameter ist nur wirksam, wenn **Inputobject** ein **psobject** ist.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-231">This parameter is effective only when the **InputObject** is a **PSObject**.</span></span>

<span data-ttu-id="d5b7c-232">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: TypeNameSet, NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: True (TypeNameSet), False (NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5b7c-233">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d5b7c-233">CommonParameters</span></span>

<span data-ttu-id="d5b7c-234">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-234">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d5b7c-235">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d5b7c-235">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d5b7c-236">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d5b7c-236">INPUTS</span></span>

### <span data-ttu-id="d5b7c-237">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="d5b7c-237">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="d5b7c-238">Sie können einen beliebigen Objekttyp an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-238">You can pipe any object type to this cmdlet.</span></span>

## <span data-ttu-id="d5b7c-239">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d5b7c-239">OUTPUTS</span></span>

### <span data-ttu-id="d5b7c-240">None oder System. Object</span><span class="sxs-lookup"><span data-stu-id="d5b7c-240">None or System.Object</span></span>

<span data-ttu-id="d5b7c-241">Wenn Sie den **passthru** -Parameter verwenden, gibt dieses Cmdlet das neu erweiterte Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-241">When you use the **PassThru** parameter, this cmdlet returns the newly-extended object.</span></span>
<span data-ttu-id="d5b7c-242">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-242">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d5b7c-243">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d5b7c-243">NOTES</span></span>

<span data-ttu-id="d5b7c-244">Sie können nur Elemente zu **psobject** -Objekten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-244">You can add members only to **PSObject** objects.</span></span> <span data-ttu-id="d5b7c-245">Verwenden Sie den-Operator, um zu bestimmen, ob ein Objekt ein **psobject** -Objekt ist `-is` .</span><span class="sxs-lookup"><span data-stu-id="d5b7c-245">To determine whether an object is a **PSObject** object, use the `-is` operator.</span></span>

<span data-ttu-id="d5b7c-246">Um z. b. ein in der Variablen gespeichertes Objekt zu testen `$obj` , geben Sie ein `$obj -is [PSObject]` .</span><span class="sxs-lookup"><span data-stu-id="d5b7c-246">For instance, to test an object stored in the `$obj` variable, type `$obj -is [PSObject]`.</span></span>

<span data-ttu-id="d5b7c-247">Die Namen der Parameter " **Membership Type** ", " **Name** ", " **value** " und " **SecondValue** " sind optional.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-247">The names of the **MemberType** , **Name** , **Value** , and **SecondValue** parameters are optional.</span></span>
<span data-ttu-id="d5b7c-248">Wenn Sie die Parameternamen weglassen, müssen die unbenannten Parameterwerte in der folgenden Reihenfolge angezeigt werden: **Mitgliedschaftstyp** , **Name** , **Wert** und **SecondValue**.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-248">If you omit the parameter names, the unnamed parameter values must appear in this order: **MemberType** , **Name** , **Value** , and **SecondValue**.</span></span>

<span data-ttu-id="d5b7c-249">Wenn Sie die Parameternamen angeben, können die Parameter in beliebiger Reihenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-249">If you include the parameter names, the parameters can appear in any order.</span></span>

<span data-ttu-id="d5b7c-250">Sie können die `$this` Automatische Variable in Skript Blöcken verwenden, die die Werte der neuen Eigenschaften und Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-250">You can use the `$this` automatic variable in script blocks that define the values of new properties and methods.</span></span>
<span data-ttu-id="d5b7c-251">Die- `$this` Variable verweist auf die Instanz des Objekts, dem die Eigenschaften und Methoden hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d5b7c-251">The `$this` variable refers to the instance of the object to which the properties and methods are being added.</span></span> <span data-ttu-id="d5b7c-252">Weitere Informationen zur- `$this` Variablen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d5b7c-252">For more information about the `$this` variable, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="d5b7c-253">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d5b7c-253">RELATED LINKS</span></span>

[<span data-ttu-id="d5b7c-254">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="d5b7c-254">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="d5b7c-255">Get-Member</span><span class="sxs-lookup"><span data-stu-id="d5b7c-255">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="d5b7c-256">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="d5b7c-256">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="d5b7c-257">New-Object</span><span class="sxs-lookup"><span data-stu-id="d5b7c-257">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="d5b7c-258">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="d5b7c-258">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)
