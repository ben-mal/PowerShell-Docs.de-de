---
external help file: Microsoft.PowerShell.Operation.Validation-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Operation.Validation
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.operation.validation/invoke-operationvalidation?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-OperationValidation
ms.openlocfilehash: 6c9d4001392de48032a0fe1ba3667db90ea614fc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214284"
---
# <span data-ttu-id="b1b4a-103">Invoke-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="b1b4a-103">Invoke-OperationValidation</span></span>

## <span data-ttu-id="b1b4a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b1b4a-104">SYNOPSIS</span></span>

<span data-ttu-id="b1b4a-105">Ruft Tests des Vorgangs Validierungs Frameworks auf.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-105">Invokes Operation Validation Framework tests.</span></span>

## <span data-ttu-id="b1b4a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b1b4a-106">SYNTAX</span></span>

### <span data-ttu-id="b1b4a-107">Fileandtest (Standard)</span><span class="sxs-lookup"><span data-stu-id="b1b4a-107">FileAndTest (Default)</span></span>

```
Invoke-OperationValidation [-TestInfo <PSObject[]>] [-IncludePesterOutput] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="b1b4a-108">Pfad</span><span class="sxs-lookup"><span data-stu-id="b1b4a-108">Path</span></span>

```
Invoke-OperationValidation [-testFilePath <String[]>] [-IncludePesterOutput] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="b1b4a-109">Usegetoperationtest</span><span class="sxs-lookup"><span data-stu-id="b1b4a-109">UseGetOperationTest</span></span>

```
Invoke-OperationValidation [-ModuleName <String[]>] [-TestType <String[]>] [-IncludePesterOutput] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b1b4a-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b1b4a-110">DESCRIPTION</span></span>

<span data-ttu-id="b1b4a-111">Das Cmdlet "Start **-OperationValidation** " ruft Tests des Vorgangs Validierungs Frameworks für ein angegebenes Modul auf.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-111">The **Invoke-OperationValidation** cmdlet invokes Operation Validation Framework tests for a specified module.</span></span>

## <span data-ttu-id="b1b4a-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b1b4a-112">EXAMPLES</span></span>

### <span data-ttu-id="b1b4a-113">Beispiel 1: Aufrufen eines Vorgangs Validierungstests</span><span class="sxs-lookup"><span data-stu-id="b1b4a-113">Example 1: Invoke an Operation Validation test</span></span>

```
PS C:\> Get-OperationValidation -ModuleName "OperationValidation" | Invoke-OperationValidation -IncludePesterOutput
Describing Simple Test Suite
 [+] first Operational test 20ms
 [+] second Operational test 19ms
 [+] third Operational test 9ms
Tests completed in 48ms
Passed: 3 Failed: 0 Skipped: 0 Pending: 0
Describing Scenario targeted tests
   Context The RemoteAccess service
    [+] The service is running 37ms
   Context The Firewall Rules
    [+] A rule for TCP port 3389 is enabled 1.19s
    [+] A rule for UDP port 3389 is enabled 11ms
Tests completed in 1.24s
Passed: 3 Failed: 0 Skipped: 0 Pending: 0




   Module: OperationValidation




