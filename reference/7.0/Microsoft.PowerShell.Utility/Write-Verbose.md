---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: 34e8d6edd7199921254a3835a9f13b6331c2d26e
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224383"
---
# <span data-ttu-id="a31c6-103">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="a31c6-103">Write-Verbose</span></span>

## <span data-ttu-id="a31c6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a31c6-104">SYNOPSIS</span></span>
<span data-ttu-id="a31c6-105">Schreibt Text in den Stream für ausführliche Meldungen.</span><span class="sxs-lookup"><span data-stu-id="a31c6-105">Writes text to the verbose message stream.</span></span>

## <span data-ttu-id="a31c6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a31c6-106">SYNTAX</span></span>

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="a31c6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a31c6-107">DESCRIPTION</span></span>

<span data-ttu-id="a31c6-108">Das `Write-Verbose` Cmdlet schreibt Text in den Stream für ausführliche Meldungen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a31c6-108">The `Write-Verbose` cmdlet writes text to the verbose message stream in PowerShell.</span></span> <span data-ttu-id="a31c6-109">In der Regel wird der Stream für ausführliche Meldungen verwendet, um ausführlichere Informationen zur Befehls Verarbeitung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a31c6-109">Typically, the verbose message stream is used to deliver more in depth information about command processing.</span></span>

<span data-ttu-id="a31c6-110">Standardmäßig wird der Stream für ausführliche Meldungen nicht angezeigt. Sie können ihn jedoch anzeigen, indem Sie den Wert der `$VerbosePreference` Variablen ändern oder den allgemeinen **ausführliche** -Parameter in einem beliebigen Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="a31c6-110">By default, the verbose message stream is not displayed, but you can display it by changing the value of the `$VerbosePreference` variable or using the **Verbose** common parameter in any command.</span></span>

## <span data-ttu-id="a31c6-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a31c6-111">EXAMPLES</span></span>

### <span data-ttu-id="a31c6-112">Beispiel 1: Schreiben einer Statusmeldung</span><span class="sxs-lookup"><span data-stu-id="a31c6-112">Example 1: Write a status message</span></span>

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

<span data-ttu-id="a31c6-113">Diese Befehle verwenden das `Write-Verbose` Cmdlet, um eine Statusmeldung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a31c6-113">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="a31c6-114">Standardmäßig wird die Meldung nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a31c6-114">By default, the message is not displayed.</span></span>

<span data-ttu-id="a31c6-115">Der zweite Befehl verwendet den allgemeinen **ausführliche** -Parameter, der alle ausführlichen Meldungen anzeigt, unabhängig vom Wert der `$VerbosePreference` Variablen.</span><span class="sxs-lookup"><span data-stu-id="a31c6-115">The second command uses the **Verbose** common parameter, which displays any verbose messages, regardless of the value of the `$VerbosePreference` variable.</span></span>

### <span data-ttu-id="a31c6-116">Beispiel 2: Festlegen $VerbosePreference und Schreiben einer Statusmeldung</span><span class="sxs-lookup"><span data-stu-id="a31c6-116">Example 2: Set $VerbosePreference and write a status message</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

<span data-ttu-id="a31c6-117">Diese Befehle verwenden das `Write-Verbose` Cmdlet, um eine Statusmeldung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a31c6-117">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="a31c6-118">Standardmäßig wird die Meldung nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a31c6-118">By default, the message is not displayed.</span></span>

<span data-ttu-id="a31c6-119">Der erste Befehl weist der Preference-Variablen den Wert Continue zu `$VerbosePreference` .</span><span class="sxs-lookup"><span data-stu-id="a31c6-119">The first command assigns a value of Continue to the `$VerbosePreference` preference variable.</span></span> <span data-ttu-id="a31c6-120">Der Standardwert, `SilentlyContinue` , unterdrückt ausführliche Meldungen.</span><span class="sxs-lookup"><span data-stu-id="a31c6-120">The default value, `SilentlyContinue`, suppresses verbose messages.</span></span> <span data-ttu-id="a31c6-121">Der zweite Befehl schreibt eine ausführliche Meldung.</span><span class="sxs-lookup"><span data-stu-id="a31c6-121">The second command writes a verbose message.</span></span>

