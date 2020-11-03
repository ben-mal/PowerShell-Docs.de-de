---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/update-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-DscConfiguration
ms.openlocfilehash: 13365902ab317a3daa41b9a951d5e2fa6e4f1b37
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213572"
---
# <span data-ttu-id="6fe76-103">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6fe76-103">Update-DscConfiguration</span></span>

## <span data-ttu-id="6fe76-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6fe76-104">SYNOPSIS</span></span>
<span data-ttu-id="6fe76-105">Überprüft den pullserver auf eine aktualisierte Konfiguration und wendet sie an.</span><span class="sxs-lookup"><span data-stu-id="6fe76-105">Checks the pull server for an updated configuration and applies it.</span></span>

## <span data-ttu-id="6fe76-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6fe76-106">SYNTAX</span></span>

### <span data-ttu-id="6fe76-107">Computernameset (Standard)</span><span class="sxs-lookup"><span data-stu-id="6fe76-107">ComputerNameSet (Default)</span></span>

```
Update-DscConfiguration [-Wait] [-JobName <String>] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6fe76-108">Cimsessionset</span><span class="sxs-lookup"><span data-stu-id="6fe76-108">CimSessionSet</span></span>

```
Update-DscConfiguration [-Wait] [-JobName <String>] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6fe76-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6fe76-109">DESCRIPTION</span></span>
<span data-ttu-id="6fe76-110">Das `Update-DscConfiguration` Cmdlet stellt eine Verbindung mit einem pullserver her, lädt die Konfiguration herunter, wenn Sie sich von der auf dem Knoten aktuellen Knoten unterscheidet, und wendet dann die Konfiguration auf den Computer an.</span><span class="sxs-lookup"><span data-stu-id="6fe76-110">The `Update-DscConfiguration` cmdlet connects to a pull server, downloads the configuration if it differs from what is current on the node, and then applies the configuration to the computer.</span></span>

<span data-ttu-id="6fe76-111">Dieses Cmdlet ist nur als Teil des Updaterollup vom [November 2014 für Windows RT 8,1, Windows 8.1 und Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) aus der Microsoft-Support-Bibliothek verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6fe76-111">This cmdlet is available only as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span>

## <span data-ttu-id="6fe76-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6fe76-112">EXAMPLES</span></span>

### <span data-ttu-id="6fe76-113">Beispiel 1: Aktualisieren einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6fe76-113">Example 1: Update a configuration</span></span>

```
PS C:\> Update-DscConfiguration -Wait -Verbose
```

<span data-ttu-id="6fe76-114">Nachdem Sie diesen Befehl ausgeführt haben, stellt der Server eine Verbindung mit dem registrierten pulldienst her, lädt die zuletzt zugewiesene Konfiguration herunter und wendet sie an.</span><span class="sxs-lookup"><span data-stu-id="6fe76-114">After running this command, the server will connect to the registered pull service, download the latest assigned configuration, and then apply it.</span></span>
<span data-ttu-id="6fe76-115">Die Parameter "-wait" und "-Verbose" sind optional.</span><span class="sxs-lookup"><span data-stu-id="6fe76-115">The -Wait and -Verbose parameters are optional.</span></span>
<span data-ttu-id="6fe76-116">Wenn Sie interaktiv arbeiten, ermöglichen diese Parameter die Echt Zeit Rückmeldung über den Fortschritt und Erfolg oder Misserfolg beim Anwenden der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="6fe76-116">When working interactively, these parameters combined enable real-time feedback about progress and success or failure when applying the configuration.</span></span>