Result  Name
------- --------
Passed  Simple Test Suite::first Operational test
Passed  Simple Test Suite::second Operational test
Passed  Simple Test Suite::third Operational test
Passed  Scenario targeted tests:The RemoteAccess service:The service is running
Passed  Scenario targeted tests:The Firewall Rules:A rule for TCP port 3389 is enabled
Passed  Scenario targeted tests:The Firewall Rules:A rule for UDP port 3389 is enabled
```

<span data-ttu-id="b1b4a-114">Mit diesem Befehl wird das Modul "OperationValidation" abgerufen und mithilfe des Pipeline-Operators an das Cmdlet "Start **-OperationValidation** " übergeben, das den Test ausführt.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-114">This command gets the module named OperationValidation, and uses the pipeline operator to pass it to the **Invoke-OperationValidation** cmdlet, which runs the test.</span></span>

## <span data-ttu-id="b1b4a-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b1b4a-115">PARAMETERS</span></span>

### <span data-ttu-id="b1b4a-116">-Includepeer Output</span><span class="sxs-lookup"><span data-stu-id="b1b4a-116">-IncludePesterOutput</span></span>

<span data-ttu-id="b1b4a-117">Enthält die Pester-Test Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-117">Includes Pester test output.</span></span>
<span data-ttu-id="b1b4a-118">Der Standardwert ist $false.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-118">The default is $False.</span></span>

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

### <span data-ttu-id="b1b4a-119">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="b1b4a-119">-ModuleName</span></span>

<span data-ttu-id="b1b4a-120">Gibt ein Array von Namen von Modulen an.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-120">Specifies an array of names of modules.</span></span>

```yaml
Type: System.String[]
Parameter Sets: UseGetOperationTest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4a-121">-testfilepath</span><span class="sxs-lookup"><span data-stu-id="b1b4a-121">-testFilePath</span></span>

<span data-ttu-id="b1b4a-122">Gibt den Pfad einer Testdatei für das Operations Validation Framework an.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-122">Specifies the path of an Operation Validation Framework test file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4a-123">-TestInfo</span><span class="sxs-lookup"><span data-stu-id="b1b4a-123">-TestInfo</span></span>

<span data-ttu-id="b1b4a-124">Gibt ein benutzerdefiniertes-Objekt an, das den Pfad zur Datei und den Namen des Tests angibt, der ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-124">Specifies a custom object that specifies the path to the file and the name of the test to run.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: FileAndTest
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4a-125">-TestType</span><span class="sxs-lookup"><span data-stu-id="b1b4a-125">-TestType</span></span>

<span data-ttu-id="b1b4a-126">Gibt ein Array von Test Typen an.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-126">Specifies an array of test types.</span></span>
<span data-ttu-id="b1b4a-127">Gültige Werte sind einfach, umfassend oder beides.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-127">Valid values are Simple, Comprehensive, or both.</span></span>
<span data-ttu-id="b1b4a-128">Der Standardwert ist "Simple, Comprehensive".</span><span class="sxs-lookup"><span data-stu-id="b1b4a-128">The default is "Simple,Comprehensive".</span></span>

```yaml
Type: System.String[]
Parameter Sets: UseGetOperationTest
Aliases:
Accepted values: Simple, Comprehensive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1b4a-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b1b4a-129">-Confirm</span></span>

<span data-ttu-id="b1b4a-130">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b1b4a-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b1b4a-131">-WhatIf</span></span>

<span data-ttu-id="b1b4a-132">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b1b4a-133">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b1b4a-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b1b4a-134">CommonParameters</span></span>
<span data-ttu-id="b1b4a-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b1b4a-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b1b4a-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b1b4a-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b1b4a-137">INPUTS</span></span>

### <span data-ttu-id="b1b4a-138">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="b1b4a-138">PSCustomObject</span></span>

<span data-ttu-id="b1b4a-139">Sie können die Ausgabe von **Get-OperationValidation** an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-139">You can pipe the output of **Get-OperationValidation** to this cmdlet.</span></span>

## <span data-ttu-id="b1b4a-140">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b1b4a-140">OUTPUTS</span></span>

### <span data-ttu-id="b1b4a-141">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="b1b4a-141">PSCustomObject</span></span>

<span data-ttu-id="b1b4a-142">Das **pscustomobject-Objekt** beschreibt, ob die Überprüfung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b1b4a-142">The **PSCustomObject** describes whether the validation was successful.</span></span>

## <span data-ttu-id="b1b4a-143">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b1b4a-143">NOTES</span></span>

## <span data-ttu-id="b1b4a-144">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b1b4a-144">RELATED LINKS</span></span>

[<span data-ttu-id="b1b4a-145">Get-OperationValidation</span><span class="sxs-lookup"><span data-stu-id="b1b4a-145">Get-OperationValidation</span></span>](Get-OperationValidation.md)
