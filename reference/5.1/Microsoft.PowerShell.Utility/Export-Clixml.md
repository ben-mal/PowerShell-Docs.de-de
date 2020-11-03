---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8485591165cce0425c85d52fbd31d40614af6249
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214063"
---
# <span data-ttu-id="45576-103">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="45576-103">Export-Clixml</span></span>

## <span data-ttu-id="45576-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="45576-104">SYNOPSIS</span></span>
<span data-ttu-id="45576-105">Erstellt eine XML-basierte Darstellung eines Objekts oder von Objekten und speichert sie in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="45576-105">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="45576-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="45576-106">SYNTAX</span></span>

### <span data-ttu-id="45576-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="45576-107">ByPath (Default)</span></span>

```
Export-Clixml [-Path] <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="45576-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="45576-108">ByLiteralPath</span></span>

```
Export-Clixml -LiteralPath <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="45576-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="45576-109">DESCRIPTION</span></span>

<span data-ttu-id="45576-110">Das- `Export-Clixml` Cmdlet erstellt eine XML-basierte Darstellung eines Common Language Infrastructure (CLI) eines Objekts oder von Objekten und speichert Sie in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="45576-110">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="45576-111">Sie können dann das- `Import-Clixml` Cmdlet verwenden, um das gespeicherte Objekt basierend auf dem Inhalt dieser Datei neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="45576-111">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="45576-112">Weitere Informationen zur CLI finden Sie unter [Sprachunabhängigkeit](/dotnet/standard/language-independence).</span><span class="sxs-lookup"><span data-stu-id="45576-112">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="45576-113">Dieses Cmdlet ähnelt `ConvertTo-Xml` , mit der Ausnahme, dass `Export-Clixml` das resultierende XML in einer Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="45576-113">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="45576-114">`ConvertTo-XML` Gibt den XML-Code zurück, sodass Sie ihn in PowerShell weiterhin verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="45576-114">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="45576-115">Eine wertvolle Verwendung von `Export-Clixml` auf Windows-Computern besteht darin, Anmelde Informationen zu exportieren und Zeichen folgen sicher als XML zu schützen.</span><span class="sxs-lookup"><span data-stu-id="45576-115">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="45576-116">Ein Beispiel finden Sie unter Beispiel 3.</span><span class="sxs-lookup"><span data-stu-id="45576-116">For an example, see Example 3.</span></span>

## <span data-ttu-id="45576-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="45576-117">EXAMPLES</span></span>

### <span data-ttu-id="45576-118">Beispiel 1: Exportieren einer Zeichenfolge in eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="45576-118">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="45576-119">In diesem Beispiel wird eine XML-Datei erstellt, die im aktuellen Verzeichnis speichert, eine Darstellung der Zeichenfolge, bei der **es sich um einen Test handelt** .</span><span class="sxs-lookup"><span data-stu-id="45576-119">This example creates an XML file that stores in the current directory, a representation of the string **This is a test** .</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="45576-120">Die Zeichenfolge, bei der **es sich um einen Test** handelt, wird über die Pipeline gesendet</span><span class="sxs-lookup"><span data-stu-id="45576-120">The string **This is a test** is sent down the pipeline.</span></span> <span data-ttu-id="45576-121">`Export-Clixml` verwendet den **path** -Parameter, um eine XML-Datei `sample.xml` mit dem Namen im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="45576-121">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="45576-122">Beispiel 2: Exportieren eines Objekts in eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="45576-122">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="45576-123">In diesem Beispiel wird veranschaulicht, wie Sie ein Objekt in eine XML-Datei exportieren können und wie Sie dann ein Objekt erstellen können, indem Sie den XML-Code aus der Datei importieren.</span><span class="sxs-lookup"><span data-stu-id="45576-123">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="45576-124">Mit dem- `Get-Acl` Cmdlet wird die Sicherheits Beschreibung der `Test.txt` Datei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="45576-124">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="45576-125">Er sendet das Objekt an die Pipeline, um die Sicherheits Beschreibung an zu übergeben `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="45576-125">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="45576-126">Die XML-basierte Darstellung des-Objekts wird in einer Datei mit dem Namen gespeichert `FileACL.xml` .</span><span class="sxs-lookup"><span data-stu-id="45576-126">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="45576-127">Das- `Import-Clixml` Cmdlet erstellt ein Objekt aus dem XML-Code in der `FileACL.xml` Datei.</span><span class="sxs-lookup"><span data-stu-id="45576-127">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="45576-128">Anschließend wird das Objekt in der Variablen gespeichert `$fileacl` .</span><span class="sxs-lookup"><span data-stu-id="45576-128">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="45576-129">Beispiel 3: Verschlüsseln eines exportierten Anmelde Informationen-Objekts</span><span class="sxs-lookup"><span data-stu-id="45576-129">Example 3: Encrypt an exported credential object</span></span>

