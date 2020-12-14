---
ms.date: 02/03/2020
keywords: powershell,core
title: Breaking Changes in PowerShell Core 6.0
description: In diesem Artikel sind die Unterschiede zwischen Windows PowerShell 5.1 und PowerShell 6.0 zusammengefasst.
ms.openlocfilehash: b53365ee72e6a6e85faa56125a8aa7961d3ecc7f
ms.sourcegitcommit: f9d855dd73b916559a22e337672dea3fbb11c634
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2020
ms.locfileid: "96833776"
---
# <a name="breaking-changes-for-powershell-6x"></a><span data-ttu-id="3e92f-104">Breaking Changes in PowerShell 6.x</span><span class="sxs-lookup"><span data-stu-id="3e92f-104">Breaking Changes for PowerShell 6.x</span></span>

## <a name="features-no-longer-available-in-powershell-core"></a><span data-ttu-id="3e92f-105">Nicht mehr verfügbare Features in PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="3e92f-105">Features no longer available in PowerShell Core</span></span>

### <a name="modules-not-shipped-for-powershell-6x"></a><span data-ttu-id="3e92f-106">Module, die nicht für PowerShell 6.x ausgeliefert werden</span><span class="sxs-lookup"><span data-stu-id="3e92f-106">Modules not shipped for PowerShell 6.x</span></span>

<span data-ttu-id="3e92f-107">Aus verschiedenen Kompatibilitätsgründen sind die folgenden Module nicht in PowerShell 6 enthalten.</span><span class="sxs-lookup"><span data-stu-id="3e92f-107">For various compatibility reasons, the following modules are not included in PowerShell 6.</span></span>

- <span data-ttu-id="3e92f-108">ISE</span><span class="sxs-lookup"><span data-stu-id="3e92f-108">ISE</span></span>
- <span data-ttu-id="3e92f-109">Microsoft.PowerShell.LocalAccounts</span><span class="sxs-lookup"><span data-stu-id="3e92f-109">Microsoft.PowerShell.LocalAccounts</span></span>
- <span data-ttu-id="3e92f-110">Microsoft.PowerShell.ODataUtils</span><span class="sxs-lookup"><span data-stu-id="3e92f-110">Microsoft.PowerShell.ODataUtils</span></span>
- <span data-ttu-id="3e92f-111">Microsoft.PowerShell.Operation.Validation</span><span class="sxs-lookup"><span data-stu-id="3e92f-111">Microsoft.PowerShell.Operation.Validation</span></span>
- <span data-ttu-id="3e92f-112">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3e92f-112">PSScheduledJob</span></span>
- <span data-ttu-id="3e92f-113">PSWorkflow</span><span class="sxs-lookup"><span data-stu-id="3e92f-113">PSWorkflow</span></span>
- <span data-ttu-id="3e92f-114">PSWorkflowUtility</span><span class="sxs-lookup"><span data-stu-id="3e92f-114">PSWorkflowUtility</span></span>

### <a name="powershell-workflow"></a><span data-ttu-id="3e92f-115">PowerShell-Workflow</span><span class="sxs-lookup"><span data-stu-id="3e92f-115">PowerShell Workflow</span></span>

<span data-ttu-id="3e92f-116">Der [PowerShell-Workflow][workflow] ist ein Feature in Windows PowerShell, das auf [Windows Workflow Foundation (WF)][workflow-foundation] basiert und die Erstellung von stabilen Runbooks für lang andauernde oder parallelisierte Aufgaben ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3e92f-116">[PowerShell Workflow][workflow] is a feature in Windows PowerShell that builds on top of [Windows Workflow Foundation (WF)][workflow-foundation] that enables the creation of robust runbooks for long-running or parallelized tasks.</span></span>

<span data-ttu-id="3e92f-117">Da Windows Workflow Foundation in .NET Core nicht unterstützt wird, bietet PowerShell Core keine Unterstützung für den PowerShell-Workflow.</span><span class="sxs-lookup"><span data-stu-id="3e92f-117">Due to the lack of support for Windows Workflow Foundation in .NET Core, we are not supporting PowerShell Workflow in PowerShell Core.</span></span>

<span data-ttu-id="3e92f-118">Zukünftig soll die native Parallelität in der PowerShell-Sprache ohne Notwendigkeit des PowerShell-Workflows ermöglicht werden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-118">In the future, we would like to enable native parallelism/concurrency in the PowerShell language without the need for PowerShell Workflow.</span></span>

<span data-ttu-id="3e92f-119">Wenn für die Fortsetzung eines Skripts nach dem Neustart des Betriebssystems Prüfpunkte erforderlich sind, empfehlen wir die Verwendung des Taskplaners, um beim Betriebssystemstart ein Skript auszuführen. Das Skript muss dabei jedoch seinen Status selbst verwalten (z. B. durch Speichern in eine Datei).</span><span class="sxs-lookup"><span data-stu-id="3e92f-119">If there is a need to use checkpoints to resume a script after the OS restarts, we recommend using Task Scheduler to run a script on OS startup, but the script would need to maintain its own state (like persisting it to a file).</span></span>

[workflow]: /previous-versions/powershell/scripting/components/workflows-guide
[workflow-foundation]: /dotnet/framework/windows-workflow-foundation/

### <a name="custom-snap-ins"></a><span data-ttu-id="3e92f-120">Benutzerdefinierte Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="3e92f-120">Custom snap-ins</span></span>

<span data-ttu-id="3e92f-121">[PowerShell-Snap-Ins][snapin] sind die Vorgänger von PowerShell-Modulen und sind in der PowerShell-Community nicht weit verbreitet.</span><span class="sxs-lookup"><span data-stu-id="3e92f-121">[PowerShell snap-ins][snapin] are a predecessor to PowerShell modules that do not have widespread adoption in the PowerShell community.</span></span>

<span data-ttu-id="3e92f-122">Aufgrund der Komplexität der unterstützenden Snap-Ins und der zu geringen Verwendung in der Community werden benutzerdefinierte Snap-Ins in PowerShell Core nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-122">Due to the complexity of supporting snap-ins and their lack of usage in the community, we no longer support custom snap-ins in PowerShell Core.</span></span>

<span data-ttu-id="3e92f-123">Dadurch funktionieren die Module `ActiveDirectory` und `DnsClient` unter Windows und Windows Server nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="3e92f-123">Today, this breaks the `ActiveDirectory` and `DnsClient` modules in Windows and Windows Server.</span></span>

[snapin]: /powershell/module/microsoft.powershell.core/about/about_pssnapins

### <a name="wmi-v1-cmdlets"></a><span data-ttu-id="3e92f-124">WMI v1-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3e92f-124">WMI v1 cmdlets</span></span>

<span data-ttu-id="3e92f-125">Aufgrund der Komplexität der beiden unterstützenden WMI-basierten Module wurden die WMI v1-Cmdlets aus PowerShell Core entfernt:</span><span class="sxs-lookup"><span data-stu-id="3e92f-125">Due to the complexity of supporting two sets of WMI-based modules, we removed the WMI v1 cmdlets from PowerShell Core:</span></span>

- `Register-WmiEvent`
- `Set-WmiInstance`
- `Invoke-WmiMethod`
- `Get-WmiObject`
- `Remove-WmiObject`

<span data-ttu-id="3e92f-126">Es wird empfohlen, dass Sie stattdessen die CIM-Cmdlets (d.h. WMI v2) verwenden, die die gleichen Funktionen sowie neue Funktionen und eine überarbeitete Syntax bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="3e92f-126">Instead, we recommend that you the use the CIM (aka WMI v2) cmdlets which provide the same functionality with new functionality and a redesigned syntax:</span></span>

- `Get-CimAssociatedInstance`
- `Get-CimClass`
- `Get-CimInstance`
- `Get-CimSession`
- `Invoke-CimMethod`
- `New-CimInstance`
- `New-CimSession`
- `New-CimSessionOption`
- `Register-CimIndicationEvent`
- `Remove-CimInstance`
- `Remove-CimSession`
- `Set-CimInstance`

### <a name="microsoftpowershelllocalaccounts"></a><span data-ttu-id="3e92f-127">Microsoft.PowerShell.LocalAccounts</span><span class="sxs-lookup"><span data-stu-id="3e92f-127">Microsoft.PowerShell.LocalAccounts</span></span>

<span data-ttu-id="3e92f-128">Aufgrund der Verwendung von nicht unterstützten APIs wurde `Microsoft.PowerShell.LocalAccounts` aus PowerShell Core entfernt, bis eine bessere Lösung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="3e92f-128">Due to the use of unsupported APIs, `Microsoft.PowerShell.LocalAccounts` has been removed from PowerShell Core until a better solution is found.</span></span>

