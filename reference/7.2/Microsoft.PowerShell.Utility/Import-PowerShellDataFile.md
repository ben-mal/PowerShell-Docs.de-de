---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: d7942abff2974064c52a8a9ac086a280959b3a63
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "99603698"
---
# <span data-ttu-id="8d00e-102">Import-PowerShellDataFile</span><span class="sxs-lookup"><span data-stu-id="8d00e-102">Import-PowerShellDataFile</span></span>

## <span data-ttu-id="8d00e-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8d00e-103">SYNOPSIS</span></span>
<span data-ttu-id="8d00e-104">Importiert Werte aus einer `.PSD1` Datei, ohne ihren Inhalt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8d00e-104">Imports values from a `.PSD1` file without invoking its contents.</span></span>

## <span data-ttu-id="8d00e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8d00e-105">SYNTAX</span></span>

### <span data-ttu-id="8d00e-106">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="8d00e-106">ByPath (Default)</span></span>

```
Import-PowerShellDataFile [-Path] <String[]> [-SkipLimitCheck] [<CommonParameters>]
```

### <span data-ttu-id="8d00e-107">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="8d00e-107">ByLiteralPath</span></span>

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [-SkipLimitCheck] [<CommonParameters>]
```

## <span data-ttu-id="8d00e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8d00e-108">DESCRIPTION</span></span>

<span data-ttu-id="8d00e-109">Mit dem- `Import-PowerShellDataFile` Cmdlet werden Schlüssel-Wert-Paare sicher aus in einer Datei definierten Hash Tabellen importiert `.PSD1` .</span><span class="sxs-lookup"><span data-stu-id="8d00e-109">The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.PSD1` file.</span></span> <span data-ttu-id="8d00e-110">Die Werte können mithilfe von `Invoke-Expression` für den Inhalt der Datei importiert werden.</span><span class="sxs-lookup"><span data-stu-id="8d00e-110">The values could be imported using `Invoke-Expression` on the contents of the file.</span></span>
<span data-ttu-id="8d00e-111">Allerdings `Invoke-Expression` führt jeden in der Datei enthaltenen Code aus.</span><span class="sxs-lookup"><span data-stu-id="8d00e-111">However, `Invoke-Expression` runs any code contained in the file.</span></span> <span data-ttu-id="8d00e-112">Dadurch können unerwünschte Ergebnisse erzeugt oder unsicherer Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8d00e-112">This could produce unwanted results or execute unsafe code.</span></span> <span data-ttu-id="8d00e-113">`Import-PowerShellDataFile` importiert die Daten, ohne den Code aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8d00e-113">`Import-PowerShellDataFile` imports the data without invoking the code.</span></span> <span data-ttu-id="8d00e-114">Standardmäßig gibt es ein 500-Schlüssel Limit, kann jedoch mit dem **skiplimitcheck** -Schalter umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="8d00e-114">By default there is a 500 key limit but can be bypassed with the **SkipLimitCheck** switch.</span></span>

## <span data-ttu-id="8d00e-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8d00e-115">EXAMPLES</span></span>

### <span data-ttu-id="8d00e-116">Beispiel 1: Abrufen von Werten aus PSD1</span><span class="sxs-lookup"><span data-stu-id="8d00e-116">Example 1: Retrieve values from PSD1</span></span>

<span data-ttu-id="8d00e-117">Dieses Beispiel ruft die Schlüssel-Wert-Paare ab, die in der Hash Tabelle gespeichert sind, die in der Datei aufbewahrt wird `Configuration.psd1` .</span><span class="sxs-lookup"><span data-stu-id="8d00e-117">This example retrieves the key-value pairs stored in the hashtable kept inside the `Configuration.psd1` file.</span></span> <span data-ttu-id="8d00e-118">`Get-Content` wird verwendet, um den Inhalt der `Configuration.psd1` Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d00e-118">`Get-Content` is used to show the contents of the `Configuration.psd1` file.</span></span>

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

## <span data-ttu-id="8d00e-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8d00e-119">PARAMETERS</span></span>

### <span data-ttu-id="8d00e-120">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="8d00e-120">-LiteralPath</span></span>

<span data-ttu-id="8d00e-121">Der Pfad zu der Datei, die importiert wird.</span><span class="sxs-lookup"><span data-stu-id="8d00e-121">The path to the file being imported.</span></span> <span data-ttu-id="8d00e-122">Alle Zeichen im Pfad werden als Literalwerte behandelt.</span><span class="sxs-lookup"><span data-stu-id="8d00e-122">All characters in the path are treated as literal values.</span></span>
<span data-ttu-id="8d00e-123">Platzhalter Zeichen werden nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8d00e-123">Wildcard characters are not processed.</span></span>

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

### <span data-ttu-id="8d00e-124">-Path</span><span class="sxs-lookup"><span data-stu-id="8d00e-124">-Path</span></span>

<span data-ttu-id="8d00e-125">Der Pfad zu der Datei, die importiert wird.</span><span class="sxs-lookup"><span data-stu-id="8d00e-125">The path to the file being imported.</span></span> <span data-ttu-id="8d00e-126">Platzhalter sind zulässig, aber nur die erste übereinstimmende Datei wird importiert.</span><span class="sxs-lookup"><span data-stu-id="8d00e-126">Wildcards are allowed but only the first matching file is imported.</span></span>

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

### <span data-ttu-id="8d00e-127">-Skiplimitcheck</span><span class="sxs-lookup"><span data-stu-id="8d00e-127">-SkipLimitCheck</span></span>

<span data-ttu-id="8d00e-128">Importiert standardmäßig `Import-PowerShellDataFile` nur 500-Schlüssel aus einer `.psd1` Datei.</span><span class="sxs-lookup"><span data-stu-id="8d00e-128">By default `Import-PowerShellDataFile` imports only 500 keys from a `.psd1` file.</span></span> <span data-ttu-id="8d00e-129">Verwenden Sie **skiplimitcheck** , um mehr als 500 Schlüssel zu importieren.</span><span class="sxs-lookup"><span data-stu-id="8d00e-129">Use **SkipLimitCheck** to import more than 500 keys.</span></span>

```yaml
Type: Switch
Parameter Sets: All
Aliases:

Required: False
Position: 0
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d00e-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8d00e-130">CommonParameters</span></span>

<span data-ttu-id="8d00e-131">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8d00e-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8d00e-132">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8d00e-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8d00e-133">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8d00e-133">INPUTS</span></span>

## <span data-ttu-id="8d00e-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8d00e-134">OUTPUTS</span></span>

### <span data-ttu-id="8d00e-135">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="8d00e-135">System.Collections.Hashtable</span></span>

## <span data-ttu-id="8d00e-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8d00e-136">NOTES</span></span>

## <span data-ttu-id="8d00e-137">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8d00e-137">RELATED LINKS</span></span>

[<span data-ttu-id="8d00e-138">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="8d00e-138">Invoke-Expression</span></span>](Invoke-Expression.md)

[<span data-ttu-id="8d00e-139">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="8d00e-139">Import-LocalizedData</span></span>](Import-LocalizedData.md)
