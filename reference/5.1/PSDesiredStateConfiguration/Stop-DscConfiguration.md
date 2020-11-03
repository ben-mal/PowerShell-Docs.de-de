---
external help file: Stop-DscConfiguration.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/19/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/stop-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DscConfiguration
ms.openlocfilehash: 93c8585ae948dfa360a2ae8e2563670de8fd6e93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213599"
---
# <span data-ttu-id="e7a9d-103">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7a9d-103">Stop-DscConfiguration</span></span>

## <span data-ttu-id="e7a9d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="e7a9d-104">SYNOPSIS</span></span>
<span data-ttu-id="e7a9d-105">Beendet einen Konfigurations Auftrag, der ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-105">Stops a configuration job that is running.</span></span>

## <span data-ttu-id="e7a9d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e7a9d-106">SYNTAX</span></span>

### <span data-ttu-id="e7a9d-107">Alle</span><span class="sxs-lookup"><span data-stu-id="e7a9d-107">All</span></span>

```
Stop-DscConfiguration [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e7a9d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e7a9d-108">DESCRIPTION</span></span>

<span data-ttu-id="e7a9d-109">Mit dem- `Stop-DscConfiguration` Cmdlet wird ein Konfigurations Auftrag angehalten, auf dem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-109">The `Stop-DscConfiguration` cmdlet stops a configuration job that is running.</span></span> <span data-ttu-id="e7a9d-110">Legen Sie mithilfe von Common Information Model (CIM)-Sitzungen fest, auf welche Computer dieses Cmdlet angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-110">Specify which computers this cmdlet applies to by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="e7a9d-111">Wenn kein Konfigurations Auftrag ausgeführt wird, gibt dieses Cmdlet eine Warnmeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-111">If there's no configuration job running, this cmdlet returns a warning message.</span></span>

<span data-ttu-id="e7a9d-112">`Stop-DscConfiguration` ist nur als Teil des Updaterollup vom [November 2014 für Windows RT 8,1, Windows 8.1 und Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) aus der Microsoft-Support-Bibliothek verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-112">`Stop-DscConfiguration` is only available as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span> <span data-ttu-id="e7a9d-113">Bevor Sie dieses Cmdlet verwenden, lesen Sie die Informationen unter [Neues in Windows PowerShell 5,0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)</span><span class="sxs-lookup"><span data-stu-id="e7a9d-113">Before you use this cmdlet, review the information in [What's New in Windows PowerShell 5.0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)</span></span>

## <span data-ttu-id="e7a9d-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="e7a9d-114">EXAMPLES</span></span>

### <span data-ttu-id="e7a9d-115">Beispiel 1: Abbrechen eines Konfigurations Auftrags</span><span class="sxs-lookup"><span data-stu-id="e7a9d-115">Example 1: Stop a configuration job</span></span>

<span data-ttu-id="e7a9d-116">In diesem Beispiel wird eine CIM-Sitzung mithilfe des `New-CimSession` Cmdlets erstellt.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-116">In this example, a CIM session is created using the `New-CimSession` cmdlet.</span></span> <span data-ttu-id="e7a9d-117">Das **cimsession** -Objekt wird zum Abbrechen eines laufenden Konfigurations Auftrags verwendet.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-117">The **CimSession** object is used to stop a running configuration job.</span></span>

```powershell
$Session = New-CimSession -ComputerName Server01 -Credential ACCOUNTS\User01
Stop-DscConfiguration -CimSession $Session
```

<span data-ttu-id="e7a9d-118">`New-CimSession` verwendet den Computer **Name** -Parameter, um den Server01-Computer anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-118">`New-CimSession` uses the **ComputerName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="e7a9d-119">Der **Credential** -Parameter gibt das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-119">The **Credential** parameter specifies the user account.</span></span> <span data-ttu-id="e7a9d-120">Das **cimsession** -Objekt wird in der- `$Session` Variable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-120">The **CimSession** object is stored in the `$Session` variable.</span></span> <span data-ttu-id="e7a9d-121">Wenn der Befehl ausgeführt wird, werden Sie zur Eingabe des Kennworts für das Benutzerkonto aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-121">When the command is run, you're prompted for the user account's password.</span></span>

<span data-ttu-id="e7a9d-122">`Stop-DscConfiguration` verwendet den **cimsession** -Parameter und das in gespeicherte-Objekt `$Session` , um den Konfigurations Auftrag zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-122">`Stop-DscConfiguration` uses the **CimSession** parameter and the object stored in `$Session` to stop the configuration job.</span></span>

## <span data-ttu-id="e7a9d-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e7a9d-123">PARAMETERS</span></span>

### <span data-ttu-id="e7a9d-124">-AsJob</span><span class="sxs-lookup"><span data-stu-id="e7a9d-124">-AsJob</span></span>

<span data-ttu-id="e7a9d-125">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-125">Indicates that this cmdlet runs the command as a background job.</span></span> <span data-ttu-id="e7a9d-126">Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e7a9d-126">For more information about PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="e7a9d-127">Um den **AsJob** -Parameter zu verwenden, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-127">To use the **AsJob** parameter, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="e7a9d-128">Unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option **als Administrator ausführen** öffnen.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-128">On Windows Vista and later versions of the Windows operating system, you must open PowerShell with the **Run as administrator** option.</span></span> <span data-ttu-id="e7a9d-129">Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7a9d-129">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e7a9d-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="e7a9d-130">-CimSession</span></span>

<span data-ttu-id="e7a9d-131">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="e7a9d-132">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe von `New-CimSession` oder `Get-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="e7a9d-132">Enter a computer name or a session object, such as the output from `New-CimSession` or `Get-CimSession`.</span></span>

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

