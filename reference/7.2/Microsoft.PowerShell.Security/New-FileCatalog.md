---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: 230f027a021017e948c8c53e5e6d0c092127ad85
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602318"
---
# <span data-ttu-id="fb1d1-102">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="fb1d1-102">New-FileCatalog</span></span>

## <span data-ttu-id="fb1d1-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fb1d1-103">SYNOPSIS</span></span>
<span data-ttu-id="fb1d1-104">`New-FileCatalog` erstellt eine Katalog Datei mit Dateihashes, die verwendet werden können, um die Authentizität einer Datei zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-104">`New-FileCatalog` creates a catalog file of file hashes that can be used to validate the authenticity of a file.</span></span>

## <span data-ttu-id="fb1d1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fb1d1-105">SYNTAX</span></span>

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="fb1d1-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fb1d1-106">DESCRIPTION</span></span>

<span data-ttu-id="fb1d1-107">`New-FileCatalog` erstellt eine [Windows-Katalog Datei](/windows-hardware/drivers/install/catalog-files) für eine Gruppe von Ordnern und Dateien.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-107">`New-FileCatalog` creates a [Windows catalog file](/windows-hardware/drivers/install/catalog-files) for a set of folders and files.</span></span> <span data-ttu-id="fb1d1-108">Diese Katalog Datei enthält Hashes für alle Dateien in den angegebenen Pfaden.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-108">This catalog file contains hashes for all files in the provided paths.</span></span> <span data-ttu-id="fb1d1-109">Benutzer können den Katalog dann mit Ihren Dateien verteilen, damit Benutzer überprüfen können, ob seit der Erstellung des Katalogs Änderungen an den Ordnern vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-109">Users can then distribute the catalog with their files so that users can validate whether any changes have been made to the folders since catalog creation time.</span></span>

<span data-ttu-id="fb1d1-110">Die Katalogversionen 1 und 2 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-110">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="fb1d1-111">Version 1 verwendet den (veralteten) SHA1-Hash Algorithmus, um Dateihashes zu erstellen, und Version 2 verwendet SHA256.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-111">Version 1 uses the (deprecated) SHA1 hashing algorithm to create file hashes, and version 2 uses SHA256.</span></span> <span data-ttu-id="fb1d1-112">Katalogversion 2 wird weder auf Windows Server 2008 R2 noch auf Windows 7 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-112">Catalog version 2 is not supported on Windows Server 2008 R2 or Windows 7.</span></span> <span data-ttu-id="fb1d1-113">Daher sollten Sie die Katalogversion 2 mit Windows 8, Windows Server 2012 und späteren Betriebssystemen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-113">You should use catalog version 2 on Windows 8, Windows Server 2012, and later operating systems.</span></span>

## <span data-ttu-id="fb1d1-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fb1d1-114">EXAMPLES</span></span>

### <span data-ttu-id="fb1d1-115">Beispiel 1: Erstellen eines Datei Katalogs für `Microsoft.PowerShell.Utility`</span><span class="sxs-lookup"><span data-stu-id="fb1d1-115">Example 1: Create a file catalog for `Microsoft.PowerShell.Utility`</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## <span data-ttu-id="fb1d1-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fb1d1-116">PARAMETERS</span></span>

### <span data-ttu-id="fb1d1-117">-Catalogfilepath</span><span class="sxs-lookup"><span data-stu-id="fb1d1-117">-CatalogFilePath</span></span>

<span data-ttu-id="fb1d1-118">Ein Pfad zu einer Datei oder einem Ordner, in der die Katalog Datei (. cat) platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-118">A path to a file or folder where the catalog file (.cat) should be placed.</span></span> <span data-ttu-id="fb1d1-119">Wenn ein Ordner Pfad angegeben wird, wird der Standard Dateiname `catalog.cat` verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-119">If a folder path is specified, the default filename `catalog.cat` will be used.</span></span>

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

### <span data-ttu-id="fb1d1-120">-CatalogVersion</span><span class="sxs-lookup"><span data-stu-id="fb1d1-120">-CatalogVersion</span></span>

<span data-ttu-id="fb1d1-121">Akzeptiert `1.0` oder `2.0` als mögliche Werte zum Angeben der Katalogversion.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-121">Accepts `1.0` or `2.0` as possible values for specifying the catalog version.</span></span> <span data-ttu-id="fb1d1-122">`1.0` sollte nach Möglichkeit vermieden werden, da der unsichere SHA-1-Hash Algorithmus verwendet wird, während `2.0` den sicheren SHA-256-Algorithmus verwendet, `1.0` ist jedoch der einzige unterstützte Algorithmus für Windows 7 und Server 2008R2.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-122">`1.0` should be used avoided whenever possible, as it uses the insecure SHA-1 hash algorithm, while `2.0` uses the secure SHA-256 algorithm However, `1.0` is the only supported algorithm on Windows 7 and Server 2008R2.</span></span>

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

### <span data-ttu-id="fb1d1-123">-Path</span><span class="sxs-lookup"><span data-stu-id="fb1d1-123">-Path</span></span>

<span data-ttu-id="fb1d1-124">Akzeptiert einen Pfad oder ein Array von Pfaden zu Dateien oder Ordnern, die in die Katalog Datei eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-124">Accepts a path or array of paths to files or folders that should be included in the catalog file.</span></span> <span data-ttu-id="fb1d1-125">Wenn ein Ordner angegeben wird, werden alle Dateien im Ordner ebenfalls eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-125">If a folder is specified, all the files in the folder will be included as well.</span></span>

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

### <span data-ttu-id="fb1d1-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fb1d1-126">-Confirm</span></span>

<span data-ttu-id="fb1d1-127">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fb1d1-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fb1d1-128">-WhatIf</span></span>

<span data-ttu-id="fb1d1-129">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-129">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fb1d1-130">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fb1d1-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fb1d1-131">CommonParameters</span></span>

<span data-ttu-id="fb1d1-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fb1d1-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fb1d1-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fb1d1-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fb1d1-134">INPUTS</span></span>

### <span data-ttu-id="fb1d1-135">System.String</span><span class="sxs-lookup"><span data-stu-id="fb1d1-135">System.String</span></span>

<span data-ttu-id="fb1d1-136">Die Pipeline verwendet eine Zeichenfolge, die als Katalog Dateiname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-136">The pipeline takes a string that is used as the catalog filename.</span></span>

## <span data-ttu-id="fb1d1-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fb1d1-137">OUTPUTS</span></span>

### <span data-ttu-id="fb1d1-138">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="fb1d1-138">System.IO.FileInfo</span></span>

## <span data-ttu-id="fb1d1-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fb1d1-139">NOTES</span></span>

<span data-ttu-id="fb1d1-140">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb1d1-140">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="fb1d1-141">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fb1d1-141">RELATED LINKS</span></span>

[<span data-ttu-id="fb1d1-142">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="fb1d1-142">Test-FileCatalog</span></span>](Test-FileCatalog.md)

[<span data-ttu-id="fb1d1-143">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="fb1d1-143">PowerShellGet</span></span>](/powerShell/module/powershellget)
