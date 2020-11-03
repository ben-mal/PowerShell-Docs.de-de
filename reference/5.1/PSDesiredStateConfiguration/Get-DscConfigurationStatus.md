---
external help file: Get-DscConfigurationStatus.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfigurationStatus
ms.openlocfilehash: 0d59ce58a70eab68441ea1fe6097bbdf7792a54f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215364"
---
# <span data-ttu-id="f6274-103">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="f6274-103">Get-DscConfigurationStatus</span></span>

## <span data-ttu-id="f6274-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f6274-104">SYNOPSIS</span></span>
<span data-ttu-id="f6274-105">Ruft Daten zu abgeschlossenen Konfigurations Ausführungen ab.</span><span class="sxs-lookup"><span data-stu-id="f6274-105">Retrieves data about completed configuration runs.</span></span>

## <span data-ttu-id="f6274-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f6274-106">SYNTAX</span></span>

```
Get-DscConfigurationStatus [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## <span data-ttu-id="f6274-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f6274-107">DESCRIPTION</span></span>
<span data-ttu-id="f6274-108">Das Cmdlet " **Get-dscconfigurationstatus** " ruft ausführliche Informationen zu abgeschlossenen Konfigurations Ausführungen auf dem System ab.</span><span class="sxs-lookup"><span data-stu-id="f6274-108">The **Get-DscConfigurationStatus** cmdlet retrieves detailed information about completed configuration runs on the system.</span></span>
<span data-ttu-id="f6274-109">Standardmäßig werden die Informationen zur letzten Konfigurations Laufzeit zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f6274-109">By default, it returns the information about the last configuration run.</span></span>
<span data-ttu-id="f6274-110">Mit diesem Cmdlet können Sie Verlaufs Informationen zu Konfigurations Ausführungen suchen, z. b. wann die Konfigurationen ausgeführt wurden, den Status der Ausführungen, die Anzahl der Ressourcen in den Konfigurationen und welche Ressourcen erfolgreich waren oder fehlgeschlagen sind.</span><span class="sxs-lookup"><span data-stu-id="f6274-110">This cmdlet is useful for finding historical information about configuration runs, such as when the configurations were run, the status of the runs, the number of resources in the configurations, and which resources succeeded or failed.</span></span>

## <span data-ttu-id="f6274-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f6274-111">EXAMPLES</span></span>

### <span data-ttu-id="f6274-112">Beispiel 1: erhalten von Informationen zur letzten Konfigurations Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f6274-112">Example 1: Get information on the last configuration run</span></span>

```
PS C:\> Get-DscConfigurationStatus
```

<span data-ttu-id="f6274-113">Mit diesem Befehl werden Informationen zur letzten Konfigurations Laufzeit abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f6274-113">This command gets information on the last configuration run.</span></span>

### <span data-ttu-id="f6274-114">Beispiel 2: erhalten von Informationen zu allen Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="f6274-114">Example 2: Get information on all configurations</span></span>

```
PS C:\> Get-DscConfigurationStatus -All
```

<span data-ttu-id="f6274-115">Mit diesem Befehl werden Informationen zu allen Konfigurationen abgerufen, die auf dem System ausgeführt wurden, einschließlich der Windows PowerShell DSC-Konsistenzprüfung (DSC).</span><span class="sxs-lookup"><span data-stu-id="f6274-115">This command gets information about all the configurations that were run on the system, including the Windows PowerShell Desired State Configuration (DSC) consistency check.</span></span>

### <span data-ttu-id="f6274-116">Beispiel 3: erhalten von Informationen zur Konfiguration, die auf einem Remote Computer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f6274-116">Example 3: Get information on the configuration run on a remote computer</span></span>

```
PS C:\> Get-DscConfigurationStatus -CimSession "Server01"
```

<span data-ttu-id="f6274-117">Mit diesem Befehl werden die Details zur Konfigurations Ausführdauer des Remote Computers namens Server01 abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f6274-117">This command gets the configuration run details of the remote computer named Server01.</span></span>
<span data-ttu-id="f6274-118">Dadurch wird mithilfe des WSMAN-Transports eine Verbindung mit dem Remote Computer hergestellt, und der Benutzer, der eine Verbindung herstellt, muss auf dem Remote Computer über Administratorrechte verfügen.</span><span class="sxs-lookup"><span data-stu-id="f6274-118">This uses the WSMan transport to connect to the remote computer and requires that the connecting user be an administrator on the remote computer.</span></span>

## <span data-ttu-id="f6274-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f6274-119">PARAMETERS</span></span>

### <span data-ttu-id="f6274-120">-All</span><span class="sxs-lookup"><span data-stu-id="f6274-120">-All</span></span>
<span data-ttu-id="f6274-121">Gibt an, dass dieses Cmdlet Informationen zu allen Konfigurations Ausführungen auf dem Computer abruft, einschließlich der Konfigurationsanwendung und der Konsistenzprüfung.</span><span class="sxs-lookup"><span data-stu-id="f6274-121">Indicates that this cmdlet retrieves information about all the configuration runs on the computer, including the configuration application and the consistency check.</span></span>

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

### <span data-ttu-id="f6274-122">-AsJob</span><span class="sxs-lookup"><span data-stu-id="f6274-122">-AsJob</span></span>
<span data-ttu-id="f6274-123">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="f6274-123">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="f6274-124">-CimSession</span><span class="sxs-lookup"><span data-stu-id="f6274-124">-CimSession</span></span>
<span data-ttu-id="f6274-125">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="f6274-125">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="f6274-126">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".</span><span class="sxs-lookup"><span data-stu-id="f6274-126">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="f6274-127">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="f6274-127">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="f6274-128">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="f6274-128">-ThrottleLimit</span></span>
<span data-ttu-id="f6274-129">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="f6274-129">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="f6274-130">Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f6274-130">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="f6274-131">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="f6274-131">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="f6274-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f6274-132">CommonParameters</span></span>
<span data-ttu-id="f6274-133">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f6274-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f6274-134">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f6274-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f6274-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f6274-135">INPUTS</span></span>

## <span data-ttu-id="f6274-136">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f6274-136">OUTPUTS</span></span>

## <span data-ttu-id="f6274-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f6274-137">NOTES</span></span>

## <span data-ttu-id="f6274-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f6274-138">RELATED LINKS</span></span>

[<span data-ttu-id="f6274-139">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="f6274-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="f6274-140">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="f6274-140">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="f6274-141">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="f6274-141">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)

[<span data-ttu-id="f6274-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="f6274-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="f6274-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="f6274-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="f6274-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="f6274-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
