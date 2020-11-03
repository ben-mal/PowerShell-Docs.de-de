---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileHash
ms.openlocfilehash: 3c82d1342f5e16da0b1bb0307bc0f5ff31b4828c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213087"
---
# <span data-ttu-id="1c7e9-103">Get-FileHash</span><span class="sxs-lookup"><span data-stu-id="1c7e9-103">Get-FileHash</span></span>

## <span data-ttu-id="1c7e9-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1c7e9-104">SYNOPSIS</span></span>
<span data-ttu-id="1c7e9-105">Berechnet den Hashwert für eine Datei mit einem angegebenen Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-105">Computes the hash value for a file by using a specified hash algorithm.</span></span>

## <span data-ttu-id="1c7e9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1c7e9-106">SYNTAX</span></span>

### <span data-ttu-id="1c7e9-107">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="1c7e9-107">Path (Default)</span></span>

```
Get-FileHash [-Path] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### <span data-ttu-id="1c7e9-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1c7e9-108">LiteralPath</span></span>

```
Get-FileHash [-LiteralPath] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### <span data-ttu-id="1c7e9-109">Streamparameterset</span><span class="sxs-lookup"><span data-stu-id="1c7e9-109">StreamParameterSet</span></span>

```
Get-FileHash [-InputStream] <Stream> [[-Algorithm] <String>] [<CommonParameters>]
```

## <span data-ttu-id="1c7e9-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1c7e9-110">DESCRIPTION</span></span>

<span data-ttu-id="1c7e9-111">Das- `Get-FileHash` Cmdlet berechnet den Hashwert für eine Datei mithilfe eines angegebenen Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-111">The `Get-FileHash` cmdlet computes the hash value for a file by using a specified hash algorithm.</span></span>
<span data-ttu-id="1c7e9-112">Ein Hashwert ist ein eindeutiger Wert, der dem Inhalt der Datei entspricht.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-112">A hash value is a unique value that corresponds to the content of the file.</span></span> <span data-ttu-id="1c7e9-113">Anstatt den Inhalt einer Datei anhand des Dateinamens, der Erweiterung oder einer anderen Bezeichnung zu identifizieren, weist ein Hash dem Inhalt einer Datei einen eindeutigen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-113">Rather than identifying the contents of a file by its file name, extension, or other designation, a hash assigns a unique value to the contents of a file.</span></span> <span data-ttu-id="1c7e9-114">Dateinamen und Erweiterungen können geändert werden, ohne den Inhalt der Datei und ohne den Hashwert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-114">File names and extensions can be changed without altering the content of the file, and without changing the hash value.</span></span> <span data-ttu-id="1c7e9-115">Ebenso kann der Inhalt der Datei geändert werden, ohne den Namen oder die Erweiterung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-115">Similarly, the file's content can be changed without changing the name or extension.</span></span> <span data-ttu-id="1c7e9-116">Durch die bloße Änderung eines einzelnen Zeichens im Inhalt einer Datei ändert sich jedoch auch deren Hashwert.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-116">However, changing even a single character in the contents of a file changes the hash value of the file.</span></span>

<span data-ttu-id="1c7e9-117">Hashwerte bieten eine im Hinblick auf die Kryptografie sichere Möglichkeit, zu gewährleisten, dass der Inhalt einer Datei nicht geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-117">The purpose of hash values is to provide a cryptographically-secure way to verify that the contents of a file have not been changed.</span></span> <span data-ttu-id="1c7e9-118">Obwohl einige Hash Algorithmen, einschließlich MD5 und SHA1, nicht mehr als sicher gegen Angriffe angesehen werden, besteht das Ziel eines sicheren Hash Algorithmus darin, den Inhalt einer Datei nicht zu ändern, entweder versehentlich oder durch böswillige oder nicht autorisierte Versuche, und denselben Hashwert beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-118">While some hash algorithms, including MD5 and SHA1, are no longer considered secure against attack, the goal of a secure hash algorithm is to render it impossible to change the contents of a file -- either by accident, or by malicious or unauthorized attempt -- and maintain the same hash value.</span></span> <span data-ttu-id="1c7e9-119">Mithilfe von Hashwerten können Sie auch bestimmen, ob zwei unterschiedliche Dateien genau den gleichen Inhalt aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-119">You can also use hash values to determine if two different files have exactly the same content.</span></span> <span data-ttu-id="1c7e9-120">Wenn die Hashwerte von zwei Dateien identisch sind, sind die Inhalte der Dateien ebenfalls identisch.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-120">If the hash values of two files are identical, the contents of the files are also identical.</span></span>

