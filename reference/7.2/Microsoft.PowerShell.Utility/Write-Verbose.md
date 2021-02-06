---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: 177e32106f37c59593bbecac13843f6603327cc9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604860"
---
# <span data-ttu-id="c93d3-102">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="c93d3-102">Write-Verbose</span></span>

## <span data-ttu-id="c93d3-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c93d3-103">SYNOPSIS</span></span>
<span data-ttu-id="c93d3-104">Schreibt Text in den Stream für ausführliche Meldungen.</span><span class="sxs-lookup"><span data-stu-id="c93d3-104">Writes text to the verbose message stream.</span></span>

## <span data-ttu-id="c93d3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c93d3-105">SYNTAX</span></span>

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="c93d3-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c93d3-106">DESCRIPTION</span></span>

<span data-ttu-id="c93d3-107">Das `Write-Verbose` Cmdlet schreibt Text in den Stream für ausführliche Meldungen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c93d3-107">The `Write-Verbose` cmdlet writes text to the verbose message stream in PowerShell.</span></span> <span data-ttu-id="c93d3-108">In der Regel wird der Stream für ausführliche Meldungen verwendet, um ausführlichere Informationen zur Befehls Verarbeitung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c93d3-108">Typically, the verbose message stream is used to deliver more in depth information about command processing.</span></span>

<span data-ttu-id="c93d3-109">Standardmäßig wird der Stream für ausführliche Meldungen nicht angezeigt. Sie können ihn jedoch anzeigen, indem Sie den Wert der `$VerbosePreference` Variablen ändern oder den allgemeinen **ausführliche** -Parameter in einem beliebigen Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="c93d3-109">By default, the verbose message stream is not displayed, but you can display it by changing the value of the `$VerbosePreference` variable or using the **Verbose** common parameter in any command.</span></span>

## <span data-ttu-id="c93d3-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c93d3-110">EXAMPLES</span></span>

### <span data-ttu-id="c93d3-111">Beispiel 1: Schreiben einer Statusmeldung</span><span class="sxs-lookup"><span data-stu-id="c93d3-111">Example 1: Write a status message</span></span>

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

<span data-ttu-id="c93d3-112">Diese Befehle verwenden das `Write-Verbose` Cmdlet, um eine Statusmeldung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c93d3-112">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="c93d3-113">Standardmäßig wird die Meldung nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c93d3-113">By default, the message is not displayed.</span></span>

<span data-ttu-id="c93d3-114">Der zweite Befehl verwendet den allgemeinen **ausführliche** -Parameter, der alle ausführlichen Meldungen anzeigt, unabhängig vom Wert der `$VerbosePreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="c93d3-114">The second command uses the **Verbose** common parameter, which displays any verbose messages, regardless of the value of the `$VerbosePreference` variable.</span></span>

### <span data-ttu-id="c93d3-115">Beispiel 2: Festlegen $VerbosePreference und Schreiben einer Statusmeldung</span><span class="sxs-lookup"><span data-stu-id="c93d3-115">Example 2: Set $VerbosePreference and write a status message</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

<span data-ttu-id="c93d3-116">Diese Befehle verwenden das `Write-Verbose` Cmdlet, um eine Statusmeldung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c93d3-116">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="c93d3-117">Standardmäßig wird die Meldung nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c93d3-117">By default, the message is not displayed.</span></span>

<span data-ttu-id="c93d3-118">Der erste Befehl weist der Preference-Variablen den Wert Continue zu `$VerbosePreference` .</span><span class="sxs-lookup"><span data-stu-id="c93d3-118">The first command assigns a value of Continue to the `$VerbosePreference` preference variable.</span></span> <span data-ttu-id="c93d3-119">Der Standardwert, `SilentlyContinue` , unterdrückt ausführliche Meldungen.</span><span class="sxs-lookup"><span data-stu-id="c93d3-119">The default value, `SilentlyContinue`, suppresses verbose messages.</span></span> <span data-ttu-id="c93d3-120">Der zweite Befehl schreibt eine ausführliche Meldung.</span><span class="sxs-lookup"><span data-stu-id="c93d3-120">The second command writes a verbose message.</span></span>

## <span data-ttu-id="c93d3-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c93d3-121">PARAMETERS</span></span>

### <span data-ttu-id="c93d3-122">-Meldung</span><span class="sxs-lookup"><span data-stu-id="c93d3-122">-Message</span></span>

<span data-ttu-id="c93d3-123">Gibt die anzuzeigende Meldung an.</span><span class="sxs-lookup"><span data-stu-id="c93d3-123">Specifies the message to display.</span></span> <span data-ttu-id="c93d3-124">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c93d3-124">This parameter is required.</span></span> <span data-ttu-id="c93d3-125">Sie können eine Meldungs Zeichenfolge auch an übergeben `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="c93d3-125">You can also pipe a message string to `Write-Verbose`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c93d3-126">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c93d3-126">CommonParameters</span></span>

