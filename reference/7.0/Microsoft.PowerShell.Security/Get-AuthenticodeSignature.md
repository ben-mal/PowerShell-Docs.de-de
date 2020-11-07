---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AuthenticodeSignature
ms.openlocfilehash: 6e205efe91f453d00f29a95f418eff89063acea8
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347141"
---
# <span data-ttu-id="688a2-103">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="688a2-103">Get-AuthenticodeSignature</span></span>

## <span data-ttu-id="688a2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="688a2-104">SYNOPSIS</span></span>
<span data-ttu-id="688a2-105">Ruft Informationen über die Authenticode-Signatur für eine Datei ab.</span><span class="sxs-lookup"><span data-stu-id="688a2-105">Gets information about the Authenticode signature for a file.</span></span>

## <span data-ttu-id="688a2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="688a2-106">SYNTAX</span></span>

### <span data-ttu-id="688a2-107">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="688a2-107">ByPath (Default)</span></span>

```
Get-AuthenticodeSignature [-FilePath] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="688a2-108">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="688a2-108">ByLiteralPath</span></span>

```
Get-AuthenticodeSignature -LiteralPath <String[]> [<CommonParameters>]
```

### <span data-ttu-id="688a2-109">Bycontent</span><span class="sxs-lookup"><span data-stu-id="688a2-109">ByContent</span></span>

```
Get-AuthenticodeSignature -SourcePathOrExtension <String[]> -Content <Byte[]> [<CommonParameters>]
```

## <span data-ttu-id="688a2-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="688a2-110">DESCRIPTION</span></span>

<span data-ttu-id="688a2-111">Das- `Get-AuthenticodeSignature` Cmdlet ruft Informationen über die Authenticode-Signatur für einen Datei-oder Dateiinhalt als Bytearray ab.</span><span class="sxs-lookup"><span data-stu-id="688a2-111">The `Get-AuthenticodeSignature` cmdlet gets information about the Authenticode signature for a file or file content as a byte array.</span></span> <span data-ttu-id="688a2-112">Wenn die Datei nicht signiert ist, werden die Informationen abgerufen, aber die Felder sind leer.</span><span class="sxs-lookup"><span data-stu-id="688a2-112">If the file is not signed, the information is retrieved, but the fields are blank.</span></span>

## <span data-ttu-id="688a2-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="688a2-113">EXAMPLES</span></span>

### <span data-ttu-id="688a2-114">Beispiel 1: erhalten der Authenticode-Signatur für eine Datei</span><span class="sxs-lookup"><span data-stu-id="688a2-114">Example 1: Get the Authenticode signature for a file</span></span>

```powershell
Get-AuthenticodeSignature -FilePath "C:\Test\NewScript.ps1"
```

<span data-ttu-id="688a2-115">Dieser Befehl ruft Informationen über die Authenticode-Signatur in der Datei NewScript.ps1 ab.</span><span class="sxs-lookup"><span data-stu-id="688a2-115">This command gets information about the Authenticode signature in the NewScript.ps1 file.</span></span> <span data-ttu-id="688a2-116">Er verwendet den **FilePath** -Parameter, um die Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="688a2-116">It uses the **FilePath** parameter to specify the file.</span></span>

### <span data-ttu-id="688a2-117">Beispiel 2: erhalten der Authenticode-Signatur für mehrere Dateien</span><span class="sxs-lookup"><span data-stu-id="688a2-117">Example 2: Get the Authenticode signature for multiple files</span></span>

```powershell
Get-AuthenticodeSignature test.ps1, test1.ps1, sign-file.ps1, makexml.ps1
```

<span data-ttu-id="688a2-118">Dieser Befehl ruft Informationen über die Authenticode-Signatur für die vier Dateien ab, die in der Befehlszeile aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="688a2-118">This command gets information about the Authenticode signature for the four files listed at the command line.</span></span> <span data-ttu-id="688a2-119">In diesem Beispiel wird der Name des **FilePath** -Parameters, der optional ist, weggelassen.</span><span class="sxs-lookup"><span data-stu-id="688a2-119">In this example, the name of the **FilePath** parameter, which is optional, is omitted.</span></span>

### <span data-ttu-id="688a2-120">Beispiel 3: nur gültige Authenticode-Signaturen für mehrere Dateien erhalten</span><span class="sxs-lookup"><span data-stu-id="688a2-120">Example 3: Get only valid Authenticode signatures for multiple files</span></span>

```powershell
Get-ChildItem $PSHOME\*.* | ForEach-object {Get-AuthenticodeSignature $_} | Where-Object {$_.status -eq "Valid"}
```

<span data-ttu-id="688a2-121">Mit diesem Befehl werden alle Dateien im Verzeichnis aufgelistet `$PSHOME` , die über eine gültige Authenticode-Signatur verfügen.</span><span class="sxs-lookup"><span data-stu-id="688a2-121">This command lists all of the files in the `$PSHOME` directory that have a valid Authenticode signature.</span></span> <span data-ttu-id="688a2-122">Die `$PSHOME` Automatische Variable enthält den Pfad zum PowerShell-Installationsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="688a2-122">The `$PSHOME` automatic variable contains the path to the PowerShell installation directory.</span></span>

<span data-ttu-id="688a2-123">Der Befehl verwendet das `Get-ChildItem` Cmdlet, um die Dateien im Verzeichnis zu erhalten `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="688a2-123">The command uses the `Get-ChildItem` cmdlet to get the files in the `$PSHOME` directory.</span></span> <span data-ttu-id="688a2-124">Dabei wird ein Muster von verwendet *.*</span><span class="sxs-lookup"><span data-stu-id="688a2-124">It uses a pattern of *.*</span></span> <span data-ttu-id="688a2-125">zum Ausschließen von Verzeichnissen (obwohl auch Dateien ohne einen Punkt im Dateinamen ausgeschlossen werden).</span><span class="sxs-lookup"><span data-stu-id="688a2-125">to exclude directories (although it also excludes files without a dot in the filename).</span></span>

