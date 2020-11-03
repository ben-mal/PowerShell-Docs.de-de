---
external help file: Get-DSCLocalConfigurationManager.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscLocalConfigurationManager
ms.openlocfilehash: 162770d8eb3a8953dcfaeb31f30742a46353b33b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215316"
---
# <span data-ttu-id="43f86-103">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="43f86-103">Get-DscLocalConfigurationManager</span></span>

## <span data-ttu-id="43f86-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="43f86-104">SYNOPSIS</span></span>

<span data-ttu-id="43f86-105">Ruft die Einstellungen des lokalen Configuration Manager (LCM) und die Zustände für den Knoten ab.</span><span class="sxs-lookup"><span data-stu-id="43f86-105">Gets Local Configuration Manager (LCM) settings and states for the node.</span></span>

## <span data-ttu-id="43f86-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43f86-106">SYNTAX</span></span>

```
Get-DscLocalConfigurationManager [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## <span data-ttu-id="43f86-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="43f86-107">DESCRIPTION</span></span>

<span data-ttu-id="43f86-108">Das `Get-DscLocalConfigurationManager` -Cmdlet ruft die LCM-Einstellungen, die metakonfiguration und die Zustände des LCM für den Knoten ab.</span><span class="sxs-lookup"><span data-stu-id="43f86-108">The `Get-DscLocalConfigurationManager` cmdlet gets LCM settings, or meta-configuration, and the states of LCM for the node.</span></span> <span data-ttu-id="43f86-109">Geben Sie Computer mithilfe von CIM-Sitzungen (Common Information Model) an.</span><span class="sxs-lookup"><span data-stu-id="43f86-109">Specify computers by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="43f86-110">Wenn Sie keinen Zielcomputer angeben, ruft das Cmdlet die Konfigurationseinstellungen vom lokalen Computer ab.</span><span class="sxs-lookup"><span data-stu-id="43f86-110">If you do not specify a target computer, the cmdlet gets the configuration settings from the local computer.</span></span>

## <span data-ttu-id="43f86-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="43f86-111">EXAMPLES</span></span>

### <span data-ttu-id="43f86-112">Beispiel 1: Get LCM-Einstellungen für den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="43f86-112">Example 1: Get LCM settings for the local computer</span></span>

```powershell
Get-DscLocalConfigurationManager
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 47edd8c9-2798-4827-839a-b35cc87e69fb
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName
```

<span data-ttu-id="43f86-113">Mit diesem Befehl werden die LCM-Einstellungen für den lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="43f86-113">This command gets LCM settings for the local computer.</span></span>

<span data-ttu-id="43f86-114">Weitere Informationen zu den einzelnen Attributen der Ausgabe finden Sie in der Dokumentation zum [Konfigurieren der lokalen Configuration Manager](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) .</span><span class="sxs-lookup"><span data-stu-id="43f86-114">For more information on the individual attributes of the output, see the [Configuring the Local Configuration Manager](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) documentation.</span></span>

### <span data-ttu-id="43f86-115">Beispiel 2: erhalten von LCM-Einstellungen für einen angegebenen Computer</span><span class="sxs-lookup"><span data-stu-id="43f86-115">Example 2: Get LCM settings for a specified computer</span></span>

```powershell
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Get-DscLocalConfigurationManager -CimSession $Session
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 169dfa57-a7f9-43be-a7a5-9dd06587e052
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName                 : Server01
PSComputerName                 : Server01
```

<span data-ttu-id="43f86-116">In diesem Beispiel werden die LCM-Einstellungen für einen von einer CIM-Sitzung angegebenen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="43f86-116">This example gets LCM settings for a computer specified by a CIM session.</span></span>
<span data-ttu-id="43f86-117">Das Beispiel erstellt eine CIM-Sitzung für einen Computer namens Server01 zur Verwendung mit dem Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43f86-117">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="43f86-118">Erstellen Sie alternativ ein Array von CIM-Sitzungen, um das Cmdlet für mehrere angegebene Computer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="43f86-118">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="43f86-119">Der erste Befehl erstellt eine CIM-Sitzung mit dem `New-CimSession` Cmdlet und speichert dann das **cimsession** -Objekt in der $Session Variable.</span><span class="sxs-lookup"><span data-stu-id="43f86-119">The first command creates a CIM session by using the `New-CimSession` cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span> <span data-ttu-id="43f86-120">Der Befehl fordert Sie zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="43f86-120">The command prompts you for a password.</span></span> <span data-ttu-id="43f86-121">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="43f86-121">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="43f86-122">Mit dem zweiten Befehl werden lokale Configuration Manager Einstellungen für die Computer abgerufen, die von den in der $Session-Variablen gespeicherten **cimsession** -Objekten identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="43f86-122">The second command gets Local Configuration Manager settings for the computers identified by the **CimSession** objects stored in the $Session variable.</span></span> <span data-ttu-id="43f86-123">In diesem Fall der Computer namens SERVER01.</span><span class="sxs-lookup"><span data-stu-id="43f86-123">In this case, the computer named Server01.</span></span>

## <span data-ttu-id="43f86-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43f86-124">PARAMETERS</span></span>

### <span data-ttu-id="43f86-125">-AsJob</span><span class="sxs-lookup"><span data-stu-id="43f86-125">-AsJob</span></span>

<span data-ttu-id="43f86-126">Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.</span><span class="sxs-lookup"><span data-stu-id="43f86-126">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="43f86-127">-CimSession</span><span class="sxs-lookup"><span data-stu-id="43f86-127">-CimSession</span></span>

<span data-ttu-id="43f86-128">Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="43f86-128">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="43f86-129">Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines- `New-CimSession` oder- `Get-CimSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="43f86-129">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span>

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

### <span data-ttu-id="43f86-130">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="43f86-130">-ThrottleLimit</span></span>

<span data-ttu-id="43f86-131">Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="43f86-131">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

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

### <span data-ttu-id="43f86-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="43f86-132">CommonParameters</span></span>

<span data-ttu-id="43f86-133">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="43f86-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43f86-134">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="43f86-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43f86-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="43f86-135">INPUTS</span></span>

## <span data-ttu-id="43f86-136">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="43f86-136">OUTPUTS</span></span>

## <span data-ttu-id="43f86-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="43f86-137">NOTES</span></span>

## <span data-ttu-id="43f86-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="43f86-138">RELATED LINKS</span></span>

[<span data-ttu-id="43f86-139">Windows PowerShell DSC – Übersicht</span><span class="sxs-lookup"><span data-stu-id="43f86-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="43f86-140">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="43f86-140">Set-DscLocalConfigurationManager</span></span>](Set-DscLocalConfigurationManager.md)
