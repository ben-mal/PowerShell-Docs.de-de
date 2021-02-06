---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-formatdata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FormatData
ms.openlocfilehash: 28eab1709de12ec5d391009aacccfd4e973a8b9b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599428"
---
# <span data-ttu-id="2f468-102">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="2f468-102">Get-FormatData</span></span>

## <span data-ttu-id="2f468-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2f468-103">SYNOPSIS</span></span>
<span data-ttu-id="2f468-104">Ruft die Formatierungsdaten in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="2f468-104">Gets the formatting data in the current session.</span></span>

## <span data-ttu-id="2f468-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2f468-105">SYNTAX</span></span>

```
Get-FormatData [[-TypeName] <String[]>] [-PowerShellVersion <Version>] [<CommonParameters>]
```

## <span data-ttu-id="2f468-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2f468-106">DESCRIPTION</span></span>

<span data-ttu-id="2f468-107">Mit dem- `Get-FormatData` Cmdlet werden die Formatierungsdaten in der aktuellen Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2f468-107">The `Get-FormatData` cmdlet gets the formatting data in the current session.</span></span>

<span data-ttu-id="2f468-108">Die Formatierungsdaten in der Sitzung umfassen das Formatieren von Daten aus `Format.ps1xml` Formatierungs Dateien, z. b. im `$PSHOME` Verzeichnis, das Formatieren von Daten für Module, die in die Sitzung importiert werden, und das Formatieren von Daten für Befehle, die Sie mithilfe des Cmdlets in die Sitzung importieren `Import-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="2f468-108">The formatting data in the session includes formatting data from `Format.ps1xml` formatting files, such as those in the `$PSHOME` directory, formatting data for modules that you import into the session, and formatting data for commands that you import into your session by using the `Import-PSSession` cmdlet.</span></span>

<span data-ttu-id="2f468-109">Mit diesem Cmdlet können Sie die Formatierungsdaten untersuchen.</span><span class="sxs-lookup"><span data-stu-id="2f468-109">You can use this cmdlet to examine the formatting data.</span></span> <span data-ttu-id="2f468-110">Anschließend können Sie mit dem `Export-FormatData` Cmdlet die Objekte serialisieren, Sie in XML konvertieren und in `Format.ps1xml` Dateien speichern.</span><span class="sxs-lookup"><span data-stu-id="2f468-110">Then, you can use the `Export-FormatData` cmdlet to serialize the objects, convert them to XML, and save them in `Format.ps1xml` files.</span></span>

<span data-ttu-id="2f468-111">Weitere Informationen zum Formatieren von Dateien in PowerShell finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="2f468-111">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="2f468-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2f468-112">EXAMPLES</span></span>

### <span data-ttu-id="2f468-113">Beispiel 1: alle Formatierungsdaten erhalten</span><span class="sxs-lookup"><span data-stu-id="2f468-113">Example 1: Get all formatting data</span></span>

<span data-ttu-id="2f468-114">In diesem Beispiel werden alle Formatierungsdaten in der Sitzung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2f468-114">This example gets all the formatting data in the session.</span></span>

```powershell
Get-FormatData
```

### <span data-ttu-id="2f468-115">Beispiel 2: Formatieren von Daten nach Typname</span><span class="sxs-lookup"><span data-stu-id="2f468-115">Example 2: Get formatting data by type name</span></span>

<span data-ttu-id="2f468-116">In diesem Beispiel werden die Formatierungsdaten Elemente abgerufen, deren Namen mit beginnen `System.Management.Automation.Cmd` .</span><span class="sxs-lookup"><span data-stu-id="2f468-116">This example gets the formatting data items whose names begin with `System.Management.Automation.Cmd`.</span></span>

```powershell
Get-FormatData -TypeName 'System.Management.Automation.Cmd*'
```

### <span data-ttu-id="2f468-117">Beispiel 3: Untersuchen eines Formatierungsdaten Objekts</span><span class="sxs-lookup"><span data-stu-id="2f468-117">Example 3: Examine a formatting data object</span></span>

<span data-ttu-id="2f468-118">Dieses Beispiel zeigt, wie Sie ein Formatierungsdatenobjekt abrufen und seine Eigenschaften untersuchen.</span><span class="sxs-lookup"><span data-stu-id="2f468-118">This example shows how to get a formatting data object and examine its properties.</span></span>

```powershell
$F = Get-FormatData -TypeName 'System.Management.Automation.Cmd*'
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

### <span data-ttu-id="2f468-119">Beispiel 4: erhalten von Formatierungsdaten und Exportieren der Daten</span><span class="sxs-lookup"><span data-stu-id="2f468-119">Example 4: Get formatting data and export it</span></span>

<span data-ttu-id="2f468-120">In diesem Beispiel wird gezeigt, wie `Get-FormatData` und verwendet `Export-FormatData` werden, um die Formatierungsdaten zu exportieren, die von einem Modul hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2f468-120">This example shows how to use `Get-FormatData` and `Export-FormatData` to export the formatting data that is added by a module.</span></span>

