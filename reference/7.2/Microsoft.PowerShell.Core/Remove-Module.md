---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Module
ms.openlocfilehash: 2954bbec68b837a73e5365ab6a1e8ecb501d4898
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602538"
---
# <span data-ttu-id="775e8-102">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="775e8-102">Remove-Module</span></span>

## <span data-ttu-id="775e8-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="775e8-103">SYNOPSIS</span></span>
<span data-ttu-id="775e8-104">Entfernt Module aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="775e8-104">Removes modules from the current session.</span></span>

## <span data-ttu-id="775e8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="775e8-105">SYNTAX</span></span>

### <span data-ttu-id="775e8-106">name</span><span class="sxs-lookup"><span data-stu-id="775e8-106">name</span></span>

```
Remove-Module [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="775e8-107">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="775e8-107">FullyQualifiedName</span></span>

```
Remove-Module [-FullyQualifiedName] <ModuleSpecification[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="775e8-108">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="775e8-108">ModuleInfo</span></span>

```
Remove-Module [-ModuleInfo] <PSModuleInfo[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="775e8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="775e8-109">DESCRIPTION</span></span>

<span data-ttu-id="775e8-110">Das **Remove-Module**-Cmdlet entfernt die Elemente eines Moduls, wie z. B. Cmdlets und Funktionen, aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="775e8-110">The **Remove-Module** cmdlet removes the members of a module, such as cmdlets and functions, from the current session.</span></span>

<span data-ttu-id="775e8-111">Wenn das Modul eine Assembly (.dll) enthält, werden alle Elemente entfernt, die von der Assembly implementiert werden, die Assembly wird jedoch nicht entladen.</span><span class="sxs-lookup"><span data-stu-id="775e8-111">If the module includes an assembly (.dll), all members that are implemented by the assembly are removed, but the assembly is not unloaded.</span></span>

<span data-ttu-id="775e8-112">Mit diesem Cmdlet wird das Modul nicht deinstalliert oder vom Computer gelöscht.</span><span class="sxs-lookup"><span data-stu-id="775e8-112">This cmdlet does not uninstall the module or delete it from the computer.</span></span>
<span data-ttu-id="775e8-113">Er wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="775e8-113">It affects only the current PowerShell session.</span></span>

## <span data-ttu-id="775e8-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="775e8-114">EXAMPLES</span></span>

### <span data-ttu-id="775e8-115">Beispiel 1: Entfernen eines Moduls</span><span class="sxs-lookup"><span data-stu-id="775e8-115">Example 1: Remove a module</span></span>

```powershell
Remove-Module -Name "BitsTransfer"
```

<span data-ttu-id="775e8-116">Mit diesem Befehl wird das BitsTransfer-Modul aus der aktuellen Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="775e8-116">This command removes the BitsTransfer module from the current session.</span></span>

### <span data-ttu-id="775e8-117">Beispiel 2: Entfernen aller Module</span><span class="sxs-lookup"><span data-stu-id="775e8-117">Example 2: Remove all modules</span></span>

```powershell
Get-Module | Remove-Module
```

<span data-ttu-id="775e8-118">Dieser Befehl entfernt alle Module aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="775e8-118">This command removes all modules from the current session.</span></span>

### <span data-ttu-id="775e8-119">Beispiel 3: Entfernen von Modulen mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="775e8-119">Example 3: Remove modules by using the pipeline</span></span>

```powershell
"FileTransfer", "PSDiagnostics" | Remove-Module -Verbose
```

```Output
VERBOSE: Performing operation "Remove-Module" on Target "filetransfer (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\filetransfer\filetransfer.psd1')".
VERBOSE: Performing operation "Remove-Module" on Target "Microsoft.BackgroundIntelligentTransfer.Management (Path: 'C:\Windows\assembly\GAC_MSIL\Microsoft.BackgroundIntelligentTransfer.Management\1.0.0.0__31bf3856ad364e35\Microsoft.BackgroundIntelligentTransfe
r.Management.dll')".
VERBOSE: Performing operation "Remove-Module" on Target "psdiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\psdiagnostics.psd1')".
VERBOSE: Removing imported function 'Start-Trace'.
VERBOSE: Removing imported function 'Stop-Trace'.
VERBOSE: Removing imported function 'Enable-WSManTrace'.
VERBOSE: Removing imported function 'Disable-WSManTrace'.
VERBOSE: Removing imported function 'Enable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Disable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Set-LogProperties'.
VERBOSE: Removing imported function 'Get-LogProperties'.
VERBOSE: Removing imported function 'Enable-PSTrace'.
VERBOSE: Removing imported function 'Disable-PSTrace'.
VERBOSE: Performing operation "Remove-Module" on Target "PSDiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\PSDiagnostics.psm1')".
```

<span data-ttu-id="775e8-120">Dieser Befehl entfernt die BitsTransfer- und PSDiagnostics-Module aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="775e8-120">This command removes the BitsTransfer and PSDiagnostics modules from the current session.</span></span>

<span data-ttu-id="775e8-121">Der Befehl verwendet einen Pipelineoperator (|), um die Modulnamen an **Remove-Module** zu senden.</span><span class="sxs-lookup"><span data-stu-id="775e8-121">The command uses a pipeline operator (|) to send the module names to **Remove-Module**.</span></span>
<span data-ttu-id="775e8-122">Er verwendet den allgemeinen *Verbose*-Parameter, um detaillierte Informationen über die zu entfernenden Elemente abzurufen.</span><span class="sxs-lookup"><span data-stu-id="775e8-122">It uses the *Verbose* common parameter to get detailed information about the members that are removed.</span></span>

<span data-ttu-id="775e8-123">In den ausführlichen Meldungen werden die Elemente angezeigt *, die entfernt* werden.</span><span class="sxs-lookup"><span data-stu-id="775e8-123">The *Verbose* messages show the items that are removed.</span></span>
<span data-ttu-id="775e8-124">Die Meldungen unterscheiden sich voneinander, da das BitsTransfer-Modul eine Assembly enthält, die die Cmdlets implementiert, sowie ein geschachteltes Modul mit seiner eigenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="775e8-124">The messages differ because the BitsTransfer module includes an assembly that implements its cmdlets and a nested module with its own assembly.</span></span>
<span data-ttu-id="775e8-125">Das PSDiagnostics-Modul umfasst eine Modulskriptdatei (.psm1), die Funktionen exportiert.</span><span class="sxs-lookup"><span data-stu-id="775e8-125">The PSDiagnostics module includes a module script file (.psm1) that exports functions.</span></span>

### <span data-ttu-id="775e8-126">Beispiel 4: Entfernen eines Moduls mithilfe von ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="775e8-126">Example 4: Remove a module by using ModuleInfo</span></span>

```powershell
$a = Get-Module BitsTransfer
Remove-Module -ModuleInfo $a
```

<span data-ttu-id="775e8-127">Dieser Befehl verwendet den *ModuleInfo* -Parameter, um das bitstransfer-Modul zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="775e8-127">This command uses the *ModuleInfo* parameter to remove the BitsTransfer module.</span></span>

## <span data-ttu-id="775e8-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="775e8-128">PARAMETERS</span></span>

### <span data-ttu-id="775e8-129">-Force</span><span class="sxs-lookup"><span data-stu-id="775e8-129">-Force</span></span>

<span data-ttu-id="775e8-130">Gibt an, dass mit diesem Cmdlet schreibgeschützte Module entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="775e8-130">Indicates that this cmdlet removes read-only modules.</span></span>
<span data-ttu-id="775e8-131">In der Standardeinstellung entfernt **Remove-Module** nur Module mit Lese-/ Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="775e8-131">By default, **Remove-Module** removes only read-write modules.</span></span>

<span data-ttu-id="775e8-132">Die Werte **ReadOnly** und **ReadWrite** sind in der **AccessMode**-Eigenschaft eines Moduls gespeichert.</span><span class="sxs-lookup"><span data-stu-id="775e8-132">The **ReadOnly** and **ReadWrite** values are stored in **AccessMode** property of a module.</span></span>

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

### <span data-ttu-id="775e8-133">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="775e8-133">-FullyQualifiedName</span></span>

<span data-ttu-id="775e8-134">Gibt die voll qualifizierten Namen von Modulen an, die entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="775e8-134">Specifies the fully qualified names of modules to remove.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="775e8-135">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="775e8-135">-ModuleInfo</span></span>

<span data-ttu-id="775e8-136">Gibt die zu entfernenden Modulobjekte an.</span><span class="sxs-lookup"><span data-stu-id="775e8-136">Specifies the module objects to remove.</span></span>
<span data-ttu-id="775e8-137">Geben Sie eine Variable ein, die ein Modul Objekt (**psmoduleinfo**) enthält, oder einen Befehl, mit dem ein Modul Objekt abgerufen wird, z. b. ein Get-Module Befehl.</span><span class="sxs-lookup"><span data-stu-id="775e8-137">Enter a variable that contains a module object (**PSModuleInfo**) or a command that gets a module object, such as a Get-Module command.</span></span>
<span data-ttu-id="775e8-138">Sie können auch Modulobjekte an **Remove-Module** übergeben.</span><span class="sxs-lookup"><span data-stu-id="775e8-138">You can also pipe module objects to **Remove-Module**.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="775e8-139">-Name</span><span class="sxs-lookup"><span data-stu-id="775e8-139">-Name</span></span>

<span data-ttu-id="775e8-140">Gibt die Namen der zu entfernenden Module an.</span><span class="sxs-lookup"><span data-stu-id="775e8-140">Specifies the names of modules to remove.</span></span>
<span data-ttu-id="775e8-141">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="775e8-141">Wildcard characters are permitted.</span></span>
<span data-ttu-id="775e8-142">Sie können auch Namenszeichenfolgen an **Remove-Module** übergeben.</span><span class="sxs-lookup"><span data-stu-id="775e8-142">You can also pipe name strings to **Remove-Module**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="775e8-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="775e8-143">-Confirm</span></span>

<span data-ttu-id="775e8-144">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="775e8-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="775e8-145">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="775e8-145">-WhatIf</span></span>

<span data-ttu-id="775e8-146">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="775e8-146">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="775e8-147">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="775e8-147">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="775e8-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="775e8-148">CommonParameters</span></span>

<span data-ttu-id="775e8-149">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="775e8-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="775e8-150">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="775e8-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="775e8-151">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="775e8-151">INPUTS</span></span>

### <span data-ttu-id="775e8-152">System. String, System. Management. Automation. psmoduleinfo</span><span class="sxs-lookup"><span data-stu-id="775e8-152">System.String, System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="775e8-153">Sie können Modulnamen und Modul Objekte über die Pipeline an **Remove-Module** übergeben.</span><span class="sxs-lookup"><span data-stu-id="775e8-153">You can pipe module names and module objects to **Remove-Module**.</span></span>

## <span data-ttu-id="775e8-154">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="775e8-154">OUTPUTS</span></span>

### <span data-ttu-id="775e8-155">Keine</span><span class="sxs-lookup"><span data-stu-id="775e8-155">None</span></span>

<span data-ttu-id="775e8-156">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="775e8-156">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="775e8-157">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="775e8-157">NOTES</span></span>

<span data-ttu-id="775e8-158">Beim Entfernen eines Moduls ist ein Ereignis für das Modul vorhanden, das ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="775e8-158">When removing a module, there is an event on the module that will execute.</span></span>
<span data-ttu-id="775e8-159">Dieses Ereignis ermöglicht einem Modul, auf das Entfernen zu reagieren und einige Bereinigungs Vorgänge auszuführen, z. b. das Freigeben von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="775e8-159">This event allows a module to react to being removed and perform some cleanup such as freeing up resources.</span></span> <span data-ttu-id="775e8-160">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="775e8-160">Example:</span></span>

<span data-ttu-id="775e8-161">$OnRemoveScript = {</span><span class="sxs-lookup"><span data-stu-id="775e8-161">$OnRemoveScript = {</span></span>

  <span data-ttu-id="775e8-162">\# Bereinigung ausführen</span><span class="sxs-lookup"><span data-stu-id="775e8-162">\# perform cleanup</span></span>

  <span data-ttu-id="775e8-163">$cachedSessions | Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="775e8-163">$cachedSessions | Remove-PSSession</span></span>

<span data-ttu-id="775e8-164">}</span><span class="sxs-lookup"><span data-stu-id="775e8-164">}</span></span>

<span data-ttu-id="775e8-165">$ExecutionContext. SessionState. Module. OnRemove + = $OnRemoveScript</span><span class="sxs-lookup"><span data-stu-id="775e8-165">$ExecutionContext.SessionState.Module.OnRemove += $OnRemoveScript</span></span>

<span data-ttu-id="775e8-166">Um vollständige Konsistenz zu gewährleisten, kann es auch hilfreich sein, auf den Abschluss des PowerShell-Prozesses zu reagieren:</span><span class="sxs-lookup"><span data-stu-id="775e8-166">For full consistency, it might be also useful to react to the closing of the PowerShell process:</span></span>

<span data-ttu-id="775e8-167">Register-EngineEvent-SourceIdentifier ([System. Management. Automation. psengineevent]:: Exit)-Action $OnRemoveScript</span><span class="sxs-lookup"><span data-stu-id="775e8-167">Register-EngineEvent -SourceIdentifier ([System.Management.Automation.PsEngineEvent]::Exiting) -Action $OnRemoveScript</span></span>

## <span data-ttu-id="775e8-168">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="775e8-168">RELATED LINKS</span></span>

[<span data-ttu-id="775e8-169">Get-Module</span><span class="sxs-lookup"><span data-stu-id="775e8-169">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="775e8-170">Import-Module</span><span class="sxs-lookup"><span data-stu-id="775e8-170">Import-Module</span></span>](Import-Module.md)