### <a name="new-webserviceproxy-cmdlet-removed"></a><span data-ttu-id="3e92f-129">Cmdlet `New-WebServiceProxy` entfernt</span><span class="sxs-lookup"><span data-stu-id="3e92f-129">`New-WebServiceProxy` cmdlet removed</span></span>

<span data-ttu-id="3e92f-130">.NET Core bietet keine Unterstützung für das Windows Communication Framework, das Dienste für die Verwendung des SOAP-Protokolls bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-130">.NET Core does not support the Windows Communication Framework, which provide services for using the SOAP protocol.</span></span> <span data-ttu-id="3e92f-131">Dieses Cmdlet wurde entfernt, weil es SOAP erfordert.</span><span class="sxs-lookup"><span data-stu-id="3e92f-131">This cmdlet was removed because it requires SOAP.</span></span>

### <a name="-transaction-cmdlets-removed"></a><span data-ttu-id="3e92f-132">`*-Transaction`-Cmdlets entfernt</span><span class="sxs-lookup"><span data-stu-id="3e92f-132">`*-Transaction` cmdlets removed</span></span>

<span data-ttu-id="3e92f-133">Die Verwendung dieser Cmdlets war sehr eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-133">These cmdlets had very limited usage.</span></span> <span data-ttu-id="3e92f-134">Es wurde entschieden, ihre Unterstützung einzustellen.</span><span class="sxs-lookup"><span data-stu-id="3e92f-134">The decision was made to discontinue support for them.</span></span>

- `Complete-Transaction`
- `Get-Transaction`
- `Start-Transaction`
- `Undo-Transaction`
- `Use-Transaction`

### <a name="security-cmdlets-not-available-on-non-windows-platforms"></a><span data-ttu-id="3e92f-135">Sicherheits-Cmdlets, die auf Nicht-Windows-Plattformen nicht verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="3e92f-135">Security cmdlets not available on non-Windows platforms</span></span>

- `Get-Acl`
- `Set-Acl`
- `Get-AuthenticodeSignature`
- `Set-AuthenticodeSignature`
- `Get-CmsMessage`
- `Protect-CmsMessage`
- `Unprotect-CmsMessage`
- `New-FileCatalog`
- `Test-FileCatalog`

### <a name="-computerand-other-windows-specific-cmdlets"></a><span data-ttu-id="3e92f-136">`*-Computer`- und andere Windows-spezifische Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3e92f-136">`*-Computer`and other Windows-specific cmdlets</span></span>

<span data-ttu-id="3e92f-137">Aufgrund der Verwendung nicht unterstützter APIs wurden die folgenden Cmdlets aus PowerShell Core entfernt, bis eine bessere Lösung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="3e92f-137">Due to the use of unsupported APIs, the following cmdlets have been removed from PowerShell Core until a better solution is found.</span></span>

- `Get-Clipboard`
- `Set-Clipboard`
- `Add-Computer`
- `Checkpoint-Computer`
- `Remove-Computer`
- `Restore-Computer`
- `Reset-ComputerMachinePassword`
- `Disable-ComputerRestore`
- `Enable-ComputerRestore`
- `Get-ComputerRestorePoint`
- `Test-ComputerSecureChannel`
- `Get-ControlPanelItem`
- `Show-ControlPanelItem`
- `Get-HotFix`
- `Clear-RecycleBin`
- `Update-List`
- `Out-Printer`
- `ConvertFrom-String`
- `Convert-String`

### <a name="-counter-cmdlets"></a><span data-ttu-id="3e92f-138">`*-Counter`-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3e92f-138">`*-Counter` cmdlets</span></span>

<span data-ttu-id="3e92f-139">Aufgrund der Verwendung von nicht unterstützten APIs wurde `*-Counter` aus PowerShell Core entfernt, bis eine bessere Lösung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="3e92f-139">Due to the use of unsupported APIs, the `*-Counter` has been removed from PowerShell Core until a better solution is found.</span></span>

### <a name="-eventlog-cmdlets"></a><span data-ttu-id="3e92f-140">`*-EventLog`-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3e92f-140">`*-EventLog` cmdlets</span></span>

<span data-ttu-id="3e92f-141">Aufgrund der Verwendung von nicht unterstützten APIs wurde `*-EventLog` aus PowerShell Core entfernt,</span><span class="sxs-lookup"><span data-stu-id="3e92f-141">Due to the use of unsupported APIs, the `*-EventLog` has been removed from PowerShell Core.</span></span> <span data-ttu-id="3e92f-142">bis eine bessere Lösung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="3e92f-142">until a better solution is found.</span></span> <span data-ttu-id="3e92f-143">Unter Windows stehen `Get-WinEvent` und `New-WinEvent` zum Abrufen und Erstellen von Ereignissen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3e92f-143">`Get-WinEvent` and `New-WinEvent` are available to get and create events on Windows.</span></span>

### <a name="cmdlets-that-use-wpf-removed"></a><span data-ttu-id="3e92f-144">Cmdlets, die WPF verwenden, wurden entfernt</span><span class="sxs-lookup"><span data-stu-id="3e92f-144">Cmdlets that use WPF removed</span></span>

<span data-ttu-id="3e92f-145">Das Windows Presentation Framework wird in CoreCLR nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-145">The Windows Presentation Framework is not supported on CoreCLR.</span></span> <span data-ttu-id="3e92f-146">Folgende Cmdlets sind betroffen:</span><span class="sxs-lookup"><span data-stu-id="3e92f-146">The following cmdlets are affected:</span></span>

- `Show-Command`
- `Out-GridView`
- <span data-ttu-id="3e92f-147">Der **showwindow**-Parameter von `Get-Help`</span><span class="sxs-lookup"><span data-stu-id="3e92f-147">The **showwindow** parameter of `Get-Help`</span></span>

### <a name="some-dsc-cmdlets-removed"></a><span data-ttu-id="3e92f-148">Einige DSC-Cmdlets wurden entfernt</span><span class="sxs-lookup"><span data-stu-id="3e92f-148">Some DSC cmdlets removed</span></span>

- `Get-DscConfiguration`
- `Publish-DscConfiguration`
- `Restore-DscConfiguration`
- `Start-DscConfiguration`
- `Stop-DscConfiguration`
- `Test-DscConfiguration`
- `Update-DscConfiguration`
- `Remove-DscConfigurationDocument`
- `Get-DscConfigurationStatus`
- `Disable-DscDebug`
- `Enable-DscDebug`
- `Get-DscLocalConfigurationManager`
- `Set-DscLocalConfigurationManager`
- `Invoke-DscResource`

## <a name="enginelanguage-changes"></a><span data-ttu-id="3e92f-149">Änderungen an der Engine bzw. Sprache</span><span class="sxs-lookup"><span data-stu-id="3e92f-149">Engine/language changes</span></span>

### <a name="rename-powershellexe-to-pwshexe-5101"></a><span data-ttu-id="3e92f-150">Umbenennung von `powershell.exe` in `pwsh.exe` [#5101](https://github.com/PowerShell/PowerShell/issues/5101)</span><span class="sxs-lookup"><span data-stu-id="3e92f-150">Rename `powershell.exe` to `pwsh.exe` [#5101](https://github.com/PowerShell/PowerShell/issues/5101)</span></span>

<span data-ttu-id="3e92f-151">Damit Benutzern eine deterministische Möglichkeit bereitgestellt werden kann, PowerShell Core unter Windows (im Gegensatz zu Windows PowerShell) aufzurufen, wurde die PowerShell Core-Binärdatei unter Windows in `pwsh.exe` und auf anderen Plattformen als Windows in `pwsh` geändert.</span><span class="sxs-lookup"><span data-stu-id="3e92f-151">In order to give users a deterministic way to call PowerShell Core on Windows (as opposed to Windows PowerShell), the PowerShell Core binary was changed to `pwsh.exe` on Windows and `pwsh` on non-Windows platforms.</span></span>

<span data-ttu-id="3e92f-152">Der abgekürzte Name ist ebenfalls mit der Benennung von Shells in anderen Plattformen als Windows konsistent.</span><span class="sxs-lookup"><span data-stu-id="3e92f-152">The shortened name is also consistent with naming of shells on non-Windows platforms.</span></span>

### <a name="dont-insert-line-breaks-to-output-except-for-tables-5193"></a><span data-ttu-id="3e92f-153">Fügen Sie keine Zeilenumbrüche in die Ausgabe ein (außer bei Tabellen) [#5193](https://github.com/PowerShell/PowerShell/issues/5193)</span><span class="sxs-lookup"><span data-stu-id="3e92f-153">Don't insert line breaks to output (except for tables) [#5193](https://github.com/PowerShell/PowerShell/issues/5193)</span></span>