<span data-ttu-id="1c7e9-121">Standardmäßig verwendet das `Get-FileHash` Cmdlet den SHA256-Algorithmus, obwohl alle vom Ziel Betriebssystem unterstützten Hash Algorithmen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-121">By default, the `Get-FileHash` cmdlet uses the SHA256 algorithm, although any hash algorithm that is supported by the target operating system can be used.</span></span>

## <span data-ttu-id="1c7e9-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1c7e9-122">EXAMPLES</span></span>

### <span data-ttu-id="1c7e9-123">Beispiel 1: Berechnen des Hashwerts für eine Datei</span><span class="sxs-lookup"><span data-stu-id="1c7e9-123">Example 1: Compute the hash value for a file</span></span>

<span data-ttu-id="1c7e9-124">In diesem Beispiel wird das- `Get-FileHash` Cmdlet verwendet, um den Hashwert für die Datei zu berechnen `/etc/apt/sources.list` .</span><span class="sxs-lookup"><span data-stu-id="1c7e9-124">This example uses the `Get-FileHash` cmdlet to compute the hash value for the `/etc/apt/sources.list` file.</span></span> <span data-ttu-id="1c7e9-125">Der verwendete Hash Algorithmus ist die Standardeinstellung, **SHA256** .</span><span class="sxs-lookup"><span data-stu-id="1c7e9-125">The hash algorithm used is the default, **SHA256** .</span></span> <span data-ttu-id="1c7e9-126">Die Ausgabe wird an das `Format-List` Cmdlet weitergeleitet, um die Ausgabe als Liste zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-126">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash /etc/apt/sources.list | Format-List
```

```Output
Algorithm : SHA256
Hash      : 3CBCFDDEC145E3382D592266BE193E5BE53443138EE6AB6CA09FF20DF609E268
Path      : /etc/apt/sources.list
```

### <span data-ttu-id="1c7e9-127">Beispiel 2: Berechnen des Hashwerts für eine ISO-Datei</span><span class="sxs-lookup"><span data-stu-id="1c7e9-127">Example 2: Compute the hash value for an ISO file</span></span>

<span data-ttu-id="1c7e9-128">In diesem Beispiel wird das `Get-FileHash` -Cmdlet und der **SHA384** -Algorithmus zum Berechnen des Hashwerts für eine ISO-Datei verwendet, die ein Administrator aus dem Internet heruntergeladen hat.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-128">This example uses the `Get-FileHash` cmdlet and the **SHA384** algorithm to compute the hash value for an ISO file that an administrator has downloaded from the internet.</span></span> <span data-ttu-id="1c7e9-129">Die Ausgabe wird an das `Format-List` Cmdlet weitergeleitet, um die Ausgabe als Liste zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-129">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash C:\Users\user1\Downloads\Contoso8_1_ENT.iso -Algorithm SHA384 | Format-List
```

```Output
Algorithm : SHA384
Hash      : 20AB1C2EE19FC96A7C66E33917D191A24E3CE9DAC99DB7C786ACCE31E559144FEAFC695C58E508E2EBBC9D3C96F21FA3
Path      : C:\Users\user1\Downloads\Contoso8_1_ENT.iso
```

### <span data-ttu-id="1c7e9-130">Beispiel 3: Berechnen des Hashwerts eines Streams</span><span class="sxs-lookup"><span data-stu-id="1c7e9-130">Example 3: Compute the hash value of a stream</span></span>

