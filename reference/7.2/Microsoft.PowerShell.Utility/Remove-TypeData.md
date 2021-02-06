---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-typedata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-TypeData
ms.openlocfilehash: 8ede1375faa1287b70eeb49689ec7fe1bb800d55
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599848"
---
# <span data-ttu-id="58549-102">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="58549-102">Remove-TypeData</span></span>

## <span data-ttu-id="58549-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="58549-103">Synopsis</span></span>
<span data-ttu-id="58549-104">Löscht erweiterte Typen aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="58549-104">Deletes extended types from the current session.</span></span>

## <span data-ttu-id="58549-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="58549-105">Syntax</span></span>

### <span data-ttu-id="58549-106">Removetypeer DataSet (Standard)</span><span class="sxs-lookup"><span data-stu-id="58549-106">RemoveTypeDataSet (Default)</span></span>

```
Remove-TypeData -TypeData <TypeData> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="58549-107">Removetypeset</span><span class="sxs-lookup"><span data-stu-id="58549-107">RemoveTypeSet</span></span>

```
Remove-TypeData [-TypeName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="58549-108">Removefileset</span><span class="sxs-lookup"><span data-stu-id="58549-108">RemoveFileSet</span></span>

```
Remove-TypeData -Path <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="58549-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="58549-109">DESCRIPTION</span></span>

<span data-ttu-id="58549-110">Mit dem- `Remove-TypeData` Cmdlet werden erweiterte Typdaten aus der aktuellen Sitzung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="58549-110">The `Remove-TypeData` cmdlet deletes extended type data from the current session.</span></span> <span data-ttu-id="58549-111">Dieses Cmdlet wirkt sich nur auf die aktuelle Sitzung und Sitzungen aus, die in der aktuellen Sitzung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="58549-111">This cmdlet affects only the current session and sessions that are created in the current session.</span></span>

<span data-ttu-id="58549-112">Sie können Objekten in PowerShell Eigenschaften und Methoden hinzufügen, indem Sie Sie in `Update-TypeData` Befehlen und `Types.ps1xml` Dateien definieren.</span><span class="sxs-lookup"><span data-stu-id="58549-112">You can add properties and methods to objects in PowerShell by defining them in `Update-TypeData` commands and `Types.ps1xml` files.</span></span> <span data-ttu-id="58549-113">`Remove-TypeData` löscht diese erweiterten Eigenschaften und Methoden aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="58549-113">`Remove-TypeData` deletes those extended properties and methods from the current session.</span></span> <span data-ttu-id="58549-114">`Remove-TypeData` die Dateien werden nicht gelöscht, oder es werden `Types.ps1xml` keine erweiterten Typdefinitionen aus den `Types.ps1xml` Dateien gelöscht.</span><span class="sxs-lookup"><span data-stu-id="58549-114">`Remove-TypeData` does not delete the `Types.ps1xml` files or delete any extended type definitions from the `Types.ps1xml` files.</span></span> <span data-ttu-id="58549-115">Weitere Informationen zu `Types.ps1xml` Dateien finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="58549-115">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span></span>

<span data-ttu-id="58549-116">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="58549-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="58549-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="58549-117">Examples</span></span>

### <span data-ttu-id="58549-118">Beispiel 1: Entfernen von Typdaten für einen angegebenen Typ</span><span class="sxs-lookup"><span data-stu-id="58549-118">Example 1: Remove type data for a specified type</span></span>

<span data-ttu-id="58549-119">In diesem Beispiel werden alle Typdaten für den **System. Array** -Typ aus der Sitzung gelöscht, einschließlich der von einer Datei hinzugefügten Typdaten `Types.ps1xml` und dynamischer Typdaten, die der Sitzung mithilfe des `Update-TypeData` Cmdlets hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="58549-119">This example deletes all type data for the **System.Array** type  from the session, including type data that was added by a `Types.ps1xml` file and dynamic type data that was added to the session by using the `Update-TypeData` cmdlet.</span></span>

```powershell
Remove-TypeData -TypeName System.Array
```

### <span data-ttu-id="58549-120">Beispiel 2: Entfernen eines erweiterten Datentyps aus einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="58549-120">Example 2: Remove an extended data type from a session</span></span>

<span data-ttu-id="58549-121">Dieses Beispiel zeigt die Auswirkung des Entfernens von erweiterten Typdaten aus einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="58549-121">This example shows the effect of removing extended type data from a session.</span></span> <span data-ttu-id="58549-122">Der erste ruft `Get-TypeData` Erweiterte Typdaten für den **System. DateTime** -Typ ab.</span><span class="sxs-lookup"><span data-stu-id="58549-122">The first `Get-TypeData` gets extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="58549-123">Die Ausgabe zeigt, dass alle **System. DateTime** -Objekte in PowerShell eine **DateTime** -Eigenschaft hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="58549-123">The output shows that a **DateTime** property has been added to all **System.DateTime** objects in PowerShell.</span></span> <span data-ttu-id="58549-124">Das- `Get-Date` Cmdlet gibt ein **System. DateTime** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="58549-124">The `Get-Date` cmdlet returns a **System.DateTime** object.</span></span> <span data-ttu-id="58549-125">Der Befehl verwendet die Punkt Notation, um den Wert der **DateTime** -Eigenschaft des **System. DateTime** -Objekts, das zurückgibt, zu erhalten `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="58549-125">The command uses dot notation to get the value of the **DateTime** property of the **System.DateTime** object that `Get-Date` returns.</span></span>

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

<span data-ttu-id="58549-126">Das nächste `Get-TypeData` Cmdlet, um alle erweiterten Typdaten für den **System. DateTime** -Typ zu erhalten, und leitet dieses an das `Remove-TypeData` Cmdlet weiter, um die erweiterten Typdaten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="58549-126">The next `Get-TypeData` cmdlet to get all extended type data for the **System.DateTime** type and pipes that to the `Remove-TypeData` cmdlet to delete the extended type data.</span></span> <span data-ttu-id="58549-127">Das letzte `Get-Date` Cmdlet zeigt die Auswirkungen des Löschens der erweiterten Typdaten für **den System. DateTime** -Typ.</span><span class="sxs-lookup"><span data-stu-id="58549-127">The last `Get-Date` cmdlet shows the effect of deleting the extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="58549-128">Da die **System. DateTime** -Eigenschaft nicht mehr vorhanden ist, gibt ein Befehl zum erhalten des Werts nichts zurück.</span><span class="sxs-lookup"><span data-stu-id="58549-128">Because the **System.DateTime** property no longer exists, a command to get its value returns nothing.</span></span>

### <span data-ttu-id="58549-129">Beispiel 3: Entfernen erweiterter Typen für Module</span><span class="sxs-lookup"><span data-stu-id="58549-129">Example 3: Remove extended types for modules</span></span>

<span data-ttu-id="58549-130">In diesem Beispiel werden alle erweiterten Typdaten für Modul Objekte entfernt.</span><span class="sxs-lookup"><span data-stu-id="58549-130">This example removes all extended type data for module objects.</span></span> <span data-ttu-id="58549-131">Wenn Sie ein Objekt an die Pipeline übergeben `Remove-TypeData` , ruft `Remove-TypeData` den Namen des Objekt Typs ab und entfernt alle Typdaten für alle Objekte dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="58549-131">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the name of the object type and removes all type data for all objects of that type.</span></span>

```powershell
Get-Module | Remove-TypeData
```

### <span data-ttu-id="58549-132">Beispiel 4: Entfernen erweiterter Typen aus angegebenen Modulen</span><span class="sxs-lookup"><span data-stu-id="58549-132">Example 4: Remove extended types from specified modules</span></span>

<span data-ttu-id="58549-133">Dieses Beispiel verwendet den **path** -Parameter des `Remove-TypeData` Cmdlets, um die erweiterten Typen zu entfernen, die in den `Types.ps1xml` von den Modulen **psscheduledjob** und **psworkflow** hinzugefügten Dateien definiert sind.</span><span class="sxs-lookup"><span data-stu-id="58549-133">This example uses the **Path** parameter of the `Remove-TypeData` cmdlet to remove the extended types that are defined in the `Types.ps1xml` files that are added by the **PSScheduledJob** and **PSWorkflow** modules.</span></span> <span data-ttu-id="58549-134">Dieser Befehl wirkt sich nicht auf dynamische Typdaten aus, die mit dem `Update-TypeData` Cmdlet hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="58549-134">This command does not affect dynamic type data that is added by using the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="58549-135">Der Befehl ist nur erfolgreich, wenn die Module in die aktuelle Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="58549-135">The command succeeds only when the modules have been imported into the current session.</span></span>

```powershell
Remove-TypeData -Path "$PSHOME\Modules\PSScheduledJob", "$PSHOME\Modules\PSWorkflow\PSWorkflow.types.ps1xml"
```

<span data-ttu-id="58549-136">Weitere Informationen zu Modulen finden Sie unter [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="58549-136">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

### <span data-ttu-id="58549-137">Beispiel 5: Entfernen erweiterter Typen aus einer Remote Sitzung</span><span class="sxs-lookup"><span data-stu-id="58549-137">Example 5: Remove extended types from a remote session</span></span>

<span data-ttu-id="58549-138">In diesem Beispiel werden erweiterte Typen aus einer Remote Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="58549-138">This example removes extended types from a remote session.</span></span> <span data-ttu-id="58549-139">Der Befehl verwendet das `Invoke-Command` Cmdlet, um erweiterte Typdaten für alle CIM-Typen in den Sitzungen in der Variablen zu entfernen `$S` .</span><span class="sxs-lookup"><span data-stu-id="58549-139">The command uses the `Invoke-Command` cmdlet to remove extended type data for all CIM types in the sessions in the `$S` variable.</span></span>

```powershell
Invoke-Command -Session $S {Get-TypeData -TypeName *CIM* | Remove-TypeData}
```

## <span data-ttu-id="58549-140">Parameter</span><span class="sxs-lookup"><span data-stu-id="58549-140">Parameters</span></span>

### <span data-ttu-id="58549-141">-Path</span><span class="sxs-lookup"><span data-stu-id="58549-141">-Path</span></span>

<span data-ttu-id="58549-142">Gibt ein Array von Dateien an, die von diesem Cmdlet aus den erweiterten Typdaten der Sitzung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="58549-142">Specifies an array of files that this cmdlet deletes from the session extended type data.</span></span> <span data-ttu-id="58549-143">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58549-143">This parameter is required.</span></span>

<span data-ttu-id="58549-144">Geben Sie die Pfade und Dateinamen von einer oder mehreren `Types.ps1xml` Dateien ein.</span><span class="sxs-lookup"><span data-stu-id="58549-144">Enter the paths and file names of one or more `Types.ps1xml` files.</span></span> <span data-ttu-id="58549-145">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58549-145">Wildcards are not supported.</span></span> <span data-ttu-id="58549-146">Wenn Sie den Pfad weglassen, wird als Standardspeicherort das aktuelle Verzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="58549-146">If you omit the path, the default location is the current directory.</span></span>

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

### <span data-ttu-id="58549-147">-Typedata</span><span class="sxs-lookup"><span data-stu-id="58549-147">-TypeData</span></span>

<span data-ttu-id="58549-148">Gibt die Typdaten an, die von diesem Cmdlet aus der Sitzung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="58549-148">Specifies the type data that this cmdlet deletes from the session.</span></span> <span data-ttu-id="58549-149">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58549-149">This parameter is required.</span></span> <span data-ttu-id="58549-150">Geben Sie eine Variable ein, die **typedata** -Objekte (**System. Management. Automation. Runspaces. typedata**) enthält, oder einen Befehl, der **typedata** -Objekte abruft, z. b. einen- `Get-TypeData` Befehl.</span><span class="sxs-lookup"><span data-stu-id="58549-150">Enter a variable that contains **TypeData** objects (**System.Management.Automation.Runspaces.TypeData**) or a command that gets **TypeData** objects, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="58549-151">Sie können **typedata** -Objekte auch über die Pipeline an senden `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="58549-151">You can also pipe **TypeData** objects to `Remove-TypeData`.</span></span>

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

### <span data-ttu-id="58549-152">-Typname</span><span class="sxs-lookup"><span data-stu-id="58549-152">-TypeName</span></span>

<span data-ttu-id="58549-153">Gibt die Typen an, für die dieses Cmdlet alle erweiterten Typdaten löscht.</span><span class="sxs-lookup"><span data-stu-id="58549-153">Specifies the types that this cmdlet deletes all extended type data for.</span></span> <span data-ttu-id="58549-154">Geben Sie für Typen im System-Namespace den kurzen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="58549-154">For types in the System namespace, enter the short name.</span></span> <span data-ttu-id="58549-155">Für andere Typen ist der vollständige Typname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58549-155">Otherwise, the full type name is required.</span></span> <span data-ttu-id="58549-156">Platzhalter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58549-156">Wildcards are not supported.</span></span>

<span data-ttu-id="58549-157">Sie können Typnamen an übergeben `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="58549-157">You can pipe type names to `Remove-TypeData`.</span></span> <span data-ttu-id="58549-158">Wenn Sie ein Objekt an übergeben `Remove-TypeData` , ruft `Remove-TypeData` den Typnamen des Objekts ab und entfernt alle Typdaten für den Objekttyp.</span><span class="sxs-lookup"><span data-stu-id="58549-158">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

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

### <span data-ttu-id="58549-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="58549-159">-Confirm</span></span>

<span data-ttu-id="58549-160">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="58549-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="58549-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="58549-161">-WhatIf</span></span>

<span data-ttu-id="58549-162">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="58549-162">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="58549-163">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="58549-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="58549-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="58549-164">CommonParameters</span></span>

<span data-ttu-id="58549-165">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="58549-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="58549-166">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="58549-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="58549-167">Eingaben</span><span class="sxs-lookup"><span data-stu-id="58549-167">Inputs</span></span>

### <span data-ttu-id="58549-168">System. Management. Automation. Runspaces. typedata</span><span class="sxs-lookup"><span data-stu-id="58549-168">System.Management.Automation.Runspaces.TypeData</span></span>

<span data-ttu-id="58549-169">Sie können das **typedata** -Objekt, z. b. die vom `Get-TypeData` Cmdlet zurückgegebenen, an übergeben `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="58549-169">You can pipe **TypeData** object, such as the ones that the `Get-TypeData` cmdlet returns, to `Remove-TypeData`.</span></span>

### <span data-ttu-id="58549-170">System.String</span><span class="sxs-lookup"><span data-stu-id="58549-170">System.String</span></span>

<span data-ttu-id="58549-171">Sie können die Typnamen an übergeben `Remove-TypeData` .</span><span class="sxs-lookup"><span data-stu-id="58549-171">You can pipe the type names to `Remove-TypeData`.</span></span> <span data-ttu-id="58549-172">Wenn Sie ein Objekt an übergeben `Remove-TypeData` , ruft `Remove-TypeData` den Typnamen des Objekts ab und entfernt alle Typdaten für den Objekttyp.</span><span class="sxs-lookup"><span data-stu-id="58549-172">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

## <span data-ttu-id="58549-173">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="58549-173">Outputs</span></span>

### <span data-ttu-id="58549-174">Keine</span><span class="sxs-lookup"><span data-stu-id="58549-174">None</span></span>

<span data-ttu-id="58549-175">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="58549-175">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="58549-176">Notizen</span><span class="sxs-lookup"><span data-stu-id="58549-176">Notes</span></span>

<span data-ttu-id="58549-177">`Remove-TypeData` nur die erweiterten Typdaten in der aktuellen Sitzung können entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="58549-177">`Remove-TypeData` can remove only the extended type data in the current session.</span></span> <span data-ttu-id="58549-178">Es kann nicht erweiterte Typdaten entfernen, die sich auf dem Computer befinden, jedoch nicht der aktuellen Sitzung hinzugefügt wurden, wie erweiterte Typen, die in Modulen definiert sind, die aber nicht in die aktuelle Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="58549-178">It cannot remove extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="58549-179">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="58549-179">Related links</span></span>

[<span data-ttu-id="58549-180">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="58549-180">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="58549-181">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="58549-181">Update-TypeData</span></span>](Update-TypeData.md)