<span data-ttu-id="3e92f-154">Zuvor wurde die Ausgabe an die Breite der Konsole angebracht, und Zeilenumbrüche wurden zur Endbreite der Konsole hinzugefügt. Das bedeutet, dass die Ausgabe nicht wie erwartet neu formatiert wurde, wenn die Größe des Terminals geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="3e92f-154">Previously, output was aligned to the width of the console and line breaks were added at the end width of the console, meaning the output didn't get reformatted as expected if the terminal was resized.</span></span> <span data-ttu-id="3e92f-155">Diese Änderung wurde nicht auf Tabellen angewendet, da Zeilenumbrüche notwendig sind, um die Spalten auszurichten.</span><span class="sxs-lookup"><span data-stu-id="3e92f-155">This change was not applied to tables, as the line breaks are necessary to keep the columns aligned.</span></span>

### <a name="skip-null-element-check-for-collections-with-a-value-type-element-type-5432"></a><span data-ttu-id="3e92f-156">Überspringen der Überprüfung auf NULL-Elemente für Sammlungen mit einem Werttyp [#5432](https://github.com/PowerShell/PowerShell/issues/5432)</span><span class="sxs-lookup"><span data-stu-id="3e92f-156">Skip null-element check for collections with a value-type element type [#5432](https://github.com/PowerShell/PowerShell/issues/5432)</span></span>

<span data-ttu-id="3e92f-157">Überspringen Sie beim Parameter `Mandatory` und bei den Attributen `ValidateNotNull` und `ValidateNotNullOrEmpty` die Überprüfung auf NULL-Elemente, wenn der Elementtyp der Sammlung ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="3e92f-157">For the `Mandatory` parameter and `ValidateNotNull` and `ValidateNotNullOrEmpty` attributes, skip the null-element check if the collection's element type is value type.</span></span>

### <a name="change-outputencoding-to-use-utf-8-nobom-encoding-rather-than-ascii-5369"></a><span data-ttu-id="3e92f-158">Ändern von `$OutputEncoding`, um die `UTF-8 NoBOM`-Codierung statt ASCII zu verwenden [#5369](https://github.com/PowerShell/PowerShell/issues/5369)</span><span class="sxs-lookup"><span data-stu-id="3e92f-158">Change `$OutputEncoding` to use `UTF-8 NoBOM` encoding rather than ASCII [#5369](https://github.com/PowerShell/PowerShell/issues/5369)</span></span>

<span data-ttu-id="3e92f-159">Die vorherige Codierung (ASCII, 7 Bit) würde in manchen Fällen zu falschen Änderungen der Ausgabe führen.</span><span class="sxs-lookup"><span data-stu-id="3e92f-159">The previous encoding, ASCII (7-bit), would result in incorrect alteration of the output in some cases.</span></span> <span data-ttu-id="3e92f-160">Durch diese Änderung soll die `UTF-8 NoBOM`-Codierung standardmäßig verwendet werden. Dadurch wird die Unicode-Ausgabe mit einer Codierung beibehalten, die von den meisten Tools und Betriebssystemen unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="3e92f-160">This change is to make `UTF-8 NoBOM` default, which preserves Unicode output with an encoding supported by most tools and operating systems.</span></span>

### <a name="remove-allscope-from-most-default-aliases-5268"></a><span data-ttu-id="3e92f-161">Entfernen von `AllScope` aus den meisten Standardaliasen [#5268](https://github.com/PowerShell/PowerShell/issues/5268)</span><span class="sxs-lookup"><span data-stu-id="3e92f-161">Remove `AllScope` from most default aliases [#5268](https://github.com/PowerShell/PowerShell/issues/5268)</span></span>

<span data-ttu-id="3e92f-162">`AllScope` wurde aus den meisten Standardaliasen entfernt, um die Erstellung von Bereichen zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="3e92f-162">To speed up scope creation, `AllScope` was removed from most default aliases.</span></span> <span data-ttu-id="3e92f-163">In einigen häufig verwendeten Aliasen, in denen die Suche schneller ist, wurde `AllScope` beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3e92f-163">`AllScope` was left for a few frequently used aliases where the lookup was faster.</span></span>

### <a name="-verbose-and--debug-no-longer-overrides-erroractionpreference-5113"></a><span data-ttu-id="3e92f-164">`-Verbose` und `-Debug` überschreibt nicht länger `$ErrorActionPreference` [#5113](https://github.com/PowerShell/PowerShell/issues/5113)</span><span class="sxs-lookup"><span data-stu-id="3e92f-164">`-Verbose` and `-Debug` no longer overrides `$ErrorActionPreference` [#5113](https://github.com/PowerShell/PowerShell/issues/5113)</span></span>

<span data-ttu-id="3e92f-165">Zuvor wurde das Verhalten von `$ErrorActionPreference` überschrieben, wenn `-Verbose` oder `-Debug` angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-165">Previously, if `-Verbose` or `-Debug` were specified, it overrode the behavior of `$ErrorActionPreference`.</span></span> <span data-ttu-id="3e92f-166">Durch diese Änderung wirken `-Verbose` und `-Debug` sich nicht mehr auf das Verhalten von `$ErrorActionPreference` aus.</span><span class="sxs-lookup"><span data-stu-id="3e92f-166">With this change, `-Verbose` and `-Debug` no longer affect the behavior of `$ErrorActionPreference`.</span></span>

## <a name="cmdlet-changes"></a><span data-ttu-id="3e92f-167">Änderungen an Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3e92f-167">Cmdlet changes</span></span>

### <a name="invoke-restmethod-doesnt-return-useful-info-when-no-data-is-returned-5320"></a><span data-ttu-id="3e92f-168">„Invoke-RestMethod“ gibt keine nützlichen Informationen zurück, wenn keine Daten zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="3e92f-168">Invoke-RestMethod doesn't return useful info when no data is returned.</span></span> [<span data-ttu-id="3e92f-169">#5320</span><span class="sxs-lookup"><span data-stu-id="3e92f-169">#5320</span></span>](https://github.com/PowerShell/PowerShell/issues/5320)

<span data-ttu-id="3e92f-170">Wenn eine API nur `null` zurückgibt, hat Invoke-RestMethod dies als die Zeichenfolge `"null"` statt `$null` serialisiert.</span><span class="sxs-lookup"><span data-stu-id="3e92f-170">When an API returns just `null`, Invoke-RestMethod was serializing this as the string `"null"` instead of `$null`.</span></span> <span data-ttu-id="3e92f-171">Diese Änderung korrigiert die Logik in `Invoke-RestMethod`, um das gültige JSON-Literal mit Einzelwert `null` ordnungsgemäß als `$null` zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="3e92f-171">This change fixes the logic in `Invoke-RestMethod` to properly serialize a valid single value JSON `null` literal as `$null`.</span></span>

### <a name="remove--protocol-from--computer-cmdlets-5277"></a><span data-ttu-id="3e92f-172">Entfernung von `-Protocol` aus `*-Computer`-Cmdlets [#5277](https://github.com/PowerShell/PowerShell/issues/5277)</span><span class="sxs-lookup"><span data-stu-id="3e92f-172">Remove `-Protocol` from `*-Computer` cmdlets [#5277](https://github.com/PowerShell/PowerShell/issues/5277)</span></span>

<span data-ttu-id="3e92f-173">Aufgrund von Problemen mit dem RPC-Remoting in CoreFX (insbesondere auf anderen Plattformen als Windows) und zur Gewährleistung einer konsistenten Remotingumgebung in PowerShell wurde der Parameter `-Protocol` aus den `\*-Computer`-Cmdlets entfernt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-173">Due to issues with RPC remoting in CoreFX (particularly on non-Windows platforms) and ensuring a consistent remoting experience in PowerShell, the `-Protocol` parameter was removed from the `\*-Computer` cmdlets.</span></span> <span data-ttu-id="3e92f-174">DCOM wird für das Remoting nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-174">DCOM is no longer supported for remoting.</span></span> <span data-ttu-id="3e92f-175">Die folgenden Cmdlets unterstützen nur das WSMAN-Remoting:</span><span class="sxs-lookup"><span data-stu-id="3e92f-175">The following cmdlets only support WSMAN remoting:</span></span>

- <span data-ttu-id="3e92f-176">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="3e92f-176">Rename-Computer</span></span>
- <span data-ttu-id="3e92f-177">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="3e92f-177">Restart-Computer</span></span>
- <span data-ttu-id="3e92f-178">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="3e92f-178">Stop-Computer</span></span>

