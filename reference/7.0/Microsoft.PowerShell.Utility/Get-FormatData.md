---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-formatdata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FormatData
ms.openlocfilehash: 22cdfce0ca9e591dfc97a6ac7ef2c1e0f0ed37ab
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210791"
---
# <span data-ttu-id="4ae21-103">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="4ae21-103">Get-FormatData</span></span>

## <span data-ttu-id="4ae21-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4ae21-104">SYNOPSIS</span></span>
<span data-ttu-id="4ae21-105">Ruft die Formatierungsdaten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="4ae21-105">Gets the formatting data in the current session.</span></span>

## <span data-ttu-id="4ae21-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4ae21-106">SYNTAX</span></span>

```
Get-FormatData [[-TypeName] <String[]>] [-PowerShellVersion <Version>] [<CommonParameters>]
```

## <span data-ttu-id="4ae21-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4ae21-107">DESCRIPTION</span></span>

<span data-ttu-id="4ae21-108">Mit dem- `Get-FormatData` Cmdlet werden die Formatierungsdaten in der aktuellen Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4ae21-108">The `Get-FormatData` cmdlet gets the formatting data in the current session.</span></span>

<span data-ttu-id="4ae21-109">Die Formatierungsdaten in der Sitzung umfassen das Formatieren von Daten aus `Format.ps1xml` Formatierungs Dateien, z. b. im `$PSHOME` Verzeichnis, das Formatieren von Daten für Module, die in die Sitzung importiert werden, und das Formatieren von Daten für Befehle, die Sie mithilfe des Cmdlets in die Sitzung importieren `Import-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="4ae21-109">The formatting data in the session includes formatting data from `Format.ps1xml` formatting files, such as those in the `$PSHOME` directory, formatting data for modules that you import into the session, and formatting data for commands that you import into your session by using the `Import-PSSession` cmdlet.</span></span>

<span data-ttu-id="4ae21-110">Mit diesem Cmdlet können Sie die Formatierungsdaten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="4ae21-110">You can use this cmdlet to examine the formatting data.</span></span> <span data-ttu-id="4ae21-111">Anschließend können Sie mit dem `Export-FormatData` Cmdlet die Objekte serialisieren, Sie in XML konvertieren und in `Format.ps1xml` Dateien speichern.</span><span class="sxs-lookup"><span data-stu-id="4ae21-111">Then, you can use the `Export-FormatData` cmdlet to serialize the objects, convert them to XML, and save them in `Format.ps1xml` files.</span></span>

<span data-ttu-id="4ae21-112">Weitere Informationen zum Formatieren von Dateien in PowerShell finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="4ae21-112">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="4ae21-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4ae21-113">EXAMPLES</span></span>

### <span data-ttu-id="4ae21-114">Beispiel 1: alle Formatierungsdaten erhalten</span><span class="sxs-lookup"><span data-stu-id="4ae21-114">Example 1: Get all formatting data</span></span>

<span data-ttu-id="4ae21-115">In diesem Beispiel werden alle Formatierungsdaten in der Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4ae21-115">This example gets all the formatting data in the session.</span></span>

```powershell
Get-FormatData -PowerShellVersion 5.1
```

> [!IMPORTANT]
> <span data-ttu-id="4ae21-116">Um sicherzustellen, dass die vollständigen typformatierungs Informationen zurückgegeben werden, sollten Sie immer den **PowerShellVersion** -Parameter mit dem Wert einschließen, `5.1` Wenn Sie einen lokalen Aufruf von verwenden `Get-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="4ae21-116">To ensure that the complete type formatting information is returned, you should always include the **PowerShellVersion** parameter with the value `5.1` when using a local invocation of `Get-FormatData`.</span></span> <span data-ttu-id="4ae21-117">Wenn der-Parameter und der-Wert weggelassen werden, werden möglicherweise nicht alle richtigen Typinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ae21-117">If the parameter and value are omitted, you may not get all the correct type information.</span></span>

### <span data-ttu-id="4ae21-118">Beispiel 2: Formatieren von Daten nach Typname</span><span class="sxs-lookup"><span data-stu-id="4ae21-118">Example 2: Get formatting data by type name</span></span>