<span data-ttu-id="45576-130">In diesem Beispiel können Sie mit den Anmelde Informationen, die Sie `$Credential` durch Ausführen des Cmdlets in der Variablen gespeichert haben `Get-Credential` , das `Export-Clixml` Cmdlet ausführen, um die Anmelde Informationen auf dem Datenträger zu speichern.</span><span class="sxs-lookup"><span data-stu-id="45576-130">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45576-131">`Export-Clixml` exportiert nur verschlüsselte Anmelde Informationen unter Windows.</span><span class="sxs-lookup"><span data-stu-id="45576-131">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="45576-132">Bei nicht-Windows-Betriebssystemen wie macOS und Linux werden Anmelde Informationen als nur-Text exportiert.</span><span class="sxs-lookup"><span data-stu-id="45576-132">On non-Windows operating systems such as macOS and Linux, credentials are exported in plain text.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="45576-133">Mit dem- `Export-Clixml` Cmdlet werden Anmelde Informationsobjekte mithilfe der Windows- [Datenschutz-API](/previous-versions/windows/apps/hh464970(v=win.10))verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="45576-133">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span>
<span data-ttu-id="45576-134">Durch die Verschlüsselung wird sichergestellt, dass nur Ihr Benutzerkonto nur auf diesem Computer den Inhalt des Anmelde Informationsobjekts entschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="45576-134">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span> <span data-ttu-id="45576-135">Die exportierte `CLIXML` Datei kann nicht auf einem anderen Computer oder von einem anderen Benutzer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45576-135">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="45576-136">Im Beispiel wird die Datei, in der die Anmelde Informationen gespeichert werden, durch dargestellt `TestScript.ps1.credential` .</span><span class="sxs-lookup"><span data-stu-id="45576-136">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="45576-137">Ersetzen Sie **testScript** durch den Namen des Skripts, mit dem die Anmelde Informationen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="45576-137">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="45576-138">Sie senden das Anmelde Informationen-Objekt über die Pipeline an `Export-Clixml` und speichern es in dem Pfad, `$Credxmlpath` , den Sie im ersten Befehl angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="45576-138">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="45576-139">Führen Sie die letzten beiden Befehle aus, um die Anmelde Informationen automatisch in das Skript zu importieren.</span><span class="sxs-lookup"><span data-stu-id="45576-139">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="45576-140">Führen `Import-Clixml` Sie aus, um das gesicherte Anmelde Informationsobjekt in das Skript zu importieren.</span><span class="sxs-lookup"><span data-stu-id="45576-140">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="45576-141">Dieser Import vermeidet das Risiko, dass nur-Text-Kenn Wörter in Ihrem Skript verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="45576-141">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

## <span data-ttu-id="45576-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="45576-142">PARAMETERS</span></span>

### <span data-ttu-id="45576-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="45576-143">-Confirm</span></span>

<span data-ttu-id="45576-144">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="45576-144">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="45576-145">-Tiefe</span><span class="sxs-lookup"><span data-stu-id="45576-145">-Depth</span></span>

<span data-ttu-id="45576-146">Gibt an, wie viele Ebenen der enthaltenen Objekte in der XML-Darstellung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="45576-146">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="45576-147">Der Standardwert ist `2`.</span><span class="sxs-lookup"><span data-stu-id="45576-147">The default value is `2`.</span></span>

