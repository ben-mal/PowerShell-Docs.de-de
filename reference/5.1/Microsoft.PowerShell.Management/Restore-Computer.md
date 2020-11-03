---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restore-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-Computer
ms.openlocfilehash: 824e9a24693c7a7de01358a048a0df55be333263
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214476"
---
# <span data-ttu-id="08a24-103">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="08a24-103">Restore-Computer</span></span>

## <span data-ttu-id="08a24-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="08a24-104">SYNOPSIS</span></span>
<span data-ttu-id="08a24-105">Startet eine Systemwiederherstellung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="08a24-105">Starts a system restore on the local computer.</span></span>

## <span data-ttu-id="08a24-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08a24-106">SYNTAX</span></span>

```
Restore-Computer [-RestorePoint] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="08a24-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08a24-107">DESCRIPTION</span></span>
<span data-ttu-id="08a24-108">Mit dem Cmdlet " **Restore-Computer** " wird der lokale Computer am angegebenen Systemwiederherstellungspunkt wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="08a24-108">The **Restore-Computer** cmdlet restores the local computer to the specified system restore point.</span></span>

<span data-ttu-id="08a24-109">**Restore-Computer** startet den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="08a24-109">**Restore-Computer** restarts the computer.</span></span>
<span data-ttu-id="08a24-110">Die Wiederherstellung wird während des Neustartvorgangs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="08a24-110">The restore is completed during the restart operation.</span></span>

<span data-ttu-id="08a24-111">System Wiederherstellungspunkte und **Restore-Computer** werden nur unter Client Betriebssystemen wie Windows 7, Windows Vista und Windows XP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="08a24-111">System restore points and **Restore-Computer** are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="08a24-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="08a24-112">EXAMPLES</span></span>

### <span data-ttu-id="08a24-113">Beispiel 1: Wiederherstellen des lokalen Computers</span><span class="sxs-lookup"><span data-stu-id="08a24-113">Example 1: Restore the local computer</span></span>

```
PS C:\> Restore-Computer -RestorePoint 253
```

<span data-ttu-id="08a24-114">Mit diesem Befehl wird der lokale Computer am Wiederherstellungspunkt mit der Sequenznummer 253 wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="08a24-114">This command restores the local computer to the restore point that has sequence number 253.</span></span>

### <span data-ttu-id="08a24-115">Beispiel 2: Wiederherstellen des lokalen Computers mit Bestätigung</span><span class="sxs-lookup"><span data-stu-id="08a24-115">Example 2: Restore the local computer with confirmation</span></span>

```
PS C:\> Restore-Computer -RestorePoint 255 -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Restore-Computer" .
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="08a24-116">Mit diesem Befehl wird der lokale Computer am Wiederherstellungspunkt mit der Sequenznummer 255 wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="08a24-116">This command restores the local computer to the restore point that has sequence number 255.</span></span>
<span data-ttu-id="08a24-117">Er verwendet den *Confirm* -Parameter, um den Benutzer aufzufordern, bevor der Vorgang tatsächlich durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="08a24-117">It uses the *Confirm* parameter to prompt the user before actually performing the operation.</span></span>

### <span data-ttu-id="08a24-118">Beispiel 3: Wiederherstellen eines Computers und Überprüfen des Status</span><span class="sxs-lookup"><span data-stu-id="08a24-118">Example 3: Restore a computer and check the status</span></span>

```
PS C:\> Get-ComputerRestorePoint
PS C:\> Restore-Computer -RestorePoint 255
PS C:\> Get-ComputerRestorePoint -LastStatus
```

<span data-ttu-id="08a24-119">Mit diesen Befehlen wird eine Systemwiederherstellung ausgeführt und ihr Status überprüft.</span><span class="sxs-lookup"><span data-stu-id="08a24-119">These commands run a system restore and then check its status.</span></span>