### <span data-ttu-id="e7a9d-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e7a9d-133">-Confirm</span></span>

<span data-ttu-id="e7a9d-134">`Stop-DscConfiguration` unterstützt den **Confirm** -Parameter nicht.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-134">`Stop-DscConfiguration` doesn't support the **Confirm** parameter.</span></span> <span data-ttu-id="e7a9d-135">Wenn der **Confirm** -Parameter verwendet wird, wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-135">If the **Confirm** parameter is used, an error is displayed.</span></span>

<span data-ttu-id="e7a9d-136">Für PowerShell-Cmdlets, die **Confirm** unterstützen, werden Sie mithilfe des-Parameters zur Überprüfung aufgefordert, bevor ein Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-136">For PowerShell cmdlets that support **Confirm** , using the parameter prompts you for verification before a command is run.</span></span>

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

### <span data-ttu-id="e7a9d-137">-Force</span><span class="sxs-lookup"><span data-stu-id="e7a9d-137">-Force</span></span>

<span data-ttu-id="e7a9d-138">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-138">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e7a9d-139">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="e7a9d-139">-ThrottleLimit</span></span>

<span data-ttu-id="e7a9d-140">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-140">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

<span data-ttu-id="e7a9d-141">Wenn dieser Parameter ausgelassen wird oder wenn der Wert `0` eingegeben wird, berechnet PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-141">If this parameter is omitted or a value of `0` is entered, PowerShell calculates an optimum throttle limit based on the number of CIM cmdlets that are running on the computer.</span></span> <span data-ttu-id="e7a9d-142">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-142">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="e7a9d-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e7a9d-143">-WhatIf</span></span>

<span data-ttu-id="e7a9d-144">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-144">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e7a9d-145">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="e7a9d-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e7a9d-146">CommonParameters</span></span>

<span data-ttu-id="e7a9d-147">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e7a9d-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e7a9d-148">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e7a9d-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e7a9d-149">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="e7a9d-149">INPUTS</span></span>

### <span data-ttu-id="e7a9d-150">Keine</span><span class="sxs-lookup"><span data-stu-id="e7a9d-150">None</span></span>

## <span data-ttu-id="e7a9d-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="e7a9d-151">OUTPUTS</span></span>

### <span data-ttu-id="e7a9d-152">Keine</span><span class="sxs-lookup"><span data-stu-id="e7a9d-152">None</span></span>

## <span data-ttu-id="e7a9d-153">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="e7a9d-153">NOTES</span></span>

## <span data-ttu-id="e7a9d-154">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="e7a9d-154">RELATED LINKS</span></span>

[<span data-ttu-id="e7a9d-155">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="e7a9d-155">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="e7a9d-156">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7a9d-156">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="e7a9d-157">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="e7a9d-157">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="e7a9d-158">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="e7a9d-158">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="e7a9d-159">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7a9d-159">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="e7a9d-160">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7a9d-160">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="e7a9d-161">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7a9d-161">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)

[<span data-ttu-id="e7a9d-162">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7a9d-162">Update-DscConfiguration</span></span>](Update-DscConfiguration.md)

[<span data-ttu-id="e7a9d-163">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="e7a9d-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)