<span data-ttu-id="45576-148">Der Standardwert kann für den Objekttyp in den Dateien überschrieben werden `Types.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="45576-148">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="45576-149">Weitere Informationen finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="45576-149">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="45576-150">-Codierung</span><span class="sxs-lookup"><span data-stu-id="45576-150">-Encoding</span></span>

<span data-ttu-id="45576-151">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="45576-151">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="45576-152">Der Standardwert ist **Unicode** .</span><span class="sxs-lookup"><span data-stu-id="45576-152">The default value is **Unicode** .</span></span>

<span data-ttu-id="45576-153">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="45576-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="45576-154">`ASCII` Verwendet den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="45576-154">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="45576-155">`BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="45576-155">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="45576-156">`Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).</span><span class="sxs-lookup"><span data-stu-id="45576-156">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="45576-157">`OEM` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.</span><span class="sxs-lookup"><span data-stu-id="45576-157">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="45576-158">`Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="45576-158">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="45576-159">`UTF7` Verwendet UTF-7.</span><span class="sxs-lookup"><span data-stu-id="45576-159">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="45576-160">`UTF8` Verwendet UTF-8.</span><span class="sxs-lookup"><span data-stu-id="45576-160">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="45576-161">`UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="45576-161">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="45576-162">-Force</span><span class="sxs-lookup"><span data-stu-id="45576-162">-Force</span></span>

<span data-ttu-id="45576-163">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="45576-163">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="45576-164">Bewirkt, dass das Cmdlet das Schreibschutzattribut der Ausgabedatei bei Bedarf deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="45576-164">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="45576-165">Das Cmdlet versucht, das Schreibschutzattribut zurückzusetzen, wenn der Befehl abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="45576-165">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="45576-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="45576-166">-InputObject</span></span>

<span data-ttu-id="45576-167">Gibt das zu konvertierende Objekt an.</span><span class="sxs-lookup"><span data-stu-id="45576-167">Specifies the object to be converted.</span></span> <span data-ttu-id="45576-168">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="45576-168">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="45576-169">Sie können Objekte auch über die Pipeline an übergeben `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="45576-169">You can also pipe objects to `Export-Clixml`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="45576-170">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="45576-170">-LiteralPath</span></span>

<span data-ttu-id="45576-171">Gibt den Pfad zur Datei an, wo die XML-Darstellung des Objekts gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="45576-171">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="45576-172">Im Gegensatz zu **path** wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="45576-172">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="45576-173">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="45576-173">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="45576-174">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="45576-174">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="45576-175">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="45576-175">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="45576-176">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="45576-176">-NoClobber</span></span>

<span data-ttu-id="45576-177">Gibt an, dass das Cmdlet den Inhalt einer vorhandenen Datei nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="45576-177">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="45576-178">Wenn eine Datei im angegebenen Pfad vorhanden ist, wird `Export-Clixml` die Datei standardmäßig ohne Warnung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="45576-178">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="45576-179">-Path</span><span class="sxs-lookup"><span data-stu-id="45576-179">-Path</span></span>

<span data-ttu-id="45576-180">Gibt den Pfad zur Datei an, wo die XML-Darstellung des Objekts gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="45576-180">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="45576-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="45576-181">-WhatIf</span></span>

<span data-ttu-id="45576-182">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="45576-182">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="45576-183">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="45576-183">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="45576-184">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="45576-184">CommonParameters</span></span>

<span data-ttu-id="45576-185">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="45576-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="45576-186">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="45576-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="45576-187">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="45576-187">INPUTS</span></span>

### <span data-ttu-id="45576-188">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="45576-188">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="45576-189">Sie können ein beliebiges Objekt an die Pipeline angleichen `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="45576-189">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="45576-190">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="45576-190">OUTPUTS</span></span>

### <span data-ttu-id="45576-191">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="45576-191">System.IO.FileInfo</span></span>

<span data-ttu-id="45576-192">`Export-Clixml` erstellt eine Datei, die den XML-Code enthält.</span><span class="sxs-lookup"><span data-stu-id="45576-192">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="45576-193">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="45576-193">NOTES</span></span>

## <span data-ttu-id="45576-194">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="45576-194">RELATED LINKS</span></span>

[<span data-ttu-id="45576-195">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="45576-195">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="45576-196">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="45576-196">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="45576-197">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="45576-197">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="45576-198">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="45576-198">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="45576-199">Join-Path</span><span class="sxs-lookup"><span data-stu-id="45576-199">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="45576-200">Anmelde Informationen auf dem Datenträger sicher speichern</span><span class="sxs-lookup"><span data-stu-id="45576-200">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="45576-201">Verwenden von PowerShell zum Übergeben von Anmelde Informationen an Legacy Systeme</span><span class="sxs-lookup"><span data-stu-id="45576-201">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[<span data-ttu-id="45576-202">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="45576-202">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