<span data-ttu-id="08a24-120">Der erste Befehl verwendet **Get-ComputerRestorePoint** , um die Wiederherstellungspunkte auf dem lokalen Computer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="08a24-120">The first command uses **Get-ComputerRestorePoint** to get the restore points on the local computer.</span></span>

<span data-ttu-id="08a24-121">Mit dem zweiten Befehl wird der Computer am Wiederherstellungspunkt mit der Sequenznummer 255 wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="08a24-121">The second command restores the computer to the restore point with sequence number 255.</span></span>

<span data-ttu-id="08a24-122">Der dritte Befehl verwendet den *laststatus* -Parameter des *Get-ComputerRestorePoint-* Cmdlets, um den Status des Wiederherstellungs Vorgangs zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="08a24-122">The third command uses the *LastStatus* parameter of *Get-ComputerRestorePoint* cmdlet to check the status of the restore operation.</span></span>
<span data-ttu-id="08a24-123">Da **Restore-Computer** einen Neustart erzwingt, wird dieser Befehl nach dem Neustart des Computers eingegeben.</span><span class="sxs-lookup"><span data-stu-id="08a24-123">Because **Restore-Computer** forces a restart, this command would be entered after the computer restarts.</span></span>

## <span data-ttu-id="08a24-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08a24-124">PARAMETERS</span></span>

### <span data-ttu-id="08a24-125">-RestorePoint</span><span class="sxs-lookup"><span data-stu-id="08a24-125">-RestorePoint</span></span>
<span data-ttu-id="08a24-126">Gibt die Sequenznummer des Wiederherstellungspunkts an.</span><span class="sxs-lookup"><span data-stu-id="08a24-126">Specifies the sequence number of the restore point.</span></span>
<span data-ttu-id="08a24-127">Verwenden Sie das Cmdlet "Get-ComputerRestorePoint", um die Sequenznummer zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="08a24-127">To find the sequence number, use the Get-ComputerRestorePoint cmdlet.</span></span>
<span data-ttu-id="08a24-128">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="08a24-128">This parameter is required.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SequenceNumber, SN, RP

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08a24-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="08a24-129">-Confirm</span></span>
<span data-ttu-id="08a24-130">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="08a24-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="08a24-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="08a24-131">-WhatIf</span></span>
<span data-ttu-id="08a24-132">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="08a24-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="08a24-133">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="08a24-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="08a24-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="08a24-134">CommonParameters</span></span>
<span data-ttu-id="08a24-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="08a24-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="08a24-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="08a24-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="08a24-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="08a24-137">INPUTS</span></span>

### <span data-ttu-id="08a24-138">Keine</span><span class="sxs-lookup"><span data-stu-id="08a24-138">None</span></span>
<span data-ttu-id="08a24-139">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="08a24-139">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="08a24-140">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="08a24-140">OUTPUTS</span></span>

### <span data-ttu-id="08a24-141">Keine</span><span class="sxs-lookup"><span data-stu-id="08a24-141">None</span></span>
<span data-ttu-id="08a24-142">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="08a24-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="08a24-143">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="08a24-143">NOTES</span></span>

* <span data-ttu-id="08a24-144">Wenn Sie einen Restore-Computer Befehl unter Windows Vista und höheren Versionen des Windows-Betriebssystems ausführen möchten, öffnen Sie Windows PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="08a24-144">To run a Restore-Computer command on Windows Vista and later versions of the Windows operating system, open Windows PowerShell by using the Run as administrator option.</span></span>
* <span data-ttu-id="08a24-145">Dieses Cmdlet verwendet die Windows-Verwaltungsinstrumentation (WMI) **SystemRestore** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="08a24-145">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

## <span data-ttu-id="08a24-146">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="08a24-146">RELATED LINKS</span></span>

[<span data-ttu-id="08a24-147">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="08a24-147">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="08a24-148">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="08a24-148">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="08a24-149">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="08a24-149">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="08a24-150">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="08a24-150">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="08a24-151">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="08a24-151">Restart-Computer</span></span>](Restart-Computer.md)
