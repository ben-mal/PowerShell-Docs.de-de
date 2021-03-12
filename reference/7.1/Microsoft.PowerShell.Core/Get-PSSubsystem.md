---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssubsystem?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSubsystem
ms.openlocfilehash: 1e08715562ab5a5b52193dacdd2c48cacb4540e8
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195531"
---
# <span data-ttu-id="3a656-102">Get-PSSubsystem</span><span class="sxs-lookup"><span data-stu-id="3a656-102">Get-PSSubsystem</span></span>

## <span data-ttu-id="3a656-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3a656-103">SYNOPSIS</span></span>
<span data-ttu-id="3a656-104">Ruft Informationen zu den in PowerShell registrierten Subsystemen ab.</span><span class="sxs-lookup"><span data-stu-id="3a656-104">Retrieves information about the subsystems registered in PowerShell.</span></span>

## <span data-ttu-id="3a656-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a656-105">SYNTAX</span></span>

### <span data-ttu-id="3a656-106">Getallset (Standard)</span><span class="sxs-lookup"><span data-stu-id="3a656-106">GetAllSet (Default)</span></span>

```
Get-PSSubsystem [<CommonParameters>]
```

### <span data-ttu-id="3a656-107">Getbykindset</span><span class="sxs-lookup"><span data-stu-id="3a656-107">GetByKindSet</span></span>

```
Get-PSSubsystem -Kind <SubsystemKind> [<CommonParameters>]
```

### <span data-ttu-id="3a656-108">Getbytypeset</span><span class="sxs-lookup"><span data-stu-id="3a656-108">GetByTypeSet</span></span>

```
Get-PSSubsystem -SubsystemType <Type> [<CommonParameters>]
```

## <span data-ttu-id="3a656-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3a656-109">DESCRIPTION</span></span>

<span data-ttu-id="3a656-110">Ruft Informationen zu den in PowerShell registrierten Subsystemen ab.</span><span class="sxs-lookup"><span data-stu-id="3a656-110">Retrieves information about the subsystems registered in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="3a656-111">Dies ist ein experimentelles Feature.</span><span class="sxs-lookup"><span data-stu-id="3a656-111">This is an experimental feature.</span></span> <span data-ttu-id="3a656-112">Dieses Cmdlet ist nur verfügbar, wenn das `PSSubsystemPluginModel` Feature aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3a656-112">This cmdlet is only available when the `PSSubsystemPluginModel` feature is enabled.</span></span> <span data-ttu-id="3a656-113">Weitere Informationen finden Sie unter [Verwenden von experimentellen Features](/powershell/scripting/learn/experimental-features).</span><span class="sxs-lookup"><span data-stu-id="3a656-113">For more information, see [Using Experimental Features](/powershell/scripting/learn/experimental-features).</span></span>

<span data-ttu-id="3a656-114">Es ermöglicht das Trennen von Komponenten von `System.Management.Automation.dll` in einzelne Subsysteme, die sich in einer eigenen Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="3a656-114">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="3a656-115">Diese Trennung reduziert den Speicherbedarf des Datenträgers der Kern-Engine von PowerShell. Zudem werden diese Komponenten zu optionalen Features für eine Minimalinstallation von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a656-115">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="3a656-116">Derzeit wird nur das Subsystem **CommandPredictor** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3a656-116">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="3a656-117">Dieses Subsystem wird zusammen mit dem PSReadLine-Modul zum Bereitstellen benutzerdefinierter Vorhersage-Plug-Ins verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a656-117">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="3a656-118">Zukünftig können **Job**, **CommandCompleter**, **Remoting** und andere Komponenten in Subsystemassemblys außerhalb von `System.Management.Automation.dll` getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="3a656-118">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

## <span data-ttu-id="3a656-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3a656-119">EXAMPLES</span></span>

### <span data-ttu-id="3a656-120">Beispiel 1: Anzeigen aller verfügbaren Subsysteme</span><span class="sxs-lookup"><span data-stu-id="3a656-120">Example 1 - Display all available subsystems</span></span>

```powershell
Get-PSSubsystem
```

```Output
Kind              SubsystemType     IsRegistered Implementations
----              -------------     ------------ ---------------
CommandPredictor  ICommandPredictor        False {}
```

### <span data-ttu-id="3a656-121">Beispiel 2: Anzeigen aller verfügbaren Subsysteme einer bestimmten Art</span><span class="sxs-lookup"><span data-stu-id="3a656-121">Example 2 - Display all available subsystems of a specific kind</span></span>

```powershell
PS> Get-PSSubsystem -Kind CommandPredictor | Format-List
```

```Output
Kind                      : CommandPredictor
SubsystemType             : System.Management.Automation.Subsystem.ICommandPredictor
AllowUnregistration       : True
AllowMultipleRegistration : True
RequiredCmdlets           : {}
RequiredFunctions         : {}
IsRegistered              : False
Implementations           : {}
```

## <span data-ttu-id="3a656-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3a656-122">PARAMETERS</span></span>

### <span data-ttu-id="3a656-123">-Kind</span><span class="sxs-lookup"><span data-stu-id="3a656-123">-Kind</span></span>


<span data-ttu-id="3a656-124">Gibt die Art des Subsystems an, das zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a656-124">Specifies the kind of subsystem to be returned.</span></span> <span data-ttu-id="3a656-125">Gültige Werte sind: `CommandPredictor` .</span><span class="sxs-lookup"><span data-stu-id="3a656-125">Valid values are: `CommandPredictor`.</span></span>

```yaml
Type: System.Management.Automation.Subsystem.SubsystemKind
Parameter Sets: GetByKindSet
Aliases:
Accepted values: CommandPredictor

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3a656-126">-Subsystemtype</span><span class="sxs-lookup"><span data-stu-id="3a656-126">-SubsystemType</span></span>

<span data-ttu-id="3a656-127">Gibt den Typ des Subsystems an, das zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a656-127">Specifies the type of subsystem to be returned.</span></span>

```yaml
Type: System.Type
Parameter Sets: GetByTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3a656-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3a656-128">CommonParameters</span></span>

<span data-ttu-id="3a656-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3a656-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3a656-130">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3a656-130">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3a656-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3a656-131">INPUTS</span></span>

### <span data-ttu-id="3a656-132">System. Management. Automation. Subsystem. subsystemkind</span><span class="sxs-lookup"><span data-stu-id="3a656-132">System.Management.Automation.Subsystem.SubsystemKind</span></span>

### <span data-ttu-id="3a656-133">System.Type</span><span class="sxs-lookup"><span data-stu-id="3a656-133">System.Type</span></span>

## <span data-ttu-id="3a656-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3a656-134">OUTPUTS</span></span>

### <span data-ttu-id="3a656-135">System. Management. Automation. Subsystem. subsysteminfo</span><span class="sxs-lookup"><span data-stu-id="3a656-135">System.Management.Automation.Subsystem.SubsystemInfo</span></span>

## <span data-ttu-id="3a656-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3a656-136">NOTES</span></span>

## <span data-ttu-id="3a656-137">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3a656-137">RELATED LINKS</span></span>

[<span data-ttu-id="3a656-138">about_experimental_features</span><span class="sxs-lookup"><span data-stu-id="3a656-138">about_experimental_features</span></span>](about/about_experimental_features.md)

[<span data-ttu-id="3a656-139">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="3a656-139">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="3a656-140">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="3a656-140">Enable-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="3a656-141">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="3a656-141">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="3a656-142">Verwenden experimenteller Features</span><span class="sxs-lookup"><span data-stu-id="3a656-142">Using Experimental Features</span></span>](/powershell/scripting/learn/experimental-features)
