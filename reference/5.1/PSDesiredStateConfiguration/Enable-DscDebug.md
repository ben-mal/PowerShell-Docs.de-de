---
external help file: Enable-DscDebug.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/enable-dscdebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-DscDebug
ms.openlocfilehash: 136481c5a1945c3d5cbd1ca7fc8ce5f580c39b0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215359"
---
# <span data-ttu-id="a1a0e-103">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="a1a0e-103">Enable-DscDebug</span></span>

## <span data-ttu-id="a1a0e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a1a0e-104">SYNOPSIS</span></span>
<span data-ttu-id="a1a0e-105">Startet das Debuggen aller DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-105">Starts debugging of all DSC resources.</span></span>

## <span data-ttu-id="a1a0e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a1a0e-106">SYNTAX</span></span>

```
Enable-DscDebug [-BreakAll] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="a1a0e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a1a0e-107">DESCRIPTION</span></span>
<span data-ttu-id="a1a0e-108">Mit dem Cmdlet " **enable-dscdebug** " wird Windows PowerShell DSC (DSC) zum Debuggen durch das DSC-Modul aktiviert, das auch als Local Configuration Manager (LCM) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-108">The **Enable-DscDebug** cmdlet enables Windows PowerShell Desired State Configuration (DSC) resource debugging by the DSC engine, which is also known as the Local Configuration Manager (LCM).</span></span>
<span data-ttu-id="a1a0e-109">Standardmäßig unterbrechen alle Ressourcen Instanzen den Debugger.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-109">By default, all resource instances break into the debugger.</span></span>

## <span data-ttu-id="a1a0e-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a1a0e-110">EXAMPLES</span></span>

### <span data-ttu-id="a1a0e-111">Beispiel 1: Starten des Debuggens</span><span class="sxs-lookup"><span data-stu-id="a1a0e-111">Example 1: Start debugging</span></span>

```
PS C:\> Enable-DscDebug -BreakAll
```

<span data-ttu-id="a1a0e-112">Mit diesem Befehl wird die DSC-Engine oder der LCM zum Starten des Debuggens von Ressourcen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-112">This command indicates to the DSC engine or LCM to start resource debugging.</span></span>
<span data-ttu-id="a1a0e-113">Beim nächsten Ausführen der Konfiguration wechselt der Prozess in den Debugger.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-113">The next time the configuration is run, the process enters the debugger.</span></span>

### <span data-ttu-id="a1a0e-114">Beispiel 2: Starten des Remote Debuggens</span><span class="sxs-lookup"><span data-stu-id="a1a0e-114">Example 2: Start remote debugging</span></span>

```
PS C:\> Enable-DscDebug -BreakAll -CimSession DeploymentServer
```

<span data-ttu-id="a1a0e-115">Dieser Befehl gibt an, dass die DSC-Engine des Remote Computers das Debuggen von Ressourcen starten soll.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-115">This command indicates to the DSC engine of the remote computer to start resource debugging.</span></span>

## <span data-ttu-id="a1a0e-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a1a0e-116">PARAMETERS</span></span>

### <span data-ttu-id="a1a0e-117">-AsJob</span><span class="sxs-lookup"><span data-stu-id="a1a0e-117">-AsJob</span></span>
<span data-ttu-id="a1a0e-118">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-118">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="a1a0e-119">-Breakall</span><span class="sxs-lookup"><span data-stu-id="a1a0e-119">-BreakAll</span></span>
<span data-ttu-id="a1a0e-120">Gibt an, dass alle Ressourcen in den Debugger eintreten, wenn eine Konfiguration ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-120">Indicates that all resources enter the debugger when a configuration runs.</span></span>

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

### <span data-ttu-id="a1a0e-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="a1a0e-121">-CimSession</span></span>
<span data-ttu-id="a1a0e-122">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-122">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="a1a0e-123">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".</span><span class="sxs-lookup"><span data-stu-id="a1a0e-123">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="a1a0e-124">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-124">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a1a0e-125">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="a1a0e-125">-ThrottleLimit</span></span>
<span data-ttu-id="a1a0e-126">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-126">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="a1a0e-127">Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-127">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="a1a0e-128">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-128">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="a1a0e-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a1a0e-129">-Confirm</span></span>
<span data-ttu-id="a1a0e-130">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a1a0e-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a1a0e-131">-WhatIf</span></span>
<span data-ttu-id="a1a0e-132">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a1a0e-133">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a1a0e-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a1a0e-134">CommonParameters</span></span>
<span data-ttu-id="a1a0e-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a1a0e-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a1a0e-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a1a0e-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a1a0e-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a1a0e-137">INPUTS</span></span>

## <span data-ttu-id="a1a0e-138">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a1a0e-138">OUTPUTS</span></span>

## <span data-ttu-id="a1a0e-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a1a0e-139">NOTES</span></span>

## <span data-ttu-id="a1a0e-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a1a0e-140">RELATED LINKS</span></span>

[<span data-ttu-id="a1a0e-141">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="a1a0e-141">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="a1a0e-142">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="a1a0e-142">Disable-DscDebug</span></span>](Disable-DscDebug.md)

[<span data-ttu-id="a1a0e-143">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1a0e-143">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="a1a0e-144">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="a1a0e-144">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="a1a0e-145">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1a0e-145">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="a1a0e-146">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1a0e-146">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="a1a0e-147">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1a0e-147">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
