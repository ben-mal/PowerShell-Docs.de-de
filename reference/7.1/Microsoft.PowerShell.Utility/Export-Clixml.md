---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8e1557bca62ade784bd5b4ed5cb170bbf079b423
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "93219676"
---
# <span data-ttu-id="f9015-103">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="f9015-103">Export-Clixml</span></span>

## <span data-ttu-id="f9015-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f9015-104">SYNOPSIS</span></span>
<span data-ttu-id="f9015-105">Erstellt eine XML-basierte Darstellung eines Objekts oder von Objekten und speichert sie in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="f9015-105">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="f9015-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f9015-106">SYNTAX</span></span>

### <span data-ttu-id="f9015-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="f9015-107">ByPath (Default)</span></span>

```
Export-Clixml [-Depth <Int32>] [-Path] <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f9015-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="f9015-108">ByLiteralPath</span></span>

```
Export-Clixml [-Depth <Int32>] -LiteralPath <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f9015-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f9015-109">DESCRIPTION</span></span>

<span data-ttu-id="f9015-110">Das- `Export-Clixml` Cmdlet erstellt eine XML-basierte Darstellung eines Common Language Infrastructure (CLI) eines Objekts oder von Objekten und speichert Sie in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="f9015-110">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="f9015-111">Sie können dann das- `Import-Clixml` Cmdlet verwenden, um das gespeicherte Objekt basierend auf dem Inhalt dieser Datei neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f9015-111">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="f9015-112">Weitere Informationen zur CLI finden Sie unter [Sprachunabhängigkeit](/dotnet/standard/language-independence).</span><span class="sxs-lookup"><span data-stu-id="f9015-112">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="f9015-113">Dieses Cmdlet ähnelt `ConvertTo-Xml` , mit der Ausnahme, dass `Export-Clixml` das resultierende XML in einer Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="f9015-113">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="f9015-114">`ConvertTo-XML` Gibt den XML-Code zurück, sodass Sie ihn in PowerShell weiterhin verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="f9015-114">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="f9015-115">Eine wertvolle Verwendung von `Export-Clixml` auf Windows-Computern besteht darin, Anmelde Informationen zu exportieren und Zeichen folgen sicher als XML zu schützen.</span><span class="sxs-lookup"><span data-stu-id="f9015-115">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="f9015-116">Ein Beispiel finden Sie unter Beispiel 3.</span><span class="sxs-lookup"><span data-stu-id="f9015-116">For an example, see Example 3.</span></span>

## <span data-ttu-id="f9015-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f9015-117">EXAMPLES</span></span>

### <span data-ttu-id="f9015-118">Beispiel 1: Exportieren einer Zeichenfolge in eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="f9015-118">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="f9015-119">In diesem Beispiel wird eine XML-Datei erstellt, die im aktuellen Verzeichnis speichert, eine Darstellung der Zeichenfolge, bei der **es sich um einen Test handelt**.</span><span class="sxs-lookup"><span data-stu-id="f9015-119">This example creates an XML file that stores in the current directory, a representation of the string **This is a test**.</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="f9015-120">Die Zeichenfolge `This is a test` wird an die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="f9015-120">The string `This is a test` is sent down the pipeline.</span></span> <span data-ttu-id="f9015-121">`Export-Clixml` verwendet den **path** -Parameter, um eine XML-Datei `sample.xml` mit dem Namen im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f9015-121">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="f9015-122">Beispiel 2: Exportieren eines Objekts in eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="f9015-122">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="f9015-123">In diesem Beispiel wird veranschaulicht, wie Sie ein Objekt in eine XML-Datei exportieren können und wie Sie dann ein Objekt erstellen können, indem Sie den XML-Code aus der Datei importieren.</span><span class="sxs-lookup"><span data-stu-id="f9015-123">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="f9015-124">Mit dem- `Get-Acl` Cmdlet wird die Sicherheits Beschreibung der `Test.txt` Datei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f9015-124">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="f9015-125">Er sendet das Objekt an die Pipeline, um die Sicherheits Beschreibung an zu übergeben `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="f9015-125">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="f9015-126">Die XML-basierte Darstellung des-Objekts wird in einer Datei mit dem Namen gespeichert `FileACL.xml` .</span><span class="sxs-lookup"><span data-stu-id="f9015-126">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="f9015-127">Das- `Import-Clixml` Cmdlet erstellt ein Objekt aus dem XML-Code in der `FileACL.xml` Datei.</span><span class="sxs-lookup"><span data-stu-id="f9015-127">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="f9015-128">Anschließend wird das Objekt in der Variablen gespeichert `$fileacl` .</span><span class="sxs-lookup"><span data-stu-id="f9015-128">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="f9015-129">Beispiel 3: Verschlüsseln eines exportierten Anmelde Informationsobjekts unter Windows</span><span class="sxs-lookup"><span data-stu-id="f9015-129">Example 3: Encrypt an exported credential object on Windows</span></span>

