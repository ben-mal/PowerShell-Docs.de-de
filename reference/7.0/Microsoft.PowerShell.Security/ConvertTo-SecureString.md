---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-SecureString
ms.openlocfilehash: c98f140a40046d1ba3e48e7063096394e358bea5
ms.sourcegitcommit: df80c558e9a4b89c9798f084bd04012ece15155c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "93225119"
---
# <span data-ttu-id="43240-103">ConvertTo-SecureString</span><span class="sxs-lookup"><span data-stu-id="43240-103">ConvertTo-SecureString</span></span>

## <span data-ttu-id="43240-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="43240-104">SYNOPSIS</span></span>
<span data-ttu-id="43240-105">Konvertiert nur-Text-oder verschlüsselte Zeichen folgen in sichere Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="43240-105">Converts plain text or encrypted strings to secure strings.</span></span>

## <span data-ttu-id="43240-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43240-106">SYNTAX</span></span>

### <span data-ttu-id="43240-107">Sicher (Standard)</span><span class="sxs-lookup"><span data-stu-id="43240-107">Secure (Default)</span></span>

```
ConvertTo-SecureString [-String] <String> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### <span data-ttu-id="43240-108">PlainText</span><span class="sxs-lookup"><span data-stu-id="43240-108">PlainText</span></span>

```
ConvertTo-SecureString [-String] <String> [-AsPlainText] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="43240-109">Öffnen</span><span class="sxs-lookup"><span data-stu-id="43240-109">Open</span></span>

```
ConvertTo-SecureString [-String] <String> [-Key <Byte[]>] [<CommonParameters>]
```

## <span data-ttu-id="43240-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="43240-110">DESCRIPTION</span></span>

<span data-ttu-id="43240-111">Das- `ConvertTo-SecureString` Cmdlet konvertiert verschlüsselte Standard Zeichenfolgen in sichere Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="43240-111">The `ConvertTo-SecureString` cmdlet converts encrypted standard strings into secure strings.</span></span> <span data-ttu-id="43240-112">Es kann auch einfachen Text in sichere Zeichenfolgen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="43240-112">It can also convert plain text to secure strings.</span></span> <span data-ttu-id="43240-113">Sie wird mit `ConvertFrom-SecureString` und verwendet `Read-Host` .</span><span class="sxs-lookup"><span data-stu-id="43240-113">It is used with `ConvertFrom-SecureString` and `Read-Host`.</span></span> <span data-ttu-id="43240-114">Die vom Cmdlet erstellte sichere Zeichenfolge kann mit Cmdlets oder Funktionen verwendet werden, die einen Parameter vom Typ " **SecureString** " erfordern.</span><span class="sxs-lookup"><span data-stu-id="43240-114">The secure string created by the cmdlet can be used with cmdlets or functions that require a parameter of type **SecureString**.</span></span> <span data-ttu-id="43240-115">Die sichere Zeichenfolge kann mithilfe des Cmdlets zurück in eine verschlüsselte Standard Zeichenfolge konvertiert werden `ConvertFrom-SecureString` .</span><span class="sxs-lookup"><span data-stu-id="43240-115">The secure string can be converted back to an encrypted, standard string using the `ConvertFrom-SecureString` cmdlet.</span></span> <span data-ttu-id="43240-116">So kann sie für die spätere Verwendung in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="43240-116">This enables it to be stored in a file for later use.</span></span>

