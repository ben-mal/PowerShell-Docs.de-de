---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-typedata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TypeData
ms.openlocfilehash: a4f7106bfeadc963a265f5fb239f9fa6bab40800
ms.sourcegitcommit: bdd0fedaf9ba534645b2f7eb1fe1241481f58715
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "105936511"
---
# <span data-ttu-id="27461-102">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="27461-102">Get-TypeData</span></span>

## <span data-ttu-id="27461-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="27461-103">Synopsis</span></span>
<span data-ttu-id="27461-104">Ruft die erweiterten Typdaten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="27461-104">Gets the extended type data in the current session.</span></span>

## <span data-ttu-id="27461-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="27461-105">Syntax</span></span>

```
Get-TypeData [[-TypeName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="27461-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="27461-106">Description</span></span>

<span data-ttu-id="27461-107">Das- `Get-TypeData` Cmdlet ruft die erweiterten Typdaten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="27461-107">The `Get-TypeData` cmdlet gets the extended type data in the current session.</span></span> <span data-ttu-id="27461-108">Dies schließt Typdaten ein, die der Sitzung durch `Types.ps1xml` Datei-und dynamische Typdaten hinzugefügt wurden, die mithilfe des-Parameters des `Update-TypeData` Cmdlets hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="27461-108">This includes type data that was added to the session by `Types.ps1xml` file and dynamic type data that was added by using the parameter of the `Update-TypeData` cmdlet.</span></span>

<span data-ttu-id="27461-109">Sie können die erweiterten Typdaten verwenden, die `Get-TypeData` zurückgibt, um die Typdaten in der Sitzung zu überprüfen und Sie an die `Update-TypeData` -und- `Remove-TypeData` Cmdlets zu senden.</span><span class="sxs-lookup"><span data-stu-id="27461-109">You can use the extended type data that `Get-TypeData` returns to examine the type data in the session and send it to the `Update-TypeData` and `Remove-TypeData` cmdlets.</span></span>

<span data-ttu-id="27461-110">Erweiterte Typdaten fügen Objekten in PowerShell Eigenschaften und Methoden hinzu.</span><span class="sxs-lookup"><span data-stu-id="27461-110">Extended type data adds properties and methods to objects in PowerShell.</span></span> <span data-ttu-id="27461-111">Sie können die hinzugefügten Eigenschaften und Methoden auf die gleiche Weise wie die im Objekttyp definierten Eigenschaften und Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="27461-111">You can use the added properties and methods in the same ways that you would use the properties and methods that are defined in the object type.</span></span> <span data-ttu-id="27461-112">Beachten Sie jedoch beim Schreiben von Skripts, dass die hinzugefügten Eigenschaften und Methoden möglicherweise nicht in jeder PowerShell-Sitzung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="27461-112">However, when writing scripts, be aware that the added properties and methods might not be present in every PowerShell session.</span></span>

<span data-ttu-id="27461-113">Weitere Informationen zu `Types.ps1xml` Dateien finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="27461-113">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span> <span data-ttu-id="27461-114">Weitere Informationen zu dynamischen Typdaten, die vom `Update-TypeData` Cmdlet hinzugefügt werden, finden Sie unter `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="27461-114">For more information about dynamic type data that the `Update-TypeData` cmdlet adds, see `Update-TypeData`.</span></span>

<span data-ttu-id="27461-115">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="27461-115">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="27461-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="27461-116">Examples</span></span>

### <span data-ttu-id="27461-117">Beispiel 1: alle erweiterten Typdaten</span><span class="sxs-lookup"><span data-stu-id="27461-117">Example 1: Get all extended type data</span></span>

<span data-ttu-id="27461-118">In diesem Beispiel werden alle erweiterten Typdaten in der aktuellen Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="27461-118">This example gets all extended type data in the current session.</span></span>

 ```powershell
Get-TypeData
```

### <span data-ttu-id="27461-119">Beispiel 2: Get Type Data by Name</span><span class="sxs-lookup"><span data-stu-id="27461-119">Example 2: Get type data by name</span></span>

