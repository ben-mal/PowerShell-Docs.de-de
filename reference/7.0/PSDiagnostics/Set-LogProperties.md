---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/set-logproperties?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LogProperties
ms.openlocfilehash: baf737a649e96488aff10959e02b59a0323e3ac4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209972"
---
# <span data-ttu-id="a3d91-102">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="a3d91-102">Set-LogProperties</span></span>

## <span data-ttu-id="a3d91-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a3d91-103">SYNOPSIS</span></span>
<span data-ttu-id="a3d91-104">Ändert die Eigenschaften eines Windows-Ereignis Protokolls.</span><span class="sxs-lookup"><span data-stu-id="a3d91-104">Changes the properties of a Windows event log.</span></span>

## <span data-ttu-id="a3d91-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a3d91-105">SYNTAX</span></span>

```
Set-LogProperties [-LogDetails] <LogDetails> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="a3d91-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a3d91-106">DESCRIPTION</span></span>

<span data-ttu-id="a3d91-107">Dieses Cmdlet ändert die Konfigurationseinstellungen eines Windows-Ereignis Protokolls.</span><span class="sxs-lookup"><span data-stu-id="a3d91-107">This cmdlet changes the configuration settings of a Windows event log.</span></span> <span data-ttu-id="a3d91-108">Dieses Cmdlet wird von den `Enable-PSTrace` -und- `Disable-PSTrace` Cmdlets verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3d91-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

<span data-ttu-id="a3d91-109">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="a3d91-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a3d91-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a3d91-110">EXAMPLES</span></span>

### <span data-ttu-id="a3d91-111">Beispiel 1: Ändern der Beibehaltungs Einstellung des Windows PowerShell-Ereignis Protokolls</span><span class="sxs-lookup"><span data-stu-id="a3d91-111">Example 1: Change the retention setting of the Windows PowerShell event log</span></span>

```powershell
$logDetails = Get-LogProperties 'Windows PowerShell'
$logDetails.Retention = $True
Set-LogProperties -LogDetails $logDetails
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : True
AutoBackup : False
MaxLogSize : 15728640
```

## <span data-ttu-id="a3d91-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a3d91-112">PARAMETERS</span></span>

### <span data-ttu-id="a3d91-113">-Force</span><span class="sxs-lookup"><span data-stu-id="a3d91-113">-Force</span></span>

<span data-ttu-id="a3d91-114">Wird verwendet, um die Änderung ohne Eingabeaufforderung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="a3d91-114">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="a3d91-115">-Logdetails</span><span class="sxs-lookup"><span data-stu-id="a3d91-115">-LogDetails</span></span>

<span data-ttu-id="a3d91-116">Die aktualisierten Konfigurationseinstellungen, die dem Ereignisprotokoll zugewiesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a3d91-116">The updated configuration settings to be assigned to the event log.</span></span>

```yaml
Type: Microsoft.PowerShell.Diagnostics.LogDetails
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a3d91-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a3d91-117">CommonParameters</span></span>

<span data-ttu-id="a3d91-118">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a3d91-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a3d91-119">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a3d91-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a3d91-120">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a3d91-120">INPUTS</span></span>

### <span data-ttu-id="a3d91-121">Microsoft. PowerShell. Diagnostics. Logdetails</span><span class="sxs-lookup"><span data-stu-id="a3d91-121">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="a3d91-122">Sie müssen ein vollständig konfiguriertes **Logdetails** -Objekt an das `Set-LogProperties` Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="a3d91-122">You must pass a fully configured **LogDetails** object to the `Set-LogProperties` cmdlet.</span></span>
<span data-ttu-id="a3d91-123">Wenn Sie eine Einstellung ändern möchten, sollten Sie daher zum `Get-LogProperties` Abrufen der aktuellen Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3d91-123">Therefore, to change one setting, you should use `Get-LogProperties` to retrieve the current configuration.</span></span>

## <span data-ttu-id="a3d91-124">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a3d91-124">OUTPUTS</span></span>

### <span data-ttu-id="a3d91-125">Keine</span><span class="sxs-lookup"><span data-stu-id="a3d91-125">None</span></span>

## <span data-ttu-id="a3d91-126">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a3d91-126">NOTES</span></span>

<span data-ttu-id="a3d91-127">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="a3d91-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a3d91-128">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a3d91-128">RELATED LINKS</span></span>

[<span data-ttu-id="a3d91-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="a3d91-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="a3d91-130">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="a3d91-130">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="a3d91-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="a3d91-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)
