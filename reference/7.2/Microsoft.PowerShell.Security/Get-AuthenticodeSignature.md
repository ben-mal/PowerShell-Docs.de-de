---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AuthenticodeSignature
ms.openlocfilehash: 16c61b1fd442eb68c458c3b524a8fc55d5eedcb6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601323"
---
# <span data-ttu-id="aa1ab-102">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="aa1ab-102">Get-AuthenticodeSignature</span></span>

## <span data-ttu-id="aa1ab-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="aa1ab-103">SYNOPSIS</span></span>
<span data-ttu-id="aa1ab-104">Ruft Informationen über die Authenticode-Signatur für eine Datei ab.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-104">Gets information about the Authenticode signature for a file.</span></span>

## <span data-ttu-id="aa1ab-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa1ab-105">SYNTAX</span></span>

### <span data-ttu-id="aa1ab-106">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="aa1ab-106">ByPath (Default)</span></span>

```
Get-AuthenticodeSignature [-FilePath] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="aa1ab-107">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="aa1ab-107">ByLiteralPath</span></span>

```
Get-AuthenticodeSignature -LiteralPath <String[]> [<CommonParameters>]
```

### <span data-ttu-id="aa1ab-108">Bycontent</span><span class="sxs-lookup"><span data-stu-id="aa1ab-108">ByContent</span></span>

```
Get-AuthenticodeSignature -SourcePathOrExtension <String[]> -Content <Byte[]> [<CommonParameters>]
```

## <span data-ttu-id="aa1ab-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa1ab-109">DESCRIPTION</span></span>

<span data-ttu-id="aa1ab-110">Das- `Get-AuthenticodeSignature` Cmdlet ruft Informationen über die Authenticode-Signatur für einen Datei-oder Dateiinhalt als Bytearray ab.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-110">The `Get-AuthenticodeSignature` cmdlet gets information about the Authenticode signature for a file or file content as a byte array.</span></span> <span data-ttu-id="aa1ab-111">Wenn die Datei nicht signiert ist, werden die Informationen abgerufen, aber die Felder sind leer.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-111">If the file is not signed, the information is retrieved, but the fields are blank.</span></span>

## <span data-ttu-id="aa1ab-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="aa1ab-112">EXAMPLES</span></span>

### <span data-ttu-id="aa1ab-113">Beispiel 1: erhalten der Authenticode-Signatur für eine Datei</span><span class="sxs-lookup"><span data-stu-id="aa1ab-113">Example 1: Get the Authenticode signature for a file</span></span>

```powershell
Get-AuthenticodeSignature -FilePath "C:\Test\NewScript.ps1"
```

<span data-ttu-id="aa1ab-114">Dieser Befehl ruft Informationen über die Authenticode-Signatur in der Datei NewScript.ps1 ab.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-114">This command gets information about the Authenticode signature in the NewScript.ps1 file.</span></span> <span data-ttu-id="aa1ab-115">Er verwendet den **FilePath** -Parameter, um die Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-115">It uses the **FilePath** parameter to specify the file.</span></span>

### <span data-ttu-id="aa1ab-116">Beispiel 2: erhalten der Authenticode-Signatur für mehrere Dateien</span><span class="sxs-lookup"><span data-stu-id="aa1ab-116">Example 2: Get the Authenticode signature for multiple files</span></span>

```powershell
Get-AuthenticodeSignature test.ps1, test1.ps1, sign-file.ps1, makexml.ps1
```

<span data-ttu-id="aa1ab-117">Dieser Befehl ruft Informationen über die Authenticode-Signatur für die vier Dateien ab, die in der Befehlszeile aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-117">This command gets information about the Authenticode signature for the four files listed at the command line.</span></span> <span data-ttu-id="aa1ab-118">In diesem Beispiel wird der Name des **FilePath** -Parameters, der optional ist, weggelassen.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-118">In this example, the name of the **FilePath** parameter, which is optional, is omitted.</span></span>

### <span data-ttu-id="aa1ab-119">Beispiel 3: nur gültige Authenticode-Signaturen für mehrere Dateien erhalten</span><span class="sxs-lookup"><span data-stu-id="aa1ab-119">Example 3: Get only valid Authenticode signatures for multiple files</span></span>

```powershell
Get-ChildItem $PSHOME\*.* | ForEach-object {Get-AuthenticodeSignature $_} | Where-Object {$_.status -eq "Valid"}
```

<span data-ttu-id="aa1ab-120">Mit diesem Befehl werden alle Dateien im Verzeichnis aufgelistet `$PSHOME` , die über eine gültige Authenticode-Signatur verfügen.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-120">This command lists all of the files in the `$PSHOME` directory that have a valid Authenticode signature.</span></span> <span data-ttu-id="aa1ab-121">Die `$PSHOME` Automatische Variable enthält den Pfad zum PowerShell-Installationsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-121">The `$PSHOME` automatic variable contains the path to the PowerShell installation directory.</span></span>

<span data-ttu-id="aa1ab-122">Der Befehl verwendet das `Get-ChildItem` Cmdlet, um die Dateien im Verzeichnis zu erhalten `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="aa1ab-122">The command uses the `Get-ChildItem` cmdlet to get the files in the `$PSHOME` directory.</span></span> <span data-ttu-id="aa1ab-123">Dabei wird ein Muster von verwendet *.*</span><span class="sxs-lookup"><span data-stu-id="aa1ab-123">It uses a pattern of *.*</span></span> <span data-ttu-id="aa1ab-124">zum Ausschließen von Verzeichnissen (obwohl auch Dateien ohne einen Punkt im Dateinamen ausgeschlossen werden).</span><span class="sxs-lookup"><span data-stu-id="aa1ab-124">to exclude directories (although it also excludes files without a dot in the filename).</span></span>

