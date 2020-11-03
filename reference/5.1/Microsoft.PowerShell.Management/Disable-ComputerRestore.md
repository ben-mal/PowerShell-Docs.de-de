---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/disable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ComputerRestore
ms.openlocfilehash: 941829c3caa0f6bb2f5712dda9eb7d8c36908062
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215495"
---
# <span data-ttu-id="904bd-103">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="904bd-103">Disable-ComputerRestore</span></span>

## <span data-ttu-id="904bd-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="904bd-104">SYNOPSIS</span></span>
<span data-ttu-id="904bd-105">Deaktiviert das Systemwiederherstellungsfeature auf dem angegebenen Dateisystemlaufwerk.</span><span class="sxs-lookup"><span data-stu-id="904bd-105">Disables the System Restore feature on the specified file system drive.</span></span>

## <span data-ttu-id="904bd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="904bd-106">SYNTAX</span></span>

```
Disable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="904bd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="904bd-107">DESCRIPTION</span></span>
<span data-ttu-id="904bd-108">Das Cmdlet " **Debuggen-computerrestore" deaktiviert** das System Wiederherstellungs Feature auf einem oder mehreren Datei System Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="904bd-108">The **Disable-ComputerRestore** cmdlet turns off the System Restore feature on one or more file system drives.</span></span>
<span data-ttu-id="904bd-109">Versuche, den Computer wiederherzustellen, haben deshalb keine Auswirkungen auf das angegebene Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="904bd-109">As a result, attempts to restore the computer do not affect the specified drive.</span></span>

<span data-ttu-id="904bd-110">Zum Deaktivieren der Systemwiederherstellung auf einem Laufwerk muss sie auf dem Systemlaufwerk deaktiviert werden, entweder zuerst oder gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="904bd-110">To disable System Restore on any drive, it must be disabled on the system drive, either first or concurrently.</span></span>

<span data-ttu-id="904bd-111">Verwenden Sie das Cmdlet %%amp;quot;Enable-ComputerRestore%%amp;quot;, um die Systemwiederherstellung erneut zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="904bd-111">To re-enable System Restore, use the Enable-ComputerRestore cmdlet.</span></span>
<span data-ttu-id="904bd-112">Mit %%amp;quot;Rstrui.exe%%amp;quot; können Sie den Status der Systemwiederherstellung für jedes Laufwerk ermitteln.</span><span class="sxs-lookup"><span data-stu-id="904bd-112">To find the state of System Restore for each drive, use Rstrui.exe.</span></span>

<span data-ttu-id="904bd-113">Systemwiederherstellungspunkte und die ComputerRestore-Cmdlets werden nur unter Clientbetriebssystemen wie Windows 7, Windows Vista und Windows XP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="904bd-113">System restore points and the ComputerRestore cmdlets are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="904bd-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="904bd-114">EXAMPLES</span></span>

### <span data-ttu-id="904bd-115">Beispiel 1: Deaktivieren der System Wiederherstellung auf dem angegebenen Laufwerk</span><span class="sxs-lookup"><span data-stu-id="904bd-115">Example 1: Disable System Restore on the specified drive</span></span>

```
PS C:\> Disable-ComputerRestore -Drive "C:\"
```

<span data-ttu-id="904bd-116">Dieser Befehl deaktiviert die Systemwiederherstellung auf Laufwerk %%amp;quot;C:%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="904bd-116">This command disables System Restore on the C: drive.</span></span>

### <span data-ttu-id="904bd-117">Beispiel 2: Deaktivieren der System Wiederherstellung auf mehreren Laufwerken</span><span class="sxs-lookup"><span data-stu-id="904bd-117">Example 2: Disable System Restore on multiple drives</span></span>

```
PS C:\> Disable-ComputerRestore "C:\", "D:\"
```

<span data-ttu-id="904bd-118">Dieser Befehl deaktiviert die Systemwiederherstellung auf den Laufwerken %%amp;quot;C:%%amp;quot; und %%amp;quot;D:%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="904bd-118">This command disables System Restore on the C: and D: drives.</span></span>
<span data-ttu-id="904bd-119">Der Befehl verwendet den *Drive* -Parameter, aber der Name des Laufwerks Parameters wird ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="904bd-119">The command uses the *Drive* parameter, but it omits the Drive parameter name.</span></span>

## <span data-ttu-id="904bd-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="904bd-120">PARAMETERS</span></span>

### <span data-ttu-id="904bd-121">-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="904bd-121">-Drive</span></span>
<span data-ttu-id="904bd-122">Gibt die Dateisystemlaufwerke an.</span><span class="sxs-lookup"><span data-stu-id="904bd-122">Specifies the file system drives.</span></span>
<span data-ttu-id="904bd-123">Geben Sie einen oder mehrere Dateisystem Laufwerk Buchstaben ein, gefolgt von einem Doppelpunkt und einem umgekehrten Schrägstrich und in Anführungszeichen (z. b. C:\). oder d:\.</span><span class="sxs-lookup"><span data-stu-id="904bd-123">Enter one or more file system drive letters, each followed by a colon and a backslash and enclosed in quotation marks, such as C:\ or D:\.</span></span>
<span data-ttu-id="904bd-124">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="904bd-124">This parameter is required.</span></span>

<span data-ttu-id="904bd-125">Mit diesem Cmdlet können Sie die Systemwiederherstellung auf einem Remotenetzlaufwerk nicht deaktivieren, auch wenn das Laufwerk dem lokalen Computer zugeordnet ist, und Sie können die Systemwiederherstellung nicht auf Laufwerken deaktivieren, die für die Systemwiederherstellung nicht geeignet sind, z. B. externe Laufwerke.</span><span class="sxs-lookup"><span data-stu-id="904bd-125">You cannot use this cmdlet to disable System Restore on a remote network drive, even if the drive is mapped to the local computer, and you cannot disable System Restore on drives that are not eligible for System Restore, such as external drives.</span></span>

<span data-ttu-id="904bd-126">Zum Deaktivieren der Systemwiederherstellung auf einem Laufwerk muss sie auf dem Systemlaufwerk deaktiviert werden, entweder zuerst oder gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="904bd-126">To disable System Restore on any drive, System Restore must be disabled on the system drive, either before or concurrently.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="904bd-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="904bd-127">-Confirm</span></span>
<span data-ttu-id="904bd-128">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="904bd-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="904bd-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="904bd-129">-WhatIf</span></span>
<span data-ttu-id="904bd-130">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="904bd-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="904bd-131">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="904bd-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="904bd-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="904bd-132">CommonParameters</span></span>
<span data-ttu-id="904bd-133">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="904bd-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="904bd-134">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="904bd-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="904bd-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="904bd-135">INPUTS</span></span>

### <span data-ttu-id="904bd-136">Keine</span><span class="sxs-lookup"><span data-stu-id="904bd-136">None</span></span>
<span data-ttu-id="904bd-137">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="904bd-137">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="904bd-138">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="904bd-138">OUTPUTS</span></span>

### <span data-ttu-id="904bd-139">Keine</span><span class="sxs-lookup"><span data-stu-id="904bd-139">None</span></span>
<span data-ttu-id="904bd-140">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="904bd-140">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="904bd-141">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="904bd-141">NOTES</span></span>

* <span data-ttu-id="904bd-142">Wenn Sie dieses Cmdlet unter Windows Vista und höheren Versionen von Windows ausführen möchten, öffnen Sie Windows PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="904bd-142">To run this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="904bd-143">Informationen zu den Dateisystem Laufwerken, die für die Systemwiederherstellung geeignet sind, finden Sie unter System in der Systemsteuerung auf der Registerkarte Systemschutz. Um diese Registerkarte in Windows PowerShell zu öffnen, geben Sie ein `SystemPropertiesProtection` .</span><span class="sxs-lookup"><span data-stu-id="904bd-143">To find the file system drives that are eligible for system restore, in System in Control Panel, see the System Protection tab. To open this tab in Windows PowerShell, type `SystemPropertiesProtection`.</span></span>

  <span data-ttu-id="904bd-144">Dieses Cmdlet verwendet die Windows-Verwaltungsinstrumentation (WMI) **SystemRestore** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="904bd-144">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

*

## <span data-ttu-id="904bd-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="904bd-145">RELATED LINKS</span></span>

[<span data-ttu-id="904bd-146">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="904bd-146">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="904bd-147">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="904bd-147">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="904bd-148">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="904bd-148">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="904bd-149">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="904bd-149">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="904bd-150">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="904bd-150">Restore-Computer</span></span>](Restore-Computer.md)
