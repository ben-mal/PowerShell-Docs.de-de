---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/enable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ComputerRestore
ms.openlocfilehash: f9616a7f9af4dd2fa45e150bb64eef65427b4947
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215492"
---
# <span data-ttu-id="bc641-103">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="bc641-103">Enable-ComputerRestore</span></span>

## <span data-ttu-id="bc641-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bc641-104">SYNOPSIS</span></span>
<span data-ttu-id="bc641-105">Aktiviert das Systemwiederherstellungsfeature auf dem angegebenen Dateisystemlaufwerk.</span><span class="sxs-lookup"><span data-stu-id="bc641-105">Enables the System Restore feature on the specified file system drive.</span></span>

## <span data-ttu-id="bc641-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bc641-106">SYNTAX</span></span>

```
Enable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bc641-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bc641-107">DESCRIPTION</span></span>
<span data-ttu-id="bc641-108">Das **enable-computerrestore-** Cmdlet aktiviert das System Wiederherstellungs Feature auf einem oder mehreren Datei System Laufwerken.</span><span class="sxs-lookup"><span data-stu-id="bc641-108">The **Enable-ComputerRestore** cmdlet turns on the System Restore feature on one or more file system drives.</span></span>
<span data-ttu-id="bc641-109">Sie können daher mit Tools wie dem Cmdlet %%amp;quot;Restore-Computer%%amp;quot; den Computer in einem vorherigen Status wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="bc641-109">As a result, you can use tools, such as the Restore-Computer cmdlet, to restore the computer to a previous state.</span></span>

<span data-ttu-id="bc641-110">Standardmäßig ist die Systemwiederherstellung auf allen freigegebenen Laufwerken aktiviert, Sie können sie jedoch deaktivieren, z. B. mit dem Cmdlet %%amp;quot;Disable-ComputerRestore%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="bc641-110">By default, System Restore is enabled on all eligible drives, but you can disable it, such as by using the Disable-ComputerRestore cmdlet.</span></span>
<span data-ttu-id="bc641-111">Zum Aktivieren (oder erneuten Aktivieren) der Systemwiederherstellung auf einem Laufwerk muss sie auf dem Systemlaufwerk aktiviert werden, entweder zuerst oder gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="bc641-111">To enable (or re-enable) System Restore on any drive, it must be enabled on the system drive, either first or concurrently.</span></span>
<span data-ttu-id="bc641-112">Mit %%amp;quot;Rstrui.exe%%amp;quot; können Sie den Status der Systemwiederherstellung für jedes Laufwerk ermitteln.</span><span class="sxs-lookup"><span data-stu-id="bc641-112">To find the state of System Restore for each drive, use Rstrui.exe.</span></span>

<span data-ttu-id="bc641-113">Systemwiederherstellungspunkte und die ComputerRestore-Cmdlets werden nur unter Clientbetriebssystemen wie Windows 7, Windows Vista und Windows XP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bc641-113">System restore points and the ComputerRestore cmdlets are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="bc641-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bc641-114">EXAMPLES</span></span>

### <span data-ttu-id="bc641-115">Beispiel 1: Aktivieren der System Wiederherstellung auf dem angegebenen Laufwerk</span><span class="sxs-lookup"><span data-stu-id="bc641-115">Example 1: Enable System Restore on the specified drive</span></span>

```
PS C:\> Enable-ComputerRestore -Drive "C:\"
```

<span data-ttu-id="bc641-116">Dieser Befehl aktiviert die Systemwiederherstellung auf Laufwerk %%amp;quot;C:%%amp;quot; des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="bc641-116">This command enables System Restore on the C: drive of the local computer.</span></span>

### <span data-ttu-id="bc641-117">Beispiel 2: Aktivieren der System Wiederherstellung auf mehreren Laufwerken</span><span class="sxs-lookup"><span data-stu-id="bc641-117">Example 2: Enable System Restore on multiple drives</span></span>

```
PS C:\> Enable-ComputerRestore -Drive "C:\", "D:\"
```

<span data-ttu-id="bc641-118">Dieser Befehl aktiviert die Systemwiederherstellung auf den Laufwerken %%amp;quot;C:%%amp;quot; und %%amp;quot;D:%%amp;quot; des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="bc641-118">This command enables System Restore on the C: and D: drives of the local computer.</span></span>

## <span data-ttu-id="bc641-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bc641-119">PARAMETERS</span></span>

### <span data-ttu-id="bc641-120">-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="bc641-120">-Drive</span></span>
<span data-ttu-id="bc641-121">Gibt die Dateisystemlaufwerke an.</span><span class="sxs-lookup"><span data-stu-id="bc641-121">Specifies the file system drives.</span></span>
<span data-ttu-id="bc641-122">Geben Sie einen oder mehrere Dateisystem Laufwerk Buchstaben ein, gefolgt von einem Doppelpunkt und einem umgekehrten Schrägstrich und in Anführungszeichen (z. b. C:\). oder d:\.</span><span class="sxs-lookup"><span data-stu-id="bc641-122">Enter one or more file system drive letters, each followed by a colon and a backslash and enclosed in quotation marks, such as C:\ or D:\.</span></span>
<span data-ttu-id="bc641-123">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bc641-123">This parameter is required.</span></span>

<span data-ttu-id="bc641-124">Mit diesem Cmdlet können Sie die Systemwiederherstellung auf einem Remotenetzlaufwerk nicht aktivieren, auch wenn das Laufwerk dem lokalen Computer zugeordnet ist, und Sie können die Systemwiederherstellung nicht auf Laufwerken aktivieren, die für die Systemwiederherstellung nicht geeignet sind, z. B. externe Laufwerke.</span><span class="sxs-lookup"><span data-stu-id="bc641-124">You cannot use this cmdlet to enable System Restore on a remote network drive, even if the drive is mapped to the local computer, and you cannot enable System Restore on drives that are not eligible for System Restore, such as external drives.</span></span>

<span data-ttu-id="bc641-125">Zum Aktivieren der Systemwiederherstellung auf einem Laufwerk muss sie auf dem Systemlaufwerk aktiviert werden, entweder zuerst oder gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="bc641-125">To enable System Restore on any drive, System Restore must be enabled on the system drive, either before or concurrently.</span></span>

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

### <span data-ttu-id="bc641-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bc641-126">-Confirm</span></span>
<span data-ttu-id="bc641-127">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="bc641-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bc641-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bc641-128">-WhatIf</span></span>
<span data-ttu-id="bc641-129">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc641-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bc641-130">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bc641-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bc641-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bc641-131">CommonParameters</span></span>
<span data-ttu-id="bc641-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bc641-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bc641-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bc641-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bc641-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bc641-134">INPUTS</span></span>

### <span data-ttu-id="bc641-135">Keine</span><span class="sxs-lookup"><span data-stu-id="bc641-135">None</span></span>
<span data-ttu-id="bc641-136">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="bc641-136">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="bc641-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bc641-137">OUTPUTS</span></span>

### <span data-ttu-id="bc641-138">Keine</span><span class="sxs-lookup"><span data-stu-id="bc641-138">None</span></span>
<span data-ttu-id="bc641-139">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="bc641-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bc641-140">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bc641-140">NOTES</span></span>

* <span data-ttu-id="bc641-141">Wenn Sie dieses Cmdlet unter Windows Vista und höheren Versionen von Windows ausführen möchten, öffnen Sie Windows PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="bc641-141">To run this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="bc641-142">Informationen zu den Dateisystem Laufwerken, die für die Systemwiederherstellung geeignet sind, finden Sie unter System in der Systemsteuerung auf der Registerkarte Systemschutz. Um diese Registerkarte in Windows PowerShell zu öffnen, geben Sie ein `SystemPropertiesProtection` .</span><span class="sxs-lookup"><span data-stu-id="bc641-142">To find the file system drives that are eligible for system restore, in System in Control Panel, see the System Protection tab. To open this tab in Windows PowerShell, type `SystemPropertiesProtection`.</span></span>

  <span data-ttu-id="bc641-143">Dieses Cmdlet verwendet die Windows-Verwaltungsinstrumentation (WMI) **SystemRestore** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="bc641-143">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

*

## <span data-ttu-id="bc641-144">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bc641-144">RELATED LINKS</span></span>

[<span data-ttu-id="bc641-145">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="bc641-145">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="bc641-146">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="bc641-146">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="bc641-147">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="bc641-147">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="bc641-148">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="bc641-148">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="bc641-149">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="bc641-149">Restore-Computer</span></span>](Restore-Computer.md)
