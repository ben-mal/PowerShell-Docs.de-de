---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-typedata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TypeData
ms.openlocfilehash: 83e520f5d48aed89bdd1a461958331185eb46b9a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210540"
---
# <span data-ttu-id="d39be-103">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="d39be-103">Get-TypeData</span></span>

## <span data-ttu-id="d39be-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d39be-104">Synopsis</span></span>
<span data-ttu-id="d39be-105">Ruft die erweiterten Typdaten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="d39be-105">Gets the extended type data in the current session.</span></span>

## <span data-ttu-id="d39be-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d39be-106">Syntax</span></span>

```
Get-TypeData [[-TypeName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="d39be-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d39be-107">Description</span></span>

<span data-ttu-id="d39be-108">Das- `Get-TypeData` Cmdlet ruft die erweiterten Typdaten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="d39be-108">The `Get-TypeData` cmdlet gets the extended type data in the current session.</span></span> <span data-ttu-id="d39be-109">Dies schließt Typdaten ein, die der Sitzung durch `Types.ps1xml` Datei-und dynamische Typdaten hinzugefügt wurden, die mithilfe des-Parameters des `Update-TypeData` Cmdlets hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="d39be-109">This includes type data that was added to the session by `Types.ps1xml` file and dynamic type data that was added by using the parameter of the `Update-TypeData` cmdlet.</span></span>

<span data-ttu-id="d39be-110">Sie können die erweiterten Typdaten verwenden, die `Get-TypeData` zurückgibt, um die Typdaten in der Sitzung zu überprüfen und Sie an die `Update-TypeData` -und- `Remove-TypeData` Cmdlets zu senden.</span><span class="sxs-lookup"><span data-stu-id="d39be-110">You can use the extended type data that `Get-TypeData` returns to examine the type data in the session and send it to the `Update-TypeData` and `Remove-TypeData` cmdlets.</span></span>

<span data-ttu-id="d39be-111">Erweiterte Typdaten fügen Objekten in PowerShell Eigenschaften und Methoden hinzu.</span><span class="sxs-lookup"><span data-stu-id="d39be-111">Extended type data adds properties and methods to objects in PowerShell.</span></span> <span data-ttu-id="d39be-112">Sie können die hinzugefügten Eigenschaften und Methoden auf die gleiche Weise wie die im Objekttyp definierten Eigenschaften und Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="d39be-112">You can use the added properties and methods in the same ways that you would use the properties and methods that are defined in the object type.</span></span> <span data-ttu-id="d39be-113">Beachten Sie jedoch beim Schreiben von Skripts, dass die hinzugefügten Eigenschaften und Methoden möglicherweise nicht in jeder PowerShell-Sitzung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d39be-113">However, when writing scripts, be aware that the added properties and methods might not be present in every PowerShell session.</span></span>

<span data-ttu-id="d39be-114">Weitere Informationen zu `Types.ps1xml` Dateien finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="d39be-114">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span> <span data-ttu-id="d39be-115">Weitere Informationen zu dynamischen Typdaten, die vom `Update-TypeData` Cmdlet hinzugefügt werden, finden Sie unter `Update-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="d39be-115">For more information about dynamic type data that the `Update-TypeData` cmdlet adds, see `Update-TypeData`.</span></span>

<span data-ttu-id="d39be-116">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d39be-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="d39be-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d39be-117">Examples</span></span>

### <span data-ttu-id="d39be-118">Beispiel 1: alle erweiterten Typdaten</span><span class="sxs-lookup"><span data-stu-id="d39be-118">Example 1: Get all extended type data</span></span>

<span data-ttu-id="d39be-119">In diesem Beispiel werden alle erweiterten Typdaten in der aktuellen Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d39be-119">This example gets all extended type data in the current session.</span></span>

 ```powershell
Get-TypeData
```

### <span data-ttu-id="d39be-120">Beispiel 2: Get Types by Name</span><span class="sxs-lookup"><span data-stu-id="d39be-120">Example 2: Get types by name</span></span>

