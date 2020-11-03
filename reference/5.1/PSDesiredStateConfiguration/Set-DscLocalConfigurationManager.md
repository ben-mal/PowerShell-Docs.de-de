---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 04/29/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/set-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DscLocalConfigurationManager
ms.openlocfilehash: 0d35aa56a52f0e6c17abd0e7b2707869e780324c
ms.sourcegitcommit: 0d4d3e47f6979876550591f62061096e7a568f7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "93218015"
---
# <span data-ttu-id="568d9-103">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="568d9-103">Set-DscLocalConfigurationManager</span></span>

## <span data-ttu-id="568d9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="568d9-104">SYNOPSIS</span></span>

<span data-ttu-id="568d9-105">Wendet lokale Configuration Manager Einstellungen (LCM) auf Knoten an.</span><span class="sxs-lookup"><span data-stu-id="568d9-105">Applies Local Configuration Manager (LCM) settings to nodes.</span></span>

## <span data-ttu-id="568d9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="568d9-106">SYNTAX</span></span>

### <span data-ttu-id="568d9-107">Computernameset (Standard)</span><span class="sxs-lookup"><span data-stu-id="568d9-107">ComputerNameSet (Default)</span></span>

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="568d9-108">Cimsessionset</span><span class="sxs-lookup"><span data-stu-id="568d9-108">CimSessionSet</span></span>

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="568d9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="568d9-109">DESCRIPTION</span></span>

<span data-ttu-id="568d9-110">Mit dem- `Set-DscLocalConfigurationManager` Cmdlet werden die LCM-Einstellungen oder die metakonfiguration auf Knoten angewendet.</span><span class="sxs-lookup"><span data-stu-id="568d9-110">The `Set-DscLocalConfigurationManager` cmdlet applies LCM settings, or meta-configuration, to nodes.</span></span> <span data-ttu-id="568d9-111">Geben Sie Computer an, indem Sie Computernamen angeben oder CIM-Sitzungen (Common Information Model) verwenden.</span><span class="sxs-lookup"><span data-stu-id="568d9-111">Specify computers by specifying computer names or by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="568d9-112">Wenn Sie keinen Zielcomputer angeben, wendet das Cmdlet Einstellungen auf dem lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="568d9-112">If you do not specify a target computer, the cmdlet applies settings to the local computer.</span></span>

## <span data-ttu-id="568d9-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="568d9-113">EXAMPLES</span></span>

### <span data-ttu-id="568d9-114">Beispiel 1: Anwenden von LCM-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="568d9-114">Example 1: Apply LCM settings</span></span>

