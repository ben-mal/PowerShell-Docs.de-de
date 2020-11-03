---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: a442d8ff9f021e1ec05671d9190d35ef97ff4d72
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215543"
---
# <span data-ttu-id="3ddf7-103">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="3ddf7-103">Convert-Path</span></span>

## <span data-ttu-id="3ddf7-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3ddf7-104">SYNOPSIS</span></span>
<span data-ttu-id="3ddf7-105">Konvertiert einen Pfad von einem PowerShell-Pfad in einen PowerShell-Anbieter Pfad.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-105">Converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="3ddf7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ddf7-106">SYNTAX</span></span>

### <span data-ttu-id="3ddf7-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="3ddf7-107">Path (Default)</span></span>

```
Convert-Path [-Path] <String[]> [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="3ddf7-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3ddf7-108">LiteralPath</span></span>

```
Convert-Path -LiteralPath <String[]> [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="3ddf7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3ddf7-109">DESCRIPTION</span></span>

<span data-ttu-id="3ddf7-110">Mit dem- `Convert-Path` Cmdlet wird ein Pfad von einem PowerShell-Pfad in einen PowerShell-Anbieter Pfad konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-110">The `Convert-Path` cmdlet converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="3ddf7-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3ddf7-111">EXAMPLES</span></span>

### <span data-ttu-id="3ddf7-112">Beispiel 1: Konvertieren des Arbeitsverzeichnisses in einen Standarddatei Systempfad</span><span class="sxs-lookup"><span data-stu-id="3ddf7-112">Example 1: Convert the working directory to a standard file system path</span></span>

<span data-ttu-id="3ddf7-113">In diesem Beispiel wird das aktuelle Arbeitsverzeichnis, das durch einen Punkt () dargestellt wird `.` , in einen Standarddatei Systempfad konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-113">This example converts the current working directory, which is represented by a dot (`.`), to a standard FileSystem path.</span></span>

```
PS C:\> Convert-Path .
C:\
```

### <span data-ttu-id="3ddf7-114">Beispiel 2: Konvertieren eines Anbieter Pfads in einen Standard Registrierungs Pfad</span><span class="sxs-lookup"><span data-stu-id="3ddf7-114">Example 2: Convert a provider path to a standard registry path</span></span>

<span data-ttu-id="3ddf7-115">In diesem Beispiel wird der PowerShell-Anbieter Pfad in einen Standard Registrierungs Pfad konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-115">This example converts the PowerShell provider path to a standard registry path.</span></span>

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### <span data-ttu-id="3ddf7-116">Beispiel 3: Konvertieren eines Pfads in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3ddf7-116">Example 3: Convert a path to a string</span></span>

<span data-ttu-id="3ddf7-117">In diesem Beispiel wird der Pfad in das Basisverzeichnis des aktuellen Anbieters (der File System-Anbieter) in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-117">This example converts the path to the home directory of the current provider, which is the FileSystem provider, to a string.</span></span>

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## <span data-ttu-id="3ddf7-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ddf7-118">PARAMETERS</span></span>

### <span data-ttu-id="3ddf7-119">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="3ddf7-119">-LiteralPath</span></span>

<span data-ttu-id="3ddf7-120">Gibt den zu konvertierenden Pfad als Zeichen folgen Array an.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-120">Specifies, as a string array, the path to be converted.</span></span> <span data-ttu-id="3ddf7-121">Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-121">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="3ddf7-122">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-122">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3ddf7-123">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-123">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3ddf7-124">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-124">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3ddf7-125">-Path</span><span class="sxs-lookup"><span data-stu-id="3ddf7-125">-Path</span></span>

<span data-ttu-id="3ddf7-126">Gibt den zu konvertierenden PowerShell-Pfad an.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-126">Specifies the PowerShell path to be converted.</span></span>

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

### <span data-ttu-id="3ddf7-127">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="3ddf7-127">-UseTransaction</span></span>
<span data-ttu-id="3ddf7-128">Schließt den Befehl in die aktive Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-128">Includes the command in the active transaction.</span></span>
<span data-ttu-id="3ddf7-129">Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-129">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="3ddf7-130">Weitere Informationen finden Sie unter about_transactions.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-130">For more information, see about_transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ddf7-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3ddf7-131">CommonParameters</span></span>

<span data-ttu-id="3ddf7-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ddf7-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3ddf7-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3ddf7-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3ddf7-134">INPUTS</span></span>

### <span data-ttu-id="3ddf7-135">System.String</span><span class="sxs-lookup"><span data-stu-id="3ddf7-135">System.String</span></span>

<span data-ttu-id="3ddf7-136">Sie können einen Pfad, aber keinen literalen Pfad, an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-136">You can pipe a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="3ddf7-137">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3ddf7-137">OUTPUTS</span></span>

### <span data-ttu-id="3ddf7-138">System.String</span><span class="sxs-lookup"><span data-stu-id="3ddf7-138">System.String</span></span>

<span data-ttu-id="3ddf7-139">Dieses Cmdlet gibt eine Zeichenfolge zurück, die den konvertierten Pfad enthält.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-139">This cmdlet returns a string that contains the converted path.</span></span>

## <span data-ttu-id="3ddf7-140">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3ddf7-140">NOTES</span></span>

<span data-ttu-id="3ddf7-141">Die Cmdlets, die das Pfad-Substantiv enthalten, bearbeiten Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-141">The cmdlets that contain the Path noun manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="3ddf7-142">Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-142">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="3ddf7-143">Verwenden Sie Sie wie " **dirname** ", " **normpath** ", " **realpath** ", " **Join** " oder andere Pfad Manipulatoren.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-143">Use them like you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="3ddf7-144">Sie können die Pfad-Cmdlets mit verschiedenen Anbietern verwenden, u. a. dem FileSystem-, Registry- und Certificate-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-144">You can use the path cmdlets with several providers, including the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="3ddf7-145">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-145">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3ddf7-146">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="3ddf7-146">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="3ddf7-147">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="3ddf7-147">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="3ddf7-148">`Convert-Path` Konvertiert nur vorhandene Pfade.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-148">`Convert-Path` only converts existing paths.</span></span> <span data-ttu-id="3ddf7-149">Sie kann nicht verwendet werden, um einen Speicherort zu konvertieren, der noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3ddf7-149">It cannot be used to convert a location that does not exist yet.</span></span>

## <span data-ttu-id="3ddf7-150">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3ddf7-150">RELATED LINKS</span></span>

[<span data-ttu-id="3ddf7-151">Join-Path</span><span class="sxs-lookup"><span data-stu-id="3ddf7-151">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="3ddf7-152">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="3ddf7-152">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="3ddf7-153">Split-Path</span><span class="sxs-lookup"><span data-stu-id="3ddf7-153">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="3ddf7-154">Test-Path</span><span class="sxs-lookup"><span data-stu-id="3ddf7-154">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="3ddf7-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="3ddf7-155">Get-PSProvider</span></span>](Get-PSProvider.md)
