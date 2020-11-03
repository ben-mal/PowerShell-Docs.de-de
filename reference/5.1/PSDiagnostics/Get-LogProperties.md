---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 0f675c2b0bf2b7e5ebfe3a1677f5bc194e8fe844
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213532"
---
# <span data-ttu-id="10914-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="10914-102">Get-LogProperties</span></span>

## <span data-ttu-id="10914-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="10914-103">SYNOPSIS</span></span>
<span data-ttu-id="10914-104">Ruft die Eigenschaften eines Windows-Ereignis Protokolls ab.</span><span class="sxs-lookup"><span data-stu-id="10914-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="10914-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="10914-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <string> [<CommonParameters>]
```

## <span data-ttu-id="10914-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="10914-106">DESCRIPTION</span></span>

<span data-ttu-id="10914-107">Dieses Cmdlet ruft die Konfigurationseinstellungen eines Windows-Ereignis Protokolls ab.</span><span class="sxs-lookup"><span data-stu-id="10914-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="10914-108">Dieses Cmdlet wird von den `Enable-PSTrace` -und- `Disable-PSTrace` Cmdlets verwendet.</span><span class="sxs-lookup"><span data-stu-id="10914-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="10914-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="10914-109">EXAMPLES</span></span>

### <span data-ttu-id="10914-110">Beispiel 1: erhalten der Konfigurationseinstellungen des Windows PowerShell-Ereignis Protokolls</span><span class="sxs-lookup"><span data-stu-id="10914-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

```powershell
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : False
AutoBackup : False
MaxLogSize : 15728640
```

## <span data-ttu-id="10914-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="10914-111">PARAMETERS</span></span>

### <span data-ttu-id="10914-112">-Name</span><span class="sxs-lookup"><span data-stu-id="10914-112">-Name</span></span>

<span data-ttu-id="10914-113">Der Name des Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="10914-113">The name of the event provider.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="10914-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="10914-114">CommonParameters</span></span>

<span data-ttu-id="10914-115">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="10914-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="10914-116">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="10914-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="10914-117">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="10914-117">INPUTS</span></span>

### <span data-ttu-id="10914-118">System.Object</span><span class="sxs-lookup"><span data-stu-id="10914-118">System.Object</span></span>

## <span data-ttu-id="10914-119">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="10914-119">OUTPUTS</span></span>

### <span data-ttu-id="10914-120">Microsoft. PowerShell. Diagnostics. Logdetails</span><span class="sxs-lookup"><span data-stu-id="10914-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="10914-121">Das **psdiagnostics** -Modul fügt dem-Namespace die **Logdetails** -Klasse hinzu `Microsoft.PowerShell.Diagnostics` .</span><span class="sxs-lookup"><span data-stu-id="10914-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="10914-122">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="10914-122">NOTES</span></span>

## <span data-ttu-id="10914-123">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="10914-123">RELATED LINKS</span></span>

[<span data-ttu-id="10914-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="10914-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="10914-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="10914-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="10914-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="10914-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)
