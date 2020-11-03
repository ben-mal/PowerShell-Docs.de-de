---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-typedata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-TypeData
ms.openlocfilehash: 926239c0bbdb17f53b7d869c0bb08c8ab125f1a4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214735"
---
# <span data-ttu-id="fe7b5-103">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="fe7b5-103">Remove-TypeData</span></span>

## <span data-ttu-id="fe7b5-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="fe7b5-104">Synopsis</span></span>
<span data-ttu-id="fe7b5-105">Löscht erweiterte Typen aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-105">Deletes extended types from the current session.</span></span>

## <span data-ttu-id="fe7b5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe7b5-106">Syntax</span></span>

### <span data-ttu-id="fe7b5-107">Removetypeer DataSet (Standard)</span><span class="sxs-lookup"><span data-stu-id="fe7b5-107">RemoveTypeDataSet (Default)</span></span>

```
Remove-TypeData -TypeData <TypeData> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fe7b5-108">Removetypeset</span><span class="sxs-lookup"><span data-stu-id="fe7b5-108">RemoveTypeSet</span></span>

```
Remove-TypeData [-TypeName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fe7b5-109">Removefileset</span><span class="sxs-lookup"><span data-stu-id="fe7b5-109">RemoveFileSet</span></span>

```
Remove-TypeData -Path <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fe7b5-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fe7b5-110">DESCRIPTION</span></span>

<span data-ttu-id="fe7b5-111">Mit dem- `Remove-TypeData` Cmdlet werden erweiterte Typdaten aus der aktuellen Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-111">The `Remove-TypeData` cmdlet deletes extended type data from the current session.</span></span> <span data-ttu-id="fe7b5-112">Dieses Cmdlet wirkt sich nur auf die aktuelle Sitzung und Sitzungen aus, die in der aktuellen Sitzung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-112">This cmdlet affects only the current session and sessions that are created in the current session.</span></span>

<span data-ttu-id="fe7b5-113">Sie können Objekten in PowerShell Eigenschaften und Methoden hinzufügen, indem Sie Sie in `Update-TypeData` Befehlen und `Types.ps1xml` Dateien definieren.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-113">You can add properties and methods to objects in PowerShell by defining them in `Update-TypeData` commands and `Types.ps1xml` files.</span></span> <span data-ttu-id="fe7b5-114">`Remove-TypeData` löscht diese erweiterten Eigenschaften und Methoden aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-114">`Remove-TypeData` deletes those extended properties and methods from the current session.</span></span> <span data-ttu-id="fe7b5-115">`Remove-TypeData` die Dateien werden nicht gelöscht, oder es werden `Types.ps1xml` keine erweiterten Typdefinitionen aus den `Types.ps1xml` Dateien gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-115">`Remove-TypeData` does not delete the `Types.ps1xml` files or delete any extended type definitions from the `Types.ps1xml` files.</span></span> <span data-ttu-id="fe7b5-116">Weitere Informationen zu `Types.ps1xml` Dateien finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="fe7b5-116">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span></span>

<span data-ttu-id="fe7b5-117">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-117">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="fe7b5-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fe7b5-118">Examples</span></span>

### <span data-ttu-id="fe7b5-119">Beispiel 1: Entfernen von Typdaten für einen angegebenen Typ</span><span class="sxs-lookup"><span data-stu-id="fe7b5-119">Example 1: Remove type data for a specified type</span></span>

<span data-ttu-id="fe7b5-120">In diesem Beispiel werden alle Typdaten für den **System. Array** -Typ aus der Sitzung gelöscht, einschließlich der von einer Datei hinzugefügten Typdaten `Types.ps1xml` und dynamischer Typdaten, die der Sitzung mithilfe des `Update-TypeData` Cmdlets hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-120">This example deletes all type data for the **System.Array** type  from the session, including type data that was added by a `Types.ps1xml` file and dynamic type data that was added to the session by using the `Update-TypeData` cmdlet.</span></span>

```powershell
Remove-TypeData -TypeName System.Array
```

### <span data-ttu-id="fe7b5-121">Beispiel 2: Entfernen eines erweiterten Datentyps aus einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="fe7b5-121">Example 2: Remove an extended data type from a session</span></span>

<span data-ttu-id="fe7b5-122">Dieses Beispiel zeigt die Auswirkung des Entfernens von erweiterten Typdaten aus einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-122">This example shows the effect of removing extended type data from a session.</span></span> <span data-ttu-id="fe7b5-123">Der erste ruft `Get-TypeData` Erweiterte Typdaten für den **System. DateTime** -Typ ab.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-123">The first `Get-TypeData` gets extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="fe7b5-124">Die Ausgabe zeigt, dass alle **System. DateTime** -Objekte in PowerShell eine **DateTime** -Eigenschaft hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-124">The output shows that a **DateTime** property has been added to all **System.DateTime** objects in PowerShell.</span></span> <span data-ttu-id="fe7b5-125">Das- `Get-Date` Cmdlet gibt ein **System. DateTime** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-125">The `Get-Date` cmdlet returns a **System.DateTime** object.</span></span> <span data-ttu-id="fe7b5-126">Der Befehl verwendet die Punkt Notation, um den Wert der **DateTime** -Eigenschaft des **System. DateTime** -Objekts, das zurückgibt, zu erhalten `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="fe7b5-126">The command uses dot notation to get the value of the **DateTime** property of the **System.DateTime** object that `Get-Date` returns.</span></span>

```powershell
Get-TypeData System.DateTime
(Get-Date).DateTime
Get-TypeData System.DateTime | Remove-TypeData
(Get-Date).DateTime
```

```Output
TypeName        Members
--------        -------
System.DateTime {[DateTime, System.Management.Automation.Runspaces.ScriptPropertyData]}

Friday, January 20, 2012 9:01:00 PM
```

<span data-ttu-id="fe7b5-127">Das nächste `Get-TypeData` Cmdlet, um alle erweiterten Typdaten für den **System. DateTime** -Typ zu erhalten, und leitet dieses an das `Remove-TypeData` Cmdlet weiter, um die erweiterten Typdaten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-127">The next `Get-TypeData` cmdlet to get all extended type data for the **System.DateTime** type and pipes that to the `Remove-TypeData` cmdlet to delete the extended type data.</span></span> <span data-ttu-id="fe7b5-128">Das letzte `Get-Date` Cmdlet zeigt die Auswirkungen des Löschens der erweiterten Typdaten für **den System. DateTime** -Typ.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-128">The last `Get-Date` cmdlet shows the effect of deleting the extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="fe7b5-129">Da die **System. DateTime** -Eigenschaft nicht mehr vorhanden ist, gibt ein Befehl zum erhalten des Werts nichts zurück.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-129">Because the **System.DateTime** property no longer exists, a command to get its value returns nothing.</span></span>

### <span data-ttu-id="fe7b5-130">Beispiel 3: Entfernen erweiterter Typen für Module</span><span class="sxs-lookup"><span data-stu-id="fe7b5-130">Example 3: Remove extended types for modules</span></span>

<span data-ttu-id="fe7b5-131">In diesem Beispiel werden alle erweiterten Typdaten für Modul Objekte entfernt.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-131">This example removes all extended type data for module objects.</span></span> <span data-ttu-id="fe7b5-132">Wenn Sie ein Objekt an die Pipeline übergeben `Remove-TypeData` , ruft `Remove-TypeData` den Namen des Objekt Typs ab und entfernt alle Typdaten für alle Objekte dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-132">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the name of the object type and removes all type data for all objects of that type.</span></span>

```powershell
Get-Module | Remove-TypeData
```

### <span data-ttu-id="fe7b5-133">Beispiel 4: Entfernen erweiterter Typen aus angegebenen Modulen</span><span class="sxs-lookup"><span data-stu-id="fe7b5-133">Example 4: Remove extended types from specified modules</span></span>

<span data-ttu-id="fe7b5-134">Dieses Beispiel verwendet den **path** -Parameter des `Remove-TypeData` Cmdlets, um die erweiterten Typen zu entfernen, die in den `Types.ps1xml` von den Modulen **psscheduledjob** und **psworkflow** hinzugefügten Dateien definiert sind.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-134">This example uses the **Path** parameter of the `Remove-TypeData` cmdlet to remove the extended types that are defined in the `Types.ps1xml` files that are added by the **PSScheduledJob** and **PSWorkflow** modules.</span></span> <span data-ttu-id="fe7b5-135">Dieser Befehl wirkt sich nicht auf dynamische Typdaten aus, die mit dem `Update-TypeData` Cmdlet hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-135">This command does not affect dynamic type data that is added by using the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="fe7b5-136">Der Befehl ist nur erfolgreich, wenn die Module in die aktuelle Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-136">The command succeeds only when the modules have been imported into the current session.</span></span>

```powershell
Remove-TypeData -Path "$PSHOME\Modules\PSScheduledJob", "$PSHOME\Modules\PSWorkflow\PSWorkflow.types.ps1xml"
```

<span data-ttu-id="fe7b5-137">Weitere Informationen zu Modulen finden Sie unter [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="fe7b5-137">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

### <span data-ttu-id="fe7b5-138">Beispiel 5: Entfernen erweiterter Typen aus einer Remote Sitzung</span><span class="sxs-lookup"><span data-stu-id="fe7b5-138">Example 5: Remove extended types from a remote session</span></span>

<span data-ttu-id="fe7b5-139">In diesem Beispiel werden erweiterte Typen aus einer Remote Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-139">This example removes extended types from a remote session.</span></span> <span data-ttu-id="fe7b5-140">Der Befehl verwendet das `Invoke-Command` Cmdlet, um erweiterte Typdaten für alle CIM-Typen in den Sitzungen in der Variablen zu entfernen `$S` .</span><span class="sxs-lookup"><span data-stu-id="fe7b5-140">The command uses the `Invoke-Command` cmdlet to remove extended type data for all CIM types in the sessions in the `$S` variable.</span></span>

```powershell
Invoke-Command -Session $S {Get-TypeData -TypeName *CIM* | Remove-TypeData}
```

## <span data-ttu-id="fe7b5-141">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe7b5-141">Parameters</span></span>

### <span data-ttu-id="fe7b5-142">-Path</span><span class="sxs-lookup"><span data-stu-id="fe7b5-142">-Path</span></span>

<span data-ttu-id="fe7b5-143">Gibt ein Array von Dateien an, die von diesem Cmdlet aus den erweiterten Typdaten der Sitzung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-143">Specifies an array of files that this cmdlet deletes from the session extended type data.</span></span> <span data-ttu-id="fe7b5-144">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-144">This parameter is required.</span></span>

<span data-ttu-id="fe7b5-145">Geben Sie die Pfade und Dateinamen von einer oder mehreren `Types.ps1xml` Dateien ein.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-145">Enter the paths and file names of one or more `Types.ps1xml` files.</span></span> <span data-ttu-id="fe7b5-146">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-146">Wildcards are not supported.</span></span> <span data-ttu-id="fe7b5-147">Wenn Sie den Pfad weglassen, wird als Standardspeicherort das aktuelle Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-147">If you omit the path, the default location is the current directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RemoveFileSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe7b5-148">-Typedata</span><span class="sxs-lookup"><span data-stu-id="fe7b5-148">-TypeData</span></span>

<span data-ttu-id="fe7b5-149">Gibt die Typdaten an, die von diesem Cmdlet aus der Sitzung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-149">Specifies the type data that this cmdlet deletes from the session.</span></span> <span data-ttu-id="fe7b5-150">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-150">This parameter is required.</span></span> <span data-ttu-id="fe7b5-151">Geben Sie eine Variable ein, die **typedata** -Objekte ( **System. Management. Automation. Runspaces. typedata** ) enthält, oder einen Befehl, der **typedata** -Objekte abruft, z. b. einen- `Get-TypeData` Befehl.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-151">Enter a variable that contains **TypeData** objects ( **System.Management.Automation.Runspaces.TypeData** ) or a command that gets **TypeData** objects, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="fe7b5-152">Sie können **typedata** -Objekte auch über die Pipeline an senden `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="fe7b5-152">You can also pipe **TypeData** objects to `Remove-TypeData`.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.TypeData
Parameter Sets: RemoveTypeDataSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fe7b5-153">-Typname</span><span class="sxs-lookup"><span data-stu-id="fe7b5-153">-TypeName</span></span>

<span data-ttu-id="fe7b5-154">Gibt die Typen an, für die dieses Cmdlet alle erweiterten Typdaten löscht.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-154">Specifies the types that this cmdlet deletes all extended type data for.</span></span> <span data-ttu-id="fe7b5-155">Geben Sie für Typen im System-Namespace den kurzen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-155">For types in the System namespace, enter the short name.</span></span> <span data-ttu-id="fe7b5-156">Für andere Typen ist der vollständige Typname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-156">Otherwise, the full type name is required.</span></span> <span data-ttu-id="fe7b5-157">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-157">Wildcards are not supported.</span></span>

<span data-ttu-id="fe7b5-158">Sie können Typnamen an übergeben `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="fe7b5-158">You can pipe type names to `Remove-TypeData`.</span></span> <span data-ttu-id="fe7b5-159">Wenn Sie ein Objekt an übergeben `Remove-TypeData` , ruft `Remove-TypeData` den Typnamen des Objekts ab und entfernt alle Typdaten für den Objekttyp.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-159">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

```yaml
Type: System.String
Parameter Sets: RemoveTypeSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fe7b5-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fe7b5-160">-Confirm</span></span>

<span data-ttu-id="fe7b5-161">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-161">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fe7b5-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fe7b5-162">-WhatIf</span></span>

<span data-ttu-id="fe7b5-163">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-163">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fe7b5-164">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-164">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fe7b5-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fe7b5-165">CommonParameters</span></span>

<span data-ttu-id="fe7b5-166">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fe7b5-167">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fe7b5-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fe7b5-168">Eingaben</span><span class="sxs-lookup"><span data-stu-id="fe7b5-168">Inputs</span></span>

### <span data-ttu-id="fe7b5-169">System. Management. Automation. Runspaces. typedata</span><span class="sxs-lookup"><span data-stu-id="fe7b5-169">System.Management.Automation.Runspaces.TypeData</span></span>

<span data-ttu-id="fe7b5-170">Sie können das **typedata** -Objekt, z. b. die vom `Get-TypeData` Cmdlet zurückgegebenen, an übergeben `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="fe7b5-170">You can pipe **TypeData** object, such as the ones that the `Get-TypeData` cmdlet returns, to `Remove-TypeData`.</span></span>

### <span data-ttu-id="fe7b5-171">System.String</span><span class="sxs-lookup"><span data-stu-id="fe7b5-171">System.String</span></span>

<span data-ttu-id="fe7b5-172">Sie können die Typnamen an übergeben `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="fe7b5-172">You can pipe the type names to `Remove-TypeData`.</span></span> <span data-ttu-id="fe7b5-173">Wenn Sie ein Objekt an übergeben `Remove-TypeData` , ruft `Remove-TypeData` den Typnamen des Objekts ab und entfernt alle Typdaten für den Objekttyp.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-173">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

## <span data-ttu-id="fe7b5-174">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="fe7b5-174">Outputs</span></span>

### <span data-ttu-id="fe7b5-175">Keine</span><span class="sxs-lookup"><span data-stu-id="fe7b5-175">None</span></span>

<span data-ttu-id="fe7b5-176">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-176">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fe7b5-177">Notizen</span><span class="sxs-lookup"><span data-stu-id="fe7b5-177">Notes</span></span>

<span data-ttu-id="fe7b5-178">`Remove-TypeData` nur die erweiterten Typdaten in der aktuellen Sitzung können entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-178">`Remove-TypeData` can remove only the extended type data in the current session.</span></span> <span data-ttu-id="fe7b5-179">Es kann nicht erweiterte Typdaten entfernen, die sich auf dem Computer befinden, jedoch nicht der aktuellen Sitzung hinzugefügt wurden, wie erweiterte Typen, die in Modulen definiert sind, die aber nicht in die aktuelle Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fe7b5-179">It cannot remove extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="fe7b5-180">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="fe7b5-180">Related links</span></span>

[<span data-ttu-id="fe7b5-181">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="fe7b5-181">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="fe7b5-182">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="fe7b5-182">Update-TypeData</span></span>](Update-TypeData.md)

