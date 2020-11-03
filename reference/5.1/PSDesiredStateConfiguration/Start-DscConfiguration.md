---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/start-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DscConfiguration
ms.openlocfilehash: c34754aeb7fce99030cf4ddb235e3e7e8161f3eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215287"
---
# <span data-ttu-id="0101a-103">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0101a-103">Start-DscConfiguration</span></span>

## <span data-ttu-id="0101a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0101a-104">SYNOPSIS</span></span>
<span data-ttu-id="0101a-105">Wendet die Konfiguration auf Knoten an.</span><span class="sxs-lookup"><span data-stu-id="0101a-105">Applies configuration to nodes.</span></span>

## <span data-ttu-id="0101a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0101a-106">SYNTAX</span></span>

### <span data-ttu-id="0101a-107">Computernameandpathset (Standard)</span><span class="sxs-lookup"><span data-stu-id="0101a-107">ComputerNameAndPathSet (Default)</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0101a-108">Cimsessionandpathset</span><span class="sxs-lookup"><span data-stu-id="0101a-108">CimSessionAndPathSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] -CimSession <CimSession[]> [-ThrottleLimit <Int32>]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0101a-109">Computernameanduseexistingset</span><span class="sxs-lookup"><span data-stu-id="0101a-109">ComputerNameAndUseExistingSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-UseExisting] [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0101a-110">Cimsessionanduseexistingset</span><span class="sxs-lookup"><span data-stu-id="0101a-110">CimSessionAndUseExistingSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] -CimSession <CimSession[]> [-ThrottleLimit <Int32>] [-UseExisting]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0101a-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0101a-111">DESCRIPTION</span></span>
<span data-ttu-id="0101a-112">Das Cmdlet **Start-DscConfiguration** wendet die Konfiguration auf Knoten an.</span><span class="sxs-lookup"><span data-stu-id="0101a-112">The **Start-DscConfiguration** cmdlet applies configuration to nodes.</span></span>
<span data-ttu-id="0101a-113">Bei Verwendung mit dem Parameter *useexistierenden* wird die vorhandene Konfiguration auf dem Bereitstellungs Zielcomputer angewendet.</span><span class="sxs-lookup"><span data-stu-id="0101a-113">When used with the *UseExisting* parameter, the existing configuration on the target computer is applied.</span></span>
<span data-ttu-id="0101a-114">Geben Sie an, auf welche Computer Sie die Konfiguration anwenden möchten, indem Sie Computernamen angeben oder Common Information Model (CIM)-Sitzungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0101a-114">Specify which computers that you want to apply configuration to by specifying computer names or by using Common Information Model (CIM) sessions.</span></span>

<span data-ttu-id="0101a-115">Standardmäßig erstellt dieses Cmdlet ein Auftrag und gibt ein **Job** Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="0101a-115">By default, this cmdlet creates a job and returns a **Job** object.</span></span>
<span data-ttu-id="0101a-116">Weitere Informationen zu Hintergrund Aufträgen erhalten Sie, wenn Sie eingeben `Get-Help about_Jobs` .</span><span class="sxs-lookup"><span data-stu-id="0101a-116">For more information about background jobs, type `Get-Help about_Jobs`.</span></span>
<span data-ttu-id="0101a-117">Geben Sie den Parameter *Wait* an, um dieses Cmdlet interaktiv zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0101a-117">To use this cmdlet interactively, specify the *Wait* parameter.</span></span>

<span data-ttu-id="0101a-118">Geben Sie den Parameter *Verbose* an, um Details dazu anzuzeigen, was das Cmdlet durchführt, wenn es Konfigurationseinstellungen anwendet.</span><span class="sxs-lookup"><span data-stu-id="0101a-118">Specify the *Verbose* parameter to see details of what the cmdlet does when it applies configuration settings.</span></span>

## <span data-ttu-id="0101a-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0101a-119">EXAMPLES</span></span>

