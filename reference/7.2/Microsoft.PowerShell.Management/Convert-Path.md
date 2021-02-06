---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: 3d39ea9498cec2669fa075d4630b7691671fea32
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601910"
---
# <span data-ttu-id="70ea3-102">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="70ea3-102">Convert-Path</span></span>

## <span data-ttu-id="70ea3-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="70ea3-103">SYNOPSIS</span></span>
<span data-ttu-id="70ea3-104">Konvertiert einen Pfad von einem PowerShell-Pfad in einen PowerShell-Anbieter Pfad.</span><span class="sxs-lookup"><span data-stu-id="70ea3-104">Converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="70ea3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="70ea3-105">SYNTAX</span></span>

### <span data-ttu-id="70ea3-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="70ea3-106">Path (Default)</span></span>

```
Convert-Path [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="70ea3-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="70ea3-107">LiteralPath</span></span>

```
Convert-Path -LiteralPath <String[]> [<CommonParameters>]
```

## <span data-ttu-id="70ea3-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="70ea3-108">DESCRIPTION</span></span>

<span data-ttu-id="70ea3-109">Mit dem- `Convert-Path` Cmdlet wird ein Pfad von einem PowerShell-Pfad in einen PowerShell-Anbieter Pfad konvertiert.</span><span class="sxs-lookup"><span data-stu-id="70ea3-109">The `Convert-Path` cmdlet converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="70ea3-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="70ea3-110">EXAMPLES</span></span>

### <span data-ttu-id="70ea3-111">Beispiel 1: Konvertieren des Arbeitsverzeichnisses in einen Standarddatei Systempfad</span><span class="sxs-lookup"><span data-stu-id="70ea3-111">Example 1: Convert the working directory to a standard file system path</span></span>

<span data-ttu-id="70ea3-112">In diesem Beispiel wird das aktuelle Arbeitsverzeichnis, das durch einen Punkt () dargestellt wird `.` , in einen Standarddatei Systempfad konvertiert.</span><span class="sxs-lookup"><span data-stu-id="70ea3-112">This example converts the current working directory, which is represented by a dot (`.`), to a standard FileSystem path.</span></span>

```
PS C:\> Convert-Path .
C:\
```

### <span data-ttu-id="70ea3-113">Beispiel 2: Konvertieren eines Anbieter Pfads in einen Standard Registrierungs Pfad</span><span class="sxs-lookup"><span data-stu-id="70ea3-113">Example 2: Convert a provider path to a standard registry path</span></span>

<span data-ttu-id="70ea3-114">In diesem Beispiel wird der PowerShell-Anbieter Pfad in einen Standard Registrierungs Pfad konvertiert.</span><span class="sxs-lookup"><span data-stu-id="70ea3-114">This example converts the PowerShell provider path to a standard registry path.</span></span>

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### <span data-ttu-id="70ea3-115">Beispiel 3: Konvertieren eines Pfads in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="70ea3-115">Example 3: Convert a path to a string</span></span>

<span data-ttu-id="70ea3-116">In diesem Beispiel wird der Pfad in das Basisverzeichnis des aktuellen Anbieters (der File System-Anbieter) in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="70ea3-116">This example converts the path to the home directory of the current provider, which is the FileSystem provider, to a string.</span></span>

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## <span data-ttu-id="70ea3-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="70ea3-117">PARAMETERS</span></span>

### <span data-ttu-id="70ea3-118">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="70ea3-118">-LiteralPath</span></span>

<span data-ttu-id="70ea3-119">Gibt den zu konvertierenden Pfad als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="70ea3-119">Specifies, as a string array, the path to be converted.</span></span> <span data-ttu-id="70ea3-120">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="70ea3-120">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="70ea3-121">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="70ea3-121">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="70ea3-122">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="70ea3-122">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="70ea3-123">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="70ea3-123">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="70ea3-124">-Path</span><span class="sxs-lookup"><span data-stu-id="70ea3-124">-Path</span></span>

<span data-ttu-id="70ea3-125">Gibt den zu konvertierenden PowerShell-Pfad an.</span><span class="sxs-lookup"><span data-stu-id="70ea3-125">Specifies the PowerShell path to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="70ea3-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="70ea3-126">CommonParameters</span></span>

<span data-ttu-id="70ea3-127">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="70ea3-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="70ea3-128">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="70ea3-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="70ea3-129">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="70ea3-129">INPUTS</span></span>

### <span data-ttu-id="70ea3-130">System.String</span><span class="sxs-lookup"><span data-stu-id="70ea3-130">System.String</span></span>

<span data-ttu-id="70ea3-131">Sie können einen Pfad, aber keinen literalen Pfad, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="70ea3-131">You can pipe a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="70ea3-132">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="70ea3-132">OUTPUTS</span></span>

### <span data-ttu-id="70ea3-133">System.String</span><span class="sxs-lookup"><span data-stu-id="70ea3-133">System.String</span></span>

<span data-ttu-id="70ea3-134">Dieses Cmdlet gibt eine Zeichenfolge zurück, die den konvertierten Pfad enthält.</span><span class="sxs-lookup"><span data-stu-id="70ea3-134">This cmdlet returns a string that contains the converted path.</span></span>

## <span data-ttu-id="70ea3-135">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="70ea3-135">NOTES</span></span>

<span data-ttu-id="70ea3-136">Die Cmdlets, die das Pfad-Substantiv enthalten, bearbeiten Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="70ea3-136">The cmdlets that contain the Path noun manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="70ea3-137">Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="70ea3-137">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="70ea3-138">Verwenden Sie Sie wie " **dirname**", " **normpath**", " **realpath**", " **Join**" oder andere Pfad Manipulatoren.</span><span class="sxs-lookup"><span data-stu-id="70ea3-138">Use them like you would use **Dirname**, **Normpath**, **Realpath**, **Join**, or other path manipulators.</span></span>

<span data-ttu-id="70ea3-139">Sie können die Pfad-Cmdlets mit verschiedenen Anbietern verwenden, u. a. dem FileSystem-, Registry- und Certificate-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="70ea3-139">You can use the path cmdlets with several providers, including the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="70ea3-140">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="70ea3-140">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="70ea3-141">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="70ea3-141">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="70ea3-142">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="70ea3-142">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="70ea3-143">`Convert-Path` Konvertiert nur vorhandene Pfade.</span><span class="sxs-lookup"><span data-stu-id="70ea3-143">`Convert-Path` only converts existing paths.</span></span> <span data-ttu-id="70ea3-144">Sie kann nicht verwendet werden, um einen Speicherort zu konvertieren, der noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="70ea3-144">It cannot be used to convert a location that does not exist yet.</span></span>

## <span data-ttu-id="70ea3-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="70ea3-145">RELATED LINKS</span></span>

[<span data-ttu-id="70ea3-146">Join-Path</span><span class="sxs-lookup"><span data-stu-id="70ea3-146">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="70ea3-147">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="70ea3-147">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="70ea3-148">Split-Path</span><span class="sxs-lookup"><span data-stu-id="70ea3-148">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="70ea3-149">Test-Path</span><span class="sxs-lookup"><span data-stu-id="70ea3-149">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="70ea3-150">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="70ea3-150">Get-PSProvider</span></span>](Get-PSProvider.md)