<span data-ttu-id="d39be-121">In diesem Beispiel werden alle Typen in der aktuellen Sitzung abgerufen, die Namen enthalten, die Ereignisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="d39be-121">This example gets all types in the current session that have names that contain Eventing.</span></span>

 ```powershell
"*Eventing*" | Get-TypeData
```

```Output
TypeName                                                  Members
--------                                                  -------
System.Diagnostics.Eventing.Reader.EventLogConfiguration  {}System.Diagnostics.Eventing.Reader.EventLogRecord
                                                          {}System.Diagnostics.Eventing.Reader.ProviderMetadata
                                                          {[ProviderName, System.Management.Automation.Runspaces.AliasProper...
```

### <span data-ttu-id="d39be-122">Beispiel 3: Ruft den Skriptblock ab, der einen Eigenschafts Wert erstellt.</span><span class="sxs-lookup"><span data-stu-id="d39be-122">Example 3: Get the script block that creates a property value</span></span>

<span data-ttu-id="d39be-123">In diesem Beispiel wird der Skriptblock abgerufen, der den Wert der **EventID-** Eigenschaft von **EventLogEntry** -Objekten erstellt.</span><span class="sxs-lookup"><span data-stu-id="d39be-123">This example gets the script block that creates the value of the **EventID** property of **EventLogEntry** objects.</span></span>

 ```powershell
(Get-TypeData *EventLogEntry*).Members.EventID
```

```Output
GetScriptBlock                     SetScriptBlock     IsHidden Name
--------------                     --------------     -------- ----
$this.get_EventID() -band 0xFFFF                         False EventID
```

### <span data-ttu-id="d39be-124">Beispiel 4: der Skriptblock, der eine Eigenschaft für ein angegebenes Objekt definiert</span><span class="sxs-lookup"><span data-stu-id="d39be-124">Example 4: Get the script block that defines a property for a specified object</span></span>

<span data-ttu-id="d39be-125">In diesem Beispiel wird der Skriptblock abgerufen, der die **DateTime** -Eigenschaft der **System. DateTime** -Objekte in PowerShell definiert.</span><span class="sxs-lookup"><span data-stu-id="d39be-125">This example gets the script block that defines the **DateTime** property of **System.DateTime** objects in PowerShell.</span></span>

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

<span data-ttu-id="d39be-126">Der Befehl verwendet das `Get-TypeData` Cmdlet, um die erweiterten Typdaten für den **System. DataTime** -Typ zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d39be-126">The command uses the `Get-TypeData` cmdlet to get the extended type data for the **System.DataTime** type.</span></span> <span data-ttu-id="d39be-127">Mit dem Befehl wird die **Members** -Eigenschaft des **TypeData** -Objekts abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d39be-127">The command gets the **Members** property of the **TypeData** object.</span></span>

<span data-ttu-id="d39be-128">Die **Members** -Eigenschaft enthält eine Hash Tabelle mit Eigenschaften und Methoden, die durch erweiterte Typdaten definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d39be-128">The **Members** property contains a hash table of properties and methods that are defined by extended type data.</span></span> <span data-ttu-id="d39be-129">Jeder Schlüssel in der Hashtabelle „Members“ ist ein Eigenschaften- oder Methodenname, und jeder Wert ist die Definition des Eigenschaften- oder Methodenwerts.</span><span class="sxs-lookup"><span data-stu-id="d39be-129">Each key in the Members hash table is a property or method name and each value is the definition of the property or method value.</span></span>

<span data-ttu-id="d39be-130">Der Befehl ruft den **DateTime** **-Schlüssel** in Membern und dessen **getscriptblock** -Eigenschafts Wert ab.</span><span class="sxs-lookup"><span data-stu-id="d39be-130">The command gets the **DateTime** key in **Members** and its **GetScriptBlock** property value.</span></span>