```
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="568d9-115">Mit diesem Befehl werden die LCM-Einstellungen von `C:\DSC\Configurations\` auf die Zielknoten angewendet.</span><span class="sxs-lookup"><span data-stu-id="568d9-115">This command applies the LCM settings from `C:\DSC\Configurations\` to the targeted nodes.</span></span> <span data-ttu-id="568d9-116">Nach dem Empfang der Einstellungen werden diese vom LCM verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="568d9-116">After receiving the settings, LCM processes them.</span></span>

> [!WARNING]
> <span data-ttu-id="568d9-117">Wenn mehrere Meta-Mappen für denselben Computer vorhanden sind, die im angegebenen Ordner gespeichert sind, wird nur die erste Meta-of-Datei angewendet.</span><span class="sxs-lookup"><span data-stu-id="568d9-117">If there are multiple meta mofs for the same computer stored in the specified folder, only the first meta mof will be applied.</span></span>

### <span data-ttu-id="568d9-118">Beispiel 2: Anwenden von LCM-Einstellungen mithilfe einer CIM-Sitzung</span><span class="sxs-lookup"><span data-stu-id="568d9-118">Example 2: Apply LCM settings by using a CIM session</span></span>

```
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\" -CimSession $Session
```

<span data-ttu-id="568d9-119">In diesem Beispiel werden die LCM-Einstellungen auf einen Computer angewendet, und die Einstellungen werden angewendet.</span><span class="sxs-lookup"><span data-stu-id="568d9-119">This example applies LCM settings to a computer and applies the settings.</span></span> <span data-ttu-id="568d9-120">Das Beispiel erstellt eine CIM-Sitzung für einen Computer namens Server01 zur Verwendung mit dem Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="568d9-120">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span> <span data-ttu-id="568d9-121">Erstellen Sie alternativ ein Array von CIM-Sitzungen, um das Cmdlet für mehrere angegebene Computer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="568d9-121">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="568d9-122">Der erste Befehl erstellt eine CIM-Sitzung mit dem `New-CimSession` Cmdlet und speichert dann das **cimsession** -Objekt in der `$Session` Variablen.</span><span class="sxs-lookup"><span data-stu-id="568d9-122">The first command creates a CIM session by using the `New-CimSession` cmdlet, and then stores the **CimSession** object in the `$Session` variable.</span></span> <span data-ttu-id="568d9-123">Der Befehl fordert Sie zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="568d9-123">The command prompts you for a password.</span></span> <span data-ttu-id="568d9-124">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="568d9-124">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="568d9-125">Mit dem zweiten Befehl werden die LCM-Einstellungen für den Zielknoten von `C:\DSC\Configurations\` auf den Computer angewendet, der durch die in der Variablen gespeicherten **cimsession** -Objekte identifiziert wird `$Session` .</span><span class="sxs-lookup"><span data-stu-id="568d9-125">The second command applies LCM settings for the targeted node from `C:\DSC\Configurations\` to the computer identified by the **CimSession** objects stored in the `$Session` variable.</span></span> <span data-ttu-id="568d9-126">In diesem Beispiel enthält die `$Session` Variable nur eine CIM-Sitzung für den Computer namens SERVER01.</span><span class="sxs-lookup"><span data-stu-id="568d9-126">In this example, the `$Session` variable contains a CIM session only for the computer named Server01.</span></span> <span data-ttu-id="568d9-127">Der Befehl wendet die Einstellungen an.</span><span class="sxs-lookup"><span data-stu-id="568d9-127">The command applies the settings.</span></span> <span data-ttu-id="568d9-128">Nach dem Empfang der Einstellungen werden diese vom LCM verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="568d9-128">After receiving the settings, LCM processes them.</span></span>

## <span data-ttu-id="568d9-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="568d9-129">PARAMETERS</span></span>

### <span data-ttu-id="568d9-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="568d9-130">-CimSession</span></span>

<span data-ttu-id="568d9-131">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="568d9-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="568d9-132">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/CimCmdlets/New-CimSession) " oder " [Get-cimsession](/powershell/module/CimCmdlets/Get-CimSession) ".</span><span class="sxs-lookup"><span data-stu-id="568d9-132">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) or [Get-CimSession](/powershell/module/CimCmdlets/Get-CimSession) cmdlet.</span></span>
<span data-ttu-id="568d9-133">Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="568d9-133">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="568d9-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="568d9-134">-ComputerName</span></span>

<span data-ttu-id="568d9-135">Gibt ein Array von Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="568d9-135">Specifies an array of computer names.</span></span> <span data-ttu-id="568d9-136">Dieser Parameter schränkt die Computer mit metakonfigurationsdokumenten im **path** -Parameter auf die im-Array angegebenen ein.</span><span class="sxs-lookup"><span data-stu-id="568d9-136">This parameter restricts the computers that have meta-configuration documents in the **Path** parameter to those specified in the array.</span></span>

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

### <span data-ttu-id="568d9-137">-Credential</span><span class="sxs-lookup"><span data-stu-id="568d9-137">-Credential</span></span>

<span data-ttu-id="568d9-138">Gibt einen Benutzernamen und ein Kennwort als ein **PSCredential** -Objekt für den Zielcomputer an.</span><span class="sxs-lookup"><span data-stu-id="568d9-138">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span> <span data-ttu-id="568d9-139">Zum Abrufen eines **PSCredential** -Objekts verwenden Sie das Get-Credential-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="568d9-139">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span> <span data-ttu-id="568d9-140">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="568d9-140">For more information, type `Get-Help Get-Credential`.</span></span>

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

### <span data-ttu-id="568d9-141">-Force</span><span class="sxs-lookup"><span data-stu-id="568d9-141">-Force</span></span>

<span data-ttu-id="568d9-142">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="568d9-142">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="568d9-143">-Path</span><span class="sxs-lookup"><span data-stu-id="568d9-143">-Path</span></span>

<span data-ttu-id="568d9-144">Gibt einen Dateipfad eines Ordners an, der Dateien mit den Konfigurationseinstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="568d9-144">Specifies a file path of a folder that contains configuration settings files.</span></span> <span data-ttu-id="568d9-145">Das Cmdlet veröffentlicht diese LCM-Einstellungen und wendet Sie auf Computern an, die im angegebenen Pfad über Einstellungsdateien verfügen.</span><span class="sxs-lookup"><span data-stu-id="568d9-145">The cmdlet publishes and applies these LCM settings to computers that have settings files in the specified path.</span></span> <span data-ttu-id="568d9-146">Jeder Zielknoten muss eine Einstellungsdatei im folgenden Format aufweisen: `NetBIOS Name.meta.mof` .</span><span class="sxs-lookup"><span data-stu-id="568d9-146">Each target node must have a settings file of the following format: `NetBIOS Name.meta.mof`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="568d9-147">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="568d9-147">-ThrottleLimit</span></span>

<span data-ttu-id="568d9-148">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="568d9-148">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span> <span data-ttu-id="568d9-149">Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="568d9-149">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span> <span data-ttu-id="568d9-150">Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.</span><span class="sxs-lookup"><span data-stu-id="568d9-150">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="568d9-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="568d9-151">-Confirm</span></span>

<span data-ttu-id="568d9-152">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="568d9-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="568d9-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="568d9-153">-WhatIf</span></span>

<span data-ttu-id="568d9-154">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="568d9-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="568d9-155">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="568d9-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="568d9-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="568d9-156">CommonParameters</span></span>

<span data-ttu-id="568d9-157">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="568d9-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="568d9-158">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="568d9-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="568d9-159">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="568d9-159">INPUTS</span></span>

## <span data-ttu-id="568d9-160">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="568d9-160">OUTPUTS</span></span>

## <span data-ttu-id="568d9-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="568d9-161">NOTES</span></span>

## <span data-ttu-id="568d9-162">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="568d9-162">RELATED LINKS</span></span>

[<span data-ttu-id="568d9-163">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="568d9-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="568d9-164">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="568d9-164">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)
