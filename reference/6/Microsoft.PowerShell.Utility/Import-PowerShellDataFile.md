---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: c3ae9fa2189b3c8b41f092b1f2ac2dfca54aebc6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214967"
---
# <span data-ttu-id="0d789-103">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="0d789-103">Import-PowerShellDataFile</span></span>

## <span data-ttu-id="0d789-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0d789-104">SYNOPSIS</span></span>
<span data-ttu-id="0d789-105">Importiert Werte aus einer `.PSD1` Datei, ohne ihren Inhalt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0d789-105">Imports values from a `.PSD1` file without invoking its contents.</span></span>

## <span data-ttu-id="0d789-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0d789-106">SYNTAX</span></span>

### <span data-ttu-id="0d789-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="0d789-107">ByPath (Default)</span></span>

```
Import-PowerShellDataFile [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="0d789-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="0d789-108">ByLiteralPath</span></span>

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="0d789-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0d789-109">DESCRIPTION</span></span>

<span data-ttu-id="0d789-110">Mit dem- `Import-PowerShellDataFile` Cmdlet werden Schlüssel-Wert-Paare sicher aus in einer Datei definierten Hash Tabellen importiert `.PSD1` .</span><span class="sxs-lookup"><span data-stu-id="0d789-110">The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.PSD1` file.</span></span> <span data-ttu-id="0d789-111">Die Werte können mithilfe von `Invoke-Expression` für den Inhalt der Datei importiert werden.</span><span class="sxs-lookup"><span data-stu-id="0d789-111">The values could be imported using `Invoke-Expression` on the contents of the file.</span></span>
<span data-ttu-id="0d789-112">Allerdings `Invoke-Expression` führt jeden in der Datei enthaltenen Code aus.</span><span class="sxs-lookup"><span data-stu-id="0d789-112">However, `Invoke-Expression` runs any code contained in the file.</span></span> <span data-ttu-id="0d789-113">Dadurch können unerwünschte Ergebnisse erzeugt oder unsicherer Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d789-113">This could produce unwanted results or execute unsafe code.</span></span> <span data-ttu-id="0d789-114">`Import-PowerShellDataFile` importiert die Daten, ohne den Code aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0d789-114">`Import-PowerShellDataFile` imports the data without invoking the code.</span></span>

## <span data-ttu-id="0d789-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0d789-115">EXAMPLES</span></span>

### <span data-ttu-id="0d789-116">Beispiel 1: Abrufen von Werten aus PSD1</span><span class="sxs-lookup"><span data-stu-id="0d789-116">Example 1: Retrieve values from PSD1</span></span>

<span data-ttu-id="0d789-117">Dieses Beispiel ruft die Schlüssel-Wert-Paare ab, die in der Hash Tabelle gespeichert sind, die in der Datei aufbewahrt wird `Configuration.psd1` .</span><span class="sxs-lookup"><span data-stu-id="0d789-117">This example retrieves the key-value pairs stored in the hashtable kept inside the `Configuration.psd1` file.</span></span> <span data-ttu-id="0d789-118">`Get-Content` wird verwendet, um den Inhalt der `Configuration.psd1` Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0d789-118">`Get-Content` is used to show the contents of the `Configuration.psd1` file.</span></span>

```powershell
Get-Content .\Configuration.psd1
$config = Import-PowerShellDataFile .\Configuration.psd1
$config.AllNodes
```

```Output
@{
    AllNodes = @(
        @{
            NodeName = 'DSC-01'
        }
        @{
            NodeName = 'DSC-02'
        }
    )
}

Name                           Value
----                           -----
NodeName                       DSC-01
NodeName                       DSC-02
```

## <span data-ttu-id="0d789-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0d789-119">PARAMETERS</span></span>

### <span data-ttu-id="0d789-120">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="0d789-120">-LiteralPath</span></span>

<span data-ttu-id="0d789-121">Der Pfad zu der Datei, die importiert wird.</span><span class="sxs-lookup"><span data-stu-id="0d789-121">The path to the file being imported.</span></span> <span data-ttu-id="0d789-122">Alle Zeichen im Pfad werden als Literalwerte behandelt.</span><span class="sxs-lookup"><span data-stu-id="0d789-122">All characters in the path are treated as literal values.</span></span>
<span data-ttu-id="0d789-123">Platzhalter Zeichen werden nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0d789-123">Wildcard characters are not processed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0d789-124">-Path</span><span class="sxs-lookup"><span data-stu-id="0d789-124">-Path</span></span>

<span data-ttu-id="0d789-125">Der Pfad zu der Datei, die importiert wird.</span><span class="sxs-lookup"><span data-stu-id="0d789-125">The path to the file being imported.</span></span> <span data-ttu-id="0d789-126">Platzhalter sind zulässig, aber nur die erste übereinstimmende Datei wird importiert.</span><span class="sxs-lookup"><span data-stu-id="0d789-126">Wildcards are allowed but only the first matching file is imported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="0d789-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0d789-127">CommonParameters</span></span>

<span data-ttu-id="0d789-128">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0d789-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0d789-129">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="0d789-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0d789-130">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0d789-130">INPUTS</span></span>

## <span data-ttu-id="0d789-131">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0d789-131">OUTPUTS</span></span>

### <span data-ttu-id="0d789-132">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="0d789-132">System.Collections.Hashtable</span></span>

## <span data-ttu-id="0d789-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0d789-133">NOTES</span></span>

## <span data-ttu-id="0d789-134">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0d789-134">RELATED LINKS</span></span>

[<span data-ttu-id="0d789-135">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="0d789-135">Invoke-Expression</span></span>](Invoke-Expression.md)

[<span data-ttu-id="0d789-136">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="0d789-136">Import-LocalizedData</span></span>](Import-LocalizedData.md)
