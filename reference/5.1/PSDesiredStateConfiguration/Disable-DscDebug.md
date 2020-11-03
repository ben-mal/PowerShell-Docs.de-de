---
external help file: Disable-DscDebug.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/disable-dscdebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-DscDebug
ms.openlocfilehash: fdaba8358772f559a33117c796a923d774b009cb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215351"
---
# <span data-ttu-id="bab92-103">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="bab92-103">Disable-DscDebug</span></span>

## <span data-ttu-id="bab92-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bab92-104">SYNOPSIS</span></span>
<span data-ttu-id="bab92-105">Beendet das Debuggen von DSC-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="bab92-105">Stops debugging of DSC resources.</span></span>

## <span data-ttu-id="bab92-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bab92-106">SYNTAX</span></span>

```
Disable-DscDebug [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="bab92-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bab92-107">DESCRIPTION</span></span>
<span data-ttu-id="bab92-108">Das Cmdlet " **Debuggen-dscdebug** " fordert an, dass das Windows PowerShell DSC-Modul das Debuggen von DSC-Ressourcen stoppt.</span><span class="sxs-lookup"><span data-stu-id="bab92-108">The **Disable-DscDebug** cmdlet requests that the Windows PowerShell Desired State Configuration (DSC) engine stop debugging of DSC resources.</span></span>
<span data-ttu-id="bab92-109">Dieses Cmdlet hat keine Auswirkung, wenn sich die DSC-Engine derzeit nicht im Debugmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="bab92-109">This cmdlet has no effect if the DSC engine is not currently in debugging mode.</span></span>

## <span data-ttu-id="bab92-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bab92-110">EXAMPLES</span></span>

### <span data-ttu-id="bab92-111">Beispiel 1: Debuggen von Ressourcen verhindern</span><span class="sxs-lookup"><span data-stu-id="bab92-111">Example 1: Stop resource debugging</span></span>

```
PS C:\> Disable-DscDebug
```

<span data-ttu-id="bab92-112">Dieser Befehl gibt an, dass das DSC-Modul auf dem lokalen Configuration Manager (LCM) das Debuggen von Ressourcen stoppt.</span><span class="sxs-lookup"><span data-stu-id="bab92-112">This command indicates to the DSC engine on the Local Configuration Manager (LCM) to stop resource debugging.</span></span>

### <span data-ttu-id="bab92-113">Beispiel 2: Überprüfen des Engine-Zustands und Debuggen</span><span class="sxs-lookup"><span data-stu-id="bab92-113">Example 2: Check the engine state and stop debugging</span></span>

```
PS C:\> if((Get-DscLocalConfigurationManager).DebugMode -like '*Break*'){Disable-DscDebug}
```

<span data-ttu-id="bab92-114">Mit diesem Befehl wird der DSC-Engine-Status überprüft und das Debuggen von Ressourcen nur beendet</span><span class="sxs-lookup"><span data-stu-id="bab92-114">This command checks the DSC engine state, and stops resource debugging only if it is already in debugging mode</span></span>

## <span data-ttu-id="bab92-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bab92-115">PARAMETERS</span></span>

### <span data-ttu-id="bab92-116">-AsJob</span><span class="sxs-lookup"><span data-stu-id="bab92-116">-AsJob</span></span>
<span data-ttu-id="bab92-117">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="bab92-117">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="bab92-118">-CimSession</span><span class="sxs-lookup"><span data-stu-id="bab92-118">-CimSession</span></span>
<span data-ttu-id="bab92-119">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="bab92-119">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="bab92-120">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".</span><span class="sxs-lookup"><span data-stu-id="bab92-120">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="bab92-121">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="bab92-121">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="bab92-122">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="bab92-122">-ThrottleLimit</span></span>
<span data-ttu-id="bab92-123">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="bab92-123">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="bab92-124">Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bab92-124">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="bab92-125">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="bab92-125">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="bab92-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bab92-126">-Confirm</span></span>
<span data-ttu-id="bab92-127">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="bab92-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bab92-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bab92-128">-WhatIf</span></span>
<span data-ttu-id="bab92-129">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bab92-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bab92-130">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bab92-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bab92-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bab92-131">CommonParameters</span></span>
<span data-ttu-id="bab92-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bab92-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bab92-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bab92-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bab92-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bab92-134">INPUTS</span></span>

## <span data-ttu-id="bab92-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bab92-135">OUTPUTS</span></span>

## <span data-ttu-id="bab92-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bab92-136">NOTES</span></span>

## <span data-ttu-id="bab92-137">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bab92-137">RELATED LINKS</span></span>

[<span data-ttu-id="bab92-138">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="bab92-138">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="bab92-139">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="bab92-139">Enable-DscDebug</span></span>](Enable-DscDebug.md)

[<span data-ttu-id="bab92-140">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="bab92-140">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="bab92-141">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="bab92-141">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)

[<span data-ttu-id="bab92-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bab92-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="bab92-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bab92-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="bab92-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bab92-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
