---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: aef0f6e63be07f0568927f8e65df675ff4f9eba7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210180"
---
# <span data-ttu-id="122b0-103">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="122b0-103">New-FileCatalog</span></span>

## <span data-ttu-id="122b0-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="122b0-104">SYNOPSIS</span></span>
<span data-ttu-id="122b0-105">`New-FileCatalog` erstellt eine Katalog Datei mit Dateihashes, die verwendet werden können, um die Authentizität einer Datei zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="122b0-105">`New-FileCatalog` creates a catalog file of file hashes that can be used to validate the authenticity of a file.</span></span>

## <span data-ttu-id="122b0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="122b0-106">SYNTAX</span></span>

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="122b0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="122b0-107">DESCRIPTION</span></span>

<span data-ttu-id="122b0-108">`New-FileCatalog` erstellt eine [Windows-Katalog Datei](/windows-hardware/drivers/install/catalog-files) für eine Gruppe von Ordnern und Dateien.</span><span class="sxs-lookup"><span data-stu-id="122b0-108">`New-FileCatalog` creates a [Windows catalog file](/windows-hardware/drivers/install/catalog-files) for a set of folders and files.</span></span>
<span data-ttu-id="122b0-109">Diese Katalog Datei enthält Hashes für alle Dateien in den angegebenen Pfaden.</span><span class="sxs-lookup"><span data-stu-id="122b0-109">This catalog file contains hashes for all files in the provided paths.</span></span>
<span data-ttu-id="122b0-110">Benutzer können den Katalog dann mit Ihren Dateien verteilen, damit Benutzer überprüfen können, ob seit der Erstellung des Katalogs Änderungen an den Ordnern vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="122b0-110">Users can then distribute the catalog with their files so that users can validate whether any changes have been made to the folders since catalog creation time.</span></span>

<span data-ttu-id="122b0-111">Die Katalogversionen 1 und 2 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="122b0-111">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="122b0-112">Version 1 verwendet den (veralteten) SHA1-Hash Algorithmus, um Dateihashes zu erstellen, und Version 2 verwendet SHA256.</span><span class="sxs-lookup"><span data-stu-id="122b0-112">Version 1 uses the (deprecated) SHA1 hashing algorithm to create file hashes, and version 2 uses SHA256.</span></span>
<span data-ttu-id="122b0-113">Katalogversion 2 wird weder auf Windows Server 2008 R2 noch auf Windows 7 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="122b0-113">Catalog version 2 is not supported on Windows Server 2008 R2 or Windows 7.</span></span>
<span data-ttu-id="122b0-114">Daher sollten Sie die Katalogversion 2 mit Windows 8, Windows Server 2012 und späteren Betriebssystemen verwenden.</span><span class="sxs-lookup"><span data-stu-id="122b0-114">You should use catalog version 2 on Windows 8, Windows Server 2012, and later operating systems.</span></span>

## <span data-ttu-id="122b0-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="122b0-115">EXAMPLES</span></span>

### <span data-ttu-id="122b0-116">Beispiel 1: Erstellen eines Datei Katalogs für `Microsoft.PowerShell.Utility`</span><span class="sxs-lookup"><span data-stu-id="122b0-116">Example 1: Create a file catalog for `Microsoft.PowerShell.Utility`</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## <span data-ttu-id="122b0-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="122b0-117">PARAMETERS</span></span>

### <span data-ttu-id="122b0-118">-Catalogfilepath</span><span class="sxs-lookup"><span data-stu-id="122b0-118">-CatalogFilePath</span></span>

<span data-ttu-id="122b0-119">Ein Pfad zu einer Datei oder einem Ordner, in der die Katalog Datei (. cat) platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="122b0-119">A path to a file or folder where the catalog file (.cat) should be placed.</span></span>
<span data-ttu-id="122b0-120">Wenn ein Ordner Pfad angegeben wird, wird der Standard Dateiname `catalog.cat` verwendet.</span><span class="sxs-lookup"><span data-stu-id="122b0-120">If a folder path is specified, the default filename `catalog.cat` will be used.</span></span>

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

### <span data-ttu-id="122b0-121">-CatalogVersion</span><span class="sxs-lookup"><span data-stu-id="122b0-121">-CatalogVersion</span></span>

<span data-ttu-id="122b0-122">Akzeptiert `1.0` oder `2.0` als mögliche Werte zum Angeben der Katalogversion.</span><span class="sxs-lookup"><span data-stu-id="122b0-122">Accepts `1.0` or `2.0` as possible values for specifying the catalog version.</span></span>
<span data-ttu-id="122b0-123">`1.0` sollte nach Möglichkeit vermieden werden, da der unsichere SHA-1-Hash Algorithmus verwendet wird, während `2.0` den sicheren SHA-256-Algorithmus verwendet, `1.0` ist jedoch der einzige unterstützte Algorithmus für Windows 7 und Server 2008R2.</span><span class="sxs-lookup"><span data-stu-id="122b0-123">`1.0` should be used avoided whenever possible, as it uses the insecure SHA-1 hash algorithm, while `2.0` uses the secure SHA-256 algorithm However, `1.0` is the only supported algorithm on Windows 7 and Server 2008R2.</span></span>

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

### <span data-ttu-id="122b0-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="122b0-124">-Confirm</span></span>

<span data-ttu-id="122b0-125">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="122b0-125">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="122b0-126">-Path</span><span class="sxs-lookup"><span data-stu-id="122b0-126">-Path</span></span>

<span data-ttu-id="122b0-127">Akzeptiert einen Pfad oder ein Array von Pfaden zu Dateien oder Ordnern, die in die Katalog Datei eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="122b0-127">Accepts a path or array of paths to files or folders that should be included in the catalog file.</span></span>
<span data-ttu-id="122b0-128">Wenn ein Ordner angegeben wird, werden alle Dateien im Ordner ebenfalls eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="122b0-128">If a folder is specified, all the files in the folder will be included as well.</span></span>

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

### <span data-ttu-id="122b0-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="122b0-129">-WhatIf</span></span>

<span data-ttu-id="122b0-130">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="122b0-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="122b0-131">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="122b0-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="122b0-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="122b0-132">CommonParameters</span></span>

<span data-ttu-id="122b0-133">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="122b0-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="122b0-134">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="122b0-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="122b0-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="122b0-135">INPUTS</span></span>

### <span data-ttu-id="122b0-136">System.String</span><span class="sxs-lookup"><span data-stu-id="122b0-136">System.String</span></span>

<span data-ttu-id="122b0-137">Die Pipeline verwendet eine Zeichenfolge, die als Katalog Dateiname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="122b0-137">The pipeline takes a string that is used as the catalog filename.</span></span>

## <span data-ttu-id="122b0-138">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="122b0-138">OUTPUTS</span></span>

### <span data-ttu-id="122b0-139">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="122b0-139">System.IO.FileInfo</span></span>

## <span data-ttu-id="122b0-140">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="122b0-140">NOTES</span></span>

## <span data-ttu-id="122b0-141">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="122b0-141">RELATED LINKS</span></span>

[<span data-ttu-id="122b0-142">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="122b0-142">Test-FileCatalog</span></span>](Test-FileCatalog.md)

[<span data-ttu-id="122b0-143">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="122b0-143">PowerShellGet</span></span>](/powerShell/module/powershellget)