```powershell
$A = Get-FormatData
Import-Module bitstransfer
$B = Get-FormatData
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

<span data-ttu-id="2f468-121">Die ersten vier Befehle verwenden die `Get-FormatData` `Import-Module` `Compare-Object` Cmdlets, und, um den Formattyp zu identifizieren, den das **bitstransfer** -Modul zur Sitzung hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="2f468-121">The first four commands use the `Get-FormatData`, `Import-Module`, and `Compare-Object` cmdlets to identify the format type that the **BitsTransfer** module adds to the session.</span></span>

<span data-ttu-id="2f468-122">Der fünfte Befehl verwendet das `Get-FormatData` Cmdlet, um den Formattyp zu erhalten, den das **bitstransfer** -Modul hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="2f468-122">The fifth command uses the `Get-FormatData` cmdlet to get the format type that the **BitsTransfer** module adds.</span></span> <span data-ttu-id="2f468-123">Er verwendet einen Pipeline Operator ( `|` ), um das Formattyp Objekt an das `Export-FormatData` Cmdlet zu senden, das es in XML zurück konvertiert und in der angegebenen `format.ps1xml` Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="2f468-123">It uses a pipeline operator (`|`) to send the format type object to the `Export-FormatData` cmdlet, which converts it back to XML and saves it in the specified `format.ps1xml` file.</span></span>

<span data-ttu-id="2f468-124">Der letzte Befehl zeigt einen Auszug aus dem `format.ps1xml` Dateiinhalt.</span><span class="sxs-lookup"><span data-stu-id="2f468-124">The final command shows an excerpt of the `format.ps1xml` file content.</span></span>

### <span data-ttu-id="2f468-125">Beispiel 5: erhalten von Formatierungsdaten basierend auf der angegebenen Version von PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f468-125">Example 5: Get formatting data based on the specified version of PowerShell</span></span>

<span data-ttu-id="2f468-126">In diesem Beispiel wird gezeigt, wie verwendet wird, `Get-FormatData` um Format Daten für einen angegebenen **Typnamen** und eine PowerShell-Version zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2f468-126">This example shows how to use `Get-FormatData` to get format data for a specified **TypeName** and PowerShell version.</span></span>

```powershell
Get-FormatData -TypeName 'Microsoft.Powershell.Utility.FileHash' -PowerShellVersion $PSVersionTable.PSVersion

TypeNames                               FormatViewDefinition
---------                               --------------------
{Microsoft.Powershell.Utility.FileHash} {Microsoft.Powershell.Utility.FileHash}
```

## <span data-ttu-id="2f468-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2f468-127">PARAMETERS</span></span>

### <span data-ttu-id="2f468-128">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="2f468-128">-PowerShellVersion</span></span>

<span data-ttu-id="2f468-129">Geben Sie die PowerShell-Version an, die von diesem Cmdlet für die Formatierungsdaten abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2f468-129">Specify the version of PowerShell this cmdlet gets for the formatting data.</span></span> <span data-ttu-id="2f468-130">Geben Sie eine zweistellige Zahl ein, die durch einen Zeitraum getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="2f468-130">Enter a two digit number separated by a period.</span></span>

<span data-ttu-id="2f468-131">Dieser Parameter wurde in PowerShell 5,1 hinzugefügt, um die Kompatibilität bei Remoting-Computern zu verbessern, die ältere Versionen von PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="2f468-131">This parameter was added in PowerShell 5.1 to improve compatibility when remoting computers running older versions of PowerShell.</span></span>

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

### <span data-ttu-id="2f468-132">-Typname</span><span class="sxs-lookup"><span data-stu-id="2f468-132">-TypeName</span></span>

<span data-ttu-id="2f468-133">Gibt die Typnamen an, die dieses Cmdlet für die Formatierungsdaten abruft.</span><span class="sxs-lookup"><span data-stu-id="2f468-133">Specifies the type names that this cmdlet gets for the formatting data.</span></span>
<span data-ttu-id="2f468-134">Geben Sie die Typnamen ein.</span><span class="sxs-lookup"><span data-stu-id="2f468-134">Enter the type names.</span></span>
<span data-ttu-id="2f468-135">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="2f468-135">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="2f468-136">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2f468-136">CommonParameters</span></span>

<span data-ttu-id="2f468-137">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2f468-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2f468-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2f468-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2f468-139">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2f468-139">INPUTS</span></span>

### <span data-ttu-id="2f468-140">Keine</span><span class="sxs-lookup"><span data-stu-id="2f468-140">None</span></span>

<span data-ttu-id="2f468-141">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="2f468-141">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="2f468-142">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2f468-142">OUTPUTS</span></span>

### <span data-ttu-id="2f468-143">System. Management. Automation. extendedtypedefinition</span><span class="sxs-lookup"><span data-stu-id="2f468-143">System.Management.Automation.ExtendedTypeDefinition</span></span>

## <span data-ttu-id="2f468-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2f468-144">NOTES</span></span>

## <span data-ttu-id="2f468-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2f468-145">RELATED LINKS</span></span>

[<span data-ttu-id="2f468-146">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="2f468-146">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="2f468-147">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="2f468-147">Update-FormatData</span></span>](Update-FormatData.md)
