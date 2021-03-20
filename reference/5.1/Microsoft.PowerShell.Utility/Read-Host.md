---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/18/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 7f8c8a71657d1d00beb4c6e22159fb2b4ad5dce4
ms.sourcegitcommit: 16a02ae47d1a85b01692101aa0aa6e91e1ba398e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "104726365"
---
# <span data-ttu-id="7cd29-102">Read-Host</span><span class="sxs-lookup"><span data-stu-id="7cd29-102">Read-Host</span></span>

## <span data-ttu-id="7cd29-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="7cd29-103">SYNOPSIS</span></span>
<span data-ttu-id="7cd29-104">Liest eine Zeile von Eingabedaten aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="7cd29-104">Reads a line of input from the console.</span></span>

## <span data-ttu-id="7cd29-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7cd29-105">SYNTAX</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="7cd29-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7cd29-106">DESCRIPTION</span></span>

<span data-ttu-id="7cd29-107">Das- `Read-Host` Cmdlet liest eine Zeile der Eingabe aus der Konsole (stdin).</span><span class="sxs-lookup"><span data-stu-id="7cd29-107">The `Read-Host` cmdlet reads a line of input from the console (stdin).</span></span> <span data-ttu-id="7cd29-108">Damit kann ein Benutzer zur Eingabe aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7cd29-108">You can use it to prompt a user for input.</span></span> <span data-ttu-id="7cd29-109">Da Sie die Eingabe als sichere Zeichenfolge speichern können, können Sie dieses Cmdlet verwenden, um Benutzer zur Eingabe von sicheren Daten, z. b. Kenn Wörtern, aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="7cd29-109">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords.</span></span>

> [!NOTE]
> <span data-ttu-id="7cd29-110">`Read-Host` hat ein Limit von 8190 Zeichen, das als Eingabe eines Benutzers akzeptiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7cd29-110">`Read-Host` has a limit of 8190 characters it can accept as input from a user.</span></span>

## <span data-ttu-id="7cd29-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="7cd29-111">EXAMPLES</span></span>

### <span data-ttu-id="7cd29-112">Beispiel 1: Speichern der Konsolen Eingabe in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="7cd29-112">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="7cd29-113">In diesem Beispiel wird die Zeichenfolge "Bitte geben Sie Ihr Alter:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7cd29-113">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="7cd29-114">Wenn ein Wert eingegeben und die EINGABETASTE gedrückt wird, wird der Wert in der Variablen gespeichert `$Age` .</span><span class="sxs-lookup"><span data-stu-id="7cd29-114">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="7cd29-115">Beispiel 2: Speichern der Konsolen Eingabe als sichere Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7cd29-115">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="7cd29-116">In diesem Beispiel wird die Zeichenfolge "Enter a password:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7cd29-116">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="7cd29-117">Wenn ein Wert eingegeben wird, werden `*` in der Konsole Sternchen () anstelle der Eingabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7cd29-117">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="7cd29-118">Wenn die EINGABETASTE gedrückt wird, wird der Wert als **SecureString** -Objekt in der `$pwd_secure_string` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7cd29-118">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## <span data-ttu-id="7cd29-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7cd29-119">PARAMETERS</span></span>

### <span data-ttu-id="7cd29-120">-Assecurestring</span><span class="sxs-lookup"><span data-stu-id="7cd29-120">-AsSecureString</span></span>

<span data-ttu-id="7cd29-121">Gibt an, dass das Cmdlet Sternchen ( `*` ) anstelle der Zeichen anzeigt, die vom Benutzer als Eingabe eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7cd29-121">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="7cd29-122">Wenn Sie diesen Parameter verwenden, ist die Ausgabe des `Read-Host` Cmdlets ein **SecureString** -Objekt (**System. Security. SecureString**).</span><span class="sxs-lookup"><span data-stu-id="7cd29-122">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object (**System.Security.SecureString**).</span></span>

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

### <span data-ttu-id="7cd29-123">-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="7cd29-123">-Prompt</span></span>

<span data-ttu-id="7cd29-124">Gibt den Text der Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="7cd29-124">Specifies the text of the prompt.</span></span> <span data-ttu-id="7cd29-125">Geben Sie eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="7cd29-125">Type a string.</span></span> <span data-ttu-id="7cd29-126">Wenn die Zeichenfolge Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="7cd29-126">If the string includes spaces, enclose it in quotation marks.</span></span> <span data-ttu-id="7cd29-127">PowerShell fügt einen Doppelpunkt ( `:` ) an den eingegebenen Text an.</span><span class="sxs-lookup"><span data-stu-id="7cd29-127">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="7cd29-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7cd29-128">CommonParameters</span></span>

<span data-ttu-id="7cd29-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7cd29-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7cd29-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7cd29-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7cd29-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="7cd29-131">INPUTS</span></span>

### <span data-ttu-id="7cd29-132">Keine</span><span class="sxs-lookup"><span data-stu-id="7cd29-132">None</span></span>

<span data-ttu-id="7cd29-133">Dieses Cmdlet akzeptiert keine Eingaben aus der PowerShell-Pipeline.</span><span class="sxs-lookup"><span data-stu-id="7cd29-133">This cmdlet does not accept input from the PowerShell pipeline.</span></span>

## <span data-ttu-id="7cd29-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="7cd29-134">OUTPUTS</span></span>

### <span data-ttu-id="7cd29-135">System. String oder System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="7cd29-135">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="7cd29-136">Wenn der **assecurestring** -Parameter verwendet wird, `Read-Host` gibt eine **SecureString** zurück.</span><span class="sxs-lookup"><span data-stu-id="7cd29-136">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="7cd29-137">Andernfalls wird eine Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7cd29-137">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="7cd29-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="7cd29-138">NOTES</span></span>

<span data-ttu-id="7cd29-139">Dieses Cmdlet liest nur aus dem stdin-Stream des Host Prozesses.</span><span class="sxs-lookup"><span data-stu-id="7cd29-139">This cmdlet only reads from the stdin stream of the host process.</span></span> <span data-ttu-id="7cd29-140">Normalerweise ist der stdin-Stream mit der Tastatur der Host Konsole verbunden.</span><span class="sxs-lookup"><span data-stu-id="7cd29-140">Usually, the stdin stream is connected to the keyboard of the host console.</span></span>

## <span data-ttu-id="7cd29-141">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="7cd29-141">RELATED LINKS</span></span>

[<span data-ttu-id="7cd29-142">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="7cd29-142">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="7cd29-143">Get-Host</span><span class="sxs-lookup"><span data-stu-id="7cd29-143">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="7cd29-144">Write-Host</span><span class="sxs-lookup"><span data-stu-id="7cd29-144">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="7cd29-145">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="7cd29-145">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