### <a name="remove--computername-from--service-cmdlets-5090"></a><span data-ttu-id="3e92f-179">Entfernung von `-ComputerName` aus `*-Service`-Cmdlets [#5090](https://github.com/PowerShell/PowerShell/issues/5094)</span><span class="sxs-lookup"><span data-stu-id="3e92f-179">Remove `-ComputerName` from `*-Service` cmdlets [#5090](https://github.com/PowerShell/PowerShell/issues/5094)</span></span>

<span data-ttu-id="3e92f-180">Der Parameter `-ComputerName` wurde aus `*-Service`-Cmdlets entfernt, um die konsistente Verwendung von PSRP zu fördern.</span><span class="sxs-lookup"><span data-stu-id="3e92f-180">In order to encourage the consistent use of PSRP, the `-ComputerName` parameter was removed from `*-Service` cmdlets.</span></span>

### <a name="fix-get-item--literalpath-ab-if-ab-doesnt-actually-exist-to-return-error-5197"></a><span data-ttu-id="3e92f-181">Korrigieren von `Get-Item -LiteralPath a*b`, wenn `a*b` nicht vorhanden ist, um Fehler zurückzugeben [#5197](https://github.com/PowerShell/PowerShell/issues/5197)</span><span class="sxs-lookup"><span data-stu-id="3e92f-181">Fix `Get-Item -LiteralPath a*b` if `a*b` doesn't actually exist to return error [#5197](https://github.com/PowerShell/PowerShell/issues/5197)</span></span>

<span data-ttu-id="3e92f-182">Zuvor wurde ein `-LiteralPath`-Cmdlet im Hintergrund beendet, wenn ein Platzhalter es wie `-Path` behandelt und dieser keine Dateien findet.</span><span class="sxs-lookup"><span data-stu-id="3e92f-182">Previously, `-LiteralPath` given a wildcard would treat it the same as `-Path` and if the wildcard found no files, it would silently exit.</span></span> <span data-ttu-id="3e92f-183">Korrekterweise sollte `-LiteralPath` ein Literal sein, sodass ein Fehler angezeigt wird, wenn die Datei nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3e92f-183">Correct behavior should be that `-LiteralPath` is literal so if the file doesn't exist, it should error.</span></span> <span data-ttu-id="3e92f-184">Die Änderung besteht darin, dass Platzhalter, die mit `-Literal` verwendet werden, als Literal behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-184">Change is to treat wildcards used with `-Literal` as literal.</span></span>

### <a name="import-csv-should-apply-pstypenames-upon-import-when-type-information-is-present-in-the-csv-5134"></a><span data-ttu-id="3e92f-185">`Import-Csv` sollte `PSTypeNames` beim Import anwenden, wenn die Typinformationen in der CSV-Datei vorhanden sind [#5134](https://github.com/PowerShell/PowerShell/issues/5134)</span><span class="sxs-lookup"><span data-stu-id="3e92f-185">`Import-Csv` should apply `PSTypeNames` upon import when type information is present in the CSV [#5134](https://github.com/PowerShell/PowerShell/issues/5134)</span></span>

<span data-ttu-id="3e92f-186">Zuvor behielten exportierte Objekte, die `Export-CSV` mit `TypeInformation` verwenden und mit `ConvertFrom-Csv` importiert wurden, die Typinformationen nicht bei.</span><span class="sxs-lookup"><span data-stu-id="3e92f-186">Previously, objects exported using `Export-CSV` with `TypeInformation` imported with `ConvertFrom-Csv` were not retaining the type information.</span></span> <span data-ttu-id="3e92f-187">Durch diese Änderung werden die Typinformationen zum Member `PSTypeNames` hinzugefügt, wenn Sie in der CSV-Datei vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3e92f-187">This change adds the type information to `PSTypeNames` member if available from the CSV file.</span></span>

### <a name="-notypeinformation-should-be-default-on-export-csv-5131"></a><span data-ttu-id="3e92f-188">`-NoTypeInformation` sollte standardmäßig auf  festgelegt sein `Export-Csv` [#5131](https://github.com/PowerShell/PowerShell/issues/5131)</span><span class="sxs-lookup"><span data-stu-id="3e92f-188">`-NoTypeInformation` should be default on `Export-Csv` [#5131](https://github.com/PowerShell/PowerShell/issues/5131)</span></span>

<span data-ttu-id="3e92f-189">Diese Änderung wurde als Reaktion auf Kundenfeedback zum Standardverhalten von `Export-CSV` durchgeführt, indem Typinformationen eingefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-189">This change was made to address customer feedback on the default behavior of `Export-CSV` to include type information.</span></span>

<span data-ttu-id="3e92f-190">Zuvor gab das Cmdlet einen Kommentar als erste Zeile aus, der den Typnamen des Objekts enthielt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-190">Previously, the cmdlet would output a comment as the first line containing the type name of the object.</span></span> <span data-ttu-id="3e92f-191">Durch diese Änderung wird dies standardmäßig unterdrückt, da es von den meisten Tools nicht interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3e92f-191">The change is to suppress this by default as it's not understood by most tools.</span></span> <span data-ttu-id="3e92f-192">Verwenden Sie `-IncludeTypeInformation`, um das vorherigen Verhalten beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="3e92f-192">Use `-IncludeTypeInformation` to retain the previous behavior.</span></span>

### <a name="web-cmdlets-should-warn-when--credential-is-sent-over-unencrypted-connections-5112"></a><span data-ttu-id="3e92f-193">Web-Cmdlets sollten eine Warnung ausgeben, wenn `-Credential` über nicht verschlüsselte Verbindungen gesendet wird [#5112](https://github.com/PowerShell/PowerShell/issues/5112)</span><span class="sxs-lookup"><span data-stu-id="3e92f-193">Web Cmdlets should warn when `-Credential` is sent over unencrypted connections [#5112](https://github.com/PowerShell/PowerShell/issues/5112)</span></span>

<span data-ttu-id="3e92f-194">Bei der Verwendung von HTTP werden Inhalte mit Kennwörtern als Klartext gesendet.</span><span class="sxs-lookup"><span data-stu-id="3e92f-194">When using HTTP, content including passwords are sent as clear-text.</span></span> <span data-ttu-id="3e92f-195">Durch diese Änderung wird dies standardmäßig nicht zugelassen, außerdem wird ein Fehler zurückgegeben, wenn Anmeldeinformationen auf unsichere Weise weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-195">This change is to not allow this by default and return an error if credentials are being passed in an insecure manner.</span></span> <span data-ttu-id="3e92f-196">Die Benutzer können dies umgehen, indem Sie den Parameter `-AllowUnencryptedAuthentication` verwenden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-196">Users can bypass this by using the `-AllowUnencryptedAuthentication` switch.</span></span>

## <a name="api-changes"></a><span data-ttu-id="3e92f-197">API-Änderungen</span><span class="sxs-lookup"><span data-stu-id="3e92f-197">API changes</span></span>

### <a name="remove-addtypecommandbase-class-5407"></a><span data-ttu-id="3e92f-198">Entfernung der `AddTypeCommandBase`-Klasse [#5407](https://github.com/PowerShell/PowerShell/issues/5407)</span><span class="sxs-lookup"><span data-stu-id="3e92f-198">Remove `AddTypeCommandBase` class [#5407](https://github.com/PowerShell/PowerShell/issues/5407)</span></span>

<span data-ttu-id="3e92f-199">Die `AddTypeCommandBase`-Klasse wurde aus `Add-Type` entfernt, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="3e92f-199">The `AddTypeCommandBase` class was removed from `Add-Type` to improve performance.</span></span> <span data-ttu-id="3e92f-200">Diese Klasse wird nur vom Cmdlet „Add-Type“ verwendet, sodass es keine Auswirkungen auf die Benutzer geben sollte.</span><span class="sxs-lookup"><span data-stu-id="3e92f-200">This class is only used by the Add-Type cmdlet and should not impact users.</span></span>

### <a name="unify-cmdlets-with-parameter--encoding-to-be-of-type-systemtextencoding-5080"></a><span data-ttu-id="3e92f-201">Vereinheitlichung von Cmdlets mit Parameter `-Encoding` mit dem Typ `System.Text.Encoding` [#5080](https://github.com/PowerShell/PowerShell/issues/5080)</span><span class="sxs-lookup"><span data-stu-id="3e92f-201">Unify cmdlets with parameter `-Encoding` to be of type `System.Text.Encoding` [#5080](https://github.com/PowerShell/PowerShell/issues/5080)</span></span>

