---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: 1c66cd3b1cc2fccc58cd75c367b41c445deb1e72
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601707"
---
# <span data-ttu-id="2092b-102">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="2092b-102">New-TemporaryFile</span></span>

## <span data-ttu-id="2092b-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2092b-103">SYNOPSIS</span></span>
<span data-ttu-id="2092b-104">Erstellt eine temporäre Datei.</span><span class="sxs-lookup"><span data-stu-id="2092b-104">Creates a temporary file.</span></span>

## <span data-ttu-id="2092b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2092b-105">SYNTAX</span></span>

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2092b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2092b-106">DESCRIPTION</span></span>

<span data-ttu-id="2092b-107">Mit diesem Cmdlet werden temporäre Dateien erstellt, die Sie in Skripts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2092b-107">This cmdlet creates temporary files that you can use in scripts.</span></span>

<span data-ttu-id="2092b-108">Mit dem- `New-TemporaryFile` Cmdlet wird eine leere Datei mit der `.tmp` Dateinamenerweiterung erstellt.</span><span class="sxs-lookup"><span data-stu-id="2092b-108">The `New-TemporaryFile` cmdlet creates an empty file that has the `.tmp` file name extension.</span></span>
<span data-ttu-id="2092b-109">Dieses Cmdlet benennt die Datei `tmp<NNNN>.tmp` , wobei `<NNNN>` eine zufällige hexadezimal Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="2092b-109">This cmdlet names the file `tmp<NNNN>.tmp`, where `<NNNN>` is a random hexadecimal number.</span></span>
<span data-ttu-id="2092b-110">Mit dem-Cmdlet wird die Datei **in Ihrem temporären** Ordner erstellt.</span><span class="sxs-lookup"><span data-stu-id="2092b-110">The cmdlet creates the file in your **TEMP** folder.</span></span>

<span data-ttu-id="2092b-111">Dieses Cmdlet verwendet die [Path. GetTempPath ()](/dotnet/api/system.io.path.gettemppath) -Methode, um **den temporären Ordner zu** suchen.</span><span class="sxs-lookup"><span data-stu-id="2092b-111">This cmdlet uses the [Path.GetTempPath()](/dotnet/api/system.io.path.gettemppath) method to find your **TEMP** folder.</span></span> <span data-ttu-id="2092b-112">Diese Methode überprüft, ob Umgebungsvariablen in der folgenden Reihenfolge vorhanden sind, und verwendet den ersten gefundenen Pfad:</span><span class="sxs-lookup"><span data-stu-id="2092b-112">This method checks for the existence of environment variables in the following order and uses the first path found:</span></span>

- <span data-ttu-id="2092b-113">Auf Windows-Plattformen:</span><span class="sxs-lookup"><span data-stu-id="2092b-113">On Windows platforms:</span></span>

  1. <span data-ttu-id="2092b-114">Der von der TMP-Umgebungsvariablen angegebene Pfad.</span><span class="sxs-lookup"><span data-stu-id="2092b-114">The path specified by the TMP environment variable.</span></span>
  1. <span data-ttu-id="2092b-115">Der von der TEMP-Umgebungsvariablen angegebene Pfad.</span><span class="sxs-lookup"><span data-stu-id="2092b-115">The path specified by the TEMP environment variable.</span></span>
  1. <span data-ttu-id="2092b-116">Der von der User Profile-Umgebungsvariablen angegebene Pfad.</span><span class="sxs-lookup"><span data-stu-id="2092b-116">The path specified by the USERPROFILE environment variable.</span></span>
  1. <span data-ttu-id="2092b-117">Das Windows-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2092b-117">The Windows directory.</span></span>

- <span data-ttu-id="2092b-118">Auf nicht-Windows-Plattformen: verwendet den von der TMPDIR-Umgebungsvariablen angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="2092b-118">On non-Windows platforms: Uses the path specified by the TMPDIR environment variable.</span></span>

## <span data-ttu-id="2092b-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2092b-119">EXAMPLES</span></span>

### <span data-ttu-id="2092b-120">Beispiel 1: Erstellen einer temporären Datei</span><span class="sxs-lookup"><span data-stu-id="2092b-120">Example 1: Create a temporary file</span></span>

```powershell
$TempFile = New-TemporaryFile
```

<span data-ttu-id="2092b-121">Mit diesem Befehl `.tmp` wird eine Datei in Ihrem temporären Ordner generiert, und anschließend wird ein Verweis auf die Datei in der `$TempFile` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2092b-121">This command generates a `.tmp` file in your temporary folder, and then stores a reference to the file in the `$TempFile` variable.</span></span> <span data-ttu-id="2092b-122">Sie können diese Datei später in Ihrem Skript verwenden.</span><span class="sxs-lookup"><span data-stu-id="2092b-122">You can use this file later in your script.</span></span>

## <span data-ttu-id="2092b-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2092b-123">PARAMETERS</span></span>

### <span data-ttu-id="2092b-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2092b-124">-Confirm</span></span>

<span data-ttu-id="2092b-125">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="2092b-125">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2092b-126">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2092b-126">-WhatIf</span></span>

<span data-ttu-id="2092b-127">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2092b-127">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2092b-128">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2092b-128">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2092b-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2092b-129">CommonParameters</span></span>

<span data-ttu-id="2092b-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2092b-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2092b-131">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="2092b-131">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2092b-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2092b-132">INPUTS</span></span>

## <span data-ttu-id="2092b-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2092b-133">OUTPUTS</span></span>

### <span data-ttu-id="2092b-134">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="2092b-134">System.IO.FileInfo</span></span>

<span data-ttu-id="2092b-135">Dieses Cmdlet gibt ein **FileInfo** -Objekt zurück, das die temporäre Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="2092b-135">This cmdlet returns a **FileInfo** object that represents the temporary file.</span></span>

## <span data-ttu-id="2092b-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2092b-136">NOTES</span></span>

## <span data-ttu-id="2092b-137">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2092b-137">RELATED LINKS</span></span>

