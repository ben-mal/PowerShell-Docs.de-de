---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/publish-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-DscConfiguration
ms.openlocfilehash: 139de2bfdb88c443e7bc48d36e37e95644556bf5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215303"
---
# <span data-ttu-id="24077-103">Publish-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="24077-103">Publish-DscConfiguration</span></span>

## <span data-ttu-id="24077-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="24077-104">SYNOPSIS</span></span>
<span data-ttu-id="24077-105">Veröffentlicht eine DSC-Konfiguration für eine Gruppe von Computern.</span><span class="sxs-lookup"><span data-stu-id="24077-105">Publishes a DSC configuration to a set of computers.</span></span>

## <span data-ttu-id="24077-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="24077-106">SYNTAX</span></span>

### <span data-ttu-id="24077-107">Computernameset (Standard)</span><span class="sxs-lookup"><span data-stu-id="24077-107">ComputerNameSet (Default)</span></span>

```
Publish-DscConfiguration [-Path] <String> [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="24077-108">Cimsessionset</span><span class="sxs-lookup"><span data-stu-id="24077-108">CimSessionSet</span></span>

```
Publish-DscConfiguration [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="24077-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="24077-109">DESCRIPTION</span></span>
<span data-ttu-id="24077-110">Mit dem Cmdlet " **Publish-dscconfiguration** " wird ein Windows PowerShell DSC-Konfigurations Dokument auf einer Gruppe von Computern veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="24077-110">The **Publish-DscConfiguration** cmdlet publishes a Windows PowerShell Desired State Configuration (DSC) configuration document on set of computers.</span></span>
<span data-ttu-id="24077-111">Mit diesem Cmdlet wird die Konfiguration nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="24077-111">This cmdlet does not apply the configuration.</span></span>
<span data-ttu-id="24077-112">Konfigurationen werden entweder durch das Start-DscConfiguration-Cmdlet angewendet, wenn Sie mit dem Parameter *useexistierenden* verwendet werden oder wenn das DSC-Modul den Konsistenz Zeitraum ausführt.</span><span class="sxs-lookup"><span data-stu-id="24077-112">Configurations are applied by either the Start-DscConfiguration cmdlet when it is used with the *UseExisting* parameter or when the DSC engine runs its consistency cycle.</span></span>
<span data-ttu-id="24077-113">Die DSC-Engine wird auch als Local Configuration Manager (LCM) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="24077-113">The DSC engine is also known as the Local Configuration Manager (LCM).</span></span>

<span data-ttu-id="24077-114">Dieses Cmdlet ist besonders nützlich, wenn Fragmente mehrerer Konfigurations Dokumente übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="24077-114">This cmdlet is especially useful when fragments of multiple configuration documents are delivered.</span></span>
<span data-ttu-id="24077-115">Wenn mehrere Konfigurations Dokument Fragmente übermittelt werden, überschreiben Sie die älteren Konfigurations Dokument Fragmente.</span><span class="sxs-lookup"><span data-stu-id="24077-115">When multiple configuration documents fragments are delivered, they overwrite the older configuration document fragments.</span></span>

## <span data-ttu-id="24077-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="24077-116">EXAMPLES</span></span>

### <span data-ttu-id="24077-117">Beispiel 1: Veröffentlichen einer Konfiguration auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="24077-117">Example 1: Publish a configuration to a remote computer</span></span>

```
PS C:\> Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

<span data-ttu-id="24077-118">Dieser Befehl veröffentlicht eine Konfiguration auf einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="24077-118">This command publishes a configuration to a remote computer.</span></span>
<span data-ttu-id="24077-119">Der Benutzer, der das Cmdlet ausführt, sollte auf dem Remote Computer Administrator sein.</span><span class="sxs-lookup"><span data-stu-id="24077-119">The user who runs the cmdlet should be administrator on the remote computer.</span></span>

## <span data-ttu-id="24077-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="24077-120">PARAMETERS</span></span>

### <span data-ttu-id="24077-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="24077-121">-CimSession</span></span>
<span data-ttu-id="24077-122">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="24077-122">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="24077-123">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".</span><span class="sxs-lookup"><span data-stu-id="24077-123">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="24077-124">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="24077-124">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="24077-125">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="24077-125">-ComputerName</span></span>
<span data-ttu-id="24077-126">Gibt einen oder mehrere Computer an, auf denen dieses Cmdlet die Konfiguration veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="24077-126">Specifies one or more computers on which this cmdlet publishes the configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="24077-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="24077-127">-Credential</span></span>
<span data-ttu-id="24077-128">Gibt Anmelde Informationen an, die für den Zugriff auf das Zielgerät verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="24077-128">Specifies credentials that are used to access the target device.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="24077-129">-Force</span><span class="sxs-lookup"><span data-stu-id="24077-129">-Force</span></span>
<span data-ttu-id="24077-130">Erzwingt das Beenden des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="24077-130">Forces the cmdlet to finish.</span></span>
<span data-ttu-id="24077-131">Wenn der lokale Configuration Manager Aktualisierungs Modus auf "Pull" festgelegt ist, wird er von der Verwendung dieses Parameters in Push geändert und die Veröffentlichung der DSC-Konfiguration aktiviert.</span><span class="sxs-lookup"><span data-stu-id="24077-131">If the Local Configuration Manager refresh mode is set to PULL, usage of this parameter changes it to PUSH and enables publication of the DSC configuration.</span></span>
<span data-ttu-id="24077-132">Wenn auch eine ausstehende DSC-Konfiguration vorhanden ist, wird diese ausstehende Konfiguration von der Verwendung dieses Parameters überschrieben.</span><span class="sxs-lookup"><span data-stu-id="24077-132">Also, if a pending DSC configuration exists, usage of this parameter overwrites that pending configuration.</span></span>

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

### <span data-ttu-id="24077-133">-Path</span><span class="sxs-lookup"><span data-stu-id="24077-133">-Path</span></span>
<span data-ttu-id="24077-134">Gibt einen Pfad an, der Konfigurationen enthält, die auf den Ziel Computern veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="24077-134">Specifies a path that contains configurations to publish to target computers.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="24077-135">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="24077-135">-ThrottleLimit</span></span>
<span data-ttu-id="24077-136">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="24077-136">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="24077-137">Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="24077-137">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="24077-138">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="24077-138">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="24077-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="24077-139">-Confirm</span></span>
<span data-ttu-id="24077-140">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="24077-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="24077-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="24077-141">-WhatIf</span></span>
<span data-ttu-id="24077-142">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24077-142">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="24077-143">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="24077-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="24077-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="24077-144">CommonParameters</span></span>
<span data-ttu-id="24077-145">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="24077-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="24077-146">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="24077-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="24077-147">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="24077-147">INPUTS</span></span>

## <span data-ttu-id="24077-148">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="24077-148">OUTPUTS</span></span>

## <span data-ttu-id="24077-149">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="24077-149">NOTES</span></span>

## <span data-ttu-id="24077-150">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="24077-150">RELATED LINKS</span></span>

[<span data-ttu-id="24077-151">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="24077-151">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="24077-152">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="24077-152">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="24077-153">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="24077-153">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="24077-154">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="24077-154">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="24077-155">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="24077-155">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="24077-156">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="24077-156">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