<span data-ttu-id="688a2-126">Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Dateien an `$PSHOME` das `ForEach-Object` Cmdlet zu senden, wobei `Get-AuthenticodeSignature` für jede Datei aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="688a2-126">The command uses a pipeline operator (`|`) to send the files in `$PSHOME` to the `ForEach-Object` cmdlet, where `Get-AuthenticodeSignature` is called for each file.</span></span>

<span data-ttu-id="688a2-127">Die Ergebnisse des `Get-AuthenticodeSignature` Befehls werden an einen Befehl gesendet `Where-Object` , der nur die Signatur Objekte mit dem Status "valid" auswählt.</span><span class="sxs-lookup"><span data-stu-id="688a2-127">The results of the `Get-AuthenticodeSignature` command are sent to a `Where-Object` command that selects only the signature objects with a status of Valid.</span></span>

### <span data-ttu-id="688a2-128">Beispiel 4: erhalten der Authenticode-Signatur für einen Dateiinhalt, der als Bytearray angegeben ist</span><span class="sxs-lookup"><span data-stu-id="688a2-128">Example 4: Get the Authenticode signature for a file content specified as byte array</span></span>

```powershell
Get-AuthenticodeSignature -Content (Get-Content foo.ps1 -AsByteStream) -SourcePathorExtension ps1
```

<span data-ttu-id="688a2-129">Dieser Befehl ruft Informationen über die Authenticode-Signatur für den Inhalt einer Datei ab.</span><span class="sxs-lookup"><span data-stu-id="688a2-129">This command gets information about the Authenticode signature for the content of a file.</span></span> <span data-ttu-id="688a2-130">In diesem Beispiel wird die Dateierweiterung zusammen mit dem Inhalt der Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="688a2-130">In this example, the file extension is specified along with the content of the file.</span></span>

## <span data-ttu-id="688a2-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="688a2-131">PARAMETERS</span></span>

### <span data-ttu-id="688a2-132">-Inhalt</span><span class="sxs-lookup"><span data-stu-id="688a2-132">-Content</span></span>