<span data-ttu-id="43240-117">Wenn die zu konvertierende Standard Zeichenfolge `ConvertFrom-SecureString` mithilfe eines angegebenen Schlüssels verschlüsselt wurde, muss der gleiche Schlüssel als Wert des **Key** -oder **SecureKey** -Parameters des `ConvertTo-SecureString` Cmdlets angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="43240-117">If the standard string being converted was encrypted with `ConvertFrom-SecureString` using a specified key, that same key must be provided as the value of the **Key** or **SecureKey** parameter of the `ConvertTo-SecureString` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="43240-118">Beachten Sie, dass die Inhalte von SecureString pro [dotnet](/dotnet/api/system.security.securestring#remarks)nicht auf nicht-Windows-Systemen verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="43240-118">Note that per [DotNet](/dotnet/api/system.security.securestring#remarks), the contents of a SecureString are not encrypted on non-Windows systems.</span></span>

## <span data-ttu-id="43240-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="43240-119">EXAMPLES</span></span>

### <span data-ttu-id="43240-120">Beispiel 1: Konvertieren einer sicheren Zeichenfolge in eine verschlüsselte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="43240-120">Example 1: Convert a secure string to an encrypted string</span></span>

<span data-ttu-id="43240-121">In diesem Beispiel wird veranschaulicht, wie eine sichere Zeichenfolge aus der Benutzereingabe erstellt, die sichere Zeichenfolge in eine verschlüsselte Standardzeichenfolge konvertiert und dann die verschlüsselte Standardzeichenfolge wieder in eine sichere Zeichenfolge konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="43240-121">This example shows how to create a secure string from user input, convert the secure string to an encrypted standard string, and then convert the encrypted standard string back to a secure string.</span></span>

```powershell
PS C:\> $Secure = Read-Host -AsSecureString
PS C:\> $Secure
System.Security.SecureString
PS C:\> $Encrypted = ConvertFrom-SecureString -SecureString $Secure
PS C:\> $Encrypted
01000000d08c9ddf0115d1118c7a00c04fc297eb010000001a114d45b8dd3f4aa11ad7c0abdae98000000000
02000000000003660000a8000000100000005df63cea84bfb7d70bd6842e7efa79820000000004800000a000
000010000000f10cd0f4a99a8d5814d94e0687d7430b100000008bf11f1960158405b2779613e9352c6d1400
0000e6b7bf46a9d485ff211b9b2a2df3bd6eb67aae41
PS C:\> $Secure2 = ConvertTo-SecureString -String $Encrypted
PS C:\> $Secure2
System.Security.SecureString
```

<span data-ttu-id="43240-122">Der erste Befehl verwendet den **assecurestring** -Parameter des `Read-Host` Cmdlets, um eine sichere Zeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="43240-122">The first command uses the **AsSecureString** parameter of the `Read-Host` cmdlet to create a secure string.</span></span> <span data-ttu-id="43240-123">Nachdem Sie den Befehl eingegeben haben, werden alle von Ihnen eingegebenen Zeichen in eine sichere Zeichenfolge konvertiert und anschließend in der `$Secure` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="43240-123">After you enter the command, any characters that you type are converted into a secure string and then saved in the `$Secure` variable.</span></span>

<span data-ttu-id="43240-124">Der zweite Befehl zeigt den Inhalt der `$Secure` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="43240-124">The second command displays the contents of the `$Secure` variable.</span></span> <span data-ttu-id="43240-125">Da die `$Secure` Variable eine sichere Zeichenfolge enthält, zeigt PowerShell nur den **System. Security. SecureString** -Typ an.</span><span class="sxs-lookup"><span data-stu-id="43240-125">Because the `$Secure` variable contains a secure string, PowerShell displays only the **System.Security.SecureString** type.</span></span>

<span data-ttu-id="43240-126">Der dritte Befehl verwendet das `ConvertFrom-SecureString` Cmdlet, um die sichere Zeichenfolge in der `$Secure` Variablen in eine verschlüsselte Standard Zeichenfolge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="43240-126">The third command uses the `ConvertFrom-SecureString` cmdlet to convert the secure string in the `$Secure` variable into an encrypted standard string.</span></span> <span data-ttu-id="43240-127">Das Ergebnis wird in der `$Encrypted` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="43240-127">It saves the result in the `$Encrypted` variable.</span></span>

<span data-ttu-id="43240-128">Der vierte Befehl zeigt die verschlüsselte Zeichenfolge im Wert der `$Encrypted` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="43240-128">The fourth command displays the encrypted string in the value of the `$Encrypted` variable.</span></span>

<span data-ttu-id="43240-129">Der fünfte Befehl verwendet das `ConvertTo-SecureString` Cmdlet, um die verschlüsselte Standard Zeichenfolge in der `$Encrypted` Variablen zurück in eine sichere Zeichenfolge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="43240-129">The fifth command uses the `ConvertTo-SecureString` cmdlet to convert the encrypted standard string in the `$Encrypted` variable back into a secure string.</span></span> <span data-ttu-id="43240-130">Das Ergebnis wird in der `$Secure2` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="43240-130">It saves the result in the `$Secure2` variable.</span></span>
<span data-ttu-id="43240-131">Der sechste Befehl zeigt den Wert der `$Secure2` Variablen an.</span><span class="sxs-lookup"><span data-stu-id="43240-131">The sixth command displays the value of the `$Secure2` variable.</span></span> <span data-ttu-id="43240-132">Der SecureString-Typ gibt an, dass der Befehl erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="43240-132">The SecureString type indicates that the command was successful.</span></span>

### <span data-ttu-id="43240-133">Beispiel 2: Erstellen einer sicheren Zeichenfolge aus einer verschlüsselten Zeichenfolge in einer Datei</span><span class="sxs-lookup"><span data-stu-id="43240-133">Example 2: Create a secure string from an encrypted string in a file</span></span>

<span data-ttu-id="43240-134">Dieses Beispiel zeigt, wie eine sichere Zeichenfolge aus einer verschlüsselten, in einer Datei gespeicherten Standardzeichenfolge erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="43240-134">This example shows how to create a secure string from an encrypted standard string that is saved in a file.</span></span>

```powershell
$Secure = Read-Host -AsSecureString
$Encrypted = ConvertFrom-SecureString -SecureString $Secure -Key (1..16)
$Encrypted | Set-Content Encrypted.txt
$Secure2 = Get-Content Encrypted.txt | ConvertTo-SecureString -Key (1..16)
```

<span data-ttu-id="43240-135">Der erste Befehl verwendet den **assecurestring** -Parameter des `Read-Host` Cmdlets, um eine sichere Zeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="43240-135">The first command uses the **AsSecureString** parameter of the `Read-Host` cmdlet to create a secure string.</span></span> <span data-ttu-id="43240-136">Nachdem Sie den Befehl eingegeben haben, werden alle von Ihnen eingegebenen Zeichen in eine sichere Zeichenfolge konvertiert und anschließend in der `$Secure` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="43240-136">After you enter the command, any characters that you type are converted into a secure string and then saved in the `$Secure` variable.</span></span>

<span data-ttu-id="43240-137">Der zweite Befehl verwendet das `ConvertFrom-SecureString` Cmdlet, um die sichere Zeichenfolge in der `$Secure` Variablen mithilfe des angegebenen Schlüssels in eine verschlüsselte Standard Zeichenfolge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="43240-137">The second command uses the `ConvertFrom-SecureString` cmdlet to convert the secure string in the `$Secure` variable into an encrypted standard string by using the specified key.</span></span> <span data-ttu-id="43240-138">Der Inhalt wird in der `$Encrypted` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="43240-138">The contents are saved in the `$Encrypted` variable.</span></span>

<span data-ttu-id="43240-139">Der dritte Befehl verwendet einen Pipeline Operator ( `|` ), um den Wert der `$Encrypted` Variablen an das `Set-Content` Cmdlet zu senden, das den Wert in der Encrypted.txt-Datei speichert.</span><span class="sxs-lookup"><span data-stu-id="43240-139">The third command uses a pipeline operator (`|`) to send the value of the `$Encrypted` variable to the `Set-Content` cmdlet, which saves the value in the Encrypted.txt file.</span></span>

<span data-ttu-id="43240-140">Der vierte Befehl verwendet das `Get-Content` Cmdlet, um die verschlüsselte Standard Zeichenfolge in der Encrypted.txt-Datei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="43240-140">The fourth command uses the `Get-Content` cmdlet to get the encrypted standard string in the Encrypted.txt file.</span></span> <span data-ttu-id="43240-141">Der Befehl verwendet einen Pipeline Operator, um die verschlüsselte Zeichenfolge an das `ConvertTo-SecureString` Cmdlet zu senden, das Sie mit dem angegebenen Schlüssel in eine sichere Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="43240-141">The command uses a pipeline operator to send the encrypted string to the `ConvertTo-SecureString` cmdlet, which converts it to a secure string by using the specified key.</span></span>
<span data-ttu-id="43240-142">Die Ergebnisse werden in der `$Secure2` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="43240-142">The results are saved in the `$Secure2` variable.</span></span>

### <span data-ttu-id="43240-143">Beispiel 3: Konvertieren einer nur-Text-Zeichenfolge in eine sichere Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="43240-143">Example 3: Convert a plain text string to a secure string</span></span>

<span data-ttu-id="43240-144">Dieser Befehl konvertiert die nur-Text-Zeichenfolge in `P@ssW0rD!` eine sichere Zeichenfolge und speichert das Ergebnis in der `$Secure_String_Pwd` Variablen.</span><span class="sxs-lookup"><span data-stu-id="43240-144">This command converts the plain text string `P@ssW0rD!` into a secure string and stores the result in the `$Secure_String_Pwd` variable.</span></span> <span data-ttu-id="43240-145">Um den **asplaintext** -Parameter zu verwenden, muss der **Force** -Parameter auch im Befehl enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="43240-145">To use the **AsPlainText** parameter, the **Force** parameter must also be included in the command.</span></span>

```powershell
$Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
```

> [!CAUTION]
> <span data-ttu-id="43240-146">Vermeiden Sie die Verwendung von nur-Text-Zeichen folgen im Skript oder über die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="43240-146">You should avoid using plain text strings in script or from the command line.</span></span> <span data-ttu-id="43240-147">Der nur-Text kann in Ereignisprotokollen und Befehlsverlauf Protokollen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="43240-147">The plain text can show up in event logs and command history logs.</span></span>

## <span data-ttu-id="43240-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43240-148">PARAMETERS</span></span>

### <span data-ttu-id="43240-149">-Asplaintext</span><span class="sxs-lookup"><span data-stu-id="43240-149">-AsPlainText</span></span>

<span data-ttu-id="43240-150">Gibt eine Nur-Text-Zeichenfolge an, die in eine sichere Zeichenfolge konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="43240-150">Specifies a plain text string to convert to a secure string.</span></span> <span data-ttu-id="43240-151">Cmdlets für sichere Zeichenfolgen tragen zum Schutz von vertraulichem Text bei.</span><span class="sxs-lookup"><span data-stu-id="43240-151">The secure string cmdlets help protect confidential text.</span></span> <span data-ttu-id="43240-152">Der Text wird zu Datenschutzzwecken verschlüsselt und nach der Verwendung aus dem Computerspeicher gelöscht.</span><span class="sxs-lookup"><span data-stu-id="43240-152">The text is encrypted for privacy and is deleted from computer memory after it is used.</span></span> <span data-ttu-id="43240-153">Wenn Sie diesen Parameter für einfachen Text als Eingabe verwenden, kann nicht das System die Eingabe nicht auf diese Weise schützen.</span><span class="sxs-lookup"><span data-stu-id="43240-153">If you use this parameter to provide plain text as input, the system cannot protect that input in this manner.</span></span> <span data-ttu-id="43240-154">Um diesen Parameter zu verwenden, müssen Sie auch den **Force** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="43240-154">To use this parameter, you must also specify the **Force** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43240-155">-Force</span><span class="sxs-lookup"><span data-stu-id="43240-155">-Force</span></span>

<span data-ttu-id="43240-156">Bestätigt, dass Sie die Auswirkungen der Verwendung des **asplaintext** -Parameters verstehen und dennoch verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="43240-156">Confirms that you understand the implications of using the **AsPlainText** parameter and still want to use it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PlainText
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43240-157">-Key</span><span class="sxs-lookup"><span data-stu-id="43240-157">-Key</span></span>

<span data-ttu-id="43240-158">Gibt den Verschlüsselungsschlüssel an, der zum Konvertieren der ursprünglichen sicheren Zeichenfolge in die verschlüsselte Standard Zeichenfolge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="43240-158">Specifies the encryption key used to convert the original secure string into the encrypted standard string.</span></span> <span data-ttu-id="43240-159">Gültige Schlüssellängen sind 16, 24 und 32 Bytes.</span><span class="sxs-lookup"><span data-stu-id="43240-159">Valid key lengths are 16, 24 and 32 bytes.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: Open
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43240-160">-SecureKey</span><span class="sxs-lookup"><span data-stu-id="43240-160">-SecureKey</span></span>

<span data-ttu-id="43240-161">Gibt den Verschlüsselungsschlüssel an, der zum Konvertieren der ursprünglichen sicheren Zeichenfolge in die verschlüsselte Standard Zeichenfolge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="43240-161">Specifies the encryption key used to convert the original secure string into the encrypted standard string.</span></span> <span data-ttu-id="43240-162">Der Schlüssel muss im Format einer sicheren Zeichenfolge bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="43240-162">The key must be provided in the format of a secure string.</span></span> <span data-ttu-id="43240-163">Die sichere Zeichenfolge wird in ein Bytearray konvertiert, das als Schlüssel verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="43240-163">The secure string will be converted to a byte array to be used as the key.</span></span> <span data-ttu-id="43240-164">Gültige sichere Schlüssellängen sind 8, 12 und 16 Code Punkte.</span><span class="sxs-lookup"><span data-stu-id="43240-164">Valid secure key lengths are 8, 12 and 16 code points.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: Secure
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43240-165">-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="43240-165">-String</span></span>

<span data-ttu-id="43240-166">Gibt die Zeichenfolge an, die in eine sichere Zeichenfolge konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="43240-166">Specifies the string to convert to a secure string.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="43240-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="43240-167">CommonParameters</span></span>

<span data-ttu-id="43240-168">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="43240-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43240-169">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="43240-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43240-170">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="43240-170">INPUTS</span></span>

### <span data-ttu-id="43240-171">System.String</span><span class="sxs-lookup"><span data-stu-id="43240-171">System.String</span></span>

<span data-ttu-id="43240-172">Sie können eine verschlüsselte Standard Zeichenfolge an übergeben `ConvertTo-SecureString` .</span><span class="sxs-lookup"><span data-stu-id="43240-172">You can pipe a standard encrypted string to `ConvertTo-SecureString`.</span></span>

## <span data-ttu-id="43240-173">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="43240-173">OUTPUTS</span></span>

### <span data-ttu-id="43240-174">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="43240-174">System.Security.SecureString</span></span>

<span data-ttu-id="43240-175">`ConvertTo-SecureString` Gibt ein **SecureString** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="43240-175">`ConvertTo-SecureString` returns a **SecureString** object.</span></span>

## <span data-ttu-id="43240-176">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="43240-176">NOTES</span></span>

<span data-ttu-id="43240-177">Einige Zeichen, z. b. Emoticons, entsprechen mehreren Code Punkten in der Zeichenfolge, in der Sie enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="43240-177">Some characters, such as emoticons, correspond to several code points in the string that contains them.</span></span> <span data-ttu-id="43240-178">Vermeiden Sie die Verwendung dieser Zeichen, da Sie bei der Verwendung in einem Kennwort Probleme und Missverständnisse verursachen können.</span><span class="sxs-lookup"><span data-stu-id="43240-178">Avoid using these characters because they may cause problems and misunderstandings when used in a password.</span></span>

## <span data-ttu-id="43240-179">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="43240-179">RELATED LINKS</span></span>

[<span data-ttu-id="43240-180">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="43240-180">ConvertFrom-SecureString</span></span>](ConvertFrom-SecureString.md)

[<span data-ttu-id="43240-181">Read-Host</span><span class="sxs-lookup"><span data-stu-id="43240-181">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)
