---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: aacc89001373ecc8ef75e630f965a8d807bd4ac3
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "93217919"
---
# <span data-ttu-id="c9ca0-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="c9ca0-103">Read-Host</span></span>

## <span data-ttu-id="c9ca0-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c9ca0-104">SYNOPSIS</span></span>
<span data-ttu-id="c9ca0-105">Liest eine Zeile von Eingabedaten aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="c9ca0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c9ca0-106">SYNTAX</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="c9ca0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c9ca0-107">DESCRIPTION</span></span>

<span data-ttu-id="c9ca0-108">Das `Read-Host` Cmdlet liest eine Zeile der Eingabe aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-108">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="c9ca0-109">Damit kann ein Benutzer zur Eingabe aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-109">You can use it to prompt a user for input.</span></span> <span data-ttu-id="c9ca0-110">Da Sie die Eingabe als sichere Zeichenfolge speichern können, können Sie dieses Cmdlet verwenden, um Benutzer zur Eingabe von sicheren Daten wie Kennwörtern oder freigegebenen Daten aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-110">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="c9ca0-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c9ca0-111">EXAMPLES</span></span>

### <span data-ttu-id="c9ca0-112">Beispiel 1: Speichern der Konsolen Eingabe in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="c9ca0-112">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="c9ca0-113">In diesem Beispiel wird die Zeichenfolge "Bitte geben Sie Ihr Alter:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-113">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="c9ca0-114">Wenn ein Wert eingegeben und die EINGABETASTE gedrückt wird, wird der Wert in der Variablen gespeichert `$Age` .</span><span class="sxs-lookup"><span data-stu-id="c9ca0-114">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="c9ca0-115">Beispiel 2: Speichern der Konsolen Eingabe als sichere Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c9ca0-115">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="c9ca0-116">In diesem Beispiel wird die Zeichenfolge "Enter a password:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-116">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="c9ca0-117">Wenn ein Wert eingegeben wird, werden `*` in der Konsole Sternchen () anstelle der Eingabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-117">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="c9ca0-118">Wenn die EINGABETASTE gedrückt wird, wird der Wert als **SecureString** -Objekt in der `$pwd_secure_string` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-118">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## <span data-ttu-id="c9ca0-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c9ca0-119">PARAMETERS</span></span>

### <span data-ttu-id="c9ca0-120">-Assecurestring</span><span class="sxs-lookup"><span data-stu-id="c9ca0-120">-AsSecureString</span></span>

<span data-ttu-id="c9ca0-121">Gibt an, dass das Cmdlet Sternchen ( `*` ) anstelle der Zeichen anzeigt, die vom Benutzer als Eingabe eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-121">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="c9ca0-122">Wenn Sie diesen Parameter verwenden, ist die Ausgabe des `Read-Host` Cmdlets ein **SecureString** -Objekt ( **System. Security. SecureString** ).</span><span class="sxs-lookup"><span data-stu-id="c9ca0-122">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object ( **System.Security.SecureString** ).</span></span>

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

### <span data-ttu-id="c9ca0-123">-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="c9ca0-123">-Prompt</span></span>

<span data-ttu-id="c9ca0-124">Gibt den Text der Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-124">Specifies the text of the prompt.</span></span>
<span data-ttu-id="c9ca0-125">Geben Sie eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-125">Type a string.</span></span>
<span data-ttu-id="c9ca0-126">Wenn die Zeichenfolge Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-126">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="c9ca0-127">PowerShell fügt einen Doppelpunkt ( `:` ) an den eingegebenen Text an.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-127">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="c9ca0-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c9ca0-128">CommonParameters</span></span>

<span data-ttu-id="c9ca0-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c9ca0-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c9ca0-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c9ca0-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c9ca0-131">INPUTS</span></span>

### <span data-ttu-id="c9ca0-132">Keine</span><span class="sxs-lookup"><span data-stu-id="c9ca0-132">None</span></span>

<span data-ttu-id="c9ca0-133">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-133">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c9ca0-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c9ca0-134">OUTPUTS</span></span>

### <span data-ttu-id="c9ca0-135">System. String oder System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="c9ca0-135">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="c9ca0-136">Wenn der **assecurestring** -Parameter verwendet wird, `Read-Host` gibt eine **SecureString** zurück.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-136">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="c9ca0-137">Andernfalls wird eine Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c9ca0-137">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="c9ca0-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c9ca0-138">NOTES</span></span>

## <span data-ttu-id="c9ca0-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c9ca0-139">RELATED LINKS</span></span>

[<span data-ttu-id="c9ca0-140">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="c9ca0-140">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="c9ca0-141">Get-Host</span><span class="sxs-lookup"><span data-stu-id="c9ca0-141">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="c9ca0-142">Write-Host</span><span class="sxs-lookup"><span data-stu-id="c9ca0-142">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="c9ca0-143">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="c9ca0-143">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
