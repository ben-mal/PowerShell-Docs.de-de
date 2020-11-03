---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/get-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-OperationValidation
ms.openlocfilehash: 22ff12848fb7aefaa7f684ee5d8723cc723a5879
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214287"
---
# <span data-ttu-id="5abda-103">Get-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="5abda-103">Get-OperationValidation</span></span>

## <span data-ttu-id="5abda-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5abda-104">SYNOPSIS</span></span>
<span data-ttu-id="5abda-105">Ruft Tests des Vorgangs Validierungs Frameworks ab.</span><span class="sxs-lookup"><span data-stu-id="5abda-105">Gets Operation Validation Framework tests.</span></span>

## <span data-ttu-id="5abda-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5abda-106">SYNTAX</span></span>

```
Get-OperationValidation [[-ModuleName] <String[]>] [-TestType <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="5abda-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5abda-107">DESCRIPTION</span></span>
<span data-ttu-id="5abda-108">Mit dem " **Get-OperationValidation"-** Cmdlet werden Vorgangs Validierungs Framework-Tests für installierte Module abgerufen.</span><span class="sxs-lookup"><span data-stu-id="5abda-108">The **Get-OperationValidation** cmdlet gets Operation Validation Framework tests for installed modules.</span></span>

<span data-ttu-id="5abda-109">Module, die einen Diagnose Ordner enthalten, werden für Pester-Tests im einfachen oder umfassenden Unterordner oder beides überprüft.</span><span class="sxs-lookup"><span data-stu-id="5abda-109">Modules that include a Diagnostics folder are inspected for Pester tests in the Simple or Comprehensive subfolder, or both.</span></span>

## <span data-ttu-id="5abda-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5abda-110">EXAMPLES</span></span>

### <span data-ttu-id="5abda-111">Beispiel 1: Abrufen von Vorgangs Validierungstests</span><span class="sxs-lookup"><span data-stu-id="5abda-111">Example 1: Get Operation Validation tests</span></span>

```
PS C:\> Get-OperationValidation -ModuleName "C:\temp\modules\AddNumbers"
    Type:     Simple
    File:     addnum.tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Simple\addnum.tests.ps1
    Name:
        Add-Em
        Subtract em
        Add-Numbers
    Type:     Comprehensive
    File:     Comp.Adding.Tests.ps1
    FilePath: C:\temp\modules\AddNumbers\Diagnostics\Comprehensive\Comp.Adding.Tests.ps1
    Name:
        Comprehensive Adding Tests
        Comprehensive Subtracting Tests
        Comprehensive Examples
```

<span data-ttu-id="5abda-112">Mit diesem Befehl werden Validierungstests aus dem Modul namens "AddNumbers" im Ordner "c:\temp\modules" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="5abda-112">This command gets validation tests from the module named AddNumbers in the C:\temp\modules folder.</span></span>

## <span data-ttu-id="5abda-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5abda-113">PARAMETERS</span></span>

### <span data-ttu-id="5abda-114">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="5abda-114">-ModuleName</span></span>
<span data-ttu-id="5abda-115">Gibt ein Array von Namen von Modulen an.</span><span class="sxs-lookup"><span data-stu-id="5abda-115">Specifies an array of names of modules.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5abda-116">-TestType</span><span class="sxs-lookup"><span data-stu-id="5abda-116">-TestType</span></span>
<span data-ttu-id="5abda-117">Gibt ein Array von Test Typen an.</span><span class="sxs-lookup"><span data-stu-id="5abda-117">Specifies an array of test types.</span></span>
<span data-ttu-id="5abda-118">Gültige Werte sind einfach, umfassend oder beides.</span><span class="sxs-lookup"><span data-stu-id="5abda-118">Valid values are Simple, Comprehensive, or both.</span></span>
<span data-ttu-id="5abda-119">Der Standardwert ist "Simple, Comprehensive".</span><span class="sxs-lookup"><span data-stu-id="5abda-119">The default is "Simple,Comprehensive".</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5abda-120">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5abda-120">CommonParameters</span></span>
<span data-ttu-id="5abda-121">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5abda-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5abda-122">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5abda-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5abda-123">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5abda-123">INPUTS</span></span>

### <span data-ttu-id="5abda-124">Keine</span><span class="sxs-lookup"><span data-stu-id="5abda-124">None</span></span>
<span data-ttu-id="5abda-125">Sie können keine Eingaben an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="5abda-125">You cannot pipe any input to this cmdlet.</span></span>

## <span data-ttu-id="5abda-126">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5abda-126">OUTPUTS</span></span>

### <span data-ttu-id="5abda-127">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="5abda-127">PSCustomObject</span></span>
<span data-ttu-id="5abda-128">Das **pscustomobject-Objekt** beschreibt die Validierung.</span><span class="sxs-lookup"><span data-stu-id="5abda-128">The **PSCustomObject** describes the validation.</span></span>

## <span data-ttu-id="5abda-129">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5abda-129">NOTES</span></span>

## <span data-ttu-id="5abda-130">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5abda-130">RELATED LINKS</span></span>

[<span data-ttu-id="5abda-131">Invoke-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="5abda-131">Invoke-OperationValidation</span></span>](Invoke-OperationValidation.md)
