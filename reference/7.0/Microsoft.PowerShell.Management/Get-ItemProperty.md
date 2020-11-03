---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: 5ef804e0274c0caaa6da1cf8714ab8aae1899068
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209692"
---
# <span data-ttu-id="d1963-103">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d1963-103">Get-ItemProperty</span></span>

## <span data-ttu-id="d1963-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d1963-104">SYNOPSIS</span></span>
<span data-ttu-id="d1963-105">Ruft die Eigenschaften eines angegebenen Elements ab.</span><span class="sxs-lookup"><span data-stu-id="d1963-105">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="d1963-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d1963-106">SYNTAX</span></span>

### <span data-ttu-id="d1963-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="d1963-107">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="d1963-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d1963-108">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="d1963-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d1963-109">DESCRIPTION</span></span>

<span data-ttu-id="d1963-110">Das- `Get-ItemProperty` Cmdlet ruft die Eigenschaften der angegebenen Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="d1963-110">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="d1963-111">Beispielsweise können Sie mit diesem Cmdlet den Wert der LastAccessTime-Eigenschaft eines Datei Objekts erhalten.</span><span class="sxs-lookup"><span data-stu-id="d1963-111">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span> <span data-ttu-id="d1963-112">Sie können dieses Cmdlet auch zum Anzeigen von Registrierungs Einträgen und deren Werten verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1963-112">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="d1963-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d1963-113">EXAMPLES</span></span>

### <span data-ttu-id="d1963-114">Beispiel 1: erhalten von Informationen zu einem bestimmten Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="d1963-114">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="d1963-115">Mit diesem Befehl werden Informationen zum `C:\Windows` Verzeichnis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d1963-115">This command gets information about the `C:\Windows` directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="d1963-116">Beispiel 2: erhalten der Eigenschaften einer bestimmten Datei</span><span class="sxs-lookup"><span data-stu-id="d1963-116">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="d1963-117">Mit diesem Befehl werden die Eigenschaften der `C:\Test\Weather.xls` Datei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d1963-117">This command gets the properties of the `C:\Test\Weather.xls` file.</span></span>
<span data-ttu-id="d1963-118">Das Ergebnis wird an das `Format-List` Cmdlet weitergeleitet, um die Ausgabe als Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1963-118">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="d1963-119">Beispiel 3: Anzeigen des Werte namens und der Daten von Registrierungs Einträgen in einem Registrierungs Unterschlüssel</span><span class="sxs-lookup"><span data-stu-id="d1963-119">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="d1963-120">Dieser Befehl zeigt den Wertnamen und die Daten der einzelnen Registrierungseinträge im Registrierungs Unterschlüssel "CurrentVersion" an.</span><span class="sxs-lookup"><span data-stu-id="d1963-120">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

> [!NOTE]
> <span data-ttu-id="d1963-121">Dieser Befehl erfordert, dass ein PowerShell-Laufwerk mit dem Namen vorhanden ist `HKLM:` , das der Hive-HKEY_LOCAL_MACHINE Struktur der Registrierung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d1963-121">This command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
>
> <span data-ttu-id="d1963-122">Ein Laufwerk mit diesem Namen und dieser Zuordnung ist standardmäßig in PowerShell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d1963-122">A drive with that name and mapping is available in PowerShell by default.</span></span>
> <span data-ttu-id="d1963-123">Der Pfad zu diesem Registrierungsunterschlüssel kann jedoch auch mit dem folgenden alternativen Pfad angegeben werden, der mit dem Anbieternamen beginnt, auf den zwei Doppelpunkte folgen:</span><span class="sxs-lookup"><span data-stu-id="d1963-123">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>
>
> <span data-ttu-id="d1963-124">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span><span class="sxs-lookup"><span data-stu-id="d1963-124">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

### <span data-ttu-id="d1963-125">Beispiel 4: erhalten Sie den Wertnamen und die Daten eines Registrierungs Eintrags in einem Registrierungs Unterschlüssel.</span><span class="sxs-lookup"><span data-stu-id="d1963-125">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="d1963-126">Mit diesem Befehl werden der Wertname und die Daten des Registrierungs Eintrags "ProgramFilesDir" im Registrierungs Unterschlüssel "CurrentVersion" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d1963-126">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="d1963-127">Der **Pfad** gibt den Unterschlüssel an, und der **Name** -Parameter gibt den Wertnamen des Eintrags an.</span><span class="sxs-lookup"><span data-stu-id="d1963-127">The **Path** specifies the subkey and the **Name** parameter specifies the value name of the entry.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="d1963-128">Beispiel 5: erhalten der Werte Namen und Daten von Registrierungs Einträgen in einem Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="d1963-128">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="d1963-129">Dieser Befehl ruft die Wertnamen und Daten der Registrierungseinträge im Registrierungsschlüssel "powershellengine" ab.</span><span class="sxs-lookup"><span data-stu-id="d1963-129">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span> <span data-ttu-id="d1963-130">Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d1963-130">The results are shown in the following sample output.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