<span data-ttu-id="3e92f-202">Der `-Encoding`-Wert `Byte` wurde aus den Cmdlets des Dateisystemanbieters entfernt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-202">The `-Encoding` value `Byte` has been removed from the filesystem provider cmdlets.</span></span> <span data-ttu-id="3e92f-203">Der neue Parameter `-AsByteStream` wird nun verwendet, um anzugeben, dass ein Bytestream als Eingabe erforderlich ist oder dass die Ausgabe ein Bytestream ist.</span><span class="sxs-lookup"><span data-stu-id="3e92f-203">A new parameter, `-AsByteStream`, is now used to specify that a byte stream is required as input or that the output is a stream of bytes.</span></span>

### <a name="add-better-error-message-for-empty-and-null--uformat-parameter-5055"></a><span data-ttu-id="3e92f-204">Verbesserte Fehlermeldung, wenn der `-UFormat`-Parameter leer oder NULL ist [#5055](https://github.com/PowerShell/PowerShell/issues/5055)</span><span class="sxs-lookup"><span data-stu-id="3e92f-204">Add better error message for empty and null `-UFormat` parameter [#5055](https://github.com/PowerShell/PowerShell/issues/5055)</span></span>

<span data-ttu-id="3e92f-205">Zuvor wurde eine Fehlermeldung angezeigt, die nicht nützlich war, wenn eine leere Formatzeichenfolge an `-UFormat` übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3e92f-205">Previously, when passing an empty format string to `-UFormat`, an unhelpful error message would appear.</span></span> <span data-ttu-id="3e92f-206">Eine Fehlermeldung mit verbesserter Beschreibung wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-206">A more descriptive error has been added.</span></span>

### <a name="clean-up-console-code-4995"></a><span data-ttu-id="3e92f-207">Bereinigung des Konsolencodes [#4995](https://github.com/PowerShell/PowerShell/issues/4995)</span><span class="sxs-lookup"><span data-stu-id="3e92f-207">Clean up console code [#4995](https://github.com/PowerShell/PowerShell/issues/4995)</span></span>

<span data-ttu-id="3e92f-208">Folgende Features wurden entfernt, da sie in PowerShell Core nicht unterstützt werden und die Unterstützung nicht geplant ist, da diese nur aus Legacygründen in Windows PowerShell vorhanden sind: der `-psconsolefile`-Parameter und -Code, der `-importsystemmodules`-Parameter und -Code sowie Code zum Ändern der Schriftart.</span><span class="sxs-lookup"><span data-stu-id="3e92f-208">The following features were removed as they are not supported in PowerShell Core, and there are no plans to add support as they exist for legacy reasons for Windows PowerShell: `-psconsolefile` switch and code, `-importsystemmodules` switch and code, and font changing code.</span></span>

### <a name="removed-runspaceconfiguration-support-4942"></a><span data-ttu-id="3e92f-209">Entfernung der Unterstützung von `RunspaceConfiguration`[#4942](https://github.com/PowerShell/PowerShell/issues/4942)</span><span class="sxs-lookup"><span data-stu-id="3e92f-209">Removed `RunspaceConfiguration` support [#4942](https://github.com/PowerShell/PowerShell/issues/4942)</span></span>

<span data-ttu-id="3e92f-210">Zuvor konnten Sie bei der programmgesteuerten Erstellung eines PowerShell-Runspaces mithilfe der API die veraltete Klasse [`RunspaceConfiguration`][runspaceconfig] oder die neuere Klasse [`InitialSessionState`][iss] verwenden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-210">Previously, when creating a PowerShell runspace programmatically using the API you could use the legacy [`RunspaceConfiguration`][runspaceconfig] or the newer [`InitialSessionState`][iss].</span></span> <span data-ttu-id="3e92f-211">Durch diese Änderung wurde die Unterstützung für `RunspaceConfiguration` entfernt, sodass nur noch `InitialSessionState` unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="3e92f-211">This change removed support for `RunspaceConfiguration` and only supports `InitialSessionState`.</span></span>

[runspaceconfig]: /dotnet/api/system.management.automation.runspaces.runspaceconfiguration
[iss]: /dotnet/api/system.management.automation.runspaces.initialsessionstate

### <a name="commandinvocationintrinsicsinvokescript-bind-arguments-to-input-instead-of-args-4923"></a><span data-ttu-id="3e92f-212">`CommandInvocationIntrinsics.InvokeScript` bindet Argumente an `$input` anstatt an `$args` [#4923](https://github.com/PowerShell/PowerShell/issues/4923)</span><span class="sxs-lookup"><span data-stu-id="3e92f-212">`CommandInvocationIntrinsics.InvokeScript` bind arguments to `$input` instead of `$args` [#4923](https://github.com/PowerShell/PowerShell/issues/4923)</span></span>

<span data-ttu-id="3e92f-213">Die falsche Position eines Parameters führte dazu, dass die Argumente als Eingabe statt als Argumente übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-213">An incorrect position of a parameter resulted in the args passed as input instead of as args.</span></span>

### <a name="remove-unsupported--showwindow-switch-from-get-help-4903"></a><span data-ttu-id="3e92f-214">Nicht unterstützter Schalter `-showwindow` aus  entfernt `Get-Help` [#4903](https://github.com/PowerShell/PowerShell/issues/4903)</span><span class="sxs-lookup"><span data-stu-id="3e92f-214">Remove unsupported `-showwindow` switch from `Get-Help` [#4903](https://github.com/PowerShell/PowerShell/issues/4903)</span></span>

<span data-ttu-id="3e92f-215">`-showwindow` basiert auf WPF. Dies wird auf CoreCLR nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-215">`-showwindow` relies on WPF, which is not supported on CoreCLR.</span></span>

### <a name="allow--to-be-used-in-registry-path-for-remove-item-4866"></a><span data-ttu-id="3e92f-216">\* kann jetzt im Registrierungspfad für  verwendet werden `Remove-Item` [#4866](https://github.com/PowerShell/PowerShell/issues/4866)</span><span class="sxs-lookup"><span data-stu-id="3e92f-216">Allow \* to be used in registry path for `Remove-Item` [#4866](https://github.com/PowerShell/PowerShell/issues/4866)</span></span>

<span data-ttu-id="3e92f-217">Zuvor wurde ein `-LiteralPath`-Cmdlet im Hintergrund beendet, wenn ein Platzhalter es wie `-Path` behandelt und dieser keine Dateien findet.</span><span class="sxs-lookup"><span data-stu-id="3e92f-217">Previously, `-LiteralPath` given a wildcard would treat it the same as `-Path` and if the wildcard found no files, it would silently exit.</span></span> <span data-ttu-id="3e92f-218">Korrekterweise sollte `-LiteralPath` ein Literal sein, sodass ein Fehler angezeigt wird, wenn die Datei nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3e92f-218">Correct behavior should be that `-LiteralPath` is literal so if the file doesn't exist, it should error.</span></span> <span data-ttu-id="3e92f-219">Die Änderung besteht darin, dass Platzhalter, die mit `-Literal` verwendet werden, als Literal behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-219">Change is to treat wildcards used with `-Literal` as literal.</span></span>

### <a name="fix-set-service-failing-test-4802"></a><span data-ttu-id="3e92f-220">Behebung eines fehlgeschlagenen Tests für `Set-Service`[#4802](https://github.com/PowerShell/PowerShell/issues/4802)</span><span class="sxs-lookup"><span data-stu-id="3e92f-220">Fix `Set-Service` failing test [#4802](https://github.com/PowerShell/PowerShell/issues/4802)</span></span>

<span data-ttu-id="3e92f-221">Zuvor wurde `foo` ignoriert, wenn `New-Service -StartupType foo` verwendet wurde, und der Dienst wurde mit Standardstarttypen erstellt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-221">Previously, if `New-Service -StartupType foo` was used, `foo` was ignored and the service was created with some default startup type.</span></span> <span data-ttu-id="3e92f-222">Durch diese Änderung soll für ungültige Starttypen explizit ein Fehler ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-222">This change is to explicitly throw an error for an invalid startup type.</span></span>

### <a name="rename-isosx-to-ismacos-4700"></a><span data-ttu-id="3e92f-223">Umbenennung von `$IsOSX` in `$IsMacOS` [#4700](https://github.com/PowerShell/PowerShell/issues/4700)</span><span class="sxs-lookup"><span data-stu-id="3e92f-223">Rename `$IsOSX` to `$IsMacOS` [#4700](https://github.com/PowerShell/PowerShell/issues/4700)</span></span>