<span data-ttu-id="4ae21-119">In diesem Beispiel werden die Formatierungsdaten Elemente abgerufen, deren Namen mit beginnen `System.Management.Automation.Cmd` .</span><span class="sxs-lookup"><span data-stu-id="4ae21-119">This example gets the formatting data items whose names begin with `System.Management.Automation.Cmd`.</span></span>

```powershell
Get-FormatData -TypeName 'System.Management.Automation.Cmd*' -PowerShellVersion 5.1
```

### <span data-ttu-id="4ae21-120">Beispiel 3: Untersuchen eines Formatierungsdaten Objekts</span><span class="sxs-lookup"><span data-stu-id="4ae21-120">Example 3: Examine a formatting data object</span></span>

<span data-ttu-id="4ae21-121">Dieses Beispiel zeigt, wie Sie ein Formatierungsdatenobjekt abrufen und seine Eigenschaften untersuchen.</span><span class="sxs-lookup"><span data-stu-id="4ae21-121">This example shows how to get a formatting data object and examine its properties.</span></span>

```powershell
$F = Get-FormatData -TypeName 'System.Management.Automation.Cmd*' -PowerShellVersion 5.1
$F
```

```Output
TypeName        FormatViewDefinition
--------        --------------------
HelpInfoShort   {help , TableControl}
```

```powershell
$F.FormatViewDefinition[0].control
```

```Output
Headers          : {System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader}
Rows             : {System.Management.Automation.TableControlRow}
AutoSize         : False
HideTableHeaders : False
GroupBy          :
OutOfBand        : False
```

```powershell
$F.FormatViewDefinition[0].control.Headers
```

```Output
Label       Alignment Width
-----       --------- -----
CommandType Undefined    15
Name        Undefined    50
Version     Undefined    10
Source      Undefined     0
```

### <span data-ttu-id="4ae21-122">Beispiel 4: erhalten von Formatierungsdaten und Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="4ae21-122">Example 4: Get formatting data and export it</span></span>

<span data-ttu-id="4ae21-123">In diesem Beispiel wird gezeigt, wie `Get-FormatData` und verwendet `Export-FormatData` werden, um die Formatierungsdaten zu exportieren, die von einem Modul hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4ae21-123">This example shows how to use `Get-FormatData` and `Export-FormatData` to export the formatting data that is added by a module.</span></span>

```powershell
$A = Get-FormatData -PowerShellVersion 5.1
Import-Module bitstransfer
$B = Get-FormatData -PowerShellVersion 5.1
Compare-Object $A $B
```

```Output
InputObject                                                SideIndicator
-----------                                                -------------
Microsoft.BackgroundIntelligentTransfer.Management.BitsJob =>
```

```powershell
Get-FormatData *bits* | Export-FormatData -FilePath c:\test\bits.format.ps1xml
Get-Content c:\test\bits.format.ps1xml
```

```Output
<?xml version="1.0" encoding="utf-8"?><Configuration><ViewDefinitions>
<View><Name>Microsoft.BackgroundIntelligentTransfer.Management.BitsJob</Name>
...
```

<span data-ttu-id="4ae21-124">Die ersten vier Befehle verwenden die `Get-FormatData` `Import-Module` `Compare-Object` Cmdlets, und, um den Formattyp zu identifizieren, den das **bitstransfer** -Modul zur Sitzung hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="4ae21-124">The first four commands use the `Get-FormatData`, `Import-Module`, and `Compare-Object` cmdlets to identify the format type that the **BitsTransfer** module adds to the session.</span></span>

<span data-ttu-id="4ae21-125">Der fünfte Befehl verwendet das `Get-FormatData` Cmdlet, um den Formattyp zu erhalten, den das **bitstransfer** -Modul hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="4ae21-125">The fifth command uses the `Get-FormatData` cmdlet to get the format type that the **BitsTransfer** module adds.</span></span> <span data-ttu-id="4ae21-126">Er verwendet einen Pipeline Operator ( `|` ), um das Formattyp Objekt an das `Export-FormatData` Cmdlet zu senden, das es in XML zurück konvertiert und in der angegebenen `format.ps1xml` Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="4ae21-126">It uses a pipeline operator (`|`) to send the format type object to the `Export-FormatData` cmdlet, which converts it back to XML and saves it in the specified `format.ps1xml` file.</span></span>