<span data-ttu-id="f9015-130">In diesem Beispiel können Sie mit den Anmelde Informationen, die Sie `$Credential` durch Ausführen des Cmdlets in der Variablen gespeichert haben `Get-Credential` , das `Export-Clixml` Cmdlet ausführen, um die Anmelde Informationen auf dem Datenträger zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f9015-130">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9015-131">`Export-Clixml` exportiert nur verschlüsselte Anmelde Informationen unter Windows.</span><span class="sxs-lookup"><span data-stu-id="f9015-131">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="f9015-132">Bei nicht-Windows-Betriebssystemen wie macOS und Linux werden Anmelde Informationen als nur-Text exportiert, der als Unicode-Zeichen Array gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f9015-132">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="f9015-133">Dies bietet eine gewisse Verschleierung, bietet aber keine Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="f9015-133">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="f9015-134">Mit dem- `Export-Clixml` Cmdlet werden Anmelde Informationsobjekte mithilfe der Windows- [Datenschutz-API](/previous-versions/windows/apps/hh464970(v=win.10))verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="f9015-134">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span> <span data-ttu-id="f9015-135">Durch die Verschlüsselung wird sichergestellt, dass nur Ihr Benutzerkonto nur auf diesem Computer den Inhalt des Anmelde Informationsobjekts entschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="f9015-135">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span>
<span data-ttu-id="f9015-136">Die exportierte `CLIXML` Datei kann nicht auf einem anderen Computer oder von einem anderen Benutzer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9015-136">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="f9015-137">Im Beispiel wird die Datei, in der die Anmelde Informationen gespeichert werden, durch dargestellt `TestScript.ps1.credential` .</span><span class="sxs-lookup"><span data-stu-id="f9015-137">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="f9015-138">Ersetzen Sie **testScript** durch den Namen des Skripts, mit dem die Anmelde Informationen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f9015-138">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="f9015-139">Sie senden das Anmelde Informationen-Objekt über die Pipeline an `Export-Clixml` und speichern es in dem Pfad, `$Credxmlpath` , den Sie im ersten Befehl angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f9015-139">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="f9015-140">Führen Sie die letzten beiden Befehle aus, um die Anmelde Informationen automatisch in das Skript zu importieren.</span><span class="sxs-lookup"><span data-stu-id="f9015-140">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="f9015-141">Führen `Import-Clixml` Sie aus, um das gesicherte Anmelde Informationsobjekt in das Skript zu importieren.</span><span class="sxs-lookup"><span data-stu-id="f9015-141">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="f9015-142">Dieser Import vermeidet das Risiko, dass nur-Text-Kenn Wörter in Ihrem Skript verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f9015-142">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

### <span data-ttu-id="f9015-143">Beispiel 4: Exportieren eines Anmelde Informationsobjekts unter Linux oder macOS</span><span class="sxs-lookup"><span data-stu-id="f9015-143">Example 4: Exporting a credential object on Linux or macOS</span></span>