<span data-ttu-id="1c7e9-131">In diesem Beispiel verwenden wir **System .net. WebClient** , um ein Paket von der [PowerShell-releaseseite](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4)herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-131">For this example, we get are using **System.Net.WebClient** to download a package from the [Powershell release page](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4).</span></span> <span data-ttu-id="1c7e9-132">Auf der releaseseite wird auch der SHA256-Hash der einzelnen Paketdateien dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-132">The release page also documents the SHA256 hash of each package file.</span></span> <span data-ttu-id="1c7e9-133">Wir können den veröffentlichten Hashwert mit dem Wert vergleichen, den wir mit berechnen `Get-FileHash` .</span><span class="sxs-lookup"><span data-stu-id="1c7e9-133">We can compare the published hash value with the one we calculate with `Get-FileHash`.</span></span>

```powershell
$wc = [System.Net.WebClient]::new()
$pkgurl = 'https://github.com/PowerShell/PowerShell/releases/download/v6.2.4/powershell_6.2.4-1.debian.9_amd64.deb'
$publishedHash = '8E28E54D601F0751922DE24632C1E716B4684876255CF82304A9B19E89A9CCAC'
$FileHash = Get-FileHash -InputStream ($wc.OpenRead($pkgurl))
$FileHash.Hash -eq $publishedHash
```

```Output
True
```

### <span data-ttu-id="1c7e9-134">Beispiel 4: Berechnen des Hashwerts einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1c7e9-134">Example 4: Compute the hash of a string</span></span>

<span data-ttu-id="1c7e9-135">PowerShell bietet kein Cmdlet, um den Hash einer Zeichenfolge zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-135">PowerShell does not provide a cmdlet to compute the hash of a string.</span></span> <span data-ttu-id="1c7e9-136">Sie können jedoch eine Zeichenfolge in einen Stream schreiben und den **InputStream** -Parameter von verwenden `Get-FileHash` , um den Hashwert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-136">However, you can write a string to a stream and use the **InputStream** parameter of `Get-FileHash` to get the hash value.</span></span>

```powershell
$stringAsStream = [System.IO.MemoryStream]::new()
$writer = [System.IO.StreamWriter]::new($stringAsStream)
$writer.write("Hello world")
$writer.Flush()
$stringAsStream.Position = 0
Get-FileHash -InputStream $stringAsStream | Select-Object Hash
```

```Output
Hash
----
64EC88CA00B268E5BA1A35678A1B5316D212F4F366B2477232534A8AECA37F3C
```

## <span data-ttu-id="1c7e9-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1c7e9-137">PARAMETERS</span></span>

### <span data-ttu-id="1c7e9-138">-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="1c7e9-138">-Algorithm</span></span>

<span data-ttu-id="1c7e9-139">Gibt die kryptografische Hash Funktion an, die zum Berechnen des Hashwerts des Inhalts der angegebenen Datei bzw. des angegebenen Streams verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-139">Specifies the cryptographic hash function to use for computing the hash value of the contents of the specified file or stream.</span></span> <span data-ttu-id="1c7e9-140">Eine kryptografische Hash Funktion hat die-Eigenschaft, dass Sie nicht gefunden werden kann, um zwei verschiedene Dateien mit demselben Hashwert zu suchen.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-140">A cryptographic hash function has the property that it is infeasible to find two different files with the same hash value.</span></span> <span data-ttu-id="1c7e9-141">Hashfunktionen werden häufig bei digitalen Signaturen und für die Datenintegrität verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-141">Hash functions are commonly used with digital signatures and for data integrity.</span></span> <span data-ttu-id="1c7e9-142">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="1c7e9-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1c7e9-143">SHA1</span><span class="sxs-lookup"><span data-stu-id="1c7e9-143">SHA1</span></span>
- <span data-ttu-id="1c7e9-144">SHA256</span><span class="sxs-lookup"><span data-stu-id="1c7e9-144">SHA256</span></span>
- <span data-ttu-id="1c7e9-145">SHA384</span><span class="sxs-lookup"><span data-stu-id="1c7e9-145">SHA384</span></span>
- <span data-ttu-id="1c7e9-146">SHA512</span><span class="sxs-lookup"><span data-stu-id="1c7e9-146">SHA512</span></span>
- <span data-ttu-id="1c7e9-147">MD5</span><span class="sxs-lookup"><span data-stu-id="1c7e9-147">MD5</span></span>