<span data-ttu-id="688a2-133">Der Inhalt einer Datei als Bytearray, für das die Authenticode-Signatur abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="688a2-133">Contents of a file as a byte array for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="688a2-134">Dieser Parameter muss mit dem **sourcepthorextension** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="688a2-134">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="688a2-135">Der Inhalt der Datei muss im Unicode-Format (UTF-16LE) vorliegen.</span><span class="sxs-lookup"><span data-stu-id="688a2-135">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="688a2-136">-FilePath</span><span class="sxs-lookup"><span data-stu-id="688a2-136">-FilePath</span></span>

<span data-ttu-id="688a2-137">Gibt den Pfad zu der Datei an, die untersucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="688a2-137">Specifies the path to the file to examine.</span></span> <span data-ttu-id="688a2-138">Platzhalter sind zulässig, aber sie müssen auf eine einzige Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="688a2-138">Wildcards are permitted, but they must lead to a single file.</span></span> <span data-ttu-id="688a2-139">Es ist nicht erforderlich, **FilePath** in der Befehlszeile einzugeben, wenn Sie einen Wert für diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="688a2-139">It is not necessary to type **FilePath** at the command line when you specify a value for this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="688a2-140">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="688a2-140">-LiteralPath</span></span>

<span data-ttu-id="688a2-141">Gibt den Pfad zur Datei an, die überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="688a2-141">Specifies the path to the file being examined.</span></span> <span data-ttu-id="688a2-142">Im Gegensatz zu **FilePath** wird der Wert des **LiteralPath** -Parameters genau wie eingegeben verwendet.</span><span class="sxs-lookup"><span data-stu-id="688a2-142">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="688a2-143">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="688a2-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="688a2-144">Wenn der Pfad ein Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="688a2-144">If the path includes an escape character, enclose it in single quotation marks.</span></span> <span data-ttu-id="688a2-145">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapezeichen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="688a2-145">Single quotation marks tell PowerShell not to interpret any characters as escape characters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="688a2-146">-Sourceplthorextension</span><span class="sxs-lookup"><span data-stu-id="688a2-146">-SourcePathOrExtension</span></span>

<span data-ttu-id="688a2-147">Der Pfad zur Datei oder zum Dateityp des Inhalts, für den die Authenticode-Signatur abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="688a2-147">Path to the file or file type of the content for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="688a2-148">Dieser Parameter wird mit **Inhalten** verwendet, bei denen der Dateiinhalt als Bytearray übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="688a2-148">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="688a2-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="688a2-149">CommonParameters</span></span>

<span data-ttu-id="688a2-150">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="688a2-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="688a2-151">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="688a2-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="688a2-152">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="688a2-152">INPUTS</span></span>

### <span data-ttu-id="688a2-153">System.String</span><span class="sxs-lookup"><span data-stu-id="688a2-153">System.String</span></span>

<span data-ttu-id="688a2-154">Sie können eine Zeichenfolge mit einem Dateipfad an die Pipeline übergeben `Get-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="688a2-154">You can pipe a string that contains a file path to `Get-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="688a2-155">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="688a2-155">OUTPUTS</span></span>

### <span data-ttu-id="688a2-156">System. Management. Automation. Signature</span><span class="sxs-lookup"><span data-stu-id="688a2-156">System.Management.Automation.Signature</span></span>

<span data-ttu-id="688a2-157">`Get-AuthenticodeSignature` Gibt ein Signatur Objekt für jede Signatur zurück, die es abruft.</span><span class="sxs-lookup"><span data-stu-id="688a2-157">`Get-AuthenticodeSignature` returns a signature object for each signature that it gets.</span></span>

## <span data-ttu-id="688a2-158">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="688a2-158">NOTES</span></span>

<span data-ttu-id="688a2-159">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="688a2-159">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="688a2-160">Informationen zu Authenticode-Signaturen in PowerShell finden Sie unter [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="688a2-160">For information about Authenticode signatures in PowerShell, see [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span></span>

## <span data-ttu-id="688a2-161">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="688a2-161">RELATED LINKS</span></span>

[<span data-ttu-id="688a2-162">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="688a2-162">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="688a2-163">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="688a2-163">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="688a2-164">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="688a2-164">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="688a2-165">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="688a2-165">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="688a2-166">about_Signing</span><span class="sxs-lookup"><span data-stu-id="688a2-166">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
