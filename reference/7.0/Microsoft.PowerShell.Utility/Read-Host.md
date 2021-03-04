---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 4f5a5705c726aef7150b734a6265308a5915decb
ms.sourcegitcommit: 1dfd5554b70c7e8f4e3df19e29c384a9c0a4b227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "101685601"
---
# <span data-ttu-id="c5604-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="c5604-103">Read-Host</span></span>

## <span data-ttu-id="c5604-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c5604-104">SYNOPSIS</span></span>
<span data-ttu-id="c5604-105">Liest eine Zeile von Eingabedaten aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="c5604-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="c5604-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5604-106">SYNTAX</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="c5604-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c5604-107">DESCRIPTION</span></span>

<span data-ttu-id="c5604-108">Das `Read-Host` Cmdlet liest eine Zeile der Eingabe aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="c5604-108">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="c5604-109">Damit kann ein Benutzer zur Eingabe aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c5604-109">You can use it to prompt a user for input.</span></span> <span data-ttu-id="c5604-110">Da Sie die Eingabe als sichere Zeichenfolge speichern können, können Sie dieses Cmdlet verwenden, um Benutzer zur Eingabe von sicheren Daten wie Kennwörtern oder freigegebenen Daten aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="c5604-110">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

> [!NOTE]
> <span data-ttu-id="c5604-111">`Read-Host` hat ein Limit von 1022 Zeichen, das als Eingabe eines Benutzers akzeptiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c5604-111">`Read-Host` has a limit of 1022 characters it can accept as input from a user.</span></span>

## <span data-ttu-id="c5604-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c5604-112">EXAMPLES</span></span>

### <span data-ttu-id="c5604-113">Beispiel 1: Speichern der Konsolen Eingabe in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="c5604-113">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="c5604-114">In diesem Beispiel wird die Zeichenfolge "Bitte geben Sie Ihr Alter:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5604-114">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="c5604-115">Wenn ein Wert eingegeben und die EINGABETASTE gedrückt wird, wird der Wert in der Variablen gespeichert `$Age` .</span><span class="sxs-lookup"><span data-stu-id="c5604-115">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="c5604-116">Beispiel 2: Speichern der Konsolen Eingabe als sichere Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c5604-116">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="c5604-117">In diesem Beispiel wird die Zeichenfolge "Enter a password:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5604-117">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="c5604-118">Wenn ein Wert eingegeben wird, werden `*` in der Konsole Sternchen () anstelle der Eingabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5604-118">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="c5604-119">Wenn die EINGABETASTE gedrückt wird, wird der Wert als **SecureString** -Objekt in der `$pwd_secure_string` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c5604-119">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## <span data-ttu-id="c5604-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5604-120">PARAMETERS</span></span>

### <span data-ttu-id="c5604-121">-Assecurestring</span><span class="sxs-lookup"><span data-stu-id="c5604-121">-AsSecureString</span></span>

<span data-ttu-id="c5604-122">Gibt an, dass das Cmdlet Sternchen ( `*` ) anstelle der Zeichen anzeigt, die vom Benutzer als Eingabe eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c5604-122">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="c5604-123">Wenn Sie diesen Parameter verwenden, ist die Ausgabe des `Read-Host` Cmdlets ein **SecureString** -Objekt (**System. Security. SecureString**).</span><span class="sxs-lookup"><span data-stu-id="c5604-123">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object (**System.Security.SecureString**).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5604-124">-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="c5604-124">-Prompt</span></span>

<span data-ttu-id="c5604-125">Gibt den Text der Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="c5604-125">Specifies the text of the prompt.</span></span> <span data-ttu-id="c5604-126">Geben Sie eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="c5604-126">Type a string.</span></span> <span data-ttu-id="c5604-127">Wenn die Zeichenfolge Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="c5604-127">If the string includes spaces, enclose it in quotation marks.</span></span> <span data-ttu-id="c5604-128">PowerShell fügt einen Doppelpunkt ( `:` ) an den eingegebenen Text an.</span><span class="sxs-lookup"><span data-stu-id="c5604-128">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="c5604-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c5604-129">CommonParameters</span></span>

<span data-ttu-id="c5604-130">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c5604-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5604-131">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c5604-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c5604-132">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c5604-132">INPUTS</span></span>

### <span data-ttu-id="c5604-133">Keine</span><span class="sxs-lookup"><span data-stu-id="c5604-133">None</span></span>

<span data-ttu-id="c5604-134">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="c5604-134">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c5604-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c5604-135">OUTPUTS</span></span>

### <span data-ttu-id="c5604-136">System. String oder System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="c5604-136">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="c5604-137">Wenn der **assecurestring** -Parameter verwendet wird, `Read-Host` gibt eine **SecureString** zurück.</span><span class="sxs-lookup"><span data-stu-id="c5604-137">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="c5604-138">Andernfalls wird eine Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c5604-138">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="c5604-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c5604-139">NOTES</span></span>

## <span data-ttu-id="c5604-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c5604-140">RELATED LINKS</span></span>

[<span data-ttu-id="c5604-141">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="c5604-141">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="c5604-142">Get-Host</span><span class="sxs-lookup"><span data-stu-id="c5604-142">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="c5604-143">Write-Host</span><span class="sxs-lookup"><span data-stu-id="c5604-143">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="c5604-144">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="c5604-144">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