<span data-ttu-id="f9015-144">In diesem Beispiel erstellen wir mithilfe des Cmdlets eine " **PSCredential** " in der `$Credential` Variablen `Get-Credential` .</span><span class="sxs-lookup"><span data-stu-id="f9015-144">In this example, we create a **PSCredential** in the `$Credential` variable using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f9015-145">Dann verwenden wir `Export-Clixml` , um die Anmelde Informationen auf dem Datenträger zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f9015-145">Then we use `Export-Clixml` to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9015-146">`Export-Clixml` exportiert nur verschlüsselte Anmelde Informationen unter Windows.</span><span class="sxs-lookup"><span data-stu-id="f9015-146">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="f9015-147">Bei nicht-Windows-Betriebssystemen wie macOS und Linux werden Anmelde Informationen als nur-Text exportiert, der als Unicode-Zeichen Array gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f9015-147">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="f9015-148">Dies bietet eine gewisse Verschleierung, bietet aber keine Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="f9015-148">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
PS> $Credential = Get-Credential

PowerShell credential request
Enter your credentials.
User: User1
Password for user User1: ********

PS> $Credential | Export-Clixml ./cred2.xml
PS> Get-Content ./cred2.xml

...
    <Props>
      <S N="UserName">User1</S>
      <SS N="Password">700061007300730077006f0072006400</SS>
    </Props>
...

PS> 'password' | Format-Hex -Encoding unicode

   Label: String (System.String) <52D60C91>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 70 00 61 00 73 00 73 00 77 00 6F 00 72 00 64 00 p a s s w o r d
```

<span data-ttu-id="f9015-149">Die Ausgabe von `Get-Content` in diesem Beispiel wurde abgeschnitten, um sich auf die Anmelde Informationen in der XML-Datei zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="f9015-149">The output of `Get-Content` in this example has been truncate to focus on the credential information in the XML file.</span></span> <span data-ttu-id="f9015-150">Beachten Sie, dass der nur-Text-Wert des Kennworts in der XML-Datei als Unicode-Zeichen Array gespeichert wird, wie von nachgewiesen `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="f9015-150">Note that the plain text value of the password is stored in the XML file as a Unicode character array as proven by `Format-Hex`.</span></span> <span data-ttu-id="f9015-151">Daher ist der Wert codiert, jedoch nicht verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="f9015-151">So the value is encoded but not encrypted.</span></span>

## <span data-ttu-id="f9015-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f9015-152">PARAMETERS</span></span>

### <span data-ttu-id="f9015-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f9015-153">-Confirm</span></span>

<span data-ttu-id="f9015-154">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="f9015-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f9015-155">-Tiefe</span><span class="sxs-lookup"><span data-stu-id="f9015-155">-Depth</span></span>

<span data-ttu-id="f9015-156">Gibt an, wie viele Ebenen der enthaltenen Objekte in der XML-Darstellung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f9015-156">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="f9015-157">Der Standardwert ist `2`.</span><span class="sxs-lookup"><span data-stu-id="f9015-157">The default value is `2`.</span></span>

<span data-ttu-id="f9015-158">Der Standardwert kann für den Objekttyp in den Dateien überschrieben werden `Types.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="f9015-158">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="f9015-159">Weitere Informationen finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="f9015-159">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

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

### <span data-ttu-id="f9015-160">-Codierung</span><span class="sxs-lookup"><span data-stu-id="f9015-160">-Encoding</span></span>

<span data-ttu-id="f9015-161">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="f9015-161">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="f9015-162">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="f9015-162">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="f9015-163">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f9015-163">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="f9015-164">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="f9015-164">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="f9015-165">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="f9015-165">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="f9015-166">`bigendianutf32`: Codiert im UTF-32-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="f9015-166">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="f9015-167">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="f9015-167">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="f9015-168">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="f9015-168">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="f9015-169">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="f9015-169">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="f9015-170">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="f9015-170">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="f9015-171">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="f9015-171">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="f9015-172">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="f9015-172">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="f9015-173">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="f9015-173">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="f9015-174">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="f9015-174">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="f9015-175">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="f9015-175">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="f9015-176">**UTF-7** \* wird nicht mehr zur Verwendung von empfohlen.</span><span class="sxs-lookup"><span data-stu-id="f9015-176">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="f9015-177">In PowerShell 7,1 wird eine Warnung geschrieben, wenn Sie `utf7` für den **Encoding** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="f9015-177">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f9015-178">-Force</span><span class="sxs-lookup"><span data-stu-id="f9015-178">-Force</span></span>

<span data-ttu-id="f9015-179">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f9015-179">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="f9015-180">Bewirkt, dass das Cmdlet das Schreibschutzattribut der Ausgabedatei bei Bedarf deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f9015-180">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="f9015-181">Das Cmdlet versucht, das Schreibschutzattribut zurückzusetzen, wenn der Befehl abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f9015-181">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="f9015-182">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f9015-182">-InputObject</span></span>

<span data-ttu-id="f9015-183">Gibt das zu konvertierende Objekt an.</span><span class="sxs-lookup"><span data-stu-id="f9015-183">Specifies the object to be converted.</span></span> <span data-ttu-id="f9015-184">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f9015-184">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="f9015-185">Sie können Objekte auch über die Pipeline an übergeben `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="f9015-185">You can also pipe objects to `Export-Clixml`.</span></span>

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

