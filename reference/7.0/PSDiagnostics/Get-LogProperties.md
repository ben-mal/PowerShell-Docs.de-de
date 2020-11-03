---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
Locale: en-US
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 08638749b7a5bb57bee804fccf9de17f50fd6736
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210703"
---
# <span data-ttu-id="bd207-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="bd207-102">Get-LogProperties</span></span>

## <span data-ttu-id="bd207-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bd207-103">SYNOPSIS</span></span>
<span data-ttu-id="bd207-104">Ruft die Eigenschaften eines Windows-Ereignis Protokolls ab.</span><span class="sxs-lookup"><span data-stu-id="bd207-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="bd207-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd207-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## <span data-ttu-id="bd207-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd207-106">DESCRIPTION</span></span>

<span data-ttu-id="bd207-107">Dieses Cmdlet ruft die Konfigurationseinstellungen eines Windows-Ereignis Protokolls ab.</span><span class="sxs-lookup"><span data-stu-id="bd207-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="bd207-108">Dieses Cmdlet wird von den `Enable-PSTrace` -und- `Disable-PSTrace` Cmdlets verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd207-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="bd207-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bd207-109">EXAMPLES</span></span>

### <span data-ttu-id="bd207-110">Beispiel 1: erhalten der Konfigurationseinstellungen des Windows PowerShell-Ereignis Protokolls</span><span class="sxs-lookup"><span data-stu-id="bd207-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

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

## <span data-ttu-id="bd207-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd207-111">PARAMETERS</span></span>

### <span data-ttu-id="bd207-112">-Name</span><span class="sxs-lookup"><span data-stu-id="bd207-112">-Name</span></span>

<span data-ttu-id="bd207-113">Der Name des Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="bd207-113">The name of the event provider.</span></span>

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

### <span data-ttu-id="bd207-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bd207-114">CommonParameters</span></span>

<span data-ttu-id="bd207-115">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd207-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd207-116">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bd207-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd207-117">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bd207-117">INPUTS</span></span>

### <span data-ttu-id="bd207-118">System.String</span><span class="sxs-lookup"><span data-stu-id="bd207-118">System.String</span></span>

## <span data-ttu-id="bd207-119">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bd207-119">OUTPUTS</span></span>

### <span data-ttu-id="bd207-120">Microsoft. PowerShell. Diagnostics. Logdetails</span><span class="sxs-lookup"><span data-stu-id="bd207-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="bd207-121">Das **psdiagnostics** -Modul fügt dem-Namespace die **Logdetails** -Klasse hinzu `Microsoft.PowerShell.Diagnostics` .</span><span class="sxs-lookup"><span data-stu-id="bd207-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="bd207-122">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bd207-122">NOTES</span></span>

## <span data-ttu-id="bd207-123">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bd207-123">RELATED LINKS</span></span>

[<span data-ttu-id="bd207-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="bd207-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="bd207-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="bd207-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="bd207-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="bd207-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)
