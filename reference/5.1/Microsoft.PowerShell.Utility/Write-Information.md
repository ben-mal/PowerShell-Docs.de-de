---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-information?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Information
ms.openlocfilehash: e0f28393c95e2c0703c489d4691edcf883b4cb05
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224300"
---
# <span data-ttu-id="8458d-103">Write-Information</span><span class="sxs-lookup"><span data-stu-id="8458d-103">Write-Information</span></span>

## <span data-ttu-id="8458d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8458d-104">SYNOPSIS</span></span>

<span data-ttu-id="8458d-105">Gibt an, wie PowerShell Daten in einem Informationsdaten Strom für einen Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8458d-105">Specifies how PowerShell handles information stream data for a command.</span></span>

## <span data-ttu-id="8458d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8458d-106">SYNTAX</span></span>

```
Write-Information [-MessageData] <Object> [[-Tags] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="8458d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8458d-107">DESCRIPTION</span></span>

<span data-ttu-id="8458d-108">Das- `Write-Information` Cmdlet gibt an, wie PowerShell Daten in einem Informationsdaten Strom für einen Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8458d-108">The `Write-Information` cmdlet specifies how PowerShell handles information stream data for a command.</span></span>

<span data-ttu-id="8458d-109">Windows PowerShell 5,0 führt einen neuen, strukturierten Informationsdaten Strom ein.</span><span class="sxs-lookup"><span data-stu-id="8458d-109">Windows PowerShell 5.0 introduces a new, structured information stream.</span></span> <span data-ttu-id="8458d-110">Mit diesem Stream können Sie strukturierte Daten zwischen einem Skript und seinen Aufrufern oder der Host Anwendung übertragen.</span><span class="sxs-lookup"><span data-stu-id="8458d-110">You can use this stream to transmit structured data between a script and its callers or the host application.</span></span>
<span data-ttu-id="8458d-111">`Write-Information` ermöglicht es Ihnen, dem Stream eine Informations Meldung hinzuzufügen und anzugeben, wie PowerShell Daten in einem Informationsdaten Strom für einen Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8458d-111">`Write-Information` lets you add an informational message to the stream, and specify how PowerShell handles information stream data for a command.</span></span> <span data-ttu-id="8458d-112">Informationsdaten Ströme funktionieren auch für `PowerShell.Streams` , Aufträge und geplante Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="8458d-112">Information streams also work for `PowerShell.Streams`, jobs, and scheduled tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="8458d-113">Der Informationsdaten Strom folgt nicht der Standard Konvention, dass seine Nachrichten mit "[Stream Name]:" vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8458d-113">The information stream does not follow the standard convention of prefixing its messages with "[Stream Name]:".</span></span> <span data-ttu-id="8458d-114">Dies wurde aus Gründen der Kürze und visuellen Sauberkeit bestimmt.</span><span class="sxs-lookup"><span data-stu-id="8458d-114">This was intended for brevity and visual cleanliness.</span></span>

<span data-ttu-id="8458d-115">Der `$InformationPreference` Wert der Einstellungs Variablen bestimmt, ob die Nachricht, die Sie für bereitstellen, zu `Write-Information` dem erwarteten Zeitpunkt im Vorgang eines Skripts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8458d-115">The `$InformationPreference` preference variable value determines whether the message you provide to `Write-Information` is displayed at the expected point in a script's operation.</span></span> <span data-ttu-id="8458d-116">Da der Standardwert dieser Variablen Standard `SilentlyContinue` mäßig nicht angezeigt wird, werden keine Informationsmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8458d-116">Because the default value of this variable is `SilentlyContinue`, by default, informational messages are not shown.</span></span> <span data-ttu-id="8458d-117">Wenn Sie den Wert von nicht ändern möchten `$InformationPreference` , können Sie seinen Wert überschreiben, indem Sie dem `InformationAction` Befehl den allgemeinen Parameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8458d-117">If you don't want to change the value of `$InformationPreference`, you can override its value by adding the `InformationAction` common parameter to your command.</span></span> <span data-ttu-id="8458d-118">Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) und [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8458d-118">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) and [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8458d-119">Ab Windows PowerShell 5,0 `Write-Host` ist ein Wrapper dafür, mit `Write-Information` `Write-Host` dem Sie die Ausgabe an den Informationsdaten Strom ausgeben können.</span><span class="sxs-lookup"><span data-stu-id="8458d-119">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="8458d-120">Dies ermöglicht die **Erfassung** oder **Unterdrückung** von Daten, die mithilfe von geschrieben wurden, während die abwärts `Write-Host` Kompatibilität beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="8458d-120">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span> <span data-ttu-id="8458d-121">Weitere Informationen finden Sie unter [Write-Host](Write-Host.md) .</span><span class="sxs-lookup"><span data-stu-id="8458d-121">For more information see [Write-Host](Write-Host.md)</span></span>

<span data-ttu-id="8458d-122">`Write-Information` ist auch eine unterstützte Workflow Aktivität in PowerShell 5. x.</span><span class="sxs-lookup"><span data-stu-id="8458d-122">`Write-Information` is also a supported workflow activity in PowerShell 5.x.</span></span>

## <span data-ttu-id="8458d-123">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8458d-123">EXAMPLES</span></span>

### <span data-ttu-id="8458d-124">Beispiel 1: Schreiben von Informationen für get-results</span><span class="sxs-lookup"><span data-stu-id="8458d-124">Example 1: Write information for Get- results</span></span>

<span data-ttu-id="8458d-125">In diesem Beispiel wird eine Informations Meldung mit dem Namen "hat ihre Features!" angezeigt, nachdem der Befehl ausgeführt wurde, `Get-WindowsFeature` um alle Features zu finden, deren namens Wert mit "p" beginnt.</span><span class="sxs-lookup"><span data-stu-id="8458d-125">In this example, you show an informational message, "Got your features!", after running the `Get-WindowsFeature` command to find all features that have a Name value that starts with 'p'.</span></span>
<span data-ttu-id="8458d-126">Da die- `$InformationPreference` Variable weiterhin auf den Standardwert festgelegt ist, `SilentlyContinue` fügen Sie den `InformationAction` -Parameter hinzu, um den Wert zu überschreiben `$InformationPreference` , und zeigen Sie die Meldung an.</span><span class="sxs-lookup"><span data-stu-id="8458d-126">Because the `$InformationPreference` variable is still set to its default, `SilentlyContinue`, you add the `InformationAction` parameter to override the `$InformationPreference` value, and show the message.</span></span> <span data-ttu-id="8458d-127">Der `InformationAction` Wert lautet "Continue", was bedeutet, dass die Meldung angezeigt wird, das Skript oder der Befehl jedoch fortgesetzt wird, wenn er noch nicht abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8458d-127">The `InformationAction` value is Continue, which means that your message is shown, but the script or command continues, if it is not yet finished.</span></span>

```powershell
Get-WindowsFeature -Name p*
Write-Information -MessageData "Got your features!" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
Got your features!
```

### <span data-ttu-id="8458d-128">Beispiel 2: Schreiben von Informationen und Markieren dieser Informationen</span><span class="sxs-lookup"><span data-stu-id="8458d-128">Example 2: Write information and tag it</span></span>

<span data-ttu-id="8458d-129">In diesem Beispiel verwenden Sie, `Write-Information` um Benutzer darüber zu informieren, dass Sie einen weiteren Befehl ausführen müssen, nachdem Sie den aktuellen Befehl ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="8458d-129">In this example, you use `Write-Information` to let users know they'll need to run another command after they're done running the current command.</span></span> <span data-ttu-id="8458d-130">Im Beispiel werden der Informations Meldung die taganweisungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8458d-130">The example adds the tag Instructions to the informational message.</span></span> <span data-ttu-id="8458d-131">Wenn Sie nach dem Ausführen dieses Befehls den Informationsdaten Strom nach Nachrichten mit markierten Anweisungen durchsuchen, wird die hier angegebene Meldung in den Ergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8458d-131">After running this command, if you search the information stream for messages tagged Instructions, the message specified here would be among the results.</span></span>

```powershell
$message = "To filter your results for PowerShell, pipe your results to the Where-Object cmdlet."
Get-WindowsFeature -Name p*
Write-Information -MessageData $message -Tags "Instructions" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
To filter your results for PowerShell, pipe your results to the Where-Object cmdlet.
```

### <span data-ttu-id="8458d-132">Beispiel 3: Schreiben von Informationen in eine Datei</span><span class="sxs-lookup"><span data-stu-id="8458d-132">Example 3: Write information to a file</span></span>

```powershell
function Test-Info
{
    Get-Process P*
    Write-Information "Here you go"
}
Test-Info 6> Info.txt
```

## <span data-ttu-id="8458d-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8458d-133">PARAMETERS</span></span>

### <span data-ttu-id="8458d-134">-MessageData</span><span class="sxs-lookup"><span data-stu-id="8458d-134">-MessageData</span></span>

<span data-ttu-id="8458d-135">Gibt eine Informations Meldung an, die Benutzern angezeigt werden soll, wenn Sie ein Skript oder einen Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="8458d-135">Specifies an informational message that you want to display to users as they run a script or command.</span></span> <span data-ttu-id="8458d-136">Schließen Sie die Informations Meldung in Anführungszeichen ein, um optimale Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="8458d-136">For best results, enclose the informational message in quotation marks.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8458d-137">-Tags</span><span class="sxs-lookup"><span data-stu-id="8458d-137">-Tags</span></span>

<span data-ttu-id="8458d-138">Gibt eine einfache Zeichenfolge an, mit der Sie Nachrichten, die Sie dem Informationsdaten Strom hinzugefügt haben, Sortieren und Filtern können `Write-Information` .</span><span class="sxs-lookup"><span data-stu-id="8458d-138">Specifies a simple string that you can use to sort and filter messages that you have added to the information stream with `Write-Information`.</span></span> <span data-ttu-id="8458d-139">Dieser Parameter funktioniert ähnlich wie der **Tags** -Parameter in `New-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="8458d-139">This parameter works similarly to the **Tags** parameter in `New-ModuleManifest`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8458d-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8458d-140">CommonParameters</span></span>

