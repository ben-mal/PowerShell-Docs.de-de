---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: c4bfe6b4ed04ae638421c18f5095403057dc03c9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210343"
---
# <span data-ttu-id="76ace-103">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="76ace-103">New-TemporaryFile</span></span>

## <span data-ttu-id="76ace-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="76ace-104">SYNOPSIS</span></span>
<span data-ttu-id="76ace-105">Erstellt eine temporäre Datei.</span><span class="sxs-lookup"><span data-stu-id="76ace-105">Creates a temporary file.</span></span>

## <span data-ttu-id="76ace-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="76ace-106">SYNTAX</span></span>

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="76ace-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="76ace-107">DESCRIPTION</span></span>

<span data-ttu-id="76ace-108">Mit diesem Cmdlet werden temporäre Dateien erstellt, die Sie in Skripts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="76ace-108">This cmdlet creates temporary files that you can use in scripts.</span></span>

<span data-ttu-id="76ace-109">Mit dem- `New-TemporaryFile` Cmdlet wird eine leere Datei mit der `.tmp` Dateinamenerweiterung erstellt.</span><span class="sxs-lookup"><span data-stu-id="76ace-109">The `New-TemporaryFile` cmdlet creates an empty file that has the `.tmp` file name extension.</span></span>
<span data-ttu-id="76ace-110">Dieses Cmdlet benennt die Datei `tmp<NNNN>.tmp` , wobei `<NNNN>` eine zufällige hexadezimal Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="76ace-110">This cmdlet names the file `tmp<NNNN>.tmp`, where `<NNNN>` is a random hexadecimal number.</span></span>
<span data-ttu-id="76ace-111">Mit dem-Cmdlet wird die Datei **in Ihrem temporären** Ordner erstellt.</span><span class="sxs-lookup"><span data-stu-id="76ace-111">The cmdlet creates the file in your **TEMP** folder.</span></span>

<span data-ttu-id="76ace-112">Dieses Cmdlet verwendet die [Path. GetTempPath ()](/dotnet/api/system.io.path.gettemppath) -Methode, um **den temporären Ordner zu** suchen.</span><span class="sxs-lookup"><span data-stu-id="76ace-112">This cmdlet uses the [Path.GetTempPath()](/dotnet/api/system.io.path.gettemppath) method to find your **TEMP** folder.</span></span> <span data-ttu-id="76ace-113">Diese Methode überprüft, ob Umgebungsvariablen in der folgenden Reihenfolge vorhanden sind, und verwendet den ersten gefundenen Pfad:</span><span class="sxs-lookup"><span data-stu-id="76ace-113">This method checks for the existence of environment variables in the following order and uses the first path found:</span></span>

- <span data-ttu-id="76ace-114">Auf Windows-Plattformen:</span><span class="sxs-lookup"><span data-stu-id="76ace-114">On Windows platforms:</span></span>

  1. <span data-ttu-id="76ace-115">Der von der TMP-Umgebungsvariablen angegebene Pfad.</span><span class="sxs-lookup"><span data-stu-id="76ace-115">The path specified by the TMP environment variable.</span></span>
  1. <span data-ttu-id="76ace-116">Der von der TEMP-Umgebungsvariablen angegebene Pfad.</span><span class="sxs-lookup"><span data-stu-id="76ace-116">The path specified by the TEMP environment variable.</span></span>
  1. <span data-ttu-id="76ace-117">Der von der User Profile-Umgebungsvariablen angegebene Pfad.</span><span class="sxs-lookup"><span data-stu-id="76ace-117">The path specified by the USERPROFILE environment variable.</span></span>
  1. <span data-ttu-id="76ace-118">Das Windows-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="76ace-118">The Windows directory.</span></span>

- <span data-ttu-id="76ace-119">Auf nicht-Windows-Plattformen: verwendet den von der TMPDIR-Umgebungsvariablen angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="76ace-119">On non-Windows platforms: Uses the path specified by the TMPDIR environment variable.</span></span>

## <span data-ttu-id="76ace-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="76ace-120">EXAMPLES</span></span>

### <span data-ttu-id="76ace-121">Beispiel 1: Erstellen einer temporären Datei</span><span class="sxs-lookup"><span data-stu-id="76ace-121">Example 1: Create a temporary file</span></span>

```powershell
$TempFile = New-TemporaryFile
```

<span data-ttu-id="76ace-122">Mit diesem Befehl `.tmp` wird eine Datei in Ihrem temporären Ordner generiert, und anschließend wird ein Verweis auf die Datei in der `$TempFile` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="76ace-122">This command generates a `.tmp` file in your temporary folder, and then stores a reference to the file in the `$TempFile` variable.</span></span> <span data-ttu-id="76ace-123">Sie können diese Datei später in Ihrem Skript verwenden.</span><span class="sxs-lookup"><span data-stu-id="76ace-123">You can use this file later in your script.</span></span>

## <span data-ttu-id="76ace-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="76ace-124">PARAMETERS</span></span>

### <span data-ttu-id="76ace-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="76ace-125">-Confirm</span></span>

<span data-ttu-id="76ace-126">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="76ace-126">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="76ace-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="76ace-127">-WhatIf</span></span>

<span data-ttu-id="76ace-128">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="76ace-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="76ace-129">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="76ace-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="76ace-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="76ace-130">CommonParameters</span></span>

<span data-ttu-id="76ace-131">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="76ace-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="76ace-132">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="76ace-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="76ace-133">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="76ace-133">INPUTS</span></span>

## <span data-ttu-id="76ace-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="76ace-134">OUTPUTS</span></span>

### <span data-ttu-id="76ace-135">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="76ace-135">System.IO.FileInfo</span></span>

<span data-ttu-id="76ace-136">Dieses Cmdlet gibt ein **FileInfo** -Objekt zurück, das die temporäre Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="76ace-136">This cmdlet returns a **FileInfo** object that represents the temporary file.</span></span>

## <span data-ttu-id="76ace-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="76ace-137">NOTES</span></span>

## <span data-ttu-id="76ace-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="76ace-138">RELATED LINKS</span></span>
