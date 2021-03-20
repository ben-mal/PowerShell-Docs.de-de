---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/18/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 9635457a7b6afc641e67bd4c9367ea4dfc5c9470
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "104726722"
---
# <span data-ttu-id="c7ed1-102">Read-Host</span><span class="sxs-lookup"><span data-stu-id="c7ed1-102">Read-Host</span></span>

## <span data-ttu-id="c7ed1-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c7ed1-103">SYNOPSIS</span></span>
<span data-ttu-id="c7ed1-104">Liest eine Zeile von Eingabedaten aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-104">Reads a line of input from the console.</span></span>

## <span data-ttu-id="c7ed1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c7ed1-105">SYNTAX</span></span>

### <span data-ttu-id="c7ed1-106">AsString (Standard)</span><span class="sxs-lookup"><span data-stu-id="c7ed1-106">AsString (Default)</span></span>

```
Read-Host [[-Prompt] <Object>] [-MaskInput] [<CommonParameters>]
```

### <span data-ttu-id="c7ed1-107">AsSecureString</span><span class="sxs-lookup"><span data-stu-id="c7ed1-107">AsSecureString</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="c7ed1-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c7ed1-108">DESCRIPTION</span></span>

<span data-ttu-id="c7ed1-109">Das- `Read-Host` Cmdlet liest eine Zeile der Eingabe aus der Konsole (stdin).</span><span class="sxs-lookup"><span data-stu-id="c7ed1-109">The `Read-Host` cmdlet reads a line of input from the console (stdin).</span></span> <span data-ttu-id="c7ed1-110">Damit kann ein Benutzer zur Eingabe aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-110">You can use it to prompt a user for input.</span></span> <span data-ttu-id="c7ed1-111">Da Sie die Eingabe als sichere Zeichenfolge speichern können, können Sie dieses Cmdlet verwenden, um Benutzer zur Eingabe von sicheren Daten, z. b. Kenn Wörtern, aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-111">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords.</span></span>

> [!NOTE]
> <span data-ttu-id="c7ed1-112">`Read-Host` hat ein Limit von 1022 Zeichen, das als Eingabe eines Benutzers akzeptiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-112">`Read-Host` has a limit of 1022 characters it can accept as input from a user.</span></span>

## <span data-ttu-id="c7ed1-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c7ed1-113">EXAMPLES</span></span>

### <span data-ttu-id="c7ed1-114">Beispiel 1: Speichern der Konsolen Eingabe in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="c7ed1-114">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="c7ed1-115">In diesem Beispiel wird die Zeichenfolge "Bitte geben Sie Ihr Alter:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-115">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="c7ed1-116">Wenn ein Wert eingegeben und die EINGABETASTE gedrückt wird, wird der Wert in der Variablen gespeichert `$Age` .</span><span class="sxs-lookup"><span data-stu-id="c7ed1-116">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="c7ed1-117">Beispiel 2: Speichern der Konsolen Eingabe als sichere Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c7ed1-117">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="c7ed1-118">In diesem Beispiel wird die Zeichenfolge "Enter a password:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-118">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="c7ed1-119">Wenn ein Wert eingegeben wird, werden `*` in der Konsole Sternchen () anstelle der Eingabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-119">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="c7ed1-120">Wenn die EINGABETASTE gedrückt wird, wird der Wert als **SecureString** -Objekt in der `$pwd_secure_string` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-120">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

### <span data-ttu-id="c7ed1-121">Beispiel 3: Maskieren von Eingaben und als nur-Text-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c7ed1-121">Example 3: Mask input and as a plaintext string</span></span>

<span data-ttu-id="c7ed1-122">In diesem Beispiel wird die Zeichenfolge "Enter a password:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-122">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="c7ed1-123">Wenn ein Wert eingegeben wird, werden `*` in der Konsole Sternchen () anstelle der Eingabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-123">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="c7ed1-124">Wenn die EINGABETASTE gedrückt wird, wird der Wert als nur-Text- **Zeichen** folgen Objekt in der `$pwd_string` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-124">When the Enter key is pressed, the value is stored as a plaintext **String** object in the `$pwd_string` variable.</span></span>

```powershell
$pwd_string = Read-Host "Enter a Password" -MaskInput
```