## <span data-ttu-id="a31c6-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a31c6-122">PARAMETERS</span></span>

### <span data-ttu-id="a31c6-123">-Meldung</span><span class="sxs-lookup"><span data-stu-id="a31c6-123">-Message</span></span>

<span data-ttu-id="a31c6-124">Gibt die anzuzeigende Meldung an.</span><span class="sxs-lookup"><span data-stu-id="a31c6-124">Specifies the message to display.</span></span> <span data-ttu-id="a31c6-125">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a31c6-125">This parameter is required.</span></span> <span data-ttu-id="a31c6-126">Sie können eine Meldungs Zeichenfolge auch an übergeben `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="a31c6-126">You can also pipe a message string to `Write-Verbose`.</span></span>

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

### <span data-ttu-id="a31c6-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a31c6-127">CommonParameters</span></span>

<span data-ttu-id="a31c6-128">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a31c6-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a31c6-129">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a31c6-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a31c6-130">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a31c6-130">INPUTS</span></span>

### <span data-ttu-id="a31c6-131">System.String</span><span class="sxs-lookup"><span data-stu-id="a31c6-131">System.String</span></span>

<span data-ttu-id="a31c6-132">Sie können eine Zeichenfolge, die die Meldung enthält, an die Pipeline übergeben `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="a31c6-132">You can pipe a string that contains the message to `Write-Verbose`.</span></span>

## <span data-ttu-id="a31c6-133">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a31c6-133">OUTPUTS</span></span>

### <span data-ttu-id="a31c6-134">Keine</span><span class="sxs-lookup"><span data-stu-id="a31c6-134">None</span></span>

<span data-ttu-id="a31c6-135">`Write-Verbose` schreibt nur in den Stream für ausführliche Meldungen.</span><span class="sxs-lookup"><span data-stu-id="a31c6-135">`Write-Verbose` writes only to the verbose message stream.</span></span>

## <span data-ttu-id="a31c6-136">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a31c6-136">NOTES</span></span>

- <span data-ttu-id="a31c6-137">Ausführliche Meldungen werden nur zurückgegeben, wenn der Befehl den allgemeinen **Verbose** -Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="a31c6-137">Verbose messages are returned only when the command uses the **Verbose** common parameter.</span></span> <span data-ttu-id="a31c6-138">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a31c6-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>
- <span data-ttu-id="a31c6-139">In Windows PowerShell-Hintergrund Aufträgen und Remote Befehlen `$VerbosePreference` bestimmen die Variablen in der Auftrags Sitzung und in der Remote Sitzung, ob die ausführliche Meldung standardmäßig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a31c6-139">In Windows PowerShell background jobs and remote commands, the `$VerbosePreference` variable in the job session and remote session determine whether the verbose message is displayed by default.</span></span>
  <span data-ttu-id="a31c6-140">Weitere Informationen zur- `$VerbosePreference` Variablen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a31c6-140">For more information about the `$VerbosePreference` variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="a31c6-141">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a31c6-141">RELATED LINKS</span></span>

[<span data-ttu-id="a31c6-142">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="a31c6-142">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="a31c6-143">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="a31c6-143">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="a31c6-144">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="a31c6-144">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="a31c6-145">Schreibfehler</span><span class="sxs-lookup"><span data-stu-id="a31c6-145">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="a31c6-146">Write-Host</span><span class="sxs-lookup"><span data-stu-id="a31c6-146">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="a31c6-147">Write-Information</span><span class="sxs-lookup"><span data-stu-id="a31c6-147">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="a31c6-148">Write-Output</span><span class="sxs-lookup"><span data-stu-id="a31c6-148">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="a31c6-149">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="a31c6-149">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="a31c6-150">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="a31c6-150">Write-Warning</span></span>](Write-Warning.md)
