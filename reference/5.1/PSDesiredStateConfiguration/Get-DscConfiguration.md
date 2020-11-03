---
external help file: Get-DSCConfiguration.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfiguration
ms.openlocfilehash: 42b24e72de4c4bcc9326d52861c08a05853b18e0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215356"
---
# <span data-ttu-id="ec265-103">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec265-103">Get-DscConfiguration</span></span>

## <span data-ttu-id="ec265-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ec265-104">SYNOPSIS</span></span>
<span data-ttu-id="ec265-105">Ruft die aktuelle Konfiguration der Knoten ab.</span><span class="sxs-lookup"><span data-stu-id="ec265-105">Gets the current configuration of the nodes.</span></span>

## <span data-ttu-id="ec265-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ec265-106">SYNTAX</span></span>

```
Get-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## <span data-ttu-id="ec265-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ec265-107">DESCRIPTION</span></span>
<span data-ttu-id="ec265-108">Mit dem Cmdlet " **Get-dscconfiguration** " wird die aktuelle Konfiguration der Knoten abgerufen, wenn die Konfiguration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ec265-108">The **Get-DscConfiguration** cmdlet gets the current configuration of the nodes, if the configuration exists.</span></span>
<span data-ttu-id="ec265-109">Geben Sie Computer mithilfe von CIM-Sitzungen (Common Information Model) an.</span><span class="sxs-lookup"><span data-stu-id="ec265-109">Specify computers by using Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="ec265-110">Wenn Sie keinen Zielcomputer angeben, ruft das Cmdlet die Konfiguration vom lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="ec265-110">If you do not specify a target computer, the cmdlet gets the configuration from the local computer.</span></span>

## <span data-ttu-id="ec265-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ec265-111">EXAMPLES</span></span>

### <span data-ttu-id="ec265-112">Beispiel 1: erhalten der Konfiguration für den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="ec265-112">Example 1: Get the configuration for the local computer</span></span>

```
PS C:\> Get-DscConfiguration
```

<span data-ttu-id="ec265-113">Mit diesem Befehl wird der aktuelle Zustand für den lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ec265-113">This command gets the current state for the local computer.</span></span>

### <span data-ttu-id="ec265-114">Beispiel 2: erhalten der Konfiguration für einen angegebenen Computer</span><span class="sxs-lookup"><span data-stu-id="ec265-114">Example 2: Get the configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Get-DscConfiguration -CimSession $Session
```

<span data-ttu-id="ec265-115">In diesem Beispiel wird der aktuelle Zustand von einem Computer abgerufen, der durch eine CIM-Sitzung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ec265-115">This example gets the current state from a computer specified by a CIM session.</span></span>
<span data-ttu-id="ec265-116">Das Beispiel erstellt eine CIM-Sitzung für einen Computer namens Server01 zur Verwendung mit dem Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec265-116">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="ec265-117">Erstellen Sie alternativ ein Array von CIM-Sitzungen, um das Cmdlet für mehrere angegebene Computer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ec265-117">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="ec265-118">Der erste Befehl erstellt eine CIM-Sitzung mithilfe des Cmdlets **New-CimSession** und speichert dann das **CimSession** -Objekt in der Variable **$Session** .</span><span class="sxs-lookup"><span data-stu-id="ec265-118">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the **$Session** variable.</span></span>
<span data-ttu-id="ec265-119">Der Befehl fordert Sie zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="ec265-119">The command prompts you for a password.</span></span>
<span data-ttu-id="ec265-120">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="ec265-120">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="ec265-121">Der zweite Befehl ruft die aktuelle Konfiguration für die Computer ab, die durch die **CimSession** -Objekte identifiziert werden, die in der Variable **$Session** gespeichert sind, in diesem Fall der Computer namens Server01.</span><span class="sxs-lookup"><span data-stu-id="ec265-121">The second command gets the current configuration for the computers identified by the **CimSession** objects stored in the **$Session** variable, in this case, the computer named Server01.</span></span>

## <span data-ttu-id="ec265-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ec265-122">PARAMETERS</span></span>

### <span data-ttu-id="ec265-123">-AsJob</span><span class="sxs-lookup"><span data-stu-id="ec265-123">-AsJob</span></span>
<span data-ttu-id="ec265-124">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="ec265-124">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="ec265-125">-CimSession</span><span class="sxs-lookup"><span data-stu-id="ec265-125">-CimSession</span></span>
<span data-ttu-id="ec265-126">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="ec265-126">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="ec265-127">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".</span><span class="sxs-lookup"><span data-stu-id="ec265-127">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="ec265-128">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="ec265-128">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="ec265-129">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="ec265-129">-ThrottleLimit</span></span>
<span data-ttu-id="ec265-130">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="ec265-130">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="ec265-131">Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec265-131">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="ec265-132">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="ec265-132">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="ec265-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ec265-133">CommonParameters</span></span>
<span data-ttu-id="ec265-134">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ec265-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ec265-135">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ec265-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ec265-136">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ec265-136">INPUTS</span></span>

## <span data-ttu-id="ec265-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ec265-137">OUTPUTS</span></span>

## <span data-ttu-id="ec265-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ec265-138">NOTES</span></span>

## <span data-ttu-id="ec265-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ec265-139">RELATED LINKS</span></span>

[<span data-ttu-id="ec265-140">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="ec265-140">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="ec265-141">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="ec265-141">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="ec265-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec265-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="ec265-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec265-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="ec265-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ec265-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