### <span data-ttu-id="6fe76-117">Beispiel 2: Aktualisieren einer Konfiguration durch Herstellen einer Verbindung über eine CIM-Sitzung</span><span class="sxs-lookup"><span data-stu-id="6fe76-117">Example 2: Update a configuration by connecting over a CIM session</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Update-DscConfiguration -CimSession $Session -Wait
```

<span data-ttu-id="6fe76-118">Der erste Befehl erstellt eine CIM-Sitzung mithilfe des Cmdlets **New-CimSession** und speichert dann das **CimSession** -Objekt in der Variable $Session.</span><span class="sxs-lookup"><span data-stu-id="6fe76-118">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="6fe76-119">Der Befehl fordert Sie zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="6fe76-119">The command prompts you for a password.</span></span>
<span data-ttu-id="6fe76-120">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="6fe76-120">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="6fe76-121">Mit dem zweiten Befehl wird der Computer aktualisiert, der in der in $Session gespeicherten **cimsession** angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6fe76-121">The second command updates the computer specified in the **CimSession** stored in $Session.</span></span>
<span data-ttu-id="6fe76-122">Der-Befehl gibt den *Wait* -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="6fe76-122">The command specifies the *Wait* parameter.</span></span>
<span data-ttu-id="6fe76-123">Die Konsole akzeptiert keine weiteren Befehle, bis der aktuelle Befehl abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6fe76-123">The console does not accept additional commands until the current command finishes.</span></span>

## <span data-ttu-id="6fe76-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6fe76-124">PARAMETERS</span></span>

### <span data-ttu-id="6fe76-125">-CimSession</span><span class="sxs-lookup"><span data-stu-id="6fe76-125">-CimSession</span></span>
<span data-ttu-id="6fe76-126">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="6fe76-126">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="6fe76-127">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".</span><span class="sxs-lookup"><span data-stu-id="6fe76-127">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="6fe76-128">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="6fe76-128">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6fe76-129">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="6fe76-129">-ComputerName</span></span>
<span data-ttu-id="6fe76-130">Gibt ein Array von Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="6fe76-130">Specifies an array of computer names.</span></span>
<span data-ttu-id="6fe76-131">Mit dem-Cmdlet werden die Konfigurationseinstellungen auf die Computer angewendet, die von diesem Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6fe76-131">The cmdlet applies the configuration settings to the computers that this parameter specifies.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6fe76-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="6fe76-132">-Credential</span></span>
<span data-ttu-id="6fe76-133">Gibt einen Benutzernamen und ein Kennwort als ein **PSCredential** -Objekt für den Zielcomputer an.</span><span class="sxs-lookup"><span data-stu-id="6fe76-133">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="6fe76-134">Zum Abrufen eines **PSCredential** -Objekts verwenden Sie das Get-Credential-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6fe76-134">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="6fe76-135">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="6fe76-135">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fe76-136">-Jobname</span><span class="sxs-lookup"><span data-stu-id="6fe76-136">-JobName</span></span>
<span data-ttu-id="6fe76-137">Gibt einen Anzeigenamen für einen Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="6fe76-137">Specifies a friendly name for a job.</span></span>
<span data-ttu-id="6fe76-138">Wenn Sie diesen Parameter angeben, wird das Cmdlet Auftrag ausgeführt und gibt ein **Job** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="6fe76-138">If you specify this parameter, the cmdlet runs as a job, and it returns a **Job** object.</span></span>

<span data-ttu-id="6fe76-139">Standardmäßig weist Windows PowerShell den Namen jobn zu, wobei N eine ganze Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="6fe76-139">By default, Windows PowerShell assigns the name JobN where N is an integer.</span></span>

<span data-ttu-id="6fe76-140">Wenn Sie den Parameter *Wait* angeben, geben Sie diesen Parameter nicht an.</span><span class="sxs-lookup"><span data-stu-id="6fe76-140">If you specify the *Wait* parameter, do not specify this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fe76-141">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="6fe76-141">-ThrottleLimit</span></span>
<span data-ttu-id="6fe76-142">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="6fe76-142">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="6fe76-143">Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6fe76-143">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="6fe76-144">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="6fe76-144">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="6fe76-145">-Wait</span><span class="sxs-lookup"><span data-stu-id="6fe76-145">-Wait</span></span>
<span data-ttu-id="6fe76-146">Gibt an, dass das Cmdlet die Konsole blockiert, bis alle Konfigurationsaufgaben abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="6fe76-146">Indicates that the cmdlet blocks the console until it finishes all configuration tasks.</span></span>

<span data-ttu-id="6fe76-147">Wenn Sie diesen Parameter angeben, geben Sie den Parameter *JobName* nicht an.</span><span class="sxs-lookup"><span data-stu-id="6fe76-147">If you specify this parameter, do not specify the *JobName* parameter.</span></span>

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

### <span data-ttu-id="6fe76-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6fe76-148">-Confirm</span></span>
<span data-ttu-id="6fe76-149">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6fe76-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6fe76-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6fe76-150">-WhatIf</span></span>
<span data-ttu-id="6fe76-151">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6fe76-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6fe76-152">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6fe76-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6fe76-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6fe76-153">CommonParameters</span></span>
<span data-ttu-id="6fe76-154">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6fe76-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6fe76-155">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6fe76-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6fe76-156">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6fe76-156">INPUTS</span></span>

## <span data-ttu-id="6fe76-157">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6fe76-157">OUTPUTS</span></span>

## <span data-ttu-id="6fe76-158">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6fe76-158">NOTES</span></span>

## <span data-ttu-id="6fe76-159">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6fe76-159">RELATED LINKS</span></span>

[<span data-ttu-id="6fe76-160">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="6fe76-160">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="6fe76-161">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6fe76-161">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="6fe76-162">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="6fe76-162">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="6fe76-163">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6fe76-163">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="6fe76-164">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6fe76-164">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="6fe76-165">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6fe76-165">Stop-DscConfiguration</span></span>](Stop-DscConfiguration.md)

[<span data-ttu-id="6fe76-166">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6fe76-166">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