<span data-ttu-id="d39be-131">Die Ausgabe zeigt den Skriptblock, der den Wert der **DateTime** -Eigenschaft jedes **System. DateTime** -Objekts in PowerShell erstellt.</span><span class="sxs-lookup"><span data-stu-id="d39be-131">The output shows the script block that creates the value of the **DateTime** property of every **System.DateTime** object in PowerShell.</span></span>

## <span data-ttu-id="d39be-132">Parameter</span><span class="sxs-lookup"><span data-stu-id="d39be-132">Parameters</span></span>

### <span data-ttu-id="d39be-133">-Typname</span><span class="sxs-lookup"><span data-stu-id="d39be-133">-TypeName</span></span>

<span data-ttu-id="d39be-134">Gibt Typdaten nur für Typen mit den angegebenen Namen als Array an.</span><span class="sxs-lookup"><span data-stu-id="d39be-134">Specifies type data as an array only for the types with the specified names.</span></span> <span data-ttu-id="d39be-135">Standardmäßig ruft `Get-TypeData` alle Typen in der Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="d39be-135">By default, `Get-TypeData` gets all types in the session.</span></span>

<span data-ttu-id="d39be-136">Geben Sie Namen oder ein Namensmuster ein.</span><span class="sxs-lookup"><span data-stu-id="d39be-136">Enter type names or a name patterns.</span></span> <span data-ttu-id="d39be-137">Vollständige Namen oder Namensmuster mit Platzhalter Zeichen sind erforderlich, auch für Typen im System-Namespace.</span><span class="sxs-lookup"><span data-stu-id="d39be-137">Full names, or name patterns with wildcard characters are required, even for types in the System namespace.</span></span> <span data-ttu-id="d39be-138">Platzhalter werden unterstützt, und der Parameter Name **tykenname** ist optional.</span><span class="sxs-lookup"><span data-stu-id="d39be-138">Wildcards are supported and the parameter name **TypeName** is optional.</span></span> <span data-ttu-id="d39be-139">Sie können Typnamen auch über die Pipeline an senden `Get-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="d39be-139">You can also pipe type names to `Get-TypeData`.</span></span>

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

### <span data-ttu-id="d39be-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d39be-140">CommonParameters</span></span>

<span data-ttu-id="d39be-141">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d39be-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d39be-142">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d39be-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d39be-143">Eingaben</span><span class="sxs-lookup"><span data-stu-id="d39be-143">Inputs</span></span>

### <span data-ttu-id="d39be-144">System.String</span><span class="sxs-lookup"><span data-stu-id="d39be-144">System.String</span></span>

<span data-ttu-id="d39be-145">Sie können Typnamen an übergeben `Get-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="d39be-145">You can pipe type names to `Get-TypeData`.</span></span>

## <span data-ttu-id="d39be-146">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="d39be-146">Outputs</span></span>

### <span data-ttu-id="d39be-147">System. Management. Automation. Runspaces. typedata</span><span class="sxs-lookup"><span data-stu-id="d39be-147">System.Management.Automation.Runspaces.TypeData</span></span>

## <span data-ttu-id="d39be-148">Notizen</span><span class="sxs-lookup"><span data-stu-id="d39be-148">Notes</span></span>

<span data-ttu-id="d39be-149">`Get-TypeData` Ruft nur die erweiterten Typdaten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="d39be-149">`Get-TypeData` gets only the extended type data in the current session.</span></span> <span data-ttu-id="d39be-150">Es ruft keine erweiterten Typdaten ab, die sich auf dem Computer befinden, aber nicht der aktuellen Sitzung hinzugefügt wurden, wie z. B. erweiterte Typen, die in Modulen definiert und nicht in die aktuelle Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d39be-150">It does not get extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="d39be-151">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="d39be-151">Related links</span></span>

[<span data-ttu-id="d39be-152">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="d39be-152">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="d39be-153">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="d39be-153">Remove-TypeData</span></span>](Remove-TypeData.md)

[<span data-ttu-id="d39be-154">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="d39be-154">Update-TypeData</span></span>](Update-TypeData.md)