<span data-ttu-id="8458d-141">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8458d-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8458d-142">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8458d-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8458d-143">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8458d-143">INPUTS</span></span>

### <span data-ttu-id="8458d-144">Keine</span><span class="sxs-lookup"><span data-stu-id="8458d-144">None</span></span>

<span data-ttu-id="8458d-145">`Write-Information` akzeptiert keine weitergeleiteten Eingaben.</span><span class="sxs-lookup"><span data-stu-id="8458d-145">`Write-Information` does not accept piped input.</span></span>

## <span data-ttu-id="8458d-146">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8458d-146">OUTPUTS</span></span>

### <span data-ttu-id="8458d-147">System. Management. Automation. informationrecord</span><span class="sxs-lookup"><span data-stu-id="8458d-147">System.Management.Automation.InformationRecord</span></span>

## <span data-ttu-id="8458d-148">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8458d-148">NOTES</span></span>

## <span data-ttu-id="8458d-149">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8458d-149">RELATED LINKS</span></span>

[<span data-ttu-id="8458d-150">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="8458d-150">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="8458d-151">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="8458d-151">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="8458d-152">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8458d-152">about_CommonParameters</span></span>](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)

[<span data-ttu-id="8458d-153">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="8458d-153">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="8458d-154">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="8458d-154">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="8458d-155">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="8458d-155">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="8458d-156">Write-Host</span><span class="sxs-lookup"><span data-stu-id="8458d-156">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="8458d-157">Write-Information</span><span class="sxs-lookup"><span data-stu-id="8458d-157">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="8458d-158">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="8458d-158">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="8458d-159">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="8458d-159">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="8458d-160">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="8458d-160">Write-Warning</span></span>](Write-Warning.md)

[<span data-ttu-id="8458d-161">Write-Output</span><span class="sxs-lookup"><span data-stu-id="8458d-161">Write-Output</span></span>](Write-Output.md)
