---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 63f9f644a81886dab498e46fce90d4ff2f7be91b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217076"
---
# <span data-ttu-id="2d96f-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="2d96f-102">Get-LogProperties</span></span>

## <span data-ttu-id="2d96f-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2d96f-103">SYNOPSIS</span></span>
<span data-ttu-id="2d96f-104">Ruft die Eigenschaften eines Windows-Ereignis Protokolls ab.</span><span class="sxs-lookup"><span data-stu-id="2d96f-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="2d96f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d96f-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## <span data-ttu-id="2d96f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2d96f-106">DESCRIPTION</span></span>

<span data-ttu-id="2d96f-107">Dieses Cmdlet ruft die Konfigurationseinstellungen eines Windows-Ereignis Protokolls ab.</span><span class="sxs-lookup"><span data-stu-id="2d96f-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="2d96f-108">Dieses Cmdlet wird von den `Enable-PSTrace` -und- `Disable-PSTrace` Cmdlets verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d96f-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="2d96f-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2d96f-109">EXAMPLES</span></span>

### <span data-ttu-id="2d96f-110">Beispiel 1: erhalten der Konfigurationseinstellungen des Windows PowerShell-Ereignis Protokolls</span><span class="sxs-lookup"><span data-stu-id="2d96f-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

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

## <span data-ttu-id="2d96f-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d96f-111">PARAMETERS</span></span>

### <span data-ttu-id="2d96f-112">-Name</span><span class="sxs-lookup"><span data-stu-id="2d96f-112">-Name</span></span>

<span data-ttu-id="2d96f-113">Der Name des Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="2d96f-113">The name of the event provider.</span></span>

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

### <span data-ttu-id="2d96f-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2d96f-114">CommonParameters</span></span>

<span data-ttu-id="2d96f-115">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2d96f-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d96f-116">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2d96f-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2d96f-117">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2d96f-117">INPUTS</span></span>

### <span data-ttu-id="2d96f-118">System.String</span><span class="sxs-lookup"><span data-stu-id="2d96f-118">System.String</span></span>

## <span data-ttu-id="2d96f-119">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2d96f-119">OUTPUTS</span></span>

### <span data-ttu-id="2d96f-120">Microsoft. PowerShell. Diagnostics. Logdetails</span><span class="sxs-lookup"><span data-stu-id="2d96f-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="2d96f-121">Das **psdiagnostics** -Modul fügt dem-Namespace die **Logdetails** -Klasse hinzu `Microsoft.PowerShell.Diagnostics` .</span><span class="sxs-lookup"><span data-stu-id="2d96f-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="2d96f-122">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2d96f-122">NOTES</span></span>

## <span data-ttu-id="2d96f-123">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2d96f-123">RELATED LINKS</span></span>

[<span data-ttu-id="2d96f-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="2d96f-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="2d96f-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="2d96f-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="2d96f-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="2d96f-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)
