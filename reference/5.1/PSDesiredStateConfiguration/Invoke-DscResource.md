---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-DscResource
ms.openlocfilehash: d73d8d6a30e6b7c08b5a0b7988ea2327be34002a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215311"
---
# <span data-ttu-id="7e316-103">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="7e316-103">Invoke-DscResource</span></span>

## <span data-ttu-id="7e316-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7e316-104">SYNOPSIS</span></span>
<span data-ttu-id="7e316-105">Führt eine Methode einer angegebenen DSC-Ressource aus.</span><span class="sxs-lookup"><span data-stu-id="7e316-105">Runs a method of a specified DSC resource.</span></span>

## <span data-ttu-id="7e316-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7e316-106">SYNTAX</span></span>

```
Invoke-DscResource [-Name] <String> [-Method] <String> -ModuleName <ModuleSpecification> -Property <Hashtable>
 [<CommonParameters>]
```

## <span data-ttu-id="7e316-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7e316-107">DESCRIPTION</span></span>
<span data-ttu-id="7e316-108">Das Cmdlet "Start **-dscresource** " führt eine Methode einer angegebenen Windows PowerShell DSC-Ressource aus.</span><span class="sxs-lookup"><span data-stu-id="7e316-108">The **Invoke-DscResource** cmdlet runs a method of a specified Windows PowerShell Desired State Configuration (DSC) resource.</span></span>
<span data-ttu-id="7e316-109">Bevor Sie dieses Cmdlet ausführen, legen Sie den Aktualisierungs Modus des lokalen Configuration Manager (LCM) auf deaktiviert fest.</span><span class="sxs-lookup"><span data-stu-id="7e316-109">Before you run this cmdlet, set the refresh mode of the Local Configuration Manager (LCM) to Disabled.</span></span>

<span data-ttu-id="7e316-110">Dieses Cmdlet ruft eine DSC-Ressource direkt auf, ohne ein Konfigurationsdokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e316-110">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span>
<span data-ttu-id="7e316-111">Mithilfe dieses Cmdlets können Konfigurations Verwaltungs Produkte Windows mithilfe von DSC-Ressourcen verwalten.</span><span class="sxs-lookup"><span data-stu-id="7e316-111">Using this cmdlet, configuration management products can manage windows by using DSC resources.</span></span>
<span data-ttu-id="7e316-112">Dieses Cmdlet ermöglicht außerdem das Debuggen von Ressourcen, wenn die DSC-Engine oder der LCM mit aktiviertem Debugging ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7e316-112">This cmdlet also enables debugging of resources when the DSC engine or LCM is running with debugging enabled.</span></span>

## <span data-ttu-id="7e316-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7e316-113">EXAMPLES</span></span>

### <span data-ttu-id="7e316-114">Beispiel 1: Aufrufen der Set-Methode einer Ressource durch Angeben der obligatorischen Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7e316-114">Example 1: Invoke the Set method of a resource by specifying its mandatory properties</span></span>

```
PS C:\> Invoke-DscResource -Name Log -Method Set -Property @{Message = 'Hello World'} -ModuleName PSDesiredStateConfiguration
```

<span data-ttu-id="7e316-115">Dieser Befehl ruft die **Set** -Methode einer Ressource namens log auf und gibt eine **Nachrichten** Eigenschaft dafür an.</span><span class="sxs-lookup"><span data-stu-id="7e316-115">This command invokes the **Set** method of a resource named Log and specifies a **Message** property for it.</span></span>

### <span data-ttu-id="7e316-116">Beispiel 2: Aufrufen der Test Methode einer Ressource für ein bestimmtes Modul</span><span class="sxs-lookup"><span data-stu-id="7e316-116">Example 2: Invoke the Test method of a resource for a specified module</span></span>

```
PS C:\> Invoke-DscResource -Name WindowsProcess -Method Test -Property @{Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'; Arguments = ''} -ModuleName PSDesiredStateConfiguration
```

<span data-ttu-id="7e316-117">Mit diesem Befehl wird die **Test** Methode einer Ressource mit dem Namen "windowsprocess" aufgerufen, die im Modul "psdesiredstatus econfiguration" enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7e316-117">This command invokes the **Test** method of a resource named WindowsProcess, which is in the module named PSDesiredStateConfiguration.</span></span>

## <span data-ttu-id="7e316-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7e316-118">PARAMETERS</span></span>

### <span data-ttu-id="7e316-119">-Methode</span><span class="sxs-lookup"><span data-stu-id="7e316-119">-Method</span></span>
<span data-ttu-id="7e316-120">Gibt die Methode der Ressource an, die von diesem Cmdlet aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7e316-120">Specifies the method of the resource that this cmdlet invokes.</span></span> <span data-ttu-id="7e316-121">Die zulässigen Werte für diesen Parameter sind: Get, Set und Test.</span><span class="sxs-lookup"><span data-stu-id="7e316-121">The acceptable values for this parameter are: Get, Set, and Test.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Get, Set, Test

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7e316-122">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="7e316-122">-ModuleName</span></span>
<span data-ttu-id="7e316-123">Gibt den Namen des Moduls an, von dem dieses Cmdlet die angegebene Ressource aufruft.</span><span class="sxs-lookup"><span data-stu-id="7e316-123">Specifies the name of the module from which this cmdlet invokes the specified resource.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7e316-124">-Name</span><span class="sxs-lookup"><span data-stu-id="7e316-124">-Name</span></span>
<span data-ttu-id="7e316-125">Gibt den Namen der zu startenden DSC-Ressource an.</span><span class="sxs-lookup"><span data-stu-id="7e316-125">Specifies the name of the DSC resource to start.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7e316-126">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7e316-126">-Property</span></span>
<span data-ttu-id="7e316-127">Gibt den Namen der Ressourceneigenschaft und deren Wert in einer Hashtabelle als Schlüssel und Wert an.</span><span class="sxs-lookup"><span data-stu-id="7e316-127">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="7e316-128">Verwenden Sie das Cmdlet **Get-DscResource** zum Ermitteln von Ressourceneigenschaften und deren Typen.</span><span class="sxs-lookup"><span data-stu-id="7e316-128">Use the **Get-DscResource** cmdlet to discover resource properties and their types.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7e316-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7e316-129">CommonParameters</span></span>
<span data-ttu-id="7e316-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7e316-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7e316-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7e316-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7e316-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7e316-132">INPUTS</span></span>

## <span data-ttu-id="7e316-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7e316-133">OUTPUTS</span></span>

### <span data-ttu-id="7e316-134">Microsoft. Management. Infrastructure. ciminstance, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="7e316-134">Microsoft.Management.Infrastructure.CimInstance, System.Boolean</span></span>

## <span data-ttu-id="7e316-135">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7e316-135">NOTES</span></span>

## <span data-ttu-id="7e316-136">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7e316-136">RELATED LINKS</span></span>

[<span data-ttu-id="7e316-137">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="7e316-137">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="7e316-138">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="7e316-138">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="7e316-139">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="7e316-139">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="7e316-140">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="7e316-140">Get-DscResource</span></span>](Get-DscResource.md)

[<span data-ttu-id="7e316-141">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="7e316-141">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="7e316-142">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="7e316-142">Set-DscLocalConfigurationManager</span></span>](Set-DscLocalConfigurationManager.md)

[<span data-ttu-id="7e316-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="7e316-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="7e316-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="7e316-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