## <span data-ttu-id="c7ed1-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c7ed1-125">PARAMETERS</span></span>

### <span data-ttu-id="c7ed1-126">-Assecurestring</span><span class="sxs-lookup"><span data-stu-id="c7ed1-126">-AsSecureString</span></span>

<span data-ttu-id="c7ed1-127">Gibt an, dass das Cmdlet Sternchen ( `*` ) anstelle der Zeichen anzeigt, die vom Benutzer als Eingabe eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-127">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="c7ed1-128">Wenn Sie diesen Parameter verwenden, ist die Ausgabe des `Read-Host` Cmdlets ein **SecureString** -Objekt (**System. Security. SecureString**).</span><span class="sxs-lookup"><span data-stu-id="c7ed1-128">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object (**System.Security.SecureString**).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsSecureString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7ed1-129">-Maskinput</span><span class="sxs-lookup"><span data-stu-id="c7ed1-129">-MaskInput</span></span>

<span data-ttu-id="c7ed1-130">Gibt an, dass das Cmdlet Sternchen ( `*` ) anstelle der Zeichen anzeigt, die vom Benutzer als Eingabe eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-130">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="c7ed1-131">Wenn Sie diesen Parameter verwenden, ist die Ausgabe des `Read-Host` Cmdlets ein **Zeichen** folgen Objekt.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-131">When you use this parameter, the output of the `Read-Host` cmdlet is a **String** object.</span></span>
<span data-ttu-id="c7ed1-132">Dies ermöglicht es Ihnen, sicher ein Kennwort einzugeben, das als Klartext anstelle von **SecureString** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-132">This allows you to safely prompt for a password that is returned as plaintext instead of **SecureString**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7ed1-133">-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="c7ed1-133">-Prompt</span></span>

<span data-ttu-id="c7ed1-134">Gibt den Text der Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-134">Specifies the text of the prompt.</span></span> <span data-ttu-id="c7ed1-135">Geben Sie eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-135">Type a string.</span></span> <span data-ttu-id="c7ed1-136">Wenn die Zeichenfolge Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-136">If the string includes spaces, enclose it in quotation marks.</span></span> <span data-ttu-id="c7ed1-137">PowerShell fügt einen Doppelpunkt ( `:` ) an den eingegebenen Text an.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-137">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c7ed1-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c7ed1-138">CommonParameters</span></span>

<span data-ttu-id="c7ed1-139">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c7ed1-140">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c7ed1-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c7ed1-141">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c7ed1-141">INPUTS</span></span>

### <span data-ttu-id="c7ed1-142">Keine</span><span class="sxs-lookup"><span data-stu-id="c7ed1-142">None</span></span>

<span data-ttu-id="c7ed1-143">Dieses Cmdlet akzeptiert keine Eingaben aus der PowerShell-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-143">This cmdlet does not accept input from the PowerShell pipeline.</span></span>

## <span data-ttu-id="c7ed1-144">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c7ed1-144">OUTPUTS</span></span>

### <span data-ttu-id="c7ed1-145">System. String oder System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="c7ed1-145">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="c7ed1-146">Wenn der **assecurestring** -Parameter verwendet wird, `Read-Host` gibt eine **SecureString** zurück.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-146">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="c7ed1-147">Andernfalls wird eine Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-147">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="c7ed1-148">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c7ed1-148">NOTES</span></span>

<span data-ttu-id="c7ed1-149">Dieses Cmdlet liest nur aus dem stdin-Stream des Host Prozesses.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-149">This cmdlet only reads from the stdin stream of the host process.</span></span> <span data-ttu-id="c7ed1-150">Normalerweise ist der stdin-Stream mit der Tastatur der Host Konsole verbunden.</span><span class="sxs-lookup"><span data-stu-id="c7ed1-150">Usually, the stdin stream is connected to the keyboard of the host console.</span></span>

## <span data-ttu-id="c7ed1-151">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c7ed1-151">RELATED LINKS</span></span>

[<span data-ttu-id="c7ed1-152">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="c7ed1-152">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="c7ed1-153">Get-Host</span><span class="sxs-lookup"><span data-stu-id="c7ed1-153">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="c7ed1-154">Write-Host</span><span class="sxs-lookup"><span data-stu-id="c7ed1-154">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="c7ed1-155">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="c7ed1-155">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