### <span data-ttu-id="0101a-120">Beispiel 1: Anwenden von Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="0101a-120">Example 1: Apply configuration settings</span></span>

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="0101a-121">Dieser Befehl wendet die Konfigurationseinstellungen von C:\DSC\Configurations\ auf alle Computer an, die über Einstellungen in diesem Ordner verfügen.</span><span class="sxs-lookup"><span data-stu-id="0101a-121">This command applies the configuration settings from C:\DSC\Configurations\ to the every computer that has settings in that folder.</span></span>
<span data-ttu-id="0101a-122">Der Befehl gibt **Job** -Objekte für jeden Zielknoten zurück, an den bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0101a-122">The command returns **Job** objects for each target node deployed to.</span></span>

### <span data-ttu-id="0101a-123">Beispiel 2: Anwenden von Konfigurationseinstellungen und warten auf den Abschluss der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0101a-123">Example 2: Apply configuration settings and wait for configuration to complete</span></span>

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -Wait -Verbose
```

<span data-ttu-id="0101a-124">Dieser Befehl wendet die Konfiguration von C:\DSC\Configurations\ auf dem lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="0101a-124">This command applies the configuration from C:\DSC\Configurations\ to the local computer.</span></span>
<span data-ttu-id="0101a-125">Der Befehl gibt **Job** -Objekte für jeden Zielknoten zurück, an den bereitgestellt wird, in diesem Fall nur für den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="0101a-125">The command returns **Job** objects for each target node deployed to, in this case, just the local computer.</span></span>
<span data-ttu-id="0101a-126">In diesem Beispiel wird der *verbose* -Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="0101a-126">This example specifies the *Verbose* parameter.</span></span>
<span data-ttu-id="0101a-127">Daher sendet der Befehl Nachrichten an die Konsole, während er fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="0101a-127">Therefore, the command sends messages to the console as it proceeds.</span></span>
<span data-ttu-id="0101a-128">Der Befehl enthält den *Wait* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="0101a-128">The command includes the *Wait* parameter.</span></span>
<span data-ttu-id="0101a-129">Daher können Sie die Konsole erst verwenden, wenn der Befehl alle Konfigurationsaufgaben abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="0101a-129">Therefore, you cannot use the console until the command finishes all configuration tasks.</span></span>

### <span data-ttu-id="0101a-130">Beispiel 3: Anwenden von Konfigurationseinstellungen mithilfe einer CIM-Sitzung</span><span class="sxs-lookup"><span data-stu-id="0101a-130">Example 3: Apply configuration settings by using a CIM session</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -CimSession $Session
```

