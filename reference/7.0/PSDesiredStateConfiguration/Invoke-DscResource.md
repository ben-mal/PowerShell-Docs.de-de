---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: 4703586008d9044ae68fd7375db65f0d0a9b9980
ms.sourcegitcommit: f05f18154913d346012527c23020d48d87ccac74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "93219527"
---
# <span data-ttu-id="99e61-103">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="99e61-103">Invoke-DscResource</span></span>

## <span data-ttu-id="99e61-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="99e61-104">SYNOPSIS</span></span>
<span data-ttu-id="99e61-105">Führt eine Methode einer angegebenen PowerShell DSC-Ressource aus.</span><span class="sxs-lookup"><span data-stu-id="99e61-105">Runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

## <span data-ttu-id="99e61-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="99e61-106">SYNTAX</span></span>

```
Invoke-DscResource [[-Method] <Object>] [[-Name] <Object>] [[-Property] <Object>]
 [[-ModuleName] <Object>] [-AsJob] [<CommonParameters>]
```

## <span data-ttu-id="99e61-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="99e61-107">DESCRIPTION</span></span>

<span data-ttu-id="99e61-108">Mit dem Cmdlet `Invoke-DscResource` wird eine Methode einer angegebenen PowerShell DSC-Ressource (Desired State Configuration) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="99e61-108">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="99e61-109">Dieses Cmdlet ruft eine DSC-Ressource direkt auf, ohne ein Konfigurationsdokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="99e61-109">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="99e61-110">Mithilfe dieses Cmdlets können Konfigurations Verwaltungs Produkte Windows oder Linux mithilfe von DSC-Ressourcen verwalten.</span><span class="sxs-lookup"><span data-stu-id="99e61-110">Using this cmdlet, configuration management products can manage windows or Linux by using DSC resources.</span></span> <span data-ttu-id="99e61-111">Dieses Cmdlet ermöglicht auch das Debuggen von Ressourcen, wenn die DSC-Engine mit aktiviertem Debuggen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="99e61-111">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="99e61-112">`Invoke-DscResource` ist eine experimentelle Funktion in PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="99e61-112">`Invoke-DscResource` is an experimental feature in PowerShell 7.</span></span> <span data-ttu-id="99e61-113">Um das Cmdlet zu verwenden, müssen Sie es mit dem folgenden Befehl aktivieren.</span><span class="sxs-lookup"><span data-stu-id="99e61-113">To use the cmdlet, you must enable it using the following command.</span></span>
>
> `Enable-ExperimentalFeature PSDesiredStateConfiguration.InvokeDscResource`

## <span data-ttu-id="99e61-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="99e61-114">EXAMPLES</span></span>

### <span data-ttu-id="99e61-115">Beispiel 1: Aufrufen der Set-Methode einer Ressource durch Angeben der obligatorischen Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="99e61-115">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

<span data-ttu-id="99e61-116">In diesem Beispiel wird die **Set** -Methode einer Ressource namens " **windowsprocess** " aufgerufen und die obligatorischen **Pfad** -und **Argument** Eigenschaften zum Starten des angegebenen Windows-Prozesses bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="99e61-116">This example invokes the **Set** method of a resource named **WindowsProcess** and provides the mandatory **Path** and **Arguments** properties to start the specified Windows process.</span></span>

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

### <span data-ttu-id="99e61-117">Beispiel 2: Aufrufen der Test Methode einer Ressource für ein bestimmtes Modul</span><span class="sxs-lookup"><span data-stu-id="99e61-117">Example 2: Invoke the Test method of a resource for a specified module</span></span>

<span data-ttu-id="99e61-118">In diesem Beispiel wird die **Test** Methode einer Ressource mit dem Namen " **windowsprocess** " aufgerufen, die im Modul " **psdesiredstatus econfiguration** " enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="99e61-118">This example invokes the **Test** method of a resource named **WindowsProcess** , which is in the module named **PSDesiredStateConfiguration**.</span></span>

