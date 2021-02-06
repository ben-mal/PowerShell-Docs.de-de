---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 732db5a049a68e059db6062d2f6c3f850d579adc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603517"
---
# <span data-ttu-id="066f4-102">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="066f4-102">Invoke-DscResource</span></span>

## <span data-ttu-id="066f4-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="066f4-103">SYNOPSIS</span></span>
<span data-ttu-id="066f4-104">Führt eine Methode einer angegebenen PowerShell DSC-Ressource aus.</span><span class="sxs-lookup"><span data-stu-id="066f4-104">Runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

## <span data-ttu-id="066f4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="066f4-105">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [[-ModuleName] <ModuleSpecification>] [-Method] <String>
 [-Property] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="066f4-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="066f4-106">DESCRIPTION</span></span>

<span data-ttu-id="066f4-107">Mit dem Cmdlet `Invoke-DscResource` wird eine Methode einer angegebenen PowerShell DSC-Ressource (Desired State Configuration) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="066f4-107">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="066f4-108">Dieses Cmdlet ruft eine DSC-Ressource direkt auf, ohne ein Konfigurationsdokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="066f4-108">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="066f4-109">Mithilfe dieses Cmdlets können Konfigurations Verwaltungs Produkte Windows oder Linux mithilfe von DSC-Ressourcen verwalten.</span><span class="sxs-lookup"><span data-stu-id="066f4-109">Using this cmdlet, configuration management products can manage windows or Linux by using DSC resources.</span></span> <span data-ttu-id="066f4-110">Dieses Cmdlet ermöglicht auch das Debuggen von Ressourcen, wenn die DSC-Engine mit aktiviertem Debuggen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="066f4-110">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="066f4-111">`Invoke-DscResource` ist eine experimentelle Funktion in PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="066f4-111">`Invoke-DscResource` is an experimental feature in PowerShell 7.</span></span> <span data-ttu-id="066f4-112">Um das Cmdlet zu verwenden, müssen Sie es mit dem folgenden Befehl aktivieren.</span><span class="sxs-lookup"><span data-stu-id="066f4-112">To use the cmdlet, you must enable it using the following command.</span></span>
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## <span data-ttu-id="066f4-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="066f4-113">EXAMPLES</span></span>

### <span data-ttu-id="066f4-114">Beispiel 1: Aufrufen der Set-Methode einer Ressource durch Angeben der obligatorischen Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="066f4-114">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

<span data-ttu-id="066f4-115">In diesem Beispiel wird die **Set** -Methode einer Ressource namens " **windowsprocess** " aufgerufen und die obligatorischen **Pfad** -und **Argument** Eigenschaften zum Starten des angegebenen Windows-Prozesses bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="066f4-115">This example invokes the **Set** method of a resource named **WindowsProcess** and provides the mandatory **Path** and **Arguments** properties to start the specified Windows process.</span></span>

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### <span data-ttu-id="066f4-116">Beispiel 2: Aufrufen der Test Methode einer Ressource für ein bestimmtes Modul</span><span class="sxs-lookup"><span data-stu-id="066f4-116">Example 2: Invoke the Test method of a resource for a specified module</span></span>

<span data-ttu-id="066f4-117">In diesem Beispiel wird die **Test** Methode einer Ressource mit dem Namen " **windowsprocess**" aufgerufen, die im Modul " **psdesiredstatus econfiguration**" enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="066f4-117">This example invokes the **Test** method of a resource named **WindowsProcess**, which is in the module named **PSDesiredStateConfiguration**.</span></span>

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## <span data-ttu-id="066f4-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="066f4-118">PARAMETERS</span></span>

### <span data-ttu-id="066f4-119">-Methode</span><span class="sxs-lookup"><span data-stu-id="066f4-119">-Method</span></span>

<span data-ttu-id="066f4-120">Gibt die Methode der Ressource an, die von diesem Cmdlet aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="066f4-120">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="066f4-121">Die zulässigen Werte für diesen Parameter sind: **Get**, **set** und **Test**.</span><span class="sxs-lookup"><span data-stu-id="066f4-121">The acceptable values for this parameter are: **Get**, **Set**, and **Test**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066f4-122">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="066f4-122">-ModuleName</span></span>

<span data-ttu-id="066f4-123">Gibt den Namen des Moduls an, von dem dieses Cmdlet die angegebene Ressource aufruft.</span><span class="sxs-lookup"><span data-stu-id="066f4-123">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="066f4-124">-Name</span><span class="sxs-lookup"><span data-stu-id="066f4-124">-Name</span></span>

<span data-ttu-id="066f4-125">Gibt den Namen der zu startenden DSC-Ressource an.</span><span class="sxs-lookup"><span data-stu-id="066f4-125">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="066f4-126">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="066f4-126">-Property</span></span>

<span data-ttu-id="066f4-127">Gibt den Namen der Ressourceneigenschaft und deren Wert in einer Hashtabelle als Schlüssel und Wert an.</span><span class="sxs-lookup"><span data-stu-id="066f4-127">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="066f4-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="066f4-128">CommonParameters</span></span>

<span data-ttu-id="066f4-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="066f4-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="066f4-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="066f4-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="066f4-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="066f4-131">INPUTS</span></span>

### <span data-ttu-id="066f4-132">System.String</span><span class="sxs-lookup"><span data-stu-id="066f4-132">System.String</span></span>

### <span data-ttu-id="066f4-133">Microsoft. PowerShell. Commands. modulespecification</span><span class="sxs-lookup"><span data-stu-id="066f4-133">Microsoft.PowerShell.Commands.ModuleSpecification</span></span>

## <span data-ttu-id="066f4-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="066f4-134">OUTPUTS</span></span>

### <span data-ttu-id="066f4-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="066f4-135">System.Object</span></span>

## <span data-ttu-id="066f4-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="066f4-136">NOTES</span></span>

- <span data-ttu-id="066f4-137">Zuvor wurden Windows PowerShell 5,1-Ressourcen im System Kontext ausgeführt, es sei denn, Sie wurden mit dem Schlüssel **psdscrunascredential** mit einem Benutzer Kontext angegeben.</span><span class="sxs-lookup"><span data-stu-id="066f4-137">Previously, Windows PowerShell 5.1 resources ran under System context unless specified with user context using the key **PsDscRunAsCredential**.</span></span> <span data-ttu-id="066f4-138">In PowerShell 7,0 werden Ressourcen im Kontext des Benutzers ausgeführt, und " **psdscrunascredential** " wird nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="066f4-138">In PowerShell 7.0, Resources run in the user's context, and **PsDscRunAsCredential** is no longer supported.</span></span> <span data-ttu-id="066f4-139">Vorherige Konfigurationen, die diesen Schlüssel verwenden, lösen eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="066f4-139">Previous configurations using this key will throw an exception.</span></span>

- <span data-ttu-id="066f4-140">Ab PowerShell 7 `Invoke-DscResource` unterstützt nicht mehr das Aufrufen von WMI DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="066f4-140">As of PowerShell 7, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="066f4-141">Dies gilt auch für die Ressourcen **File** und **Log** in **PSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="066f4-141">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

## <span data-ttu-id="066f4-142">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="066f4-142">RELATED LINKS</span></span>

[<span data-ttu-id="066f4-143">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="066f4-143">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="066f4-144">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="066f4-144">Get-DscResource</span></span>](Get-DscResource.md)