<span data-ttu-id="0101a-131">In diesem Beispiel werden die Konfigurationseinstellungen für einen bestimmten Computer angewendet.</span><span class="sxs-lookup"><span data-stu-id="0101a-131">This example applies configuration settings to a specified computer.</span></span>
<span data-ttu-id="0101a-132">Das Beispiel erstellt eine CIM-Sitzung für einen Computer namens Server01 zur Verwendung mit dem Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0101a-132">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="0101a-133">Erstellen Sie alternativ ein Array von CIM-Sitzungen, um das Cmdlet für mehrere angegebene Computer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="0101a-133">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="0101a-134">Der erste Befehl erstellt eine CIM-Sitzung mithilfe des Cmdlets **New-CimSession** und speichert dann das **CimSession** -Objekt in der Variable $Session.</span><span class="sxs-lookup"><span data-stu-id="0101a-134">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="0101a-135">Der Befehl fordert Sie zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="0101a-135">The command prompts you for a password.</span></span>
<span data-ttu-id="0101a-136">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help NewCimSession`.</span><span class="sxs-lookup"><span data-stu-id="0101a-136">For more information, type `Get-Help NewCimSession`.</span></span>

<span data-ttu-id="0101a-137">Mit dem zweiten Befehl werden die Konfigurationseinstellungen von c:\dsc\configurations\ auf die Computer angewendet, die von den in der $Session Variablen gespeicherten **cimsession** -Objekten identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="0101a-137">The second command applies the configuration settings from C:\DSC\Configurations\ to the computers identified by the **CimSession** objects stored in the $Session variable.</span></span>
<span data-ttu-id="0101a-138">In diesem Beispiel enthält die Variable $Session eine CIM-Sitzung nur für den Computer namens Server01.</span><span class="sxs-lookup"><span data-stu-id="0101a-138">In this example, the $Session variable contains a CIM session only for the computer named Server01.</span></span>
<span data-ttu-id="0101a-139">Der Befehl wendet die Konfiguration an.</span><span class="sxs-lookup"><span data-stu-id="0101a-139">The command applies the configuration.</span></span>
<span data-ttu-id="0101a-140">Der Befehl erstellt **Job** -Objekte für jeden konfigurierten Computer.</span><span class="sxs-lookup"><span data-stu-id="0101a-140">The command creates **Job** objects for each configured computer.</span></span>

## <span data-ttu-id="0101a-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0101a-141">PARAMETERS</span></span>

### <span data-ttu-id="0101a-142">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0101a-142">-CimSession</span></span>
<span data-ttu-id="0101a-143">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="0101a-143">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="0101a-144">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".</span><span class="sxs-lookup"><span data-stu-id="0101a-144">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="0101a-145">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="0101a-145">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0101a-146">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0101a-146">-ComputerName</span></span>
<span data-ttu-id="0101a-147">Gibt ein Array von Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="0101a-147">Specifies an array of computer names.</span></span>
<span data-ttu-id="0101a-148">Dieser Parameter schränkt die Computer mit Konfigurations Dokumenten im *path* -Parameter auf die im-Array angegebenen ein.</span><span class="sxs-lookup"><span data-stu-id="0101a-148">This parameter restricts the computers that have configuration documents in the *Path* parameter to those specified in the array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0101a-149">-Credential</span><span class="sxs-lookup"><span data-stu-id="0101a-149">-Credential</span></span>
<span data-ttu-id="0101a-150">Gibt einen Benutzernamen und ein Kennwort als ein **PSCredential** -Objekt für den Zielcomputer an.</span><span class="sxs-lookup"><span data-stu-id="0101a-150">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="0101a-151">Zum Abrufen eines **PSCredential** -Objekts verwenden Sie das Get-Credential-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0101a-151">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="0101a-152">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="0101a-152">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0101a-153">-Force</span><span class="sxs-lookup"><span data-stu-id="0101a-153">-Force</span></span>
<span data-ttu-id="0101a-154">Beendet den derzeit auf dem Bereitstellungs Zielcomputer laufenden Konfigurations Vorgang und startet den neuen Start-Configuration Vorgang.</span><span class="sxs-lookup"><span data-stu-id="0101a-154">Stops the configuration operation currently running on the target computer and begins the new Start-Configuration operation.</span></span>
<span data-ttu-id="0101a-155">Wenn die Eigenschaft " **erfrischendes Modus** " des lokalen Configuration Manager auf " **Pull** " festgelegt ist, wird Sie durch Angabe dieses Parameters in **Push** geändert.</span><span class="sxs-lookup"><span data-stu-id="0101a-155">If the **RefreshMode** property of the Local Configuration Manager is set to **Pull** , specifying this parameter changes it to **Push** .</span></span>

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

### <span data-ttu-id="0101a-156">-Jobname</span><span class="sxs-lookup"><span data-stu-id="0101a-156">-JobName</span></span>
<span data-ttu-id="0101a-157">Gibt einen Anzeigenamen für einen Auftrag an.</span><span class="sxs-lookup"><span data-stu-id="0101a-157">Specifies a friendly name for a job.</span></span>
<span data-ttu-id="0101a-158">Wenn Sie diesen Parameter angeben, wird das Cmdlet Auftrag ausgeführt und gibt ein **Job** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="0101a-158">If you specify this parameter, the cmdlet runs as a job, and it returns a **Job** object.</span></span>

<span data-ttu-id="0101a-159">Standardmäßig weist Windows PowerShell den Namen jobn zu, wobei N eine ganze Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="0101a-159">By default, Windows PowerShell assigns the name JobN where N is an integer.</span></span>

<span data-ttu-id="0101a-160">Wenn Sie den Parameter *Wait* angeben, geben Sie diesen Parameter nicht an.</span><span class="sxs-lookup"><span data-stu-id="0101a-160">If you specify the *Wait* parameter, do not specify this parameter.</span></span>

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

### <span data-ttu-id="0101a-161">-Path</span><span class="sxs-lookup"><span data-stu-id="0101a-161">-Path</span></span>
<span data-ttu-id="0101a-162">Gibt einen Dateipfad eines Ordners an, der Dateien mit den Konfigurationseinstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="0101a-162">Specifies a file path of a folder that contains configuration settings files.</span></span>
<span data-ttu-id="0101a-163">Dieses Cmdlet veröffentlicht diese Konfigurationseinstellungen und wendet Sie auf Computern an, die im angegebenen Pfad über Einstellungsdateien verfügen.</span><span class="sxs-lookup"><span data-stu-id="0101a-163">This cmdlet publishes and applies these configuration settings to computers that have settings files in the specified path.</span></span>
<span data-ttu-id="0101a-164">Jeder Zielknoten muss über eine Einstellungsdatei im folgenden Format verfügen: NetBIOS Name. mof.</span><span class="sxs-lookup"><span data-stu-id="0101a-164">Each target node must have a settings file of the following format: NetBIOS Name.mof.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0101a-165">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0101a-165">-ThrottleLimit</span></span>
<span data-ttu-id="0101a-166">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="0101a-166">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="0101a-167">Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0101a-167">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="0101a-168">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="0101a-168">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="0101a-169">-Useexistierenden</span><span class="sxs-lookup"><span data-stu-id="0101a-169">-UseExisting</span></span>
<span data-ttu-id="0101a-170">Gibt an, dass dieses Cmdlet die vorhandene Konfiguration anwendet.</span><span class="sxs-lookup"><span data-stu-id="0101a-170">Indicates that this cmdlet applies the existing configuration.</span></span>
<span data-ttu-id="0101a-171">Die Konfiguration kann auf dem Bereitstellungs Zielcomputer mithilfe von **Start-dscconfiguration** oder Veröffentlichung mithilfe des Publish-DscConfiguration-Cmdlets auf dem Zielcomputer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="0101a-171">The configuration can exist on the target computer by enactment using **Start-DscConfiguration** or by publication using the Publish-DscConfiguration cmdlet.</span></span>

<span data-ttu-id="0101a-172">Bevor Sie diesen Parameter für dieses Cmdlet angeben, überprüfen Sie die Informationen unter [Neues in Windows PowerShell 5,0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)</span><span class="sxs-lookup"><span data-stu-id="0101a-172">Before you specify this parameter for this cmdlet, review the information in [What's New in Windows PowerShell 5.0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameAndUseExistingSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0101a-173">-Wait</span><span class="sxs-lookup"><span data-stu-id="0101a-173">-Wait</span></span>
<span data-ttu-id="0101a-174">Gibt an, dass das Cmdlet die Konsole blockiert, bis alle Konfigurationsaufgaben abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="0101a-174">Indicates that the cmdlet blocks the console until it finishes all configuration tasks.</span></span>

<span data-ttu-id="0101a-175">Wenn Sie diesen Parameter angeben, geben Sie den Parameter *JobName* nicht an.</span><span class="sxs-lookup"><span data-stu-id="0101a-175">If you specify this parameter, do not specify the *JobName* parameter.</span></span>

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

### <span data-ttu-id="0101a-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0101a-176">-Confirm</span></span>
<span data-ttu-id="0101a-177">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="0101a-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0101a-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0101a-178">-WhatIf</span></span>
<span data-ttu-id="0101a-179">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0101a-179">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0101a-180">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0101a-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0101a-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0101a-181">CommonParameters</span></span>
<span data-ttu-id="0101a-182">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0101a-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0101a-183">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0101a-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0101a-184">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0101a-184">INPUTS</span></span>

## <span data-ttu-id="0101a-185">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0101a-185">OUTPUTS</span></span>

## <span data-ttu-id="0101a-186">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0101a-186">NOTES</span></span>

## <span data-ttu-id="0101a-187">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0101a-187">RELATED LINKS</span></span>

[<span data-ttu-id="0101a-188">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="0101a-188">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="0101a-189">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0101a-189">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="0101a-190">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="0101a-190">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="0101a-191">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0101a-191">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="0101a-192">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0101a-192">Stop-DscConfiguration</span></span>](Stop-DscConfiguration.md)

[<span data-ttu-id="0101a-193">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0101a-193">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)

[<span data-ttu-id="0101a-194">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0101a-194">Update-DscConfiguration</span></span>](Update-DscConfiguration.md)