<span data-ttu-id="27461-120">In diesem Beispiel werden alle Typdaten in der aktuellen Sitzung abgerufen, deren Name mit "System.IO" gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="27461-120">This example gets all type data in the current session whose name is qualified with "System.IO".</span></span>

```powershell
Get-TypeData -TypeName System.IO.*
```

```Output
TypeName                Members
--------                -------
System.IO.DirectoryInfo {[Mode, System.Management.Automation.Runspaces.CodePropert…
System.IO.FileInfo      {[Mode, System.Management.Automation.Runspaces.CodePropert…
```

### <span data-ttu-id="27461-121">Beispiel 3: Ruft den Skriptblock ab, der einen Eigenschafts Wert erstellt.</span><span class="sxs-lookup"><span data-stu-id="27461-121">Example 3: Get the script block that creates a property value</span></span>

<span data-ttu-id="27461-122">In diesem Beispiel wird der Skriptblock abgerufen, der den Wert der **EventID-** Eigenschaft von **EventLogEntry** -Objekten erstellt.</span><span class="sxs-lookup"><span data-stu-id="27461-122">This example gets the script block that creates the value of the **EventID** property of **EventLogEntry** objects.</span></span>

 ```powershell
(Get-TypeData *EventLogEntry*).Members.EventID
```

```Output
GetScriptBlock                     SetScriptBlock     IsHidden Name
--------------                     --------------     -------- ----
$this.get_EventID() -band 0xFFFF                         False EventID
```

### <span data-ttu-id="27461-123">Beispiel 4: der Skriptblock, der eine Eigenschaft für ein angegebenes Objekt definiert</span><span class="sxs-lookup"><span data-stu-id="27461-123">Example 4: Get the script block that defines a property for a specified object</span></span>

<span data-ttu-id="27461-124">In diesem Beispiel wird der Skriptblock abgerufen, der die **DateTime** -Eigenschaft der **System. DateTime** -Objekte in PowerShell definiert.</span><span class="sxs-lookup"><span data-stu-id="27461-124">This example gets the script block that defines the **DateTime** property of **System.DateTime** objects in PowerShell.</span></span>

 ```powershell
(Get-TypeData -TypeName System.DateTime).Members["DateTime"].GetScriptBlock
if ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq  "Date") {
    "{0}" -f $this.ToLongDateString()
}
elseif ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq "Time") {
    "{0}" -f  $this.ToLongTimeString()
}
else {
    "{0} {1}" -f $this.ToLongDateString(), $this.ToLongTimeString()
}
```

<span data-ttu-id="27461-125">Der Befehl verwendet das `Get-TypeData` Cmdlet, um die erweiterten Typdaten für den **System. DataTime** -Typ zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="27461-125">The command uses the `Get-TypeData` cmdlet to get the extended type data for the **System.DataTime** type.</span></span> <span data-ttu-id="27461-126">Mit dem Befehl wird die **Members**-Eigenschaft des **TypeData**-Objekts abgerufen.</span><span class="sxs-lookup"><span data-stu-id="27461-126">The command gets the **Members** property of the **TypeData** object.</span></span>

<span data-ttu-id="27461-127">Die **Members** -Eigenschaft enthält eine Hash Tabelle mit Eigenschaften und Methoden, die durch erweiterte Typdaten definiert werden.</span><span class="sxs-lookup"><span data-stu-id="27461-127">The **Members** property contains a hash table of properties and methods that are defined by extended type data.</span></span> <span data-ttu-id="27461-128">Jeder Schlüssel in der Hashtabelle „Members“ ist ein Eigenschaften- oder Methodenname, und jeder Wert ist die Definition des Eigenschaften- oder Methodenwerts.</span><span class="sxs-lookup"><span data-stu-id="27461-128">Each key in the Members hash table is a property or method name and each value is the definition of the property or method value.</span></span>

<span data-ttu-id="27461-129">Der Befehl ruft den **DateTime** **-Schlüssel** in Membern und dessen **getscriptblock** -Eigenschafts Wert ab.</span><span class="sxs-lookup"><span data-stu-id="27461-129">The command gets the **DateTime** key in **Members** and its **GetScriptBlock** property value.</span></span>