### <span data-ttu-id="f9015-186">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="f9015-186">-LiteralPath</span></span>

<span data-ttu-id="f9015-187">Gibt den Pfad zur Datei an, wo die XML-Darstellung des Objekts gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f9015-187">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="f9015-188">Im Gegensatz zu **path** wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f9015-188">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="f9015-189">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="f9015-189">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="f9015-190">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="f9015-190">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="f9015-191">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="f9015-191">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f9015-192">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="f9015-192">-NoClobber</span></span>

<span data-ttu-id="f9015-193">Gibt an, dass das Cmdlet den Inhalt einer vorhandenen Datei nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="f9015-193">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="f9015-194">Wenn eine Datei im angegebenen Pfad vorhanden ist, wird `Export-Clixml` die Datei standardmäßig ohne Warnung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9015-194">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="f9015-195">-Path</span><span class="sxs-lookup"><span data-stu-id="f9015-195">-Path</span></span>

<span data-ttu-id="f9015-196">Gibt den Pfad zur Datei an, wo die XML-Darstellung des Objekts gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f9015-196">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

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

### <span data-ttu-id="f9015-197">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f9015-197">-WhatIf</span></span>

<span data-ttu-id="f9015-198">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f9015-198">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f9015-199">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9015-199">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="f9015-200">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f9015-200">CommonParameters</span></span>

<span data-ttu-id="f9015-201">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f9015-201">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f9015-202">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f9015-202">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f9015-203">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f9015-203">INPUTS</span></span>

### <span data-ttu-id="f9015-204">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="f9015-204">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="f9015-205">Sie können ein beliebiges Objekt an die Pipeline angleichen `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="f9015-205">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="f9015-206">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f9015-206">OUTPUTS</span></span>

### <span data-ttu-id="f9015-207">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="f9015-207">System.IO.FileInfo</span></span>

<span data-ttu-id="f9015-208">`Export-Clixml` erstellt eine Datei, die den XML-Code enthält.</span><span class="sxs-lookup"><span data-stu-id="f9015-208">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="f9015-209">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f9015-209">NOTES</span></span>

## <span data-ttu-id="f9015-210">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f9015-210">RELATED LINKS</span></span>

[<span data-ttu-id="f9015-211">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="f9015-211">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="f9015-212">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="f9015-212">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="f9015-213">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="f9015-213">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="f9015-214">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="f9015-214">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="f9015-215">Join-Path</span><span class="sxs-lookup"><span data-stu-id="f9015-215">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

[<span data-ttu-id="f9015-216">Anmelde Informationen auf dem Datenträger sicher speichern</span><span class="sxs-lookup"><span data-stu-id="f9015-216">Securely Store Credentials on Disk</span></span>](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)

[<span data-ttu-id="f9015-217">Verwenden von PowerShell zum Übergeben von Anmelde Informationen an Legacy Systeme</span><span class="sxs-lookup"><span data-stu-id="f9015-217">Use PowerShell to Pass Credentials to Legacy Systems</span></span>](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)

[<span data-ttu-id="f9015-218">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="f9015-218">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