<span data-ttu-id="aa1ab-125">Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Dateien an `$PSHOME` das `ForEach-Object` Cmdlet zu senden, wobei `Get-AuthenticodeSignature` für jede Datei aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-125">The command uses a pipeline operator (`|`) to send the files in `$PSHOME` to the `ForEach-Object` cmdlet, where `Get-AuthenticodeSignature` is called for each file.</span></span>

<span data-ttu-id="aa1ab-126">Die Ergebnisse des `Get-AuthenticodeSignature` Befehls werden an einen Befehl gesendet `Where-Object` , der nur die Signatur Objekte mit dem Status "valid" auswählt.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-126">The results of the `Get-AuthenticodeSignature` command are sent to a `Where-Object` command that selects only the signature objects with a status of Valid.</span></span>

### <span data-ttu-id="aa1ab-127">Beispiel 4: erhalten der Authenticode-Signatur für einen Dateiinhalt, der als Bytearray angegeben ist</span><span class="sxs-lookup"><span data-stu-id="aa1ab-127">Example 4: Get the Authenticode signature for a file content specified as byte array</span></span>

```powershell
Get-AuthenticodeSignature -Content (Get-Content foo.ps1 -AsByteStream) -SourcePathorExtension ps1
```

<span data-ttu-id="aa1ab-128">Dieser Befehl ruft Informationen über die Authenticode-Signatur für den Inhalt einer Datei ab.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-128">This command gets information about the Authenticode signature for the content of a file.</span></span> <span data-ttu-id="aa1ab-129">In diesem Beispiel wird die Dateierweiterung zusammen mit dem Inhalt der Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-129">In this example, the file extension is specified along with the content of the file.</span></span>

## <span data-ttu-id="aa1ab-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa1ab-130">PARAMETERS</span></span>

### <span data-ttu-id="aa1ab-131">-Inhalt</span><span class="sxs-lookup"><span data-stu-id="aa1ab-131">-Content</span></span>

<span data-ttu-id="aa1ab-132">Der Inhalt einer Datei als Bytearray, für das die Authenticode-Signatur abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-132">Contents of a file as a byte array for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="aa1ab-133">Dieser Parameter muss mit dem **sourcepthorextension** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-133">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="aa1ab-134">Der Inhalt der Datei muss im Unicode-Format (UTF-16LE) vorliegen.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-134">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

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