<span data-ttu-id="1c7e9-148">Wenn kein Wert angegeben oder der Parameter weggelassen wird, ist der Standardwert SHA256.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-148">If no value is specified, or if the parameter is omitted, the default value is SHA256.</span></span>

<span data-ttu-id="1c7e9-149">MD5 und SHA1, die nicht mehr als sicher eingestuft werden, sollten aus Sicherheitsgründen nur zur einfachen Überprüfung von Änderungen verwendet werden und nicht zum Generieren von Hashwerten für Dateien, die vor Angriffen oder Manipulation geschützt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-149">For security reasons, MD5 and SHA1, which are no longer considered secure, should only be used for simple change validation, and should not be used to generate hash values for files that require protection from attack or tampering.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: SHA1, SHA256, SHA384, SHA512, MD5

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1c7e9-150">-InputStream</span><span class="sxs-lookup"><span data-stu-id="1c7e9-150">-InputStream</span></span>

<span data-ttu-id="1c7e9-151">Gibt den Eingabestream an.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-151">Specifies the input stream.</span></span>

```yaml
Type: System.IO.Stream
Parameter Sets: StreamParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1c7e9-152">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="1c7e9-152">-LiteralPath</span></span>

<span data-ttu-id="1c7e9-153">Gibt den Pfad zu einer Datei an.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-153">Specifies the path to a file.</span></span> <span data-ttu-id="1c7e9-154">Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-154">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="1c7e9-155">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-155">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="1c7e9-156">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-156">If the path includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="1c7e9-157">Einfache Anführungszeichen weisen PowerShell an, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-157">Single quotation marks instruct PowerShell not to interpret characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1c7e9-158">-Path</span><span class="sxs-lookup"><span data-stu-id="1c7e9-158">-Path</span></span>

<span data-ttu-id="1c7e9-159">Gibt den Pfad zu einer oder mehreren Dateien als Array an.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-159">Specifies the path to one or more files as an array.</span></span> <span data-ttu-id="1c7e9-160">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-160">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="1c7e9-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1c7e9-161">CommonParameters</span></span>

<span data-ttu-id="1c7e9-162">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1c7e9-163">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1c7e9-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1c7e9-164">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1c7e9-164">INPUTS</span></span>

### <span data-ttu-id="1c7e9-165">System.String</span><span class="sxs-lookup"><span data-stu-id="1c7e9-165">System.String</span></span>

<span data-ttu-id="1c7e9-166">Sie können eine Zeichenfolge über die Pipeline an das `Get-FileHash` Cmdlet übergeben, das einen Pfad zu einer oder mehreren Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-166">You can pipe a string to the `Get-FileHash` cmdlet that contains a path to one or more files.</span></span>

## <span data-ttu-id="1c7e9-167">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1c7e9-167">OUTPUTS</span></span>

### <span data-ttu-id="1c7e9-168">Microsoft. PowerShell. Utility. flehash</span><span class="sxs-lookup"><span data-stu-id="1c7e9-168">Microsoft.Powershell.Utility.FileHash</span></span>

<span data-ttu-id="1c7e9-169">`Get-FileHash` Gibt ein Objekt zurück, das den Pfad zur angegebenen Datei, den Wert des berechneten Hashs und den zum Berechnen des Hashs verwendeten Algorithmus darstellt.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-169">`Get-FileHash` returns an object that represents the path to the specified file, the value of the computed hash, and the algorithm used to compute the hash.</span></span>

## <span data-ttu-id="1c7e9-170">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1c7e9-170">NOTES</span></span>

## <span data-ttu-id="1c7e9-171">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1c7e9-171">RELATED LINKS</span></span>

[<span data-ttu-id="1c7e9-172">Format-List</span><span class="sxs-lookup"><span data-stu-id="1c7e9-172">Format-List</span></span>](Format-List.md)