<span data-ttu-id="27461-130">Die Ausgabe zeigt den Skriptblock, der den Wert der **DateTime** -Eigenschaft jedes **System. DateTime** -Objekts in PowerShell erstellt.</span><span class="sxs-lookup"><span data-stu-id="27461-130">The output shows the script block that creates the value of the **DateTime** property of every **System.DateTime** object in PowerShell.</span></span>

## <span data-ttu-id="27461-131">Parameter</span><span class="sxs-lookup"><span data-stu-id="27461-131">Parameters</span></span>

### <span data-ttu-id="27461-132">-Typname</span><span class="sxs-lookup"><span data-stu-id="27461-132">-TypeName</span></span>

<span data-ttu-id="27461-133">Gibt Typdaten nur für Typen mit den angegebenen Namen als Array an.</span><span class="sxs-lookup"><span data-stu-id="27461-133">Specifies type data as an array only for the types with the specified names.</span></span> <span data-ttu-id="27461-134">Standardmäßig ruft `Get-TypeData` alle Typen in der Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="27461-134">By default, `Get-TypeData` gets all types in the session.</span></span>

<span data-ttu-id="27461-135">Geben Sie Namen oder ein Namensmuster ein.</span><span class="sxs-lookup"><span data-stu-id="27461-135">Enter type names or a name patterns.</span></span> <span data-ttu-id="27461-136">Vollständige Namen oder Namensmuster mit Platzhalter Zeichen sind erforderlich, auch für Typen im System-Namespace.</span><span class="sxs-lookup"><span data-stu-id="27461-136">Full names, or name patterns with wildcard characters are required, even for types in the System namespace.</span></span> <span data-ttu-id="27461-137">Platzhalter werden unterstützt, und der Parameter Name **tykenname** ist optional.</span><span class="sxs-lookup"><span data-stu-id="27461-137">Wildcards are supported and the parameter name **TypeName** is optional.</span></span> <span data-ttu-id="27461-138">Sie können Typnamen auch über die Pipeline an senden `Get-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="27461-138">You can also pipe type names to `Get-TypeData`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="27461-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="27461-139">CommonParameters</span></span>

<span data-ttu-id="27461-140">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="27461-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27461-141">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="27461-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27461-142">Eingaben</span><span class="sxs-lookup"><span data-stu-id="27461-142">Inputs</span></span>

### <span data-ttu-id="27461-143">System.String</span><span class="sxs-lookup"><span data-stu-id="27461-143">System.String</span></span>

<span data-ttu-id="27461-144">Sie können Typnamen an übergeben `Get-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="27461-144">You can pipe type names to `Get-TypeData`.</span></span>

## <span data-ttu-id="27461-145">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="27461-145">Outputs</span></span>

### <span data-ttu-id="27461-146">System. Management. Automation. Runspaces. typedata</span><span class="sxs-lookup"><span data-stu-id="27461-146">System.Management.Automation.Runspaces.TypeData</span></span>

## <span data-ttu-id="27461-147">Notizen</span><span class="sxs-lookup"><span data-stu-id="27461-147">Notes</span></span>

<span data-ttu-id="27461-148">`Get-TypeData` Ruft nur die erweiterten Typdaten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="27461-148">`Get-TypeData` gets only the extended type data in the current session.</span></span> <span data-ttu-id="27461-149">Es ruft keine erweiterten Typdaten ab, die sich auf dem Computer befinden, aber nicht der aktuellen Sitzung hinzugefügt wurden, wie z. B. erweiterte Typen, die in Modulen definiert und nicht in die aktuelle Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="27461-149">It does not get extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="27461-150">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="27461-150">Related links</span></span>

[<span data-ttu-id="27461-151">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="27461-151">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="27461-152">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="27461-152">Remove-TypeData</span></span>](Remove-TypeData.md)

[<span data-ttu-id="27461-153">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="27461-153">Update-TypeData</span></span>](Update-TypeData.md)