<span data-ttu-id="4ae21-127">Der letzte Befehl zeigt einen Auszug aus dem `format.ps1xml` Dateiinhalt.</span><span class="sxs-lookup"><span data-stu-id="4ae21-127">The final command shows an excerpt of the `format.ps1xml` file content.</span></span>

### <span data-ttu-id="4ae21-128">Beispiel 5: erhalten von Formatierungsdaten basierend auf der angegebenen Version von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ae21-128">Example 5: Get formatting data based on the specified version of PowerShell</span></span>

<span data-ttu-id="4ae21-129">In diesem Beispiel wird gezeigt, wie verwendet wird, `Get-FormatData` um Format Daten für einen angegebenen **Typnamen** und eine PowerShell-Version zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4ae21-129">This example shows how to use `Get-FormatData` to get format data for a specified **TypeName** and PowerShell version.</span></span>

```powershell
Get-FormatData -TypeName 'Microsoft.Powershell.Utility.FileHash' -PowerShellVersion $PSVersionTable.PSVersion

TypeNames                               FormatViewDefinition
---------                               --------------------
{Microsoft.Powershell.Utility.FileHash} {Microsoft.Powershell.Utility.FileHash}
```

## <span data-ttu-id="4ae21-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4ae21-130">PARAMETERS</span></span>

### <span data-ttu-id="4ae21-131">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="4ae21-131">-PowerShellVersion</span></span>

<span data-ttu-id="4ae21-132">Geben Sie die PowerShell-Version an, die von diesem Cmdlet für die Formatierungsdaten abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4ae21-132">Specify the version of PowerShell this cmdlet gets for the formatting data.</span></span> <span data-ttu-id="4ae21-133">Geben Sie eine zweistellige Zahl ein, die durch einen Zeitraum getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="4ae21-133">Enter a two digit number separated by a period.</span></span>

<span data-ttu-id="4ae21-134">Dieser Parameter wurde in PowerShell 5,1 hinzugefügt, um die Kompatibilität bei Remoting-Computern zu verbessern, die ältere Versionen von PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="4ae21-134">This parameter was added in PowerShell 5.1 to improve compatibility when remoting computers running older versions of PowerShell.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4ae21-135">-Typname</span><span class="sxs-lookup"><span data-stu-id="4ae21-135">-TypeName</span></span>

<span data-ttu-id="4ae21-136">Gibt die Typnamen an, die dieses Cmdlet für die Formatierungsdaten abruft.</span><span class="sxs-lookup"><span data-stu-id="4ae21-136">Specifies the type names that this cmdlet gets for the formatting data.</span></span>
<span data-ttu-id="4ae21-137">Geben Sie die Typnamen ein.</span><span class="sxs-lookup"><span data-stu-id="4ae21-137">Enter the type names.</span></span>
<span data-ttu-id="4ae21-138">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="4ae21-138">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="4ae21-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4ae21-139">CommonParameters</span></span>

<span data-ttu-id="4ae21-140">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4ae21-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4ae21-141">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4ae21-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4ae21-142">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4ae21-142">INPUTS</span></span>

### <span data-ttu-id="4ae21-143">Keine</span><span class="sxs-lookup"><span data-stu-id="4ae21-143">None</span></span>

<span data-ttu-id="4ae21-144">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="4ae21-144">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4ae21-145">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4ae21-145">OUTPUTS</span></span>

### <span data-ttu-id="4ae21-146">System. Management. Automation. extendedtypedefinition</span><span class="sxs-lookup"><span data-stu-id="4ae21-146">System.Management.Automation.ExtendedTypeDefinition</span></span>

## <span data-ttu-id="4ae21-147">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4ae21-147">NOTES</span></span>

## <span data-ttu-id="4ae21-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4ae21-148">RELATED LINKS</span></span>

[<span data-ttu-id="4ae21-149">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="4ae21-149">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="4ae21-150">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="4ae21-150">Update-FormatData</span></span>](Update-FormatData.md)
