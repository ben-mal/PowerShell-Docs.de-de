---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: 20116c12f09d6a9a36f33b656a36e30c2096db70
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605378"
---
# <span data-ttu-id="4e963-102">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4e963-102">Get-ItemProperty</span></span>

## <span data-ttu-id="4e963-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4e963-103">SYNOPSIS</span></span>
<span data-ttu-id="4e963-104">Ruft die Eigenschaften eines angegebenen Elements ab.</span><span class="sxs-lookup"><span data-stu-id="4e963-104">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="4e963-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4e963-105">SYNTAX</span></span>

### <span data-ttu-id="4e963-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="4e963-106">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="4e963-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4e963-107">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="4e963-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4e963-108">DESCRIPTION</span></span>

<span data-ttu-id="4e963-109">Das- `Get-ItemProperty` Cmdlet ruft die Eigenschaften der angegebenen Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="4e963-109">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="4e963-110">Beispielsweise können Sie mit diesem Cmdlet den Wert der LastAccessTime-Eigenschaft eines Datei Objekts erhalten.</span><span class="sxs-lookup"><span data-stu-id="4e963-110">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span> <span data-ttu-id="4e963-111">Sie können dieses Cmdlet auch zum Anzeigen von Registrierungs Einträgen und deren Werten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e963-111">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="4e963-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4e963-112">EXAMPLES</span></span>

### <span data-ttu-id="4e963-113">Beispiel 1: erhalten von Informationen zu einem bestimmten Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="4e963-113">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="4e963-114">Mit diesem Befehl werden Informationen zum `C:\Windows` Verzeichnis abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4e963-114">This command gets information about the `C:\Windows` directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="4e963-115">Beispiel 2: erhalten der Eigenschaften einer bestimmten Datei</span><span class="sxs-lookup"><span data-stu-id="4e963-115">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="4e963-116">Mit diesem Befehl werden die Eigenschaften der `C:\Test\Weather.xls` Datei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4e963-116">This command gets the properties of the `C:\Test\Weather.xls` file.</span></span>
<span data-ttu-id="4e963-117">Das Ergebnis wird an das `Format-List` Cmdlet weitergeleitet, um die Ausgabe als Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4e963-117">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="4e963-118">Beispiel 3: Anzeigen des Werte namens und der Daten von Registrierungs Einträgen in einem Registrierungs Unterschlüssel</span><span class="sxs-lookup"><span data-stu-id="4e963-118">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="4e963-119">Dieser Befehl zeigt den Wertnamen und die Daten der einzelnen Registrierungseinträge im Registrierungs Unterschlüssel "CurrentVersion" an.</span><span class="sxs-lookup"><span data-stu-id="4e963-119">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

> [!NOTE]
> <span data-ttu-id="4e963-120">Dieser Befehl erfordert, dass ein PowerShell-Laufwerk mit dem Namen vorhanden ist `HKLM:` , das der Hive-HKEY_LOCAL_MACHINE Struktur der Registrierung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4e963-120">This command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
>
> <span data-ttu-id="4e963-121">Ein Laufwerk mit diesem Namen und dieser Zuordnung ist standardmäßig in PowerShell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e963-121">A drive with that name and mapping is available in PowerShell by default.</span></span>
> <span data-ttu-id="4e963-122">Der Pfad zu diesem Registrierungsunterschlüssel kann jedoch auch mit dem folgenden alternativen Pfad angegeben werden, der mit dem Anbieternamen beginnt, auf den zwei Doppelpunkte folgen:</span><span class="sxs-lookup"><span data-stu-id="4e963-122">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>
>
> <span data-ttu-id="4e963-123">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span><span class="sxs-lookup"><span data-stu-id="4e963-123">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

### <span data-ttu-id="4e963-124">Beispiel 4: erhalten Sie den Wertnamen und die Daten eines Registrierungs Eintrags in einem Registrierungs Unterschlüssel.</span><span class="sxs-lookup"><span data-stu-id="4e963-124">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="4e963-125">Mit diesem Befehl werden der Wertname und die Daten des Registrierungs Eintrags "ProgramFilesDir" im Registrierungs Unterschlüssel "CurrentVersion" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4e963-125">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="4e963-126">Der **Pfad** gibt den Unterschlüssel an, und der **Name** -Parameter gibt den Wertnamen des Eintrags an.</span><span class="sxs-lookup"><span data-stu-id="4e963-126">The **Path** specifies the subkey and the **Name** parameter specifies the value name of the entry.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="4e963-127">Beispiel 5: erhalten der Werte Namen und Daten von Registrierungs Einträgen in einem Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="4e963-127">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="4e963-128">Dieser Befehl ruft die Wertnamen und Daten der Registrierungseinträge im Registrierungsschlüssel "powershellengine" ab.</span><span class="sxs-lookup"><span data-stu-id="4e963-128">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span> <span data-ttu-id="4e963-129">Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e963-129">The results are shown in the following sample output.</span></span>

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