<span data-ttu-id="c93d3-127">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c93d3-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c93d3-128">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="c93d3-128">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c93d3-129">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c93d3-129">INPUTS</span></span>

### <span data-ttu-id="c93d3-130">System.String</span><span class="sxs-lookup"><span data-stu-id="c93d3-130">System.String</span></span>

<span data-ttu-id="c93d3-131">Sie können eine Zeichenfolge, die die Meldung enthält, an die Pipeline übergeben `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="c93d3-131">You can pipe a string that contains the message to `Write-Verbose`.</span></span>

## <span data-ttu-id="c93d3-132">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c93d3-132">OUTPUTS</span></span>

### <span data-ttu-id="c93d3-133">Keine</span><span class="sxs-lookup"><span data-stu-id="c93d3-133">None</span></span>

<span data-ttu-id="c93d3-134">`Write-Verbose` schreibt nur in den Stream für ausführliche Meldungen.</span><span class="sxs-lookup"><span data-stu-id="c93d3-134">`Write-Verbose` writes only to the verbose message stream.</span></span>

## <span data-ttu-id="c93d3-135">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c93d3-135">NOTES</span></span>

- <span data-ttu-id="c93d3-136">Ausführliche Meldungen werden nur zurückgegeben, wenn der Befehl den allgemeinen **Verbose**-Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="c93d3-136">Verbose messages are returned only when the command uses the **Verbose** common parameter.</span></span> <span data-ttu-id="c93d3-137">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c93d3-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>
- <span data-ttu-id="c93d3-138">In Windows PowerShell-Hintergrund Aufträgen und Remote Befehlen `$VerbosePreference` bestimmen die Variablen in der Auftrags Sitzung und in der Remote Sitzung, ob die ausführliche Meldung standardmäßig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c93d3-138">In Windows PowerShell background jobs and remote commands, the `$VerbosePreference` variable in the job session and remote session determine whether the verbose message is displayed by default.</span></span>
  <span data-ttu-id="c93d3-139">Weitere Informationen zur- `$VerbosePreference` Variablen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="c93d3-139">For more information about the `$VerbosePreference` variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="c93d3-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c93d3-140">RELATED LINKS</span></span>

[<span data-ttu-id="c93d3-141">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="c93d3-141">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="c93d3-142">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="c93d3-142">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="c93d3-143">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="c93d3-143">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="c93d3-144">Write-Error</span><span class="sxs-lookup"><span data-stu-id="c93d3-144">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="c93d3-145">Write-Host</span><span class="sxs-lookup"><span data-stu-id="c93d3-145">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="c93d3-146">Write-Information</span><span class="sxs-lookup"><span data-stu-id="c93d3-146">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="c93d3-147">Write-Output</span><span class="sxs-lookup"><span data-stu-id="c93d3-147">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="c93d3-148">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="c93d3-148">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="c93d3-149">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="c93d3-149">Write-Warning</span></span>](Write-Warning.md)
