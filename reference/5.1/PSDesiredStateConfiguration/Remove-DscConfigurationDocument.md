---
external help file: Remove-DscConfigurationDocument.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DscConfigurationDocument
ms.openlocfilehash: d3e9b15dfeea94921503247adc08b291eed9d7d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215300"
---
# <span data-ttu-id="23a04-103">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="23a04-103">Remove-DscConfigurationDocument</span></span>

## <span data-ttu-id="23a04-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="23a04-104">SYNOPSIS</span></span>
<span data-ttu-id="23a04-105">Entfernt ein Konfigurations Dokument aus dem DSC-Konfigurations Speicher.</span><span class="sxs-lookup"><span data-stu-id="23a04-105">Removes a configuration document from the DSC configuration store.</span></span>

## <span data-ttu-id="23a04-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23a04-106">SYNTAX</span></span>

```
Remove-DscConfigurationDocument -Stage <Stage> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="23a04-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23a04-107">DESCRIPTION</span></span>
<span data-ttu-id="23a04-108">Mit dem- `Remove-DscConfigurationDocument` Cmdlet wird ein Konfigurations Dokument (. MOF-Datei) aus dem Konfigurations Speicher für Windows PowerShell DSC (DSC) entfernt.</span><span class="sxs-lookup"><span data-stu-id="23a04-108">The `Remove-DscConfigurationDocument` cmdlet removes a configuration document (.mof file) from the Windows PowerShell Desired State Configuration (DSC) configuration store.</span></span>
<span data-ttu-id="23a04-109">Während der Konfiguration `Start-DscConfiguration` kopiert das Cmdlet eine MOF-Datei in einen Ordner auf dem Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="23a04-109">During configuration, the `Start-DscConfiguration` cmdlet copies a .mof file to a folder on the target computer.</span></span>
<span data-ttu-id="23a04-110">Dieses Cmdlet entfernt dieses Konfigurations Dokument und führt zusätzliche Bereinigung durch.</span><span class="sxs-lookup"><span data-stu-id="23a04-110">This cmdlet removes that configuration document and does additional cleanup.</span></span>

<span data-ttu-id="23a04-111">Dieses Cmdlet ist nur als Teil des Updaterollup vom [November 2014 für Windows RT 8,1, Windows 8.1 und Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) aus der Microsoft-Support-Bibliothek verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23a04-111">This cmdlet is available only as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span>

## <span data-ttu-id="23a04-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="23a04-112">EXAMPLES</span></span>

### <span data-ttu-id="23a04-113">Beispiel 1: Entfernen des aktuellen Konfigurations Dokuments</span><span class="sxs-lookup"><span data-stu-id="23a04-113">Example 1: Remove the current configuration document</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Remove-DscConfigurationDocument -Stage Current -CimSession $Session
```

<span data-ttu-id="23a04-114">Der erste Befehl erstellt eine CIM-Sitzung mithilfe des Cmdlets **New-CimSession** und speichert dann das **CimSession** -Objekt in der Variable $Session.</span><span class="sxs-lookup"><span data-stu-id="23a04-114">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="23a04-115">Der Befehl fordert Sie zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="23a04-115">The command prompts you for a password.</span></span>
<span data-ttu-id="23a04-116">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="23a04-116">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="23a04-117">Mit dem zweiten Befehl wird das aktuelle Konfigurations Dokument für den Computer entfernt, der in der in $Session gespeicherten **cimsession** angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="23a04-117">The second command removes the current configuration document for the computer specified in the **CimSession** stored in $Session.</span></span>

## <span data-ttu-id="23a04-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23a04-118">PARAMETERS</span></span>

### <span data-ttu-id="23a04-119">-AsJob</span><span class="sxs-lookup"><span data-stu-id="23a04-119">-AsJob</span></span>
<span data-ttu-id="23a04-120">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="23a04-120">Indicates that this cmdlet runs the command as a background job.</span></span>

