---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 2efe75730ef7d35618dc0d1fbf7a8d6f8a5db5ae
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605368"
---
# <span data-ttu-id="4c257-102">Read-Host</span><span class="sxs-lookup"><span data-stu-id="4c257-102">Read-Host</span></span>

## <span data-ttu-id="4c257-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4c257-103">SYNOPSIS</span></span>
<span data-ttu-id="4c257-104">Liest eine Zeile von Eingabedaten aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="4c257-104">Reads a line of input from the console.</span></span>

## <span data-ttu-id="4c257-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c257-105">SYNTAX</span></span>

### <span data-ttu-id="4c257-106">AsString (Standard)</span><span class="sxs-lookup"><span data-stu-id="4c257-106">AsString (Default)</span></span>

```
Read-Host [[-Prompt] <Object>] [-MaskInput] [<CommonParameters>]
```

### <span data-ttu-id="4c257-107">AsSecureString</span><span class="sxs-lookup"><span data-stu-id="4c257-107">AsSecureString</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="4c257-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c257-108">DESCRIPTION</span></span>

<span data-ttu-id="4c257-109">Das `Read-Host` Cmdlet liest eine Zeile der Eingabe aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="4c257-109">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="4c257-110">Damit kann ein Benutzer zur Eingabe aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4c257-110">You can use it to prompt a user for input.</span></span> <span data-ttu-id="4c257-111">Da Sie die Eingabe als sichere Zeichenfolge speichern können, können Sie dieses Cmdlet verwenden, um Benutzer zur Eingabe von sicheren Daten wie Kennwörtern oder freigegebenen Daten aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="4c257-111">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="4c257-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4c257-112">EXAMPLES</span></span>

### <span data-ttu-id="4c257-113">Beispiel 1: Speichern der Konsolen Eingabe in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="4c257-113">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="4c257-114">In diesem Beispiel wird die Zeichenfolge "Bitte geben Sie Ihr Alter:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c257-114">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="4c257-115">Wenn ein Wert eingegeben und die EINGABETASTE gedrückt wird, wird der Wert in der Variablen gespeichert `$Age` .</span><span class="sxs-lookup"><span data-stu-id="4c257-115">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="4c257-116">Beispiel 2: Speichern der Konsolen Eingabe als sichere Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4c257-116">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="4c257-117">In diesem Beispiel wird die Zeichenfolge "Enter a password:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c257-117">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="4c257-118">Wenn ein Wert eingegeben wird, werden `*` in der Konsole Sternchen () anstelle der Eingabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c257-118">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="4c257-119">Wenn die EINGABETASTE gedrückt wird, wird der Wert als **SecureString** -Objekt in der `$pwd_secure_string` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4c257-119">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

### <span data-ttu-id="4c257-120">Beispiel 3: Maskieren von Eingaben und als nur-Text-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4c257-120">Example 3: Mask input and as a plaintext string</span></span>

<span data-ttu-id="4c257-121">In diesem Beispiel wird die Zeichenfolge "Enter a password:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c257-121">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="4c257-122">Wenn ein Wert eingegeben wird, werden `*` in der Konsole Sternchen () anstelle der Eingabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c257-122">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="4c257-123">Wenn die EINGABETASTE gedrückt wird, wird der Wert als nur-Text- **Zeichen** folgen Objekt in der `$pwd_string` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4c257-123">When the Enter key is pressed, the value is stored as a plaintext **String** object in the `$pwd_string` variable.</span></span>

```powershell
$pwd_string = Read-Host "Enter a Password" -MaskInput
```

## <span data-ttu-id="4c257-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c257-124">PARAMETERS</span></span>

### <span data-ttu-id="4c257-125">-Assecurestring</span><span class="sxs-lookup"><span data-stu-id="4c257-125">-AsSecureString</span></span>

<span data-ttu-id="4c257-126">Gibt an, dass das Cmdlet Sternchen ( `*` ) anstelle der Zeichen anzeigt, die vom Benutzer als Eingabe eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4c257-126">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="4c257-127">Wenn Sie diesen Parameter verwenden, ist die Ausgabe des `Read-Host` Cmdlets ein **SecureString** -Objekt (**System. Security. SecureString**).</span><span class="sxs-lookup"><span data-stu-id="4c257-127">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object (**System.Security.SecureString**).</span></span>

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

### <span data-ttu-id="4c257-128">-Maskinput</span><span class="sxs-lookup"><span data-stu-id="4c257-128">-MaskInput</span></span>

<span data-ttu-id="4c257-129">Gibt an, dass das Cmdlet Sternchen ( `*` ) anstelle der Zeichen anzeigt, die vom Benutzer als Eingabe eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4c257-129">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="4c257-130">Wenn Sie diesen Parameter verwenden, ist die Ausgabe des `Read-Host` Cmdlets ein **Zeichen** folgen Objekt.</span><span class="sxs-lookup"><span data-stu-id="4c257-130">When you use this parameter, the output of the `Read-Host` cmdlet is a **String** object.</span></span>
<span data-ttu-id="4c257-131">Dies ermöglicht es Ihnen, sicher ein Kennwort einzugeben, das als Klartext anstelle von **SecureString** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4c257-131">This allows you to safely prompt for a password that is returned as plaintext instead of **SecureString**.</span></span>

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

### <span data-ttu-id="4c257-132">-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="4c257-132">-Prompt</span></span>

<span data-ttu-id="4c257-133">Gibt den Text der Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="4c257-133">Specifies the text of the prompt.</span></span>
<span data-ttu-id="4c257-134">Geben Sie eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="4c257-134">Type a string.</span></span>
<span data-ttu-id="4c257-135">Wenn die Zeichenfolge Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="4c257-135">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="4c257-136">PowerShell fügt einen Doppelpunkt ( `:` ) an den eingegebenen Text an.</span><span class="sxs-lookup"><span data-stu-id="4c257-136">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="4c257-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4c257-137">CommonParameters</span></span>

<span data-ttu-id="4c257-138">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c257-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c257-139">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c257-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c257-140">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4c257-140">INPUTS</span></span>

### <span data-ttu-id="4c257-141">Keine</span><span class="sxs-lookup"><span data-stu-id="4c257-141">None</span></span>

<span data-ttu-id="4c257-142">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="4c257-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4c257-143">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4c257-143">OUTPUTS</span></span>

### <span data-ttu-id="4c257-144">System. String oder System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="4c257-144">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="4c257-145">Wenn der **assecurestring** -Parameter verwendet wird, `Read-Host` gibt eine **SecureString** zurück.</span><span class="sxs-lookup"><span data-stu-id="4c257-145">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="4c257-146">Andernfalls wird eine Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4c257-146">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="4c257-147">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4c257-147">NOTES</span></span>

## <span data-ttu-id="4c257-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4c257-148">RELATED LINKS</span></span>

[<span data-ttu-id="4c257-149">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="4c257-149">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="4c257-150">Get-Host</span><span class="sxs-lookup"><span data-stu-id="4c257-150">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="4c257-151">Write-Host</span><span class="sxs-lookup"><span data-stu-id="4c257-151">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="4c257-152">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="4c257-152">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
