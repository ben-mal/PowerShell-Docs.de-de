---
external help file: Microsoft.PowerShell.Security.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/convertfrom-securestring?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SecureString
ms.openlocfilehash: 4dae7806cbec85347a8dfa01348be72061214c6c
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "93217988"
---
# <span data-ttu-id="f5ddb-103">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="f5ddb-103">ConvertFrom-SecureString</span></span>

## <span data-ttu-id="f5ddb-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f5ddb-104">SYNOPSIS</span></span>
<span data-ttu-id="f5ddb-105">Konvertiert eine sichere Zeichenfolge in eine verschlüsselte Standard Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-105">Converts a secure string to an encrypted standard string.</span></span>

## <span data-ttu-id="f5ddb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f5ddb-106">SYNTAX</span></span>

### <span data-ttu-id="f5ddb-107">Sicher (Standard)</span><span class="sxs-lookup"><span data-stu-id="f5ddb-107">Secure (Default)</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [[-SecureKey] <SecureString>] [<CommonParameters>]
```

### <span data-ttu-id="f5ddb-108">Öffnen</span><span class="sxs-lookup"><span data-stu-id="f5ddb-108">Open</span></span>

```
ConvertFrom-SecureString [-SecureString] <SecureString> [-Key <Byte[]>] [<CommonParameters>]
```

## <span data-ttu-id="f5ddb-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5ddb-109">DESCRIPTION</span></span>

<span data-ttu-id="f5ddb-110">Das **ConvertFrom-SecureString-** Cmdlet konvertiert eine sichere Zeichenfolge ( **System. Security. SecureString** ) in eine verschlüsselte Standard Zeichenfolge ( **System. String** ).</span><span class="sxs-lookup"><span data-stu-id="f5ddb-110">The **ConvertFrom-SecureString** cmdlet converts a secure string ( **System.Security.SecureString** ) into an encrypted standard string ( **System.String** ).</span></span> <span data-ttu-id="f5ddb-111">Im Gegensatz zu einer sicheren Zeichenfolge kann eine verschlüsselte Standardzeichenfolge zur späteren Verwendung in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-111">Unlike a secure string, an encrypted standard string can be saved in a file for later use.</span></span> <span data-ttu-id="f5ddb-112">Die verschlüsselte Standard Zeichenfolge kann mit dem-Cmdlet zurück in das sichere Zeichen folgen Format konvertiert werden `ConvertTo-SecureString` .</span><span class="sxs-lookup"><span data-stu-id="f5ddb-112">The encrypted standard string can be converted back to its secure string format by using the `ConvertTo-SecureString` cmdlet.</span></span>

<span data-ttu-id="f5ddb-113">Wenn ein Verschlüsselungsschlüssel mithilfe des **Key** - oder **SecureKey** -Parameters angegeben wird, wird der AES (Advanced Encryption Standard)-Verschlüsselungsalgorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-113">If an encryption key is specified by using the **Key** or **SecureKey** parameters, the Advanced Encryption Standard (AES) encryption algorithm is used.</span></span> <span data-ttu-id="f5ddb-114">Der angegebene Schlüssel muss eine Länge von 128, 192 oder 256 Bits haben, da dies die vom AES-Verschlüsselungsalgorithmus unterstützten Schlüssellängen sind.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-114">The specified key must have a length of 128, 192, or 256 bits because those are the key lengths supported by the AES encryption algorithm.</span></span> <span data-ttu-id="f5ddb-115">Wenn kein Schlüssel angegeben ist, wird Windows Data Protection API (DPAPI) zum Verschlüsseln der Standardzeichenfolgendarstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-115">If no key is specified, the Windows Data Protection API (DPAPI) is used to encrypt the standard string representation.</span></span>

## <span data-ttu-id="f5ddb-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f5ddb-116">EXAMPLES</span></span>

### <span data-ttu-id="f5ddb-117">Beispiel 1: Erstellen einer sicheren Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5ddb-117">Example 1: Create a secure string</span></span>

```powershell
$SecureString = Read-Host -AsSecureString
```

<span data-ttu-id="f5ddb-118">Dieser Befehl erstellt eine sichere Zeichenfolge aus Zeichen, die Sie an der Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-118">This command creates a secure string from characters that you type at the command prompt.</span></span> <span data-ttu-id="f5ddb-119">Geben Sie nach Eingabe des Befehls die Zeichenfolge ein, die Sie als sichere Zeichenfolge speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-119">After entering the command, type the string you want to store as a secure string.</span></span> <span data-ttu-id="f5ddb-120">Ein Sternchen ( `*` ) wird angezeigt, das die einzelnen Zeichen darstellt, die Sie eingeben.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-120">An asterisk (`*`) is displayed to represent each character that you type.</span></span>

### <span data-ttu-id="f5ddb-121">Beispiel 2: Konvertieren einer sicheren Zeichenfolge in eine verschlüsselte Standard Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f5ddb-121">Example 2: Convert a secure string to an encrypted standard string</span></span>

```powershell
$StandardString = ConvertFrom-SecureString $SecureString
```

<span data-ttu-id="f5ddb-122">Dieser Befehl konvertiert die sichere Zeichenfolge in der `$SecureString` Variablen in eine verschlüsselte Standard Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-122">This command converts the secure string in the `$SecureString` variable to an encrypted standard string.</span></span> <span data-ttu-id="f5ddb-123">Die resultierende verschlüsselte Standard Zeichenfolge wird in der `$StandardString` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-123">The resulting encrypted standard string is stored in the `$StandardString` variable.</span></span>

### <span data-ttu-id="f5ddb-124">Beispiel 3: Konvertieren einer sicheren Zeichenfolge in eine verschlüsselte Standard Zeichenfolge mit einem 192-Bit-Schlüssel</span><span class="sxs-lookup"><span data-stu-id="f5ddb-124">Example 3: Convert a secure string to an encrypted standard string with a 192-bit key</span></span>

```powershell
$Key = (3,4,2,3,56,34,254,222,1,1,2,23,42,54,33,233,1,34,2,7,6,5,35,43)
$StandardString = ConvertFrom-SecureString $SecureString -Key $Key
```

<span data-ttu-id="f5ddb-125">Diese Befehle verwenden den Advanced Encryption Standard (AES)-Algorithmus, um die in der Variablen gespeicherte sichere Zeichenfolge in eine `$SecureString` verschlüsselte Standard Zeichenfolge mit einem 192-Bit-Schlüssel zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-125">These commands use the Advanced Encryption Standard (AES) algorithm to convert the secure string stored in the `$SecureString` variable to an encrypted standard string with a 192-bit key.</span></span> <span data-ttu-id="f5ddb-126">Die resultierende verschlüsselte Standard Zeichenfolge wird in der `$StandardString` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-126">The resulting encrypted standard string is stored in the `$StandardString` variable.</span></span>

<span data-ttu-id="f5ddb-127">Der erste Befehl speichert einen Schlüssel in der `$Key` Variablen.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-127">The first command stores a key in the `$Key` variable.</span></span> <span data-ttu-id="f5ddb-128">Der Schlüssel ist ein Array aus 24 Dezimalzahlen, von denen jede kleiner als 256 sein muss, damit Sie in ein einzelnes nicht signiertes Byte passt.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-128">The key is an array of 24 decimal numerals, each of which must be less than 256 to fit within a single unsigned byte.</span></span>

<span data-ttu-id="f5ddb-129">Da jede Dezimalzahl ein einzelnes Byte (8 Bits) darstellt, verfügt der Schlüssel über 24 Ziffern für insgesamt 192 Bits (8 x 24).</span><span class="sxs-lookup"><span data-stu-id="f5ddb-129">Because each decimal numeral represents a single byte (8 bits), the key has 24 digits for a total of 192 bits (8 x 24).</span></span> <span data-ttu-id="f5ddb-130">Dies ist eine gültige Schlüssellänge für den AES-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-130">This is a valid key length for the AES algorithm.</span></span>

<span data-ttu-id="f5ddb-131">Der zweite Befehl verwendet den Schlüssel in der `$Key` Variablen, um die sichere Zeichenfolge in eine verschlüsselte Standard Zeichenfolge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-131">The second command uses the key in the `$Key` variable to convert the secure string to an encrypted standard string.</span></span>

## <span data-ttu-id="f5ddb-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f5ddb-132">PARAMETERS</span></span>

### <span data-ttu-id="f5ddb-133">-Key</span><span class="sxs-lookup"><span data-stu-id="f5ddb-133">-Key</span></span>

<span data-ttu-id="f5ddb-134">Gibt den Verschlüsselungsschlüssel als Bytearray an.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-134">Specifies the encryption key as a byte array.</span></span>

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

### <span data-ttu-id="f5ddb-135">-SecureKey</span><span class="sxs-lookup"><span data-stu-id="f5ddb-135">-SecureKey</span></span>

<span data-ttu-id="f5ddb-136">Gibt den Verschlüsselungsschlüssel als sichere Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-136">Specifies the encryption key as a secure string.</span></span> <span data-ttu-id="f5ddb-137">Der Wert der sicheren Zeichenfolge wird in ein Bytearray konvertiert, bevor er als Schlüssel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-137">The secure string value is converted to a byte array before being used as the key.</span></span>

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

### <span data-ttu-id="f5ddb-138">-SecureString</span><span class="sxs-lookup"><span data-stu-id="f5ddb-138">-SecureString</span></span>

<span data-ttu-id="f5ddb-139">Gibt die sichere Zeichenfolge an, die in eine verschlüsselte Standardzeichenfolge konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-139">Specifies the secure string to convert to an encrypted standard string.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f5ddb-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f5ddb-140">CommonParameters</span></span>

<span data-ttu-id="f5ddb-141">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f5ddb-142">Weitere Informationen finden Sie unter "about_CommonParameters" (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f5ddb-142">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f5ddb-143">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f5ddb-143">INPUTS</span></span>

### <span data-ttu-id="f5ddb-144">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="f5ddb-144">System.Security.SecureString</span></span>

<span data-ttu-id="f5ddb-145">Sie können ein **SecureString** -Objekt über die Pipeline an ConvertFrom-SecureString übergeben.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-145">You can pipe a **SecureString** object to ConvertFrom-SecureString.</span></span>

## <span data-ttu-id="f5ddb-146">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f5ddb-146">OUTPUTS</span></span>

### <span data-ttu-id="f5ddb-147">System.String</span><span class="sxs-lookup"><span data-stu-id="f5ddb-147">System.String</span></span>

<span data-ttu-id="f5ddb-148">ConvertFrom-SecureString gibt ein Standardzeichenfolgenobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-148">ConvertFrom-SecureString returns a standard string object.</span></span>

## <span data-ttu-id="f5ddb-149">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f5ddb-149">NOTES</span></span>

- <span data-ttu-id="f5ddb-150">Verwenden Sie den **assecurestring** -Parameter des Cmdlets, um eine sichere Zeichenfolge aus Zeichen zu erstellen, die an der Eingabeaufforderung eingegeben werden `Read-Host` .</span><span class="sxs-lookup"><span data-stu-id="f5ddb-150">To create a secure string from characters that are typed at the command prompt, use the **AsSecureString** parameter of the `Read-Host` cmdlet.</span></span>
- <span data-ttu-id="f5ddb-151">Wenn Sie die **Schlüssel** -oder **SecureKey** -Parameter verwenden, um einen Schlüssel anzugeben, muss die Schlüssellänge korrekt sein.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-151">When you use the **Key** or **SecureKey** parameters to specify a key, the key length must be correct.</span></span> <span data-ttu-id="f5ddb-152">Beispielsweise kann ein Schlüssel von 128 Bits als Bytearray mit 16 Dezimalzahlen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-152">For example, a key of 128 bits can be specified as a byte array of 16 decimal numerals.</span></span>
  <span data-ttu-id="f5ddb-153">Entsprechend entsprechen 192-Bit-und 256-Bit-Schlüssel Byte Arrays mit 24 und 32 Dezimalzahlen.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-153">Similarly, 192-bit and 256-bit keys correspond to byte arrays of 24 and 32 decimal numerals, respectively.</span></span>
- <span data-ttu-id="f5ddb-154">Einige Zeichen, z. b. Emoticons, entsprechen mehreren Code Punkten in der Zeichenfolge, in der Sie enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-154">Some characters, such as emoticons, correspond to several code points in the string that contains them.</span></span> <span data-ttu-id="f5ddb-155">Vermeiden Sie die Verwendung dieser Zeichen, da Sie bei der Verwendung in einem Kennwort Probleme und Missverständnisse verursachen können.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-155">Avoid using these characters because they may cause problems and misunderstandings when used in a password.</span></span>

## <span data-ttu-id="f5ddb-156">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f5ddb-156">RELATED LINKS</span></span>

[<span data-ttu-id="f5ddb-157">ConvertTo-SecureString</span><span class="sxs-lookup"><span data-stu-id="f5ddb-157">ConvertTo-SecureString</span></span>](ConvertTo-SecureString.md)

[<span data-ttu-id="f5ddb-158">Read-Host</span><span class="sxs-lookup"><span data-stu-id="f5ddb-158">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)