<span data-ttu-id="23a04-121">Wenn Sie den *AsJob* -Parameter angeben, gibt der Befehl ein Objekt zurück, das den Auftrag darstellt, und zeigt dann die Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="23a04-121">If you specify the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span>
<span data-ttu-id="23a04-122">Sie können die Arbeit in der Sitzung fortsetzen, bis der Auftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="23a04-122">You can continue to work in the session until the job finishes.</span></span>
<span data-ttu-id="23a04-123">Der Auftrag wird auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23a04-123">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="23a04-124">Um den Auftrag zu verwalten, verwenden Sie die Job-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="23a04-124">To manage the job, use the Job cmdlets.</span></span>
<span data-ttu-id="23a04-125">Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.</span><span class="sxs-lookup"><span data-stu-id="23a04-125">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="23a04-126">Um diesen Parameter verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein. unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie Windows PowerShell mit der Option als Administrator ausführen öffnen.</span><span class="sxs-lookup"><span data-stu-id="23a04-126">To use this parameter, the local and remote computers must be configured for remoting, and on Windows Vista and later versions of the Windows operating system, you must open Windows PowerShell with the Run as administrator option.</span></span>
<span data-ttu-id="23a04-127">Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23a04-127">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="23a04-128">Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="23a04-128">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="23a04-129">-CimSession</span><span class="sxs-lookup"><span data-stu-id="23a04-129">-CimSession</span></span>
<span data-ttu-id="23a04-130">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="23a04-130">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="23a04-131">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " **New-cimsession** " oder " **Get-cimsession** ".</span><span class="sxs-lookup"><span data-stu-id="23a04-131">Enter a computer name or a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet.</span></span>

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

### <span data-ttu-id="23a04-132">-Force</span><span class="sxs-lookup"><span data-stu-id="23a04-132">-Force</span></span>
<span data-ttu-id="23a04-133">Gibt an, dass dieses Cmdlet den laufenden Konfigurations Auftrag beendet, bevor das Konfigurations Dokument entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="23a04-133">Indicates that this cmdlet stops the running configuration job before it removes the configuration document.</span></span>
<span data-ttu-id="23a04-134">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="23a04-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="23a04-135">-Phase</span><span class="sxs-lookup"><span data-stu-id="23a04-135">-Stage</span></span>
<span data-ttu-id="23a04-136">Gibt an, welches Konfigurationsdokument entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="23a04-136">Specifies which configuration document to remove.</span></span>
<span data-ttu-id="23a04-137">Sie können mehrere Dokumente angeben.</span><span class="sxs-lookup"><span data-stu-id="23a04-137">You can specify multiple documents.</span></span>
<span data-ttu-id="23a04-138">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="23a04-138">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="23a04-139">Aktuell.</span><span class="sxs-lookup"><span data-stu-id="23a04-139">Current.</span></span>
<span data-ttu-id="23a04-140">Entfernen Sie das Konfigurations Dokument, das den aktuellen Status des Systems beschreibt.</span><span class="sxs-lookup"><span data-stu-id="23a04-140">Remove the configuration document that describes the current state of the system.</span></span>
- <span data-ttu-id="23a04-141">Ausstehend.</span><span class="sxs-lookup"><span data-stu-id="23a04-141">Pending.</span></span>
<span data-ttu-id="23a04-142">Entfernen Sie das Konfigurations Dokument, das den ausstehenden Status des Systems beschreibt.</span><span class="sxs-lookup"><span data-stu-id="23a04-142">Remove the configuration document that describes the pending state of the system.</span></span>
- <span data-ttu-id="23a04-143">Vorherige</span><span class="sxs-lookup"><span data-stu-id="23a04-143">Previous.</span></span>
<span data-ttu-id="23a04-144">Entfernen Sie das Konfigurations Dokument, das den vorherigen Zustand des Systems beschreibt.</span><span class="sxs-lookup"><span data-stu-id="23a04-144">Remove the configuration document that describes the previous state of the system.</span></span>

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoveDscConfigurationDocument.Stage
Parameter Sets: (All)
Aliases:
Accepted values: Current, Pending, Previous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23a04-145">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="23a04-145">-ThrottleLimit</span></span>
<span data-ttu-id="23a04-146">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="23a04-146">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="23a04-147">Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23a04-147">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="23a04-148">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="23a04-148">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="23a04-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="23a04-149">-Confirm</span></span>
<span data-ttu-id="23a04-150">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="23a04-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="23a04-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="23a04-151">-WhatIf</span></span>
<span data-ttu-id="23a04-152">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="23a04-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="23a04-153">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="23a04-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="23a04-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23a04-154">CommonParameters</span></span>
<span data-ttu-id="23a04-155">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="23a04-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23a04-156">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="23a04-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23a04-157">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="23a04-157">INPUTS</span></span>

### <span data-ttu-id="23a04-158">Keine</span><span class="sxs-lookup"><span data-stu-id="23a04-158">None</span></span>

## <span data-ttu-id="23a04-159">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="23a04-159">OUTPUTS</span></span>

### <span data-ttu-id="23a04-160">Keine</span><span class="sxs-lookup"><span data-stu-id="23a04-160">None</span></span>

## <span data-ttu-id="23a04-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="23a04-161">NOTES</span></span>

## <span data-ttu-id="23a04-162">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="23a04-162">RELATED LINKS</span></span>

[<span data-ttu-id="23a04-163">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="23a04-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="23a04-164">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="23a04-164">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="23a04-165">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="23a04-165">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)
