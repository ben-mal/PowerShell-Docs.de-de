---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-clixml?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Clixml
ms.openlocfilehash: 3658ea5eded0fed95a1c9a1ea6e7d84a557e1e36
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602547"
---
# <span data-ttu-id="7a6cf-102">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="7a6cf-102">Import-Clixml</span></span>

## <span data-ttu-id="7a6cf-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7a6cf-103">SYNOPSIS</span></span>
<span data-ttu-id="7a6cf-104">Importiert eine CliXML-Datei und erstellt entsprechende Objekte in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-104">Imports a CLIXML file and creates corresponding objects in PowerShell.</span></span>

## <span data-ttu-id="7a6cf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7a6cf-105">SYNTAX</span></span>

### <span data-ttu-id="7a6cf-106">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="7a6cf-106">ByPath (Default)</span></span>

```
Import-Clixml [-Path] <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

### <span data-ttu-id="7a6cf-107">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="7a6cf-107">ByLiteralPath</span></span>

```
Import-Clixml -LiteralPath <String[]> [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

## <span data-ttu-id="7a6cf-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7a6cf-108">DESCRIPTION</span></span>

<span data-ttu-id="7a6cf-109">Das- `Import-Clixml` Cmdlet importiert eine Common Language Infrastructure (CLI)-XML-Datei mit Daten, die Microsoft .NET Framework-Objekten darstellen, und erstellt die PowerShell-Objekte.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-109">The `Import-Clixml` cmdlet imports a Common Language Infrastructure (CLI) XML file with data that represents Microsoft .NET Framework objects and creates the PowerShell objects.</span></span> <span data-ttu-id="7a6cf-110">Weitere Informationen zur CLI finden Sie unter [Sprachunabhängigkeit](/dotnet/standard/language-independence).</span><span class="sxs-lookup"><span data-stu-id="7a6cf-110">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="7a6cf-111">Eine wertvolle Verwendung von `Import-Clixml` auf Windows-Computern besteht darin, Anmelde Informationen und sichere Zeichen folgen zu importieren, die mithilfe von als sicheres XML exportiert wurden `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="7a6cf-111">A valuable use of `Import-Clixml` on Windows computers is to import credentials and secure strings that were exported as secure XML using `Export-Clixml`.</span></span> <span data-ttu-id="7a6cf-112">Ein Beispiel finden Sie unter Beispiel 2.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-112">For an example, see Example 2.</span></span>

<span data-ttu-id="7a6cf-113">`Import-Clixml` verwendet die Byte Reihenfolge-Markierung (BOM), um das Codierungsformat der Datei zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-113">`Import-Clixml` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="7a6cf-114">Wenn die Datei keine BOM enthält, wird davon ausgegangen, dass die Codierung UTF8 ist.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-114">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="7a6cf-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7a6cf-115">EXAMPLES</span></span>

### <span data-ttu-id="7a6cf-116">Beispiel 1: Importieren einer serialisierten Datei und erneutes Erstellen eines Objekts</span><span class="sxs-lookup"><span data-stu-id="7a6cf-116">Example 1: Import a serialized file and recreate an object</span></span>

<span data-ttu-id="7a6cf-117">In diesem Beispiel wird das- `Export-Clixml` Cmdlet verwendet, um eine serialisierte Kopie der von zurückgegebenen Prozessinformationen zu speichern `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="7a6cf-117">This example uses the `Export-Clixml` cmdlet to save a serialized copy of the process information returned by `Get-Process`.</span></span> <span data-ttu-id="7a6cf-118">`Import-Clixml` Ruft den Inhalt der serialisierten Datei ab und erstellt ein in der Variablen gespeichertes Objekt neu `$Processes` .</span><span class="sxs-lookup"><span data-stu-id="7a6cf-118">`Import-Clixml` retrieves the serialized file's contents and recreates an object that is stored in the `$Processes` variable.</span></span>

```powershell
Get-Process | Export-Clixml -Path .\pi.xml
$Processes = Import-Clixml -Path .\pi.xml
```

### <span data-ttu-id="7a6cf-119">Beispiel 2: Importieren eines sicheren Anmelde Informationsobjekts</span><span class="sxs-lookup"><span data-stu-id="7a6cf-119">Example 2: Import a secure credential object</span></span>

<span data-ttu-id="7a6cf-120">In diesem Beispiel können Sie mit den Anmelde Informationen, die Sie `$Credential` durch Ausführen des Cmdlets in der Variablen gespeichert haben `Get-Credential` , das `Export-Clixml` Cmdlet ausführen, um die Anmelde Informationen auf dem Datenträger zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-120">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a6cf-121">`Export-Clixml` exportiert nur verschlüsselte Anmelde Informationen unter Windows.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-121">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="7a6cf-122">Bei nicht-Windows-Betriebssystemen wie macOS und Linux werden Anmelde Informationen als nur-Text exportiert.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-122">On non-Windows operating systems such as macOS and Linux, credentials are exported in plain text.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="7a6cf-123">Mit dem- `Export-Clixml` Cmdlet werden Anmelde Informationsobjekte mithilfe der Windows- [Datenschutz-API](/previous-versions/windows/apps/hh464970(v=win.10))verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-123">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span>
<span data-ttu-id="7a6cf-124">Durch die Verschlüsselung wird sichergestellt, dass nur Ihr Benutzerkonto den Inhalt des Anmelde Informationsobjekts entschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-124">The encryption ensures that only your user account can decrypt the contents of the credential object.</span></span> <span data-ttu-id="7a6cf-125">Die exportierte `CLIXML` Datei kann nicht auf einem anderen Computer oder von einem anderen Benutzer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-125">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="7a6cf-126">Im Beispiel wird die Datei, in der die Anmelde Informationen gespeichert werden, durch dargestellt `TestScript.ps1.credential` .</span><span class="sxs-lookup"><span data-stu-id="7a6cf-126">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="7a6cf-127">Ersetzen Sie **testScript** durch den Namen des Skripts, mit dem die Anmelde Informationen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-127">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="7a6cf-128">Sie senden das Anmelde Informationen-Objekt über die Pipeline an `Export-Clixml` und speichern es in dem Pfad, `$Credxmlpath` , den Sie im ersten Befehl angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-128">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="7a6cf-129">Führen Sie die letzten beiden Befehle aus, um die Anmelde Informationen automatisch in das Skript zu importieren.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-129">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="7a6cf-130">Führen `Import-Clixml` Sie aus, um das gesicherte Anmelde Informationsobjekt in das Skript zu importieren.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-130">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="7a6cf-131">Dieser Import vermeidet das Risiko, dass nur-Text-Kenn Wörter in Ihrem Skript verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-131">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

## <span data-ttu-id="7a6cf-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7a6cf-132">PARAMETERS</span></span>

### <span data-ttu-id="7a6cf-133">-Zuerst</span><span class="sxs-lookup"><span data-stu-id="7a6cf-133">-First</span></span>

<span data-ttu-id="7a6cf-134">Ruft nur die angegebene Anzahl von Objekten ab.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-134">Gets only the specified number of objects.</span></span> <span data-ttu-id="7a6cf-135">Geben Sie die Anzahl der abzurufenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-135">Enter the number of objects to get.</span></span>

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a6cf-136">-Incluabtotalcount</span><span class="sxs-lookup"><span data-stu-id="7a6cf-136">-IncludeTotalCount</span></span>

<span data-ttu-id="7a6cf-137">Gibt die Gesamtanzahl der Objekte im DataSet an, gefolgt von den ausgewählten Objekten.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-137">Reports the total number of objects in the data set followed by the selected objects.</span></span> <span data-ttu-id="7a6cf-138">Wenn das Cmdlet die Gesamtanzahl nicht ermitteln kann, wird eine **unbekannte Gesamtanzahl** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-138">If the cmdlet can't determine the total count, it displays **Unknown total count**.</span></span> <span data-ttu-id="7a6cf-139">Die Ganzzahl hat eine **Genauigkeits** Eigenschaft, die die Zuverlässigkeit des Gesamtanzahl Werts angibt.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-139">The integer has an **Accuracy** property that indicates the reliability of the total count value.</span></span> <span data-ttu-id="7a6cf-140">Der Wert der **Genauigkeit** reicht von bis zu, d. h., das `0.0` `1.0` `0.0` Cmdlet kann die Objekte nicht zählen, `1.0` bedeutet, dass die Anzahl exakt ist, und ein Wert zwischen `0.0` und `1.0` gibt eine immer zuverlässigere Schätzung an.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-140">The value of **Accuracy** ranges from `0.0` to `1.0` where `0.0` means that the cmdlet couldn't count the objects, `1.0` means that the count is exact, and a value between `0.0` and `1.0` indicates an increasingly reliable estimate.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a6cf-141">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="7a6cf-141">-LiteralPath</span></span>

<span data-ttu-id="7a6cf-142">Gibt den Pfad zu den XML-Dateien an.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-142">Specifies the path to the XML files.</span></span> <span data-ttu-id="7a6cf-143">Im Gegensatz zu **path** wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-143">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="7a6cf-144">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="7a6cf-145">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="7a6cf-146">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7a6cf-147">-Path</span><span class="sxs-lookup"><span data-stu-id="7a6cf-147">-Path</span></span>

<span data-ttu-id="7a6cf-148">Gibt den Pfad zu den XML-Dateien an.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-148">Specifies the path to the XML files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7a6cf-149">-Skip</span><span class="sxs-lookup"><span data-stu-id="7a6cf-149">-Skip</span></span>

<span data-ttu-id="7a6cf-150">Ignoriert die angegebene Anzahl an Objekten und ruft anschließend die übrigen Objekte ab.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-150">Ignores the specified number of objects and then gets the remaining objects.</span></span> <span data-ttu-id="7a6cf-151">Geben Sie die Anzahl der zu überspringenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-151">Enter the number of objects to skip.</span></span>

```yaml
Type: System.UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a6cf-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7a6cf-152">CommonParameters</span></span>

<span data-ttu-id="7a6cf-153">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7a6cf-154">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7a6cf-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7a6cf-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7a6cf-155">INPUTS</span></span>

### <span data-ttu-id="7a6cf-156">System.String</span><span class="sxs-lookup"><span data-stu-id="7a6cf-156">System.String</span></span>

<span data-ttu-id="7a6cf-157">Sie können eine Zeichenfolge mit einem Pfad zu Pipeline Pipeline in Pipeline `Import-Clixml`</span><span class="sxs-lookup"><span data-stu-id="7a6cf-157">You can pipeline a string that contains a path to `Import-Clixml`.</span></span>

## <span data-ttu-id="7a6cf-158">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7a6cf-158">OUTPUTS</span></span>

### <span data-ttu-id="7a6cf-159">PSObject</span><span class="sxs-lookup"><span data-stu-id="7a6cf-159">PSObject</span></span>

<span data-ttu-id="7a6cf-160">`Import-Clixml` gibt Objekte zurück, die aus den gespeicherten XML-Dateien deserialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-160">`Import-Clixml` returns objects that were deserialized from the stored XML files.</span></span>

## <span data-ttu-id="7a6cf-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7a6cf-161">NOTES</span></span>

<span data-ttu-id="7a6cf-162">Wenn Sie für einen Parameter mehrere Werte angeben, verwenden Sie Kommas zur Trennung der Werte.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-162">When specifying multiple values for a parameter, use commas to separate the values.</span></span> <span data-ttu-id="7a6cf-163">Beispiel: `<parameter-name> <value1>, <value2>`.</span><span class="sxs-lookup"><span data-stu-id="7a6cf-163">For example, `<parameter-name> <value1>, <value2>`.</span></span>

## <span data-ttu-id="7a6cf-164">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7a6cf-164">RELATED LINKS</span></span>

[<span data-ttu-id="7a6cf-165">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="7a6cf-165">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="7a6cf-166">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="7a6cf-166">Introducing XML Serialization</span></span>](/dotnet/standard/serialization/introducing-xml-serialization)

[<span data-ttu-id="7a6cf-167">Join-Path</span><span class="sxs-lookup"><span data-stu-id="7a6cf-167">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="7a6cf-168">Anmelde Informationen auf dem Datenträger sicher speichern</span><span class="sxs-lookup"><span data-stu-id="7a6cf-168">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="7a6cf-169">Verwenden von PowerShell zum Übergeben von Anmelde Informationen an Legacy Systeme</span><span class="sxs-lookup"><span data-stu-id="7a6cf-169">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

