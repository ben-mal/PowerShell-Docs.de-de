---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-warning?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Warning
ms.openlocfilehash: 5553f61038c10d0c7c251609f729d157c53b03b9
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224212"
---
# <span data-ttu-id="45c63-103">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="45c63-103">Write-Warning</span></span>

## <span data-ttu-id="45c63-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="45c63-104">SYNOPSIS</span></span>
<span data-ttu-id="45c63-105">Schreibt eine Warnmeldung.</span><span class="sxs-lookup"><span data-stu-id="45c63-105">Writes a warning message.</span></span>

## <span data-ttu-id="45c63-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="45c63-106">SYNTAX</span></span>

```
Write-Warning [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="45c63-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="45c63-107">DESCRIPTION</span></span>

<span data-ttu-id="45c63-108">Mit dem- `Write-Warning` Cmdlet wird eine Warnmeldung in den PowerShell-Host geschrieben.</span><span class="sxs-lookup"><span data-stu-id="45c63-108">The `Write-Warning` cmdlet writes a warning message to the PowerShell host.</span></span> <span data-ttu-id="45c63-109">Die Antwort auf die Warnung hängt vom Wert der Variablen des Benutzers `$WarningPreference` und der Verwendung des allgemeinen **WarningAction** -Parameters ab.</span><span class="sxs-lookup"><span data-stu-id="45c63-109">The response to the warning depends on the value of the user's `$WarningPreference` variable and the use of the **WarningAction** common parameter.</span></span>

## <span data-ttu-id="45c63-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="45c63-110">EXAMPLES</span></span>

### <span data-ttu-id="45c63-111">Beispiel 1: Schreiben einer Warnmeldung</span><span class="sxs-lookup"><span data-stu-id="45c63-111">Example 1: Write a warning message</span></span>

<span data-ttu-id="45c63-112">Mit diesem Befehl wird die Meldung "Warnung: Dies ist nur eine Test Warnung" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45c63-112">This command displays the message "WARNING: This is only a test warning."</span></span>

```powershell
Write-Warning "This is only a test warning."
```

### <span data-ttu-id="45c63-113">Beispiel 2: übergeben einer Zeichenfolge an Write-Warning</span><span class="sxs-lookup"><span data-stu-id="45c63-113">Example 2: Pass a string to Write-Warning</span></span>

<span data-ttu-id="45c63-114">Dieser Befehl zeigt, dass Sie einen Pipeline Operator () verwenden können, um `|` eine Zeichenfolge an zu senden `Write-Warning` .</span><span class="sxs-lookup"><span data-stu-id="45c63-114">This command shows that you can use a pipeline operator (`|`) to send a string to `Write-Warning`.</span></span>
<span data-ttu-id="45c63-115">Sie können die Zeichenfolge in einer Variablen speichern, wie in diesem Befehl gezeigt, oder die Zeichenfolge direkt an die Pipeline übergeben `Write-Warning` .</span><span class="sxs-lookup"><span data-stu-id="45c63-115">You can save the string in a variable, as shown in this command, or pipe the string directly to `Write-Warning`.</span></span>

```powershell
$w = "This is only a test warning."
$w | Write-Warning
```

### <span data-ttu-id="45c63-116">Beispiel 3: Festlegen der $WarningPreference Variable und Schreiben einer Warnung</span><span class="sxs-lookup"><span data-stu-id="45c63-116">Example 3: Set the $WarningPreference variable and write a warning</span></span>

<span data-ttu-id="45c63-117">Dieses Beispiel zeigt die Auswirkung des Werts der `$WarningPreference` Variablen in einem `Write-Warning` Befehl.</span><span class="sxs-lookup"><span data-stu-id="45c63-117">This example shows the effect of the value of the `$WarningPreference` variable on a `Write-Warning` command.</span></span>

```powershell
PS> $WarningPreference
Continue
PS> Write-Warning "This is only a test warning."
This is only a test warning.
PS> $WarningPreference = "SilentlyContinue"
PS> Write-Warning "This is only a test warning."
PS> $WarningPreference = "Stop"
PS> Write-Warning "This is only a test warning."
WARNING: This is only a test message.
Write-Warning : Command execution stopped because the shell variable "WarningPreference" is set to Stop.
At line:1 char:14
     + Write-Warning <<<<  "This is only a test message."