## <span data-ttu-id="4e963-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4e963-130">PARAMETERS</span></span>

### <span data-ttu-id="4e963-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="4e963-131">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="4e963-132">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4e963-132">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="4e963-133">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="4e963-133">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="4e963-134">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="4e963-134">-Exclude</span></span>

<span data-ttu-id="4e963-135">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4e963-135">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="4e963-136">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="4e963-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="4e963-137">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="4e963-137">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="4e963-138">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="4e963-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="4e963-139">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="4e963-139">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="4e963-140">-Filter</span><span class="sxs-lookup"><span data-stu-id="4e963-140">-Filter</span></span>

<span data-ttu-id="4e963-141">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="4e963-141">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="4e963-142">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4e963-142">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="4e963-143">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="4e963-143">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="4e963-144">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="4e963-144">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="4e963-145">-Include</span><span class="sxs-lookup"><span data-stu-id="4e963-145">-Include</span></span>

<span data-ttu-id="4e963-146">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="4e963-146">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="4e963-147">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="4e963-147">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="4e963-148">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="4e963-148">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="4e963-149">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="4e963-149">Wildcard characters are permitted.</span></span> <span data-ttu-id="4e963-150">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="4e963-150">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="4e963-151">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="4e963-151">-LiteralPath</span></span>

<span data-ttu-id="4e963-152">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="4e963-152">Specifies a path to one or more locations.</span></span> <span data-ttu-id="4e963-153">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="4e963-153">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="4e963-154">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="4e963-154">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="4e963-155">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="4e963-155">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="4e963-156">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="4e963-156">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="4e963-157">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="4e963-157">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="4e963-158">-Name</span><span class="sxs-lookup"><span data-stu-id="4e963-158">-Name</span></span>

<span data-ttu-id="4e963-159">Gibt den Namen der abzurufenden Eigenschaft oder Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="4e963-159">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="4e963-160">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="4e963-160">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="4e963-161">-Path</span><span class="sxs-lookup"><span data-stu-id="4e963-161">-Path</span></span>

<span data-ttu-id="4e963-162">Gibt den Pfad zu den Elementen an.</span><span class="sxs-lookup"><span data-stu-id="4e963-162">Specifies the path to the item or items.</span></span>
<span data-ttu-id="4e963-163">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="4e963-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="4e963-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4e963-164">CommonParameters</span></span>

<span data-ttu-id="4e963-165">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="4e963-165">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="4e963-166">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4e963-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4e963-167">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4e963-167">INPUTS</span></span>

### <span data-ttu-id="4e963-168">System.String</span><span class="sxs-lookup"><span data-stu-id="4e963-168">System.String</span></span>

<span data-ttu-id="4e963-169">Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Get-ItemProperty` .</span><span class="sxs-lookup"><span data-stu-id="4e963-169">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="4e963-170">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4e963-170">OUTPUTS</span></span>

### <span data-ttu-id="4e963-171">System. Boolean, System. String, System. DateTime</span><span class="sxs-lookup"><span data-stu-id="4e963-171">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="4e963-172">`Get-ItemProperty` Gibt ein-Objekt für jede Element Eigenschaft zurück, die es abruft.</span><span class="sxs-lookup"><span data-stu-id="4e963-172">`Get-ItemProperty` returns an object for each item property that it gets.</span></span> <span data-ttu-id="4e963-173">Der Objekttyp richtet sich nach dem abgerufenen Objekt.</span><span class="sxs-lookup"><span data-stu-id="4e963-173">The object type depends on the object that is retrieved.</span></span> <span data-ttu-id="4e963-174">Beispielsweise wird auf einem Dateisystemlaufwerk möglicherweise eine Datei oder ein Ordner zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4e963-174">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="4e963-175">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4e963-175">NOTES</span></span>

<span data-ttu-id="4e963-176">Das- `Get-ItemProperty` Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="4e963-176">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="4e963-177">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="4e963-177">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="4e963-178">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="4e963-178">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="4e963-179">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4e963-179">RELATED LINKS</span></span>

[<span data-ttu-id="4e963-180">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4e963-180">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="4e963-181">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4e963-181">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="4e963-182">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4e963-182">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="4e963-183">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4e963-183">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="4e963-184">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4e963-184">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="4e963-185">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4e963-185">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="4e963-186">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4e963-186">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="4e963-187">about_Providers</span><span class="sxs-lookup"><span data-stu-id="4e963-187">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