<span data-ttu-id="3e92f-224">Die Benennung in PowerShell sollte konsistent mit unserer Benennung und mit der Verwendung von macOS statt OSX (Apple) konform sein.</span><span class="sxs-lookup"><span data-stu-id="3e92f-224">The naming in PowerShell should be consistent with our naming and conform to Apple's use of macOS instead of OSX.</span></span> <span data-ttu-id="3e92f-225">Aus Gründen der Lesbarkeit und Konsistenz wird jedoch die Groß- und Kleinschreibung von Pascal beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3e92f-225">However, for readability and consistently we are staying with Pascal casing.</span></span>

### <a name="make-error-message-consistent-when-invalid-script-is-passed-to--file-better-error-when-passed-ambiguous-argument-4573"></a><span data-ttu-id="3e92f-226">Fehlermeldungen sollten konsistent sein, wenn ein ungültiges Skript an „-File“ übergeben wird; Fehlermeldungen beim Übergeben eines mehrdeutigen Arguments sollten verbessert werden [#4573](https://github.com/PowerShell/PowerShell/issues/4573)</span><span class="sxs-lookup"><span data-stu-id="3e92f-226">Make error message consistent when invalid script is passed to -File, better error when passed ambiguous argument [#4573](https://github.com/PowerShell/PowerShell/issues/4573)</span></span>

<span data-ttu-id="3e92f-227">Änderung der Exitcodes von `pwsh.exe` für eine Übereinstimmung mit Unix-Konventionen</span><span class="sxs-lookup"><span data-stu-id="3e92f-227">Change the exit codes of `pwsh.exe` to align with Unix conventions</span></span>

### <a name="removal-of-localaccount-and-cmdlets-from--diagnostics-modules-4302-4303"></a><span data-ttu-id="3e92f-228">Entfernung von `LocalAccount` und Cmdlets aus `Diagnostics`-Modulen</span><span class="sxs-lookup"><span data-stu-id="3e92f-228">Removal of `LocalAccount` and cmdlets from  `Diagnostics` modules.</span></span> <span data-ttu-id="3e92f-229">[#4302](https://github.com/PowerShell/PowerShell/issues/4302) [#4303](https://github.com/PowerShell/PowerShell/issues/4303)</span><span class="sxs-lookup"><span data-stu-id="3e92f-229">[#4302](https://github.com/PowerShell/PowerShell/issues/4302) [#4303](https://github.com/PowerShell/PowerShell/issues/4303)</span></span>

<span data-ttu-id="3e92f-230">Aufgrund von nicht unterstützten APIs wurden das `LocalAccounts`-Modul und die `Counter`-Cmdlets aus dem `Diagnostics`-Modul entfernt, bis eine bessere Lösung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="3e92f-230">Due to unsupported APIs, the `LocalAccounts` module and the `Counter` cmdlets in the `Diagnostics` module were removed until a better solution is found.</span></span>

### <a name="executing-powershell-script-with-bool-parameter-does-not-work-4036"></a><span data-ttu-id="3e92f-231">Das Ausführen des PowerShell-Skripts mit booleschen Parametern funktioniert nicht [#4036](https://github.com/PowerShell/PowerShell/issues/4036)</span><span class="sxs-lookup"><span data-stu-id="3e92f-231">Executing PowerShell script with bool parameter does not work [#4036](https://github.com/PowerShell/PowerShell/issues/4036)</span></span>

<span data-ttu-id="3e92f-232">Zuvor wurde bei der Verwendung von **powershell.exe** (jetzt **pwsh.exe**), um ein PowerShell-Skript mithilfe von `-File` auszuführen, keine Möglichkeit bereitgestellt, `$true`/`$false` als Parameterwert zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="3e92f-232">Previously, using **powershell.exe** (now **pwsh.exe**) to execute a PowerShell script using `-File` provided no way to pass `$true`/`$false` as parameter values.</span></span> <span data-ttu-id="3e92f-233">Die Unterstützung für `$true`/`$false` als analysierte Werte für Parameter wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-233">Support for `$true`/`$false` as parsed values to parameters was added.</span></span> <span data-ttu-id="3e92f-234">Parameterwerte werden ebenfalls unterstützt, da die derzeit dokumentierte Syntax nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3e92f-234">Switch values are also supported as currently documented syntax doesn't work.</span></span>

### <a name="remove-clrversion-property-from-psversiontable-4027"></a><span data-ttu-id="3e92f-235">Entfernung der `ClrVersion`-Eigenschaft aus `$PSVersionTable` [#4027](https://github.com/PowerShell/PowerShell/issues/4027)</span><span class="sxs-lookup"><span data-stu-id="3e92f-235">Remove `ClrVersion` property from `$PSVersionTable` [#4027](https://github.com/PowerShell/PowerShell/issues/4027)</span></span>

<span data-ttu-id="3e92f-236">Die `ClrVersion`-Eigenschaft von `$PSVersionTable` ist in CoreCLR nicht nützlich, und Endbenutzer sollten diesen Wert nicht verwenden, um die Kompatibilität zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="3e92f-236">The `ClrVersion` property of `$PSVersionTable` is not useful with CoreCLR, end users should not be using that value to determine compatibility.</span></span>

### <a name="change-positional-parameter-for-powershellexe-from--command-to--file-4019"></a><span data-ttu-id="3e92f-237">Änderung des positionellen Parameters für `powershell.exe` von `-Command` in `-File` [#4019](https://github.com/PowerShell/PowerShell/issues/4019)</span><span class="sxs-lookup"><span data-stu-id="3e92f-237">Change positional parameter for `powershell.exe` from `-Command` to `-File` [#4019](https://github.com/PowerShell/PowerShell/issues/4019)</span></span>

<span data-ttu-id="3e92f-238">Die Verwendung von Shebang in PowerShell auf anderen Plattformen als Windows wird ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3e92f-238">Enable shebang use of PowerShell on non-Windows platforms.</span></span> <span data-ttu-id="3e92f-239">Das bedeutet, dass Sie auf Unix-basierten Systemen ein Skript ausführen können, das PowerShell automatisch aufruft, anstatt `pwsh` explizit aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="3e92f-239">This means on Unix based systems, you can make a script executable that would invoke PowerShell automatically rather than explicitly invoking `pwsh`.</span></span> <span data-ttu-id="3e92f-240">Dies bedeutet ebenfalls, dass Sie `powershell foo.ps1` oder `powershell fooScript` durchführen können, ohne `-File` anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3e92f-240">This also means that you can now do things like `powershell foo.ps1` or `powershell fooScript` without specifying `-File`.</span></span> <span data-ttu-id="3e92f-241">Durch diese Änderung ist es jedoch erforderlich, dass Sie explizit `-c` oder `-Command` angeben, wenn Sie z.B. versuchen, `powershell.exe Get-Command` durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="3e92f-241">However, this change now requires that you explicitly specify `-c` or `-Command` when trying to do things like `powershell.exe Get-Command`.</span></span>

### <a name="implement-unicode-escape-parsing-3958"></a><span data-ttu-id="3e92f-242">Implementierung der Analyse von Unicode-Escapesequenzen [#3958](https://github.com/PowerShell/PowerShell/issues/3958)</span><span class="sxs-lookup"><span data-stu-id="3e92f-242">Implement Unicode escape parsing [#3958](https://github.com/PowerShell/PowerShell/issues/3958)</span></span>