```

<span data-ttu-id="45c63-118">Der erste Befehl zeigt den Standardwert der `$WarningPreference` Variablen an, die ist `Continue` .</span><span class="sxs-lookup"><span data-stu-id="45c63-118">The first command displays the default value of the `$WarningPreference` variable, which is `Continue`.</span></span> <span data-ttu-id="45c63-119">Beim Schreiben einer Warnung wird daher die Warnmeldung angezeigt, und die Ausführung wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="45c63-119">As a result, when you write a warning, the warning message is displayed and execution continues.</span></span>

<span data-ttu-id="45c63-120">Wenn Sie den Wert der Variablen ändern `$WarningPreference` , ändert sich die Auswirkung des `Write-Warning` Befehls erneut.</span><span class="sxs-lookup"><span data-stu-id="45c63-120">When you change the value of the `$WarningPreference` variable, the effect of the `Write-Warning` command changes again.</span></span> <span data-ttu-id="45c63-121">`SilentlyContinue`Der Wert unterdrückt die Warnung.</span><span class="sxs-lookup"><span data-stu-id="45c63-121">A value of `SilentlyContinue` suppresses the warning.</span></span> <span data-ttu-id="45c63-122">`Stop`Der Wert zeigt die Warnung an und beendet dann die Ausführung des Befehls.</span><span class="sxs-lookup"><span data-stu-id="45c63-122">A value of `Stop` displays the warning and then stops execution of the command.</span></span>

<span data-ttu-id="45c63-123">Weitere Informationen zur- `$WarningPreference` Variablen finden Sie unter [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="45c63-123">For more information about the `$WarningPreference` variable, see [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="45c63-124">Beispiel 4: Festlegen des WarningAction-Parameters und Schreiben einer Warnung</span><span class="sxs-lookup"><span data-stu-id="45c63-124">Example 4: Set the WarningAction parameter and write a warning</span></span>

<span data-ttu-id="45c63-125">Dieses Beispiel zeigt die Auswirkung des allgemeinen **WarningAction** -Parameters auf einen `Write-Warning` Befehl.</span><span class="sxs-lookup"><span data-stu-id="45c63-125">This example shows the effect of the **WarningAction** common parameter on a `Write-Warning` command.</span></span> <span data-ttu-id="45c63-126">Sie können den allgemeinen **WarningAction** -Parameter mit jedem Cmdlet verwenden, um zu bestimmen, wie PowerShell auf Warnungen reagiert, die durch diesen Befehl entstehen.</span><span class="sxs-lookup"><span data-stu-id="45c63-126">You can use the **WarningAction** common parameter with any cmdlet to determine how PowerShell responds to warnings resulting from that command.</span></span> <span data-ttu-id="45c63-127">Der allgemeine **WarningAction** -Parameter überschreibt den Wert von `$WarningPreference` nur für diesen speziellen Befehl.</span><span class="sxs-lookup"><span data-stu-id="45c63-127">The **WarningAction** common parameter overrides the value of the `$WarningPreference` only for that particular command.</span></span>

```powershell
PS> Write-Warning "This is only a test warning." -WarningAction Inquire
WARNING: This is only a test warning.
Confirm
Continue with this operation?
 [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="45c63-128">Dieser Befehl verwendet das `Write-Warning` Cmdlet, um eine Warnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="45c63-128">This command uses the `Write-Warning` cmdlet to display a warning.</span></span> <span data-ttu-id="45c63-129">Der allgemeine **WarningAction** -Parameter mit dem Wert "Anfrage" weist das System an, den Benutzer zur Eingabe aufzufordern, wenn der Befehl eine Warnung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="45c63-129">The **WarningAction** common parameter with a value of Inquire directs the system to prompt the user when the command displays a warning.</span></span>

<span data-ttu-id="45c63-130">Weitere Informationen zu den allgemeinen **WarningAction** -Parametern finden Sie unter [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="45c63-130">For more information about the **WarningAction** common parameter, see [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="45c63-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="45c63-131">PARAMETERS</span></span>

### <span data-ttu-id="45c63-132">-Meldung</span><span class="sxs-lookup"><span data-stu-id="45c63-132">-Message</span></span>
<span data-ttu-id="45c63-133">Gibt die Warnmeldung an.</span><span class="sxs-lookup"><span data-stu-id="45c63-133">Specifies the warning message.</span></span>

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

### <span data-ttu-id="45c63-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="45c63-134">CommonParameters</span></span>

<span data-ttu-id="45c63-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="45c63-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="45c63-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="45c63-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="45c63-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="45c63-137">INPUTS</span></span>

### <span data-ttu-id="45c63-138">System.String</span><span class="sxs-lookup"><span data-stu-id="45c63-138">System.String</span></span>

<span data-ttu-id="45c63-139">Sie können eine Zeichenfolge, die die Warnung enthält, an die Pipeline übergeben `Write-Warning` .</span><span class="sxs-lookup"><span data-stu-id="45c63-139">You can pipe a string that contains the warning to `Write-Warning`.</span></span>

## <span data-ttu-id="45c63-140">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="45c63-140">OUTPUTS</span></span>

### <span data-ttu-id="45c63-141">Keine</span><span class="sxs-lookup"><span data-stu-id="45c63-141">None</span></span>

<span data-ttu-id="45c63-142">`Write-Warning` schreibt nur in den Warnungs Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="45c63-142">`Write-Warning` writes only to the warning stream.</span></span> <span data-ttu-id="45c63-143">Es generiert keine andere Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="45c63-143">It does not generate any other output.</span></span>

## <span data-ttu-id="45c63-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="45c63-144">NOTES</span></span>

<span data-ttu-id="45c63-145">Der Standardwert für die `$WarningPreference` Variable ist `Continue` , wodurch die Warnung angezeigt und die Ausführung des Befehls fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="45c63-145">The default value for the `$WarningPreference` variable is `Continue`, which displays the warning and then continues executing the command.</span></span> <span data-ttu-id="45c63-146">Um gültige Werte für eine Einstellungs Variable wie zu ermitteln `$WarningPreference` , legen Sie Sie auf eine Zeichenfolge zufälliger Zeichen fest, z. b. "ABC".</span><span class="sxs-lookup"><span data-stu-id="45c63-146">To determine valid values for a preference variable such as `$WarningPreference`, set it to a string of random characters, such as "abc".</span></span> <span data-ttu-id="45c63-147">Die resultierende Fehlermeldung listet die gültigen Werte auf.</span><span class="sxs-lookup"><span data-stu-id="45c63-147">The resulting error message lists the valid values.</span></span>

## <span data-ttu-id="45c63-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="45c63-148">RELATED LINKS</span></span>

[<span data-ttu-id="45c63-149">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="45c63-149">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="45c63-150">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="45c63-150">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="45c63-151">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="45c63-151">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="45c63-152">Schreibfehler</span><span class="sxs-lookup"><span data-stu-id="45c63-152">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="45c63-153">Write-Host</span><span class="sxs-lookup"><span data-stu-id="45c63-153">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="45c63-154">Write-Information</span><span class="sxs-lookup"><span data-stu-id="45c63-154">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="45c63-155">Write-Output</span><span class="sxs-lookup"><span data-stu-id="45c63-155">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="45c63-156">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="45c63-156">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="45c63-157">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="45c63-157">Write-Verbose</span></span>](Write-Verbose.md)
