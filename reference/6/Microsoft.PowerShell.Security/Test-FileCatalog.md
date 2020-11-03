---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/test-filecatalog?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-FileCatalog
ms.openlocfilehash: 072e0b4420613f2de356b35e741a558501c05e1c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216876"
---
# <span data-ttu-id="29c68-103">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="29c68-103">Test-FileCatalog</span></span>

## <span data-ttu-id="29c68-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="29c68-104">SYNOPSIS</span></span>
<span data-ttu-id="29c68-105">`Test-FileCatalog` überprüft, ob die Hashes, die in einer Katalog Datei (. cat) enthalten sind, mit den Hashwerten der eigentlichen Dateien übereinstimmen, um ihre Echtheit zu validieren.</span><span class="sxs-lookup"><span data-stu-id="29c68-105">`Test-FileCatalog` validates whether the hashes contained in a catalog file (.cat) matches the hashes of the actual files in order to validate their authenticity.</span></span>

<span data-ttu-id="29c68-106">Dieses Cmdlet wird nur unter Windows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="29c68-106">This cmdlet is only supported on Windows.</span></span>

## <span data-ttu-id="29c68-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29c68-107">SYNTAX</span></span>

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>] [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="29c68-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="29c68-108">DESCRIPTION</span></span>

<span data-ttu-id="29c68-109">`Test-FileCatalog` überprüft die Authentizität von Dateien, indem die Dateihashes einer Katalog Datei (. cat) mit den Hashes der tatsächlichen Dateien auf dem Datenträger verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="29c68-109">`Test-FileCatalog` validates the authenticity of files by comparing the file hashes of a catalog file (.cat) with the hashes of actual files on disk.</span></span>
<span data-ttu-id="29c68-110">Wenn keine Übereinstimmungen gefunden werden, wird der Status "validationfailed" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="29c68-110">If it detects any mismatches, it returns the status as ValidationFailed.</span></span> <span data-ttu-id="29c68-111">Benutzer können alle diese Informationen mithilfe des Parameters -Detailed abrufen.</span><span class="sxs-lookup"><span data-stu-id="29c68-111">Users can retrieve all this information by using the -Detailed parameter.</span></span>
<span data-ttu-id="29c68-112">Außerdem wird der Signierungs Status des Katalogs in der Signatur Eigenschaft angezeigt, der dem aufrufenden `Get-AuthenticodeSignature` Cmdlet in der Katalog Datei entspricht.</span><span class="sxs-lookup"><span data-stu-id="29c68-112">It also displays signing status of catalog in Signature property which is equivalent to calling `Get-AuthenticodeSignature` cmdlet on the catalog file.</span></span>
<span data-ttu-id="29c68-113">Benutzer können außerdem jede Datei während der Überprüfung mithilfe des Parameters -FilesToSkip überspringen.</span><span class="sxs-lookup"><span data-stu-id="29c68-113">Users can also skip any file during validation by using the -FilesToSkip parameter.</span></span>

<span data-ttu-id="29c68-114">Dieses Cmdlet wird nur unter Windows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="29c68-114">This cmdlet is only supported on Windows.</span></span>

## <span data-ttu-id="29c68-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="29c68-115">EXAMPLES</span></span>

### <span data-ttu-id="29c68-116">Beispiel 1: Erstellen und Validieren eines Datei Katalogs</span><span class="sxs-lookup"><span data-stu-id="29c68-116">Example 1: Create and validate a file catalog</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0

Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Valid
```

### <span data-ttu-id="29c68-117">Beispiel 2: Überprüfen eines Datei Katalogs mit detaillierter Ausgabe</span><span class="sxs-lookup"><span data-stu-id="29c68-117">Example 2: Validate a file catalog with detailed output</span></span>

```powershell
Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Status        : Valid
HashAlgorithm : SHA256
CatalogItems  : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
PathItems     : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
Signature     : System.Management.Automation.Signature
```

## <span data-ttu-id="29c68-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29c68-118">PARAMETERS</span></span>

### <span data-ttu-id="29c68-119">-Catalogfilepath</span><span class="sxs-lookup"><span data-stu-id="29c68-119">-CatalogFilePath</span></span>

<span data-ttu-id="29c68-120">Ein Pfad zu einer Katalog Datei (. cat), die die Hashes enthält, die für die Validierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="29c68-120">A path to a catalog file (.cat) that contains the hashes to be used for validation.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="29c68-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="29c68-121">-Confirm</span></span>

<span data-ttu-id="29c68-122">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="29c68-122">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="29c68-123">-Detailed</span><span class="sxs-lookup"><span data-stu-id="29c68-123">-Detailed</span></span>

<span data-ttu-id="29c68-124">Gibt weitere Informationen zu einem detaillierteren Objekt zurück, `CatalogInformation` das die getesteten Dateien, die erwarteten/tatsächlichen Hashwerte und eine Authenticode-Signatur der Katalog Datei enthält, wenn diese signiert ist.</span><span class="sxs-lookup"><span data-stu-id="29c68-124">Returns more information a more detailed `CatalogInformation` object that contains the files tested, their expected/actual hashes, and an Authenticode signature of the catalog file if it's signed.</span></span>

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

### <span data-ttu-id="29c68-125">-Filestoskip</span><span class="sxs-lookup"><span data-stu-id="29c68-125">-FilesToSkip</span></span>

<span data-ttu-id="29c68-126">Ein Array von Pfaden, die nicht als Teil der Validierung getestet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="29c68-126">An array of paths that should not be tested as part of the validation.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29c68-127">-Path</span><span class="sxs-lookup"><span data-stu-id="29c68-127">-Path</span></span>

<span data-ttu-id="29c68-128">Ein Ordner oder ein Array von Dateien, die für die Katalog Datei überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="29c68-128">A folder or array of files that should be validated against the catalog file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="29c68-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="29c68-129">-WhatIf</span></span>

<span data-ttu-id="29c68-130">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="29c68-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="29c68-131">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="29c68-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="29c68-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="29c68-132">CommonParameters</span></span>

<span data-ttu-id="29c68-133">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="29c68-133">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="29c68-134">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="29c68-134">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="29c68-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="29c68-135">INPUTS</span></span>

### <span data-ttu-id="29c68-136">System. IO. Director yinfo [], System. String []</span><span class="sxs-lookup"><span data-stu-id="29c68-136">System.IO.DirectoryInfo[], System.String[]</span></span>

<span data-ttu-id="29c68-137">Die Pipeline akzeptiert ein Array von Zeichen folgen oder `DirectoryInfo` Objekten, die Pfade zu den Dateien darstellen, die überprüft werden müssen.</span><span class="sxs-lookup"><span data-stu-id="29c68-137">The pipeline accepts an array of strings or `DirectoryInfo` objects that represent paths to the files that need to be validated.</span></span>

## <span data-ttu-id="29c68-138">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="29c68-138">OUTPUTS</span></span>

### <span data-ttu-id="29c68-139">System. Management. Automation. catalogvalidationstatus</span><span class="sxs-lookup"><span data-stu-id="29c68-139">System.Management.Automation.CatalogValidationStatus</span></span>

<span data-ttu-id="29c68-140">Der Standard Rückgabetyp, der entweder den Wert `Valid` oder enthält `ValidationFailed` .</span><span class="sxs-lookup"><span data-stu-id="29c68-140">The default return type containing a value of either `Valid` or `ValidationFailed`.</span></span>

### <span data-ttu-id="29c68-141">System. Management. Automation. cataloginformation</span><span class="sxs-lookup"><span data-stu-id="29c68-141">System.Management.Automation.CatalogInformation</span></span>

<span data-ttu-id="29c68-142">Ein ausführlicheres Objekt, das zurückgegeben wird, wenn verwendet `-Detailed` wird. es kann verwendet werden, um bestimmte Dateien zu analysieren, die die Überprüfung möglicherweise bestanden haben oder nicht, welche Hashwerte erwartet werden, und der im Katalog verwendete Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="29c68-142">A more detailed object returned when using `-Detailed` which can be used to analyze specific files that may or may not have passed validation, which hashes were expected vs. found, and the algorithm used in the catalog.</span></span>

## <span data-ttu-id="29c68-143">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="29c68-143">NOTES</span></span>

## <span data-ttu-id="29c68-144">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="29c68-144">RELATED LINKS</span></span>

[<span data-ttu-id="29c68-145">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="29c68-145">New-FileCatalog</span></span>](New-FileCatalog.md)

[<span data-ttu-id="29c68-146">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="29c68-146">PowerShellGet</span></span>](/powershell/module/PowerShellGet)