<span data-ttu-id="3e92f-243">`` `u####`` oder `` `u{####}`` wird in das entsprechende Unicode-Zeichen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3e92f-243">`` `u####`` or `` `u{####}`` is converted to the corresponding Unicode character.</span></span> <span data-ttu-id="3e92f-244">Verwenden Sie das Hochkommazeichen (``` ``u```), um ein Literal (`` `u``) auszugeben.</span><span class="sxs-lookup"><span data-stu-id="3e92f-244">To output a literal `` `u``, escape the backtick: ``` ``u```.</span></span>

### <a name="change-new-modulemanifest-encoding-to-utf8nobom-on-non-windows-platforms-3940"></a><span data-ttu-id="3e92f-245">Änderung der `New-ModuleManifest`-Codierung in `UTF8NoBOM` auf anderen Plattformen als Windows [#3940](https://github.com/PowerShell/PowerShell/issues/3940)</span><span class="sxs-lookup"><span data-stu-id="3e92f-245">Change `New-ModuleManifest` encoding to `UTF8NoBOM` on non-Windows platforms [#3940](https://github.com/PowerShell/PowerShell/issues/3940)</span></span>

<span data-ttu-id="3e92f-246">Zuvor hat `New-ModuleManifest` PSD1-Manifeste in UTF-16 mit Bytereihenfolge-Marken erstellt, wodurch ein Problem für Linux-Tools entstand.</span><span class="sxs-lookup"><span data-stu-id="3e92f-246">Previously, `New-ModuleManifest` creates psd1 manifests in UTF-16 with BOM, creating a problem for Linux tools.</span></span> <span data-ttu-id="3e92f-247">Durch diese Änderung wird die Codierung auf anderen Plattformen als Windows von `New-ModuleManifest` in UTF (ohne Bytereihenfolge-Marken) geändert.</span><span class="sxs-lookup"><span data-stu-id="3e92f-247">This breaking change changes the encoding of `New-ModuleManifest` to be UTF (no BOM) in non-Windows platforms.</span></span>

### <a name="prevent-get-childitem-from-recursing-into-symlinks-1875-3780"></a><span data-ttu-id="3e92f-248">Verhindern, dass `Get-ChildItem` symbolische Links rekursiv durchläuft (#1875)</span><span class="sxs-lookup"><span data-stu-id="3e92f-248">Prevent `Get-ChildItem` from recursing into symlinks (#1875).</span></span> [<span data-ttu-id="3e92f-249">#3780</span><span class="sxs-lookup"><span data-stu-id="3e92f-249">#3780</span></span>](https://github.com/PowerShell/PowerShell/issues/3780)

<span data-ttu-id="3e92f-250">Durch diese Änderung wird `Get-ChildItem` besser auf `ls -r` unter Unix sowie auf die nativen `dir /s`-Befehle unter Windows abgestimmt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-250">This change brings `Get-ChildItem` more in line with the Unix `ls -r` and the Windows `dir /s` native commands.</span></span> <span data-ttu-id="3e92f-251">Wie die genannten Befehle zeigt das Cmdlet symbolische Links zu Verzeichnissen an, die während der Rekursion gefunden werden. Diese werden jedoch nicht rekursiv durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="3e92f-251">Like the mentioned commands, the cmdlet displays symbolic links to directories found during recursion, but does not recurse into them.</span></span>

### <a name="fix-get-content--delimiter-to-not-include-the-delimiter-in-the-returned-lines-3706"></a><span data-ttu-id="3e92f-252">`Get-Content -Delimiter` sollte kein Trennzeichen in den zurückgegebenen Zeilen enthalten [#3706](https://github.com/PowerShell/PowerShell/issues/3706)</span><span class="sxs-lookup"><span data-stu-id="3e92f-252">Fix `Get-Content -Delimiter` to not include the delimiter in the returned lines [#3706](https://github.com/PowerShell/PowerShell/issues/3706)</span></span>

<span data-ttu-id="3e92f-253">Zuvor war die Ausgabe bei der Verwendung von `Get-Content -Delimiter` inkonsistent und unpraktisch, da weitere Verarbeitung der Daten erforderlich ist, um das Trennzeichen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="3e92f-253">Previously, the output while using `Get-Content -Delimiter` was inconsistent and inconvenient as it required further processing of the data to remove the delimiter.</span></span> <span data-ttu-id="3e92f-254">Durch diese Änderung wird das Trennzeichen aus den zurückgegebenen Zeilen entfernt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-254">This change removes the delimiter in returned lines.</span></span>

### <a name="implement-format-hex-in-c-3320"></a><span data-ttu-id="3e92f-255">Implementierung von „Format-Hex“ in C# [#3320](https://github.com/PowerShell/PowerShell/issues/3320)</span><span class="sxs-lookup"><span data-stu-id="3e92f-255">Implement Format-Hex in C# [#3320](https://github.com/PowerShell/PowerShell/issues/3320)</span></span>

<span data-ttu-id="3e92f-256">Der Parameter `-Raw` ist nun kein Vorgang mehr (d.h. er führt keine Aktion aus).</span><span class="sxs-lookup"><span data-stu-id="3e92f-256">The `-Raw` parameter is now a "no-op" (in that it does nothing).</span></span> <span data-ttu-id="3e92f-257">Zukünftig wird die gesamte Ausgabe als richtige Darstellung der Zahlen angezeigt, die alle Bytes für den Typ enthält. Vor der Änderung war dies die formale Aufgabe des `-Raw`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="3e92f-257">Going forward all of the output will be displayed with a true representation of numbers that includes all of the bytes for its type (what the `-Raw` parameter was formally doing prior to this change).</span></span>

### <a name="powershell-as-a-default-shell-doesnt-work-with-script-command-3319"></a><span data-ttu-id="3e92f-258">PowerShell funktioniert nicht als Standardshell mit dem Skriptbefehl [#3319](https://github.com/PowerShell/PowerShell/issues/3319)</span><span class="sxs-lookup"><span data-stu-id="3e92f-258">PowerShell as a default shell doesn't work with script command [#3319](https://github.com/PowerShell/PowerShell/issues/3319)</span></span>

<span data-ttu-id="3e92f-259">Unter Unix ist es Konvention, dass Shells `-i` für eine inaktive Shell akzeptieren und viele Tools dieses Verhalten erwarten (z.B. `script` und wenn PowerShell als Standardshell festgelegt wird) und die Shell mit dem Parameter `-i` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3e92f-259">On Unix, it is a convention for shells to accept `-i` for an interactive shell and many tools expect this behavior (`script` for example, and when setting PowerShell as the default shell) and calls the shell with the `-i` switch.</span></span> <span data-ttu-id="3e92f-260">Dies ist ein Breaking Change, da `-i` zuvor einfach verwendet werden konnte, um mit `-inputformat` übereinzustimmen. Nun muss hierfür `-in` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-260">This change is breaking in that `-i` previously could be used as short hand to match `-inputformat`, which now needs to be `-in`.</span></span>

### <a name="typo-fix-in-get-computerinfo-property-name-3167"></a><span data-ttu-id="3e92f-261">Behebung eines Tippfehlers im Eigenschaftenname von Get-ComputerInfo [#3167](https://github.com/PowerShell/PowerShell/issues/3167)</span><span class="sxs-lookup"><span data-stu-id="3e92f-261">Typo fix in Get-ComputerInfo property name [#3167](https://github.com/PowerShell/PowerShell/issues/3167)</span></span>

<span data-ttu-id="3e92f-262">`BiosSerialNumber` wurde fälschlicherweise als `BiosSeralNumber` geschrieben und wurde in die richtige Schreibweise geändert.</span><span class="sxs-lookup"><span data-stu-id="3e92f-262">`BiosSerialNumber` was misspelled as `BiosSeralNumber` and has been changed to the correct spelling.</span></span>

### <a name="add-get-stringhash-and-get-filehash-cmdlets-3024"></a><span data-ttu-id="3e92f-263">Hinzufügung der `Get-StringHash`- und `Get-FileHash`-Cmdlets [#3024](https://github.com/PowerShell/PowerShell/issues/3024)</span><span class="sxs-lookup"><span data-stu-id="3e92f-263">Add `Get-StringHash` and `Get-FileHash` cmdlets [#3024](https://github.com/PowerShell/PowerShell/issues/3024)</span></span>

<span data-ttu-id="3e92f-264">Diese Änderung besteht darin, dass einige Hashalgorithmen von CoreFX nicht unterstützt werden und deshalb nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3e92f-264">This change is that some hash algorithms are not supported by CoreFX, therefore they are no longer available:</span></span>

- `MACTripleDES`
- `RIPEMD160`

### <a name="add-validation-on-get--cmdlets-where-passing-null-returns-all-objects-instead-of-error-2672"></a><span data-ttu-id="3e92f-265">Hinzufügung der Überprüfung von `Get-*`-Cmdlets, wenn mein Übergeben von „$null“ alle Objekte statt eines Fehlers zurückgegeben werden [#2672](https://github.com/PowerShell/PowerShell/issues/2672)</span><span class="sxs-lookup"><span data-stu-id="3e92f-265">Add validation on `Get-*` cmdlets where passing $null returns all objects instead of error [#2672](https://github.com/PowerShell/PowerShell/issues/2672)</span></span>

<span data-ttu-id="3e92f-266">Das Übergeben von `$null` an eines der folgenden Cmdlets löst nun einen Fehler aus:</span><span class="sxs-lookup"><span data-stu-id="3e92f-266">Passing `$null` to any of the following now throws an error:</span></span>

- `Get-Credential -UserName`
- `Get-Event -SourceIdentifier`
- `Get-EventSubscriber -SourceIdentifier`
- `Get-Help -Name`
- `Get-PSBreakpoint -Script`
- `Get-PSProvider -PSProvider`
- `Get-PSSessionConfiguration -Name`
- `Get-PSSnapin -Name`
- `Get-Runspace -Name`
- `Get-RunspaceDebug -RunspaceName`
- `Get-Service -Name`
- `Get-TraceSource -Name`
- `Get-Variable -Name`
- `Get-WmiObject -Class`
- `Get-WmiObject -Property`

### <a name="add-support-w3c-extended-log-file-format-in-import-csv-2482"></a><span data-ttu-id="3e92f-267">Unterstützung für das erweiterte W3C-Protokolldateiformat in  hinzugefügt `Import-Csv` [#2482](https://github.com/PowerShell/PowerShell/issues/2482)</span><span class="sxs-lookup"><span data-stu-id="3e92f-267">Add support W3C Extended Log File Format in `Import-Csv` [#2482](https://github.com/PowerShell/PowerShell/issues/2482)</span></span>

<span data-ttu-id="3e92f-268">Zuvor konnte das Cmdlet `Import-Csv` nicht verwendet werden, um die Protokolldateien direkt im erweiterten W3C-Protokollformat zu importieren. Hierfür waren zusätzliche Aktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3e92f-268">Previously, the `Import-Csv` cmdlet cannot be used to directly import the log files in W3C extended log format and additional action would be required.</span></span> <span data-ttu-id="3e92f-269">Durch diese Änderung wird das erweiterte W3C-Protokollformat unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-269">With this change, W3C extended log format is supported.</span></span>

### <a name="parameter-binding-problem-with-valuefromremainingarguments-in-ps-functions-2035"></a><span data-ttu-id="3e92f-270">Problem mit der Bindung von Parametern mit `ValueFromRemainingArguments` in PowerShell-Funktionen [#2035](https://github.com/PowerShell/PowerShell/issues/2035)</span><span class="sxs-lookup"><span data-stu-id="3e92f-270">Parameter binding problem with `ValueFromRemainingArguments` in PS functions [#2035](https://github.com/PowerShell/PowerShell/issues/2035)</span></span>

<span data-ttu-id="3e92f-271">`ValueFromRemainingArguments` gibt nun die Werte als Array statt als Einzelwert, der ein Array darstellt, zurück.</span><span class="sxs-lookup"><span data-stu-id="3e92f-271">`ValueFromRemainingArguments` now returns the values as an array instead of a single value which itself is an array.</span></span>

### <a name="buildversion-is-removed-from-psversiontable-1415"></a><span data-ttu-id="3e92f-272">`BuildVersion` aus  entfernt `$PSVersionTable` [#1415](https://github.com/PowerShell/PowerShell/issues/1415)</span><span class="sxs-lookup"><span data-stu-id="3e92f-272">`BuildVersion` is removed from `$PSVersionTable` [#1415](https://github.com/PowerShell/PowerShell/issues/1415)</span></span>

<span data-ttu-id="3e92f-273">Die `BuildVersion`-Eigenschaft wurde aus `$PSVersionTable` entfernt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-273">Remove the `BuildVersion` property from `$PSVersionTable`.</span></span> <span data-ttu-id="3e92f-274">Diese Eigenschaft war an die Windows-Buildversion gebunden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-274">This property was tied to the Windows build version.</span></span> <span data-ttu-id="3e92f-275">Stattdessen wird empfohlen, die genaue Version von PowerShell Core mit `GitCommitId` abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3e92f-275">Instead, we recommend that you use `GitCommitId` to retrieve the exact build version of PowerShell Core.</span></span>

### <a name="changes-to-web-cmdlets"></a><span data-ttu-id="3e92f-276">Änderungen an Web-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3e92f-276">Changes to Web Cmdlets</span></span>

<span data-ttu-id="3e92f-277">Die zugrunde liegende .NET-API der Web-Cmdlets wurde in `System.Net.Http.HttpClient` geändert.</span><span class="sxs-lookup"><span data-stu-id="3e92f-277">The underlying .NET API of the Web Cmdlets has been changed to `System.Net.Http.HttpClient`.</span></span> <span data-ttu-id="3e92f-278">Diese Änderung bietet viele Vorteile.</span><span class="sxs-lookup"><span data-stu-id="3e92f-278">This change provides many benefits.</span></span> <span data-ttu-id="3e92f-279">Diese Änderung führte jedoch zusammen mit der mangelnden Interoperabilität mit Internet Explorer dazu, dass einige Breaking Changes in `Invoke-WebRequest` und `Invoke-RestMethod` auftraten.</span><span class="sxs-lookup"><span data-stu-id="3e92f-279">However, this change along with a lack of interoperability with Internet Explorer have resulted in several breaking changes within `Invoke-WebRequest` and `Invoke-RestMethod`.</span></span>

- <span data-ttu-id="3e92f-280">`Invoke-WebRequest` unterstützt nun ausschließlich die grundlegende HTML-Analyse.</span><span class="sxs-lookup"><span data-stu-id="3e92f-280">`Invoke-WebRequest` now supports basic HTML Parsing only.</span></span> <span data-ttu-id="3e92f-281">`Invoke-WebRequest` gibt immer ein `BasicHtmlWebResponseObject`-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="3e92f-281">`Invoke-WebRequest` always returns a `BasicHtmlWebResponseObject` object.</span></span> <span data-ttu-id="3e92f-282">Die Eigenschaften `ParsedHtml` und `Forms` wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-282">The `ParsedHtml` and `Forms` properties have been removed.</span></span>
- <span data-ttu-id="3e92f-283">Die `BasicHtmlWebResponseObject.Headers`-Werte entsprechen nun `String[]` statt `String`.</span><span class="sxs-lookup"><span data-stu-id="3e92f-283">`BasicHtmlWebResponseObject.Headers` values are now `String[]` instead of `String`.</span></span>
- <span data-ttu-id="3e92f-284">`BasicHtmlWebResponseObject.BaseResponse` ist nun ein `System.Net.Http.HttpResponseMessage`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-284">`BasicHtmlWebResponseObject.BaseResponse` is now a `System.Net.Http.HttpResponseMessage` object.</span></span>
- <span data-ttu-id="3e92f-285">Die `Response`-Eigenschaft von Web-Cmdlet-Ausnahmen ist nun ein `System.Net.Http.HttpResponseMessage`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-285">The `Response` property on Web Cmdlet exceptions is now a `System.Net.Http.HttpResponseMessage` object.</span></span>
- <span data-ttu-id="3e92f-286">Die strenge RFC-Headeranalyse wird nun standardmäßig für den `-Headers`- und `-UserAgent`-Parameter durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-286">Strict RFC header parsing is now default for the `-Headers` and `-UserAgent` parameter.</span></span> <span data-ttu-id="3e92f-287">Dies kann mit `-SkipHeaderValidation` umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="3e92f-287">This can be bypassed with `-SkipHeaderValidation`.</span></span>
- <span data-ttu-id="3e92f-288">Die URI-Schemas `file://` und `ftp://` werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-288">`file://` and `ftp://` URI schemes are no longer supported.</span></span>
- <span data-ttu-id="3e92f-289">Die `System.Net.ServicePointManager`-Einstellungen werden nicht mehr berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="3e92f-289">`System.Net.ServicePointManager` settings are no longer honored.</span></span>
- <span data-ttu-id="3e92f-290">Derzeit ist keine zertifikatbasierte Authentifizierung unter macOS verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3e92f-290">There is currently no certificate based authentication available on macOS.</span></span>
- <span data-ttu-id="3e92f-291">Das Verwenden eines `-Credential`- statt einem `http://`-URI führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="3e92f-291">Use of `-Credential` over an `http://` URI will result in an error.</span></span> <span data-ttu-id="3e92f-292">Verwenden Sie einen `https://`-URI, oder geben Sie den `-AllowUnencryptedAuthentication`-Parameter an, um den Fehler zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="3e92f-292">Use an `https://` URI or supply the `-AllowUnencryptedAuthentication` parameter to suppress the error.</span></span>
- <span data-ttu-id="3e92f-293">`-MaximumRedirection` erzeugt nun einen Fehler mit Abbruch, wenn Umleitungsversuche die angegebene Grenze überschreiten, anstatt die Ergebnisse der letzten Umleitung zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="3e92f-293">`-MaximumRedirection` now produces a terminating error when redirection attempts exceed the provided limit instead of returning the results of the last redirection.</span></span>
- <span data-ttu-id="3e92f-294">In PowerShell 6.2 wurde eine Änderung an der standardmäßigen UTF-8-Codierung für JSON-Antworten vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="3e92f-294">In PowerShell 6.2, a change was made to default to UTF-8 encoding for JSON responses.</span></span> <span data-ttu-id="3e92f-295">Wenn für eine JSON-Antwort kein Zeichensatz angegeben wird, muss die Standardcodierung gemäß RFC 8259 UTF-8 lauten.</span><span class="sxs-lookup"><span data-stu-id="3e92f-295">When a charset is not supplied for a JSON response, the default encoding should be UTF-8 per RFC 8259.</span></span>
