---
external help file: Restore-DSCConfiguration.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/restore-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-DscConfiguration
ms.openlocfilehash: 823032f7665d9ec83faa59c37560510e049efdd2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215295"
---
# <span data-ttu-id="0775f-103">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0775f-103">Restore-DscConfiguration</span></span>

## <span data-ttu-id="0775f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0775f-104">SYNOPSIS</span></span>
<span data-ttu-id="0775f-105">Wendet die vorherige Konfiguration für den Knoten erneut an.</span><span class="sxs-lookup"><span data-stu-id="0775f-105">Reapplies the previous configuration for the node.</span></span>

## <span data-ttu-id="0775f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0775f-106">SYNTAX</span></span>

```
Restore-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="0775f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0775f-107">DESCRIPTION</span></span>
<span data-ttu-id="0775f-108">Das Cmdlet **Restore-dscconfiguration** wendet die vorherige Konfiguration für den Knoten erneut an, wenn eine vorherige Konfiguration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0775f-108">The **Restore-DscConfiguration** cmdlet reapplies the previous configuration for the node, if a previous configuration exists.</span></span>
<span data-ttu-id="0775f-109">Geben Sie Computer mithilfe von CIM-Sitzungen (Common Information Model) an.</span><span class="sxs-lookup"><span data-stu-id="0775f-109">Specify computers by using Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="0775f-110">Wenn Sie keinen Zielcomputer angeben, stellt das Cmdlet die Konfiguration des lokalen Computers wieder her.</span><span class="sxs-lookup"><span data-stu-id="0775f-110">If you do not specify a target computer, the cmdlet restores the configuration of the local computer.</span></span>
<span data-ttu-id="0775f-111">Wenn für einen bestimmten Knoten keine vorherige Konfiguration vorhanden ist, gibt dieses Cmdlet eine Fehlermeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="0775f-111">If there is no previous configuration for a particular node, this cmdlet returns an error message.</span></span>

<span data-ttu-id="0775f-112">Dieses Cmdlet unterstützt den **Confirm** -Parameter nicht.</span><span class="sxs-lookup"><span data-stu-id="0775f-112">This cmdlet does not support the **Confirm** parameter.</span></span>

## <span data-ttu-id="0775f-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0775f-113">EXAMPLES</span></span>

### <span data-ttu-id="0775f-114">Beispiel 1: Wiederherstellen der Konfiguration für den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="0775f-114">Example 1: Restore the configuration for the local computer</span></span>

```
PS C:\> Restore-DscConfiguration
```

<span data-ttu-id="0775f-115">Dieser Befehl stellt die Konfiguration für den lokalen Computer wieder her.</span><span class="sxs-lookup"><span data-stu-id="0775f-115">This command restores the configuration for the local computer.</span></span>

### <span data-ttu-id="0775f-116">Beispiel 2: Wiederherstellen der Konfiguration für einen angegebenen Computer</span><span class="sxs-lookup"><span data-stu-id="0775f-116">Example 2: Restore configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Restore-DscConfiguration -CimSession $Session
```

<span data-ttu-id="0775f-117">In diesem Beispiel wird die Konfiguration von einem von einer CIM-Sitzung angegebenen Computer wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="0775f-117">This example restores configuration on a computer specified by a CIM session.</span></span>
<span data-ttu-id="0775f-118">Das Beispiel erstellt eine CIM-Sitzung für einen Computer namens Server01 zur Verwendung mit dem Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0775f-118">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="0775f-119">Erstellen Sie alternativ ein Array von CIM-Sitzungen, um das Cmdlet für mehrere angegebene Computer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="0775f-119">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="0775f-120">Der erste Befehl erstellt eine CIM-Sitzung mithilfe des Cmdlets **New-CimSession** und speichert dann das **CimSession** -Objekt in der Variable $Session.</span><span class="sxs-lookup"><span data-stu-id="0775f-120">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="0775f-121">Der Befehl fordert Sie zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="0775f-121">The command prompts you for a password.</span></span>
<span data-ttu-id="0775f-122">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="0775f-122">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="0775f-123">Der zweite Befehl stellt die Konfiguration für die Computer wieder her, die durch die **CimSession** -Objekte identifiziert werden, die in der Variable $Session gespeichert sind, in diesem Fall der Computer namens Server01.</span><span class="sxs-lookup"><span data-stu-id="0775f-123">The second command restores the configuration for the computers identified by the **CimSession** objects stored in the $Session variable, in this case, the computer named Server01.</span></span>

## <span data-ttu-id="0775f-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0775f-124">PARAMETERS</span></span>

### <span data-ttu-id="0775f-125">-AsJob</span><span class="sxs-lookup"><span data-stu-id="0775f-125">-AsJob</span></span>
<span data-ttu-id="0775f-126">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="0775f-126">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="0775f-127">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0775f-127">-CimSession</span></span>
<span data-ttu-id="0775f-128">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="0775f-128">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="0775f-129">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " **New-cimsession** " oder " **Get-cimsession** ".</span><span class="sxs-lookup"><span data-stu-id="0775f-129">Enter a computer name or a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet.</span></span>

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

### <span data-ttu-id="0775f-130">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0775f-130">-ThrottleLimit</span></span>
<span data-ttu-id="0775f-131">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="0775f-131">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

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

### <span data-ttu-id="0775f-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0775f-132">-Confirm</span></span>
<span data-ttu-id="0775f-133">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="0775f-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0775f-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0775f-134">-WhatIf</span></span>
<span data-ttu-id="0775f-135">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0775f-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0775f-136">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0775f-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0775f-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0775f-137">CommonParameters</span></span>
<span data-ttu-id="0775f-138">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0775f-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0775f-139">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0775f-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0775f-140">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0775f-140">INPUTS</span></span>

## <span data-ttu-id="0775f-141">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0775f-141">OUTPUTS</span></span>

## <span data-ttu-id="0775f-142">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0775f-142">NOTES</span></span>

## <span data-ttu-id="0775f-143">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0775f-143">RELATED LINKS</span></span>

[<span data-ttu-id="0775f-144">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="0775f-144">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="0775f-145">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0775f-145">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="0775f-146">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="0775f-146">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="0775f-147">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0775f-147">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="0775f-148">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0775f-148">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