```powershell
$SplatParam = @{
  Name = 'WindowsProcess'
  ModuleName = 'PSDesiredStateConfiguration'
  Property = @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''}
  Method = Test
}

Invoke-DscResource @SplatParam
```

## <span data-ttu-id="99e61-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="99e61-119">PARAMETERS</span></span>

### <span data-ttu-id="99e61-120">-Methode</span><span class="sxs-lookup"><span data-stu-id="99e61-120">-Method</span></span>

<span data-ttu-id="99e61-121">Gibt die Methode der Ressource an, die von diesem Cmdlet aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="99e61-121">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="99e61-122">Die zulässigen Werte für diesen Parameter sind: **Get** , **set** und **Test**.</span><span class="sxs-lookup"><span data-stu-id="99e61-122">The acceptable values for this parameter are: **Get** , **Set** , and **Test**.</span></span>

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="99e61-123">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="99e61-123">-ModuleName</span></span>

<span data-ttu-id="99e61-124">Gibt den Namen des Moduls an, von dem dieses Cmdlet die angegebene Ressource aufruft.</span><span class="sxs-lookup"><span data-stu-id="99e61-124">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="99e61-125">-Name</span><span class="sxs-lookup"><span data-stu-id="99e61-125">-Name</span></span>

<span data-ttu-id="99e61-126">Gibt den Namen der zu startenden DSC-Ressource an.</span><span class="sxs-lookup"><span data-stu-id="99e61-126">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="99e61-127">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="99e61-127">-Property</span></span>

<span data-ttu-id="99e61-128">Gibt den Namen der Ressourceneigenschaft und deren Wert in einer Hashtabelle als Schlüssel und Wert an.</span><span class="sxs-lookup"><span data-stu-id="99e61-128">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span>

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="99e61-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="99e61-129">CommonParameters</span></span>

<span data-ttu-id="99e61-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="99e61-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="99e61-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="99e61-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="99e61-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="99e61-132">INPUTS</span></span>

## <span data-ttu-id="99e61-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="99e61-133">OUTPUTS</span></span>

### <span data-ttu-id="99e61-134">Microsoft. Management. Infrastructure. ciminstance, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="99e61-134">Microsoft.Management.Infrastructure.CimInstance, System.Boolean</span></span>

## <span data-ttu-id="99e61-135">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="99e61-135">NOTES</span></span>

- <span data-ttu-id="99e61-136">Zuvor wurden Windows PowerShell 5,1-Ressourcen im System Kontext ausgeführt, es sei denn, Sie wurden mit dem Schlüssel **psdscrunascredential** mit einem Benutzer Kontext angegeben.</span><span class="sxs-lookup"><span data-stu-id="99e61-136">Previously, Windows PowerShell 5.1 resources ran under System context unless specified with user context using the key **PsDscRunAsCredential**.</span></span> <span data-ttu-id="99e61-137">In PowerShell 7,0 werden Ressourcen im Kontext des Benutzers ausgeführt, und " **psdscrunascredential** " wird nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99e61-137">In PowerShell 7.0, Resources run in the user's context, and **PsDscRunAsCredential** is no longer supported.</span></span> <span data-ttu-id="99e61-138">Vorherige Konfigurationen, die diesen Schlüssel verwenden, lösen eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="99e61-138">Previous configurations using this key will throw an exception.</span></span>

- <span data-ttu-id="99e61-139">Ab PowerShell 7 `Invoke-DscResource` unterstützt nicht mehr das Aufrufen von WMI DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="99e61-139">As of PowerShell 7, `Invoke-DscResource` no longer supports invoking WMI DSC resources.</span></span> <span data-ttu-id="99e61-140">Dies gilt auch für die Ressourcen **File** und **Log** in **PSDesiredStateConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="99e61-140">This includes the **File** and **Log** resources in **PSDesiredStateConfiguration**.</span></span>

## <span data-ttu-id="99e61-141">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="99e61-141">RELATED LINKS</span></span>

[<span data-ttu-id="99e61-142">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="99e61-142">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="99e61-143">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="99e61-143">Get-DscResource</span></span>](Get-DscResource.md)
