---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/join-path?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-Path
ms.openlocfilehash: 3f9859a7d78ae9daf43b1d72df26ac30d2d551cd
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209991"
---
# <span data-ttu-id="8c6fb-103">Join-Path</span><span class="sxs-lookup"><span data-stu-id="8c6fb-103">Join-Path</span></span>

## <span data-ttu-id="8c6fb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8c6fb-104">SYNOPSIS</span></span>
<span data-ttu-id="8c6fb-105">Kombiniert einen Pfad und einen untergeordneten Pfad zu einem Pfad.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-105">Combines a path and a child path into a single path.</span></span>

## <span data-ttu-id="8c6fb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8c6fb-106">SYNTAX</span></span>

```
Join-Path [-Path] <String[]> [-ChildPath] <String> [[-AdditionalChildPath] <String[]>] [-Resolve]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="8c6fb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8c6fb-107">DESCRIPTION</span></span>

<span data-ttu-id="8c6fb-108">Das `Join-Path` Cmdlet kombiniert einen Pfad und einen untergeordneten Pfad zu einem einzigen Pfad.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-108">The `Join-Path` cmdlet combines a path and child-path into a single path.</span></span>
<span data-ttu-id="8c6fb-109">Der Anbieter stellt die Pfadtrennzeichen bereit.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-109">The provider supplies the path delimiters.</span></span>

## <span data-ttu-id="8c6fb-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8c6fb-110">EXAMPLES</span></span>

### <span data-ttu-id="8c6fb-111">Beispiel 1: kombinieren eines Pfads mit einem untergeordneten Pfad</span><span class="sxs-lookup"><span data-stu-id="8c6fb-111">Example 1: Combine a path with a child path</span></span>

```powershell
PS C:\> Join-Path -Path "path" -ChildPath "childpath"
```

```output
path\childpath
```

<span data-ttu-id="8c6fb-112">Dieser Befehl verwendet `Join-Path` , um einen Pfad mit einem childpath zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-112">This command uses `Join-Path` to combine a path with a childpath.</span></span>

<span data-ttu-id="8c6fb-113">Da der Befehl vom Anbieter ausgeführt wird `FileSystem` , stellt er das `\` Trennzeichen zum Verknüpfen der Pfade bereit.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-113">Since the command is executed from the `FileSystem` provider, it provides the `\` delimiter to join the paths.</span></span>

### <span data-ttu-id="8c6fb-114">Beispiel 2: Kombinieren von Pfaden, die bereits Verzeichnis Trennzeichen enthalten</span><span class="sxs-lookup"><span data-stu-id="8c6fb-114">Example 2: Combine paths that already contain directory separators</span></span>

```powershell
PS C:\> Join-Path -Path "path\" -ChildPath "\childpath"
```

```output
path\childpath
```

<span data-ttu-id="8c6fb-115">Vorhandene Verzeichnis Trennzeichen, die `\` so behandelt werden, dass es nur ein Trennzeichen zwischen `Path` und gibt `ChildPath`</span><span class="sxs-lookup"><span data-stu-id="8c6fb-115">Existing directory separators `\` and handled so there is only one separator between `Path` and `ChildPath`</span></span>

### <span data-ttu-id="8c6fb-116">Beispiel 3: Anzeigen von Dateien und Ordnern durch Zusammenfügen eines Pfads mit einem untergeordneten Pfad</span><span class="sxs-lookup"><span data-stu-id="8c6fb-116">Example 3: Display files and folders by joining a path with a child path</span></span>

```powershell
Join-Path "C:\win*" "System*" -Resolve
```

<span data-ttu-id="8c6fb-117">Mit diesem Befehl werden die Dateien und Ordner angezeigt, auf die verwiesen wird, indem der c:\win \* -Pfad und der untergeordnete Pfad des Systems angeschlossen werden \* .</span><span class="sxs-lookup"><span data-stu-id="8c6fb-117">This command displays the files and folders that are referenced by joining the C:\Win\* path and the System\* child path.</span></span>
<span data-ttu-id="8c6fb-118">Es zeigt die gleichen Dateien und Ordner wie `Get-ChildItem` an, zeigt jedoch den voll qualifizierten Pfad zu jedem Element an.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-118">It displays the same files and folders as `Get-ChildItem`, but it displays the fully qualified path to each item.</span></span>
<span data-ttu-id="8c6fb-119">In diesem Befehl werden die `Path` `ChildPath` optionalen Parameternamen und weggelassen.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-119">In this command, the `Path` and `ChildPath` optional parameter names are omitted.</span></span>

### <span data-ttu-id="8c6fb-120">Beispiel 4: Verwenden von Join-Path mit dem PowerShell-Registrierungs Anbieter</span><span class="sxs-lookup"><span data-stu-id="8c6fb-120">Example 4: Use Join-Path with the PowerShell registry provider</span></span>

```powershell
PS HKLM:\> Join-Path -Path System -ChildPath *ControlSet* -Resolve
```

```output
HKLM:\System\ControlSet001
HKLM:\System\CurrentControlSet
```

<span data-ttu-id="8c6fb-121">Dieser Befehl zeigt die Registrierungsschlüssel im `HKLM\System` Registrierungs Unterschlüssel an, die `ControlSet` enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-121">This command displays the registry keys in the `HKLM\System` registry subkey that include `ControlSet`.</span></span>

<span data-ttu-id="8c6fb-122">Der- `Resolve` Parameter versucht, den verbundenen Pfad aufzulösen, einschließlich Platzhalter aus dem aktuellen Anbieter Pfad. `HKLM:\`</span><span class="sxs-lookup"><span data-stu-id="8c6fb-122">The `Resolve` parameter, attempts to resolve the joined path, including wildcards from the current provider path `HKLM:\`</span></span>

### <span data-ttu-id="8c6fb-123">Beispiel 5: Kombinieren mehrerer Pfad Stämme mit einem untergeordneten Pfad</span><span class="sxs-lookup"><span data-stu-id="8c6fb-123">Example 5: Combine multiple path roots with a child path</span></span>

```powershell
Join-Path -Path C:, D:, E:, F: -ChildPath New
```

```output
C:\New
D:\New
E:\New
F:\New
```

<span data-ttu-id="8c6fb-124">Dieser Befehl verwendet `Join-Path` , um mehrere Pfad Stämme mit einem untergeordneten Pfad zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-124">This command uses `Join-Path` to combine multiple path roots with a child path.</span></span>

> [!NOTE]
> <span data-ttu-id="8c6fb-125">Die von angegebenen Laufwerke `Path` müssen vorhanden sein, oder der Join dieses Eintrags schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-125">The Drives specified by `Path` must exist or the join of that entry will fail.</span></span>

### <span data-ttu-id="8c6fb-126">Beispiel 6: Kombinieren der Stämme eines Dateisystem Laufwerks mit einem untergeordneten Pfad</span><span class="sxs-lookup"><span data-stu-id="8c6fb-126">Example 6: Combine the roots of a file system drive with a child path</span></span>

```powershell
Get-PSDrive -PSProvider filesystem | ForEach-Object {$_.root} | Join-Path -ChildPath "Subdir"
```

```output
C:\Subdir
D:\Subdir
```

<span data-ttu-id="8c6fb-127">Dieser Befehl kombiniert die Stämme der einzelnen PowerShell-Dateisystem Laufwerke in der-Konsole mit dem untergeordneten subdir-Pfad.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-127">This command combines the roots of each PowerShell file system drive in the console with the Subdir child path.</span></span>

<span data-ttu-id="8c6fb-128">Der Befehl verwendet das `Get-PSDrive` Cmdlet, um die vom File System-Anbieter unterstützten PowerShell-Laufwerke zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-128">The command uses the `Get-PSDrive` cmdlet to get the PowerShell drives supported by the FileSystem provider.</span></span>
<span data-ttu-id="8c6fb-129">`ForEach-Object`Mit der-Anweisung wird nur die Root-Eigenschaft der `PSDriveInfo` -Objekte ausgewählt und mit dem angegebenen untergeordneten Pfad kombiniert.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-129">The `ForEach-Object` statement selects only the Root property of the `PSDriveInfo` objects and combines it with the specified child path.</span></span>

<span data-ttu-id="8c6fb-130">Die Ausgabe zeigt, dass die PowerShell-Laufwerke auf dem Computer ein Laufwerk enthalten, das dem Verzeichnis "c:\Program Files" zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-130">The output shows that the PowerShell drives on the computer included a drive mapped to the C:\Program Files directory.</span></span>

### <span data-ttu-id="8c6fb-131">Beispiel 7: Kombinieren einer unbestimmten Anzahl von Pfaden</span><span class="sxs-lookup"><span data-stu-id="8c6fb-131">Example 7: Combine an indefinite number of paths</span></span>

```powershell
Join-Path a b c d e f g
```

```Output
a\b\c\d\e\f\g
```

<span data-ttu-id="8c6fb-132">Der- `AdditionalChildPath` Parameter ermöglicht die zusammen Fügung einer unbegrenzten Anzahl von Pfaden.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-132">The `AdditionalChildPath` parameter allows the joining of an unlimited number of paths.</span></span>

<span data-ttu-id="8c6fb-133">In diesem Beispiel werden keine Parameternamen verwendet, daher wird "a" an `Path` , "b" `ChildPath` und "c-g" an gebunden. `AdditionalChildPath`</span><span class="sxs-lookup"><span data-stu-id="8c6fb-133">In this example, no parameter names are used, thus "a" binds to `Path`, "b" to `ChildPath` and "c-g" to `AdditionalChildPath`</span></span>

## <span data-ttu-id="8c6fb-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8c6fb-134">PARAMETERS</span></span>

### <span data-ttu-id="8c6fb-135">-Additionalchildpath</span><span class="sxs-lookup"><span data-stu-id="8c6fb-135">-AdditionalChildPath</span></span>

<span data-ttu-id="8c6fb-136">Gibt zusätzliche Elemente an, die an den Wert des *path* -Parameters angefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-136">Specifies additional elements to append to the value of the *Path* parameter.</span></span> <span data-ttu-id="8c6fb-137">Der `ChildPath` -Parameter ist weiterhin obligatorisch und muss ebenfalls angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-137">The `ChildPath` parameter is still mandatory and must be specified as well.</span></span>

<span data-ttu-id="8c6fb-138">Dieser Parameter wird mit der- `ValueFromRemainingArguments` Eigenschaft angegeben, die das beitreten zu einer unbestimmten Anzahl von Pfaden ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-138">This parameter is specified with the `ValueFromRemainingArguments` property which enables joining an indefinite number of paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8c6fb-139">-Childpath</span><span class="sxs-lookup"><span data-stu-id="8c6fb-139">-ChildPath</span></span>

<span data-ttu-id="8c6fb-140">Gibt die Elemente an, die an den Wert des-Parameters angefügt werden sollen `Path` .</span><span class="sxs-lookup"><span data-stu-id="8c6fb-140">Specifies the elements to append to the value of the `Path` parameter.</span></span>
<span data-ttu-id="8c6fb-141">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-141">Wildcards are permitted.</span></span>
<span data-ttu-id="8c6fb-142">Der- `ChildPath` Parameter ist erforderlich, obwohl der Parameter Name ("childpath") optional ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-142">The `ChildPath` parameter is required, although the parameter name ("ChildPath") is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="8c6fb-143">-Credential</span><span class="sxs-lookup"><span data-stu-id="8c6fb-143">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="8c6fb-144">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-144">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="8c6fb-145">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="8c6fb-145">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8c6fb-146">-Path</span><span class="sxs-lookup"><span data-stu-id="8c6fb-146">-Path</span></span>

<span data-ttu-id="8c6fb-147">Gibt die Hauptpfade an, an die der untergeordnete Pfad angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-147">Specifies the main path (or paths) to which the child-path is appended.</span></span>
<span data-ttu-id="8c6fb-148">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-148">Wildcards are permitted.</span></span>

<span data-ttu-id="8c6fb-149">Der Wert von `Path` bestimmt, welcher Anbieter die Pfade verbindet, und fügt die Pfad Trennzeichen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-149">The value of `Path` determines which provider joins the paths and adds the path delimiters.</span></span>
<span data-ttu-id="8c6fb-150">Der- `Path` Parameter ist erforderlich, obwohl der Parameter Name ("Path") optional ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-150">The `Path` parameter is required, although the parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="8c6fb-151">-Auflösen</span><span class="sxs-lookup"><span data-stu-id="8c6fb-151">-Resolve</span></span>

<span data-ttu-id="8c6fb-152">Gibt an, dass dieses Cmdlet versuchen soll, den verbundenen Pfad vom aktuellen Anbieter aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-152">Indicates that this cmdlet should attempt to resolve the joined path from the current provider.</span></span>

- <span data-ttu-id="8c6fb-153">Wenn Platzhalter verwendet werden, gibt das Cmdlet alle Pfade zurück, die dem verbundenen Pfad entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-153">If wildcards are used, the cmdlet returns all paths that match the joined path.</span></span>
- <span data-ttu-id="8c6fb-154">Wenn **keine** Platzhalter verwendet werden, tritt beim Cmdlet ein Fehler auf, wenn der Pfad nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-154">If **no** wildcards are used, the cmdlet will error if the path does not exist.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8c6fb-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8c6fb-155">CommonParameters</span></span>

<span data-ttu-id="8c6fb-156">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8c6fb-157">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8c6fb-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8c6fb-158">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8c6fb-158">INPUTS</span></span>

### <span data-ttu-id="8c6fb-159">System.String</span><span class="sxs-lookup"><span data-stu-id="8c6fb-159">System.String</span></span>

<span data-ttu-id="8c6fb-160">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-160">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="8c6fb-161">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8c6fb-161">OUTPUTS</span></span>

### <span data-ttu-id="8c6fb-162">System.String</span><span class="sxs-lookup"><span data-stu-id="8c6fb-162">System.String</span></span>

<span data-ttu-id="8c6fb-163">Dieses Cmdlet gibt eine Zeichenfolge zurück, die den resultierenden Pfad enthält.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-163">This cmdlet returns a string that contains the resulting path.</span></span>

## <span data-ttu-id="8c6fb-164">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8c6fb-164">NOTES</span></span>

<span data-ttu-id="8c6fb-165">Die Cmdlets, die das Pfad-Substantiv enthalten (die Path-Cmdlets), bearbeiten Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-165">The cmdlets that contain the Path noun (the Path cmdlets) manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="8c6fb-166">Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-166">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="8c6fb-167">Die Verwendung entspricht der von %%amp;quot;Dirname%%amp;quot;, %%amp;quot;Normpath%%amp;quot;, %%amp;quot;Realpath%%amp;quot;, %%amp;quot;Join%%amp;quot; und anderer Befehle zum Bearbeiten von Pfaden.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-167">Use them like you would use Dirname, Normpath, Realpath, Join, or other path manipulators.</span></span>

<span data-ttu-id="8c6fb-168">Sie können die Pfad-Cmdlets mit verschiedenen Anbietern verwenden, einschließlich `FileSystem` der `Registry` Anbieter, und `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="8c6fb-168">You can use the path cmdlets with several providers, including the `FileSystem`, `Registry`, and `Certificate` providers.</span></span>

<span data-ttu-id="8c6fb-169">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="8c6fb-169">This cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="8c6fb-170">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="8c6fb-170">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="8c6fb-171">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8c6fb-171">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="8c6fb-172">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8c6fb-172">RELATED LINKS</span></span>

[<span data-ttu-id="8c6fb-173">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="8c6fb-173">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="8c6fb-174">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="8c6fb-174">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="8c6fb-175">Split-Path</span><span class="sxs-lookup"><span data-stu-id="8c6fb-175">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="8c6fb-176">Test-Path</span><span class="sxs-lookup"><span data-stu-id="8c6fb-176">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="8c6fb-177">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="8c6fb-177">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="8c6fb-178">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="8c6fb-178">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="8c6fb-179">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="8c6fb-179">Get-PSDrive</span></span>](Get-PSDrive.md)
