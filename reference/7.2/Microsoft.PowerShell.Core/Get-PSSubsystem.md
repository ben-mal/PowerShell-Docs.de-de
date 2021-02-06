---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 10/15/2020
schema: 2.0.0
ms.openlocfilehash: 5cb8ddbd06f8b7fdbadae0b7c738e26a68ff5c48
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603156"
---
# <span data-ttu-id="4992f-101">Get-PSSubsystem</span><span class="sxs-lookup"><span data-stu-id="4992f-101">Get-PSSubsystem</span></span>

## <span data-ttu-id="4992f-102">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4992f-102">SYNOPSIS</span></span>
<span data-ttu-id="4992f-103">Ruft Informationen zu den in PowerShell registrierten Subsystemen ab.</span><span class="sxs-lookup"><span data-stu-id="4992f-103">Retrieves information about the subsystems registered in PowerShell.</span></span>

## <span data-ttu-id="4992f-104">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4992f-104">SYNTAX</span></span>

### <span data-ttu-id="4992f-105">Getallset (Standard)</span><span class="sxs-lookup"><span data-stu-id="4992f-105">GetAllSet (Default)</span></span>

```
Get-PSSubsystem [<CommonParameters>]
```

### <span data-ttu-id="4992f-106">Getbykindset</span><span class="sxs-lookup"><span data-stu-id="4992f-106">GetByKindSet</span></span>

```
Get-PSSubsystem -Kind <SubsystemKind> [<CommonParameters>]
```

### <span data-ttu-id="4992f-107">Getbytypeset</span><span class="sxs-lookup"><span data-stu-id="4992f-107">GetByTypeSet</span></span>

```
Get-PSSubsystem -SubsystemType <Type> [<CommonParameters>]
```

## <span data-ttu-id="4992f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4992f-108">DESCRIPTION</span></span>

<span data-ttu-id="4992f-109">Ruft Informationen zu den in PowerShell registrierten Subsystemen ab.</span><span class="sxs-lookup"><span data-stu-id="4992f-109">Retrieves information about the subsystems registered in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="4992f-110">Dies ist ein experimentelles Feature.</span><span class="sxs-lookup"><span data-stu-id="4992f-110">This is an experimental feature.</span></span> <span data-ttu-id="4992f-111">Dieses Cmdlet ist nur verfügbar, wenn das `PSSubsystemPluginModel` Feature aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4992f-111">This cmdlet is only available when the `PSSubsystemPluginModel` feature is enabled.</span></span> <span data-ttu-id="4992f-112">Weitere Informationen finden Sie unter [Verwenden von experimentellen Features](/powershell/scripting/learn/experimental-features).</span><span class="sxs-lookup"><span data-stu-id="4992f-112">For more information, see [Using Experimental Features](/powershell/scripting/learn/experimental-features).</span></span>

<span data-ttu-id="4992f-113">Es ermöglicht das Trennen von Komponenten von `System.Management.Automation.dll` in einzelne Subsysteme, die sich in einer eigenen Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="4992f-113">The feature makes it possible to separate components of `System.Management.Automation.dll` into individual subsystems that reside in their own assembly.</span></span> <span data-ttu-id="4992f-114">Diese Trennung reduziert den Speicherbedarf des Datenträgers der Kern-Engine von PowerShell. Zudem werden diese Komponenten zu optionalen Features für eine Minimalinstallation von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4992f-114">This separation reduces the disk footprint of the core PowerShell engine and allows these components to become optional features for a minimal PowerShell installation.</span></span>

<span data-ttu-id="4992f-115">Derzeit wird nur das Subsystem **CommandPredictor** unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4992f-115">Currently, only the **CommandPredictor** subsystem is supported.</span></span> <span data-ttu-id="4992f-116">Dieses Subsystem wird zusammen mit dem PSReadLine-Modul zum Bereitstellen benutzerdefinierter Vorhersage-Plug-Ins verwendet.</span><span class="sxs-lookup"><span data-stu-id="4992f-116">This subsystem is used along with the PSReadLine module to provide custom prediction plugins.</span></span> <span data-ttu-id="4992f-117">Zukünftig können **Job**, **CommandCompleter**, **Remoting** und andere Komponenten in Subsystemassemblys außerhalb von `System.Management.Automation.dll` getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="4992f-117">In future, **Job**, **CommandCompleter**, **Remoting** and other components could be separated into subsystem assemblies outside of `System.Management.Automation.dll`.</span></span>

