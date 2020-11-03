---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/read-host?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Read-Host
ms.openlocfilehash: 8e0c1057a4117eb60cdc8ec494470dacaca78699
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "93217932"
---
# <span data-ttu-id="97f53-103">Read-Host</span><span class="sxs-lookup"><span data-stu-id="97f53-103">Read-Host</span></span>

## <span data-ttu-id="97f53-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="97f53-104">SYNOPSIS</span></span>
<span data-ttu-id="97f53-105">Liest eine Zeile von Eingabedaten aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="97f53-105">Reads a line of input from the console.</span></span>

## <span data-ttu-id="97f53-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="97f53-106">SYNTAX</span></span>

```
Read-Host [[-Prompt] <Object>] [-AsSecureString] [<CommonParameters>]
```

## <span data-ttu-id="97f53-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="97f53-107">DESCRIPTION</span></span>

<span data-ttu-id="97f53-108">Das `Read-Host` Cmdlet liest eine Zeile der Eingabe aus der Konsole.</span><span class="sxs-lookup"><span data-stu-id="97f53-108">The `Read-Host` cmdlet reads a line of input from the console.</span></span> <span data-ttu-id="97f53-109">Damit kann ein Benutzer zur Eingabe aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="97f53-109">You can use it to prompt a user for input.</span></span> <span data-ttu-id="97f53-110">Da Sie die Eingabe als sichere Zeichenfolge speichern können, können Sie dieses Cmdlet verwenden, um Benutzer zur Eingabe von sicheren Daten wie Kennwörtern oder freigegebenen Daten aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="97f53-110">Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords, as well as shared data.</span></span>

## <span data-ttu-id="97f53-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="97f53-111">EXAMPLES</span></span>

### <span data-ttu-id="97f53-112">Beispiel 1: Speichern der Konsolen Eingabe in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="97f53-112">Example 1: Save console input to a variable</span></span>

<span data-ttu-id="97f53-113">In diesem Beispiel wird die Zeichenfolge "Bitte geben Sie Ihr Alter:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97f53-113">This example displays the string "Please enter your age:" as a prompt.</span></span> <span data-ttu-id="97f53-114">Wenn ein Wert eingegeben und die EINGABETASTE gedrückt wird, wird der Wert in der Variablen gespeichert `$Age` .</span><span class="sxs-lookup"><span data-stu-id="97f53-114">When a value is entered and the Enter key is pressed, the value is stored in the `$Age` variable.</span></span>

```powershell
$Age = Read-Host "Please enter your age"
```

### <span data-ttu-id="97f53-115">Beispiel 2: Speichern der Konsolen Eingabe als sichere Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="97f53-115">Example 2: Save console input as a secure string</span></span>

<span data-ttu-id="97f53-116">In diesem Beispiel wird die Zeichenfolge "Enter a password:" als Eingabeaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97f53-116">This example displays the string "Enter a Password:" as a prompt.</span></span> <span data-ttu-id="97f53-117">Wenn ein Wert eingegeben wird, werden `*` in der Konsole Sternchen () anstelle der Eingabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97f53-117">As a value is being entered, asterisks (`*`) appear on the console in place of the input.</span></span> <span data-ttu-id="97f53-118">Wenn die EINGABETASTE gedrückt wird, wird der Wert als **SecureString** -Objekt in der `$pwd_secure_string` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="97f53-118">When the Enter key is pressed, the value is stored as a **SecureString** object in the `$pwd_secure_string` variable.</span></span>

```powershell
$pwd_secure_string = Read-Host "Enter a Password" -AsSecureString
```

## <span data-ttu-id="97f53-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="97f53-119">PARAMETERS</span></span>

### <span data-ttu-id="97f53-120">-Assecurestring</span><span class="sxs-lookup"><span data-stu-id="97f53-120">-AsSecureString</span></span>

<span data-ttu-id="97f53-121">Gibt an, dass das Cmdlet Sternchen ( `*` ) anstelle der Zeichen anzeigt, die vom Benutzer als Eingabe eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="97f53-121">Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input.</span></span> <span data-ttu-id="97f53-122">Wenn Sie diesen Parameter verwenden, ist die Ausgabe des `Read-Host` Cmdlets ein **SecureString** -Objekt ( **System. Security. SecureString** ).</span><span class="sxs-lookup"><span data-stu-id="97f53-122">When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** object ( **System.Security.SecureString** ).</span></span>

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

### <span data-ttu-id="97f53-123">-Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="97f53-123">-Prompt</span></span>

<span data-ttu-id="97f53-124">Gibt den Text der Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="97f53-124">Specifies the text of the prompt.</span></span>
<span data-ttu-id="97f53-125">Geben Sie eine Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="97f53-125">Type a string.</span></span>
<span data-ttu-id="97f53-126">Wenn die Zeichenfolge Leerzeichen enthält, müssen Sie sie in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="97f53-126">If the string includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="97f53-127">PowerShell fügt einen Doppelpunkt ( `:` ) an den eingegebenen Text an.</span><span class="sxs-lookup"><span data-stu-id="97f53-127">PowerShell appends a colon (`:`) to the text that you enter.</span></span>

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

### <span data-ttu-id="97f53-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="97f53-128">CommonParameters</span></span>

<span data-ttu-id="97f53-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="97f53-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="97f53-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="97f53-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="97f53-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="97f53-131">INPUTS</span></span>

### <span data-ttu-id="97f53-132">Keine</span><span class="sxs-lookup"><span data-stu-id="97f53-132">None</span></span>

<span data-ttu-id="97f53-133">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="97f53-133">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="97f53-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="97f53-134">OUTPUTS</span></span>

### <span data-ttu-id="97f53-135">System. String oder System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="97f53-135">System.String or System.Security.SecureString</span></span>

<span data-ttu-id="97f53-136">Wenn der **assecurestring** -Parameter verwendet wird, `Read-Host` gibt eine **SecureString** zurück.</span><span class="sxs-lookup"><span data-stu-id="97f53-136">If the **AsSecureString** parameter is used, `Read-Host` returns a **SecureString**.</span></span> <span data-ttu-id="97f53-137">Andernfalls wird eine Zeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="97f53-137">Otherwise, it returns a string.</span></span>

## <span data-ttu-id="97f53-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="97f53-138">NOTES</span></span>

## <span data-ttu-id="97f53-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="97f53-139">RELATED LINKS</span></span>

[<span data-ttu-id="97f53-140">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="97f53-140">Clear-Host</span></span>](../microsoft.powershell.core/clear-host.md)

[<span data-ttu-id="97f53-141">Get-Host</span><span class="sxs-lookup"><span data-stu-id="97f53-141">Get-Host</span></span>](Get-Host.md)

[<span data-ttu-id="97f53-142">Write-Host</span><span class="sxs-lookup"><span data-stu-id="97f53-142">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="97f53-143">ConvertFrom-SecureString</span><span class="sxs-lookup"><span data-stu-id="97f53-143">ConvertFrom-SecureString</span></span>](../Microsoft.PowerShell.Security/ConvertFrom-SecureString.md)