## <span data-ttu-id="d1963-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d1963-131">PARAMETERS</span></span>

### <span data-ttu-id="d1963-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="d1963-132">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="d1963-133">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d1963-133">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="d1963-134">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="d1963-134">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d1963-135">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="d1963-135">-Exclude</span></span>

<span data-ttu-id="d1963-136">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d1963-136">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="d1963-137">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d1963-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d1963-138">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="d1963-138">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="d1963-139">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d1963-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="d1963-140">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="d1963-140">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d1963-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="d1963-141">-Filter</span></span>

<span data-ttu-id="d1963-142">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="d1963-142">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="d1963-143">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d1963-143">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="d1963-144">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="d1963-144">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="d1963-145">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="d1963-145">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d1963-146">-Include</span><span class="sxs-lookup"><span data-stu-id="d1963-146">-Include</span></span>

<span data-ttu-id="d1963-147">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="d1963-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="d1963-148">Der Wert dieses Parameters qualifiziert den **Path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="d1963-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d1963-149">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="d1963-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="d1963-150">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d1963-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="d1963-151">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="d1963-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d1963-152">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="d1963-152">-LiteralPath</span></span>

<span data-ttu-id="d1963-153">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="d1963-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="d1963-154">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d1963-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="d1963-155">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="d1963-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d1963-156">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="d1963-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="d1963-157">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="d1963-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="d1963-158">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="d1963-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="d1963-159">-Name</span><span class="sxs-lookup"><span data-stu-id="d1963-159">-Name</span></span>

<span data-ttu-id="d1963-160">Gibt den Namen der abzurufenden Eigenschaft oder Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="d1963-160">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="d1963-161">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d1963-161">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d1963-162">-Path</span><span class="sxs-lookup"><span data-stu-id="d1963-162">-Path</span></span>

<span data-ttu-id="d1963-163">Gibt den Pfad zu den Elementen an.</span><span class="sxs-lookup"><span data-stu-id="d1963-163">Specifies the path to the item or items.</span></span>
<span data-ttu-id="d1963-164">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d1963-164">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="d1963-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d1963-165">CommonParameters</span></span>

<span data-ttu-id="d1963-166">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d1963-166">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d1963-167">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d1963-167">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d1963-168">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d1963-168">INPUTS</span></span>

### <span data-ttu-id="d1963-169">System.String</span><span class="sxs-lookup"><span data-stu-id="d1963-169">System.String</span></span>

<span data-ttu-id="d1963-170">Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Get-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="d1963-170">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="d1963-171">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d1963-171">OUTPUTS</span></span>

### <span data-ttu-id="d1963-172">System. Boolean, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="d1963-172">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="d1963-173">`Get-ItemProperty` Gibt ein-Objekt für jede Element Eigenschaft zurück, die es abruft.</span><span class="sxs-lookup"><span data-stu-id="d1963-173">`Get-ItemProperty` returns an object for each item property that it gets.</span></span> <span data-ttu-id="d1963-174">Der Objekttyp richtet sich nach dem abgerufenen Objekt.</span><span class="sxs-lookup"><span data-stu-id="d1963-174">The object type depends on the object that is retrieved.</span></span> <span data-ttu-id="d1963-175">Beispielsweise wird auf einem Dateisystemlaufwerk möglicherweise eine Datei oder ein Ordner zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d1963-175">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="d1963-176">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d1963-176">NOTES</span></span>

<span data-ttu-id="d1963-177">Das- `Get-ItemProperty` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d1963-177">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d1963-178">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="d1963-178">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d1963-179">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d1963-179">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d1963-180">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d1963-180">RELATED LINKS</span></span>

[<span data-ttu-id="d1963-181">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d1963-181">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="d1963-182">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d1963-182">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="d1963-183">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d1963-183">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="d1963-184">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d1963-184">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="d1963-185">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d1963-185">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="d1963-186">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d1963-186">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="d1963-187">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d1963-187">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="d1963-188">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d1963-188">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