## <span data-ttu-id="4992f-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4992f-118">EXAMPLES</span></span>

### <span data-ttu-id="4992f-119">Beispiel 1: Anzeigen aller verfügbaren Subsysteme</span><span class="sxs-lookup"><span data-stu-id="4992f-119">Example 1 - Display all available subsystems</span></span>

```powershell
Get-PSSubsystem
```

```Output
Kind              SubsystemType     IsRegistered Implementations
----              -------------     ------------ ---------------
CommandPredictor  ICommandPredictor        False {}
```

### <span data-ttu-id="4992f-120">Beispiel 2: Anzeigen aller verfügbaren Subsysteme einer bestimmten Art</span><span class="sxs-lookup"><span data-stu-id="4992f-120">Example 2 - Display all available subsystems of a specific kind</span></span>

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

## <span data-ttu-id="4992f-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4992f-121">PARAMETERS</span></span>

### <span data-ttu-id="4992f-122">-Kind</span><span class="sxs-lookup"><span data-stu-id="4992f-122">-Kind</span></span>


<span data-ttu-id="4992f-123">Gibt die Art des Subsystems an, das zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="4992f-123">Specifies the kind of subsystem to be returned.</span></span> <span data-ttu-id="4992f-124">Gültige Werte sind: `CommandPredictor` .</span><span class="sxs-lookup"><span data-stu-id="4992f-124">Valid values are: `CommandPredictor`.</span></span>

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

### <span data-ttu-id="4992f-125">-Subsystemtype</span><span class="sxs-lookup"><span data-stu-id="4992f-125">-SubsystemType</span></span>

<span data-ttu-id="4992f-126">Gibt den Typ des Subsystems an, das zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="4992f-126">Specifies the type of subsystem to be returned.</span></span>

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

### <span data-ttu-id="4992f-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4992f-127">CommonParameters</span></span>

<span data-ttu-id="4992f-128">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4992f-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4992f-129">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4992f-129">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4992f-130">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4992f-130">INPUTS</span></span>

### <span data-ttu-id="4992f-131">System. Management. Automation. Subsystem. subsystemkind</span><span class="sxs-lookup"><span data-stu-id="4992f-131">System.Management.Automation.Subsystem.SubsystemKind</span></span>

### <span data-ttu-id="4992f-132">System.Type</span><span class="sxs-lookup"><span data-stu-id="4992f-132">System.Type</span></span>

## <span data-ttu-id="4992f-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4992f-133">OUTPUTS</span></span>

### <span data-ttu-id="4992f-134">System. Management. Automation. Subsystem. subsysteminfo</span><span class="sxs-lookup"><span data-stu-id="4992f-134">System.Management.Automation.Subsystem.SubsystemInfo</span></span>

## <span data-ttu-id="4992f-135">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4992f-135">NOTES</span></span>

## <span data-ttu-id="4992f-136">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4992f-136">RELATED LINKS</span></span>

[<span data-ttu-id="4992f-137">about_experimental_features</span><span class="sxs-lookup"><span data-stu-id="4992f-137">about_experimental_features</span></span>](about/about_experimental_features.md)

[<span data-ttu-id="4992f-138">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="4992f-138">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="4992f-139">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="4992f-139">Enable-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="4992f-140">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="4992f-140">Get-ExperimentalFeature</span></span>](Get-ExperimentalFeature.md)

[<span data-ttu-id="4992f-141">Verwenden experimenteller Features</span><span class="sxs-lookup"><span data-stu-id="4992f-141">Using Experimental Features</span></span>](/powershell/scripting/learn/experimental-features)