### <span data-ttu-id="aa1ab-135">-FilePath</span><span class="sxs-lookup"><span data-stu-id="aa1ab-135">-FilePath</span></span>

<span data-ttu-id="aa1ab-136">Gibt den Pfad zu der Datei an, die untersucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-136">Specifies the path to the file to examine.</span></span> <span data-ttu-id="aa1ab-137">Platzhalter sind zulässig, aber sie müssen auf eine einzige Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-137">Wildcards are permitted, but they must lead to a single file.</span></span> <span data-ttu-id="aa1ab-138">Es ist nicht erforderlich, **FilePath** in der Befehlszeile einzugeben, wenn Sie einen Wert für diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-138">It is not necessary to type **FilePath** at the command line when you specify a value for this parameter.</span></span>

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

### <span data-ttu-id="aa1ab-139">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="aa1ab-139">-LiteralPath</span></span>

<span data-ttu-id="aa1ab-140">Gibt den Pfad zur Datei an, die überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-140">Specifies the path to the file being examined.</span></span> <span data-ttu-id="aa1ab-141">Im Gegensatz zu **FilePath** wird der Wert des **LiteralPath**-Parameters genau wie eingegeben verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-141">Unlike **FilePath**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="aa1ab-142">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-142">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="aa1ab-143">Wenn der Pfad ein Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-143">If the path includes an escape character, enclose it in single quotation marks.</span></span> <span data-ttu-id="aa1ab-144">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapezeichen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-144">Single quotation marks tell PowerShell not to interpret any characters as escape characters.</span></span>

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

### <span data-ttu-id="aa1ab-145">-Sourceplthorextension</span><span class="sxs-lookup"><span data-stu-id="aa1ab-145">-SourcePathOrExtension</span></span>

<span data-ttu-id="aa1ab-146">Der Pfad zur Datei oder zum Dateityp des Inhalts, für den die Authenticode-Signatur abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-146">Path to the file or file type of the content for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="aa1ab-147">Dieser Parameter wird mit **Inhalten** verwendet, bei denen der Dateiinhalt als Bytearray übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-147">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

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

### <span data-ttu-id="aa1ab-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aa1ab-148">CommonParameters</span></span>

<span data-ttu-id="aa1ab-149">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa1ab-150">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="aa1ab-150">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="aa1ab-151">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="aa1ab-151">INPUTS</span></span>

### <span data-ttu-id="aa1ab-152">System.String</span><span class="sxs-lookup"><span data-stu-id="aa1ab-152">System.String</span></span>

<span data-ttu-id="aa1ab-153">Sie können eine Zeichenfolge mit einem Dateipfad an die Pipeline übergeben `Get-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="aa1ab-153">You can pipe a string that contains a file path to `Get-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="aa1ab-154">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="aa1ab-154">OUTPUTS</span></span>

### <span data-ttu-id="aa1ab-155">System. Management. Automation. Signature</span><span class="sxs-lookup"><span data-stu-id="aa1ab-155">System.Management.Automation.Signature</span></span>

<span data-ttu-id="aa1ab-156">`Get-AuthenticodeSignature` Gibt ein Signatur Objekt für jede Signatur zurück, die es abruft.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-156">`Get-AuthenticodeSignature` returns a signature object for each signature that it gets.</span></span>

## <span data-ttu-id="aa1ab-157">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="aa1ab-157">NOTES</span></span>

<span data-ttu-id="aa1ab-158">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="aa1ab-158">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="aa1ab-159">Informationen zu Authenticode-Signaturen in PowerShell finden Sie unter [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="aa1ab-159">For information about Authenticode signatures in PowerShell, see [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span></span>

## <span data-ttu-id="aa1ab-160">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="aa1ab-160">RELATED LINKS</span></span>

[<span data-ttu-id="aa1ab-161">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="aa1ab-161">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="aa1ab-162">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="aa1ab-162">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="aa1ab-163">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="aa1ab-163">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="aa1ab-164">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="aa1ab-164">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="aa1ab-165">about_Signing</span><span class="sxs-lookup"><span data-stu-id="aa1ab-165">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
