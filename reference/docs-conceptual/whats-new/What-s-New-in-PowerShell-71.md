---
title: Neuerungen in PowerShell 7.1
description: In PowerShell 7.1 veröffentlichte neue Features und Änderungen
ms.date: 12/15/2020
ms.openlocfilehash: 6bbeccd07dd696ee019828bdcd68ce3f6ee627e3
ms.sourcegitcommit: 1628fd2a1f50aec2f31ffb1c451a3ce77c08983c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97577206"
---
# <a name="whats-new-in-powershell-71"></a><span data-ttu-id="2e0a2-103">Neuerungen in PowerShell 7.1</span><span class="sxs-lookup"><span data-stu-id="2e0a2-103">What's New in PowerShell 7.1</span></span>

<span data-ttu-id="2e0a2-104">Am 11. November 2020 wurde die allgemeine Verfügbarkeit von PowerShell 7.1 [angekündigt](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/).</span><span class="sxs-lookup"><span data-stu-id="2e0a2-104">On November 11, 2020 we [announced](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/) the general availability of PowerShell 7.1.</span></span> <span data-ttu-id="2e0a2-105">Aufbauend auf den in PowerShell 7.0 geschaffenen Grundlagen konzentrierten sich unsere Bemühungen auf in der Community gemeldete Issues und umfassen eine Reihe von Verbesserungen und Korrekturen.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-105">Building on the foundation established in PowerShell 7.0, our efforts focused on community issues and include a number of improvements and fixes.</span></span> <span data-ttu-id="2e0a2-106">Wir engagieren uns dafür, dass PowerShell auch weiterhin eine stabile und leistungsstarke Plattform bleibt.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-106">We are committed to ensuring that PowerShell remains a stable and performant platform.</span></span>

<span data-ttu-id="2e0a2-107">PowerShell 7.1 umfasst die folgenden Features, Updates und Breaking Changes.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-107">PowerShell 7.1 includes the following features, updates, and breaking changes.</span></span>

- <span data-ttu-id="2e0a2-108">PSReadLine 2.1.0, einschließlich Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="2e0a2-108">PSReadLine 2.1.0, which includes Predictive IntelliSense</span></span>
- <span data-ttu-id="2e0a2-109">Veröffentlichung von PowerShell 7.1 im Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="2e0a2-109">PowerShell 7.1 has been published to the Microsoft Store</span></span>
- <span data-ttu-id="2e0a2-110">Installerpakete für neue Betriebssystemversionen mit Unterstützung für ARM64 aktualisiert</span><span class="sxs-lookup"><span data-stu-id="2e0a2-110">Installer packages updated for new OS versions with support for ARM64</span></span>
- <span data-ttu-id="2e0a2-111">Höherstufung von vier neuen experimentellen und zwei experimentellen Features auf Mainstreamfeatures</span><span class="sxs-lookup"><span data-stu-id="2e0a2-111">4 new experimental features and 2 experimental features promoted to mainstream</span></span>
- <span data-ttu-id="2e0a2-112">Mehrere Breaking Changes zur Verbesserung der Benutzerfreundlichkeit</span><span class="sxs-lookup"><span data-stu-id="2e0a2-112">Several breaking changes to improve usability</span></span>

<span data-ttu-id="2e0a2-113">Eine umfassende Liste der Änderungen finden Sie im [Änderungsprotokoll](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md) im GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-113">For a complete list of changes, see the [CHANGELOG](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md) in the GitHub repository.</span></span>

## <a name="psreadline-210"></a><span data-ttu-id="2e0a2-114">PSReadLine 2.1.0</span><span class="sxs-lookup"><span data-stu-id="2e0a2-114">PSReadLine 2.1.0</span></span>

<span data-ttu-id="2e0a2-115">Zu PowerShell 7.1 gehört auch PSReadLine 2.1.0.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-115">PowerShell 7.1 also include PSReadLine 2.1.0.</span></span> <span data-ttu-id="2e0a2-116">Diese Version enthält Predictive IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-116">This version includes Predictive IntelliSense.</span></span> <span data-ttu-id="2e0a2-117">Weitere Informationen zum Feature Predictive IntelliSense finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/).</span><span class="sxs-lookup"><span data-stu-id="2e0a2-117">For more information about the Predictive IntelliSense feature, see the [announcement](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/) in the PowerShell blog.</span></span>

## <a name="microsoft-store-installer-package"></a><span data-ttu-id="2e0a2-118">Microsoft Store-Installerpaket</span><span class="sxs-lookup"><span data-stu-id="2e0a2-118">Microsoft Store installer package</span></span>

<span data-ttu-id="2e0a2-119">PowerShell 7.1 wurde im Microsoft Store veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-119">PowerShell 7.1 has been published to the Microsoft Store.</span></span> <span data-ttu-id="2e0a2-120">Die PowerShell-Version finden Sie auf der Website von [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) oder in der Store-Anwendung unter Windows.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-120">You can find the PowerShell release on the [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) website or in the Store application in Windows.</span></span>

<span data-ttu-id="2e0a2-121">Vorteile des Microsoft Store-Pakets:</span><span class="sxs-lookup"><span data-stu-id="2e0a2-121">Benefits of the Microsoft Store package:</span></span>

- <span data-ttu-id="2e0a2-122">Direkt in Windows 10 integrierte automatische Updates</span><span class="sxs-lookup"><span data-stu-id="2e0a2-122">Automatic updates built right into Windows 10</span></span>
- <span data-ttu-id="2e0a2-123">Integration in andere Softwareverteilungsmechanismen wie Intune und SCCM</span><span class="sxs-lookup"><span data-stu-id="2e0a2-123">Integrates with other software distribution mechanisms like Intune and SCCM</span></span>

> [!NOTE]
> <span data-ttu-id="2e0a2-124">Alle in `$PSHOME` gespeicherten Konfigurationseinstellungen auf Systemebene lassen sich nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-124">Any system-level configuration settings stored in `$PSHOME` cannot be modified.</span></span> <span data-ttu-id="2e0a2-125">Dies schließt die WSMAN-Konfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-125">This includes the WSMAN configuration.</span></span> <span data-ttu-id="2e0a2-126">Dadurch wird verhindert, dass Remotesitzungen eine Verbindung mit auf Store basierenden Installationen von PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-126">This prevents remote sessions from connecting to Store-based installs of PowerShell.</span></span> <span data-ttu-id="2e0a2-127">Konfigurationen auf Benutzerebene und SSH-Remoting werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-127">User-level configurations and SSH remoting are supported.</span></span>

## <a name="other-installers"></a><span data-ttu-id="2e0a2-128">Andere Installer</span><span class="sxs-lookup"><span data-stu-id="2e0a2-128">Other installers</span></span>

<span data-ttu-id="2e0a2-129">Weitere aktuelle Informationen zu unterstützten Betriebssystemen und zum Supportlebenszyklus finden Sie unter [PowerShell-Supportlebenszyklus](/powershell/scripting/powershell-support-lifecycle).</span><span class="sxs-lookup"><span data-stu-id="2e0a2-129">For more up-to-date information about supported operating systems and support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle).</span></span>

<span data-ttu-id="2e0a2-130">Prüfen Sie die Installationsanweisungen für Ihr bevorzugtes Betriebssystem:</span><span class="sxs-lookup"><span data-stu-id="2e0a2-130">Check the installation instructions for your preferred operating system:</span></span>

- [<span data-ttu-id="2e0a2-131">Windows</span><span class="sxs-lookup"><span data-stu-id="2e0a2-131">Windows</span></span>](/powershell/scripting/install/installing-powershell-core-on-windows)
- [<span data-ttu-id="2e0a2-132">macOS</span><span class="sxs-lookup"><span data-stu-id="2e0a2-132">macOS</span></span>](/powershell/scripting/install/installing-powershell-core-on-macos)
- [<span data-ttu-id="2e0a2-133">Linux</span><span class="sxs-lookup"><span data-stu-id="2e0a2-133">Linux</span></span>](/powershell/scripting/install/installing-powershell-core-on-linux)

<span data-ttu-id="2e0a2-134">Darüber hinaus unterstützt PowerShell 7.1 die ARM32- und ARM64-Varianten von Debian, Ubuntu und ARM64 Alpine Linux.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-134">Additionally, PowerShell 7.1 supports ARM32 and ARM64 flavors of Debian, Ubuntu, and ARM64 Alpine Linux.</span></span>

<span data-ttu-id="2e0a2-135">Wenngleich nicht offiziell unterstützt, hat die Community auch Pakete für [Arch](https://aur.archlinux.org/packages/powershell/) und Kali Linux bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-135">While not officially supported, the community has also provided packages for [Arch](https://aur.archlinux.org/packages/powershell/) and Kali Linux.</span></span>

> [!NOTE]
> <span data-ttu-id="2e0a2-136">Debian ab Version 10, CentOS ab Version 8, Ubuntu 20.04, Alpine und ARM unterstützen WinRM-Remoting zurzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-136">Debian 10+, CentOS 8+, Ubuntu 20.04, Alpine and Arm currently do not support WinRM remoting.</span></span> <span data-ttu-id="2e0a2-137">Einzelheiten zum Einrichten von SSH-basiertem Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="2e0a2-137">For details on setting up SSH-based remoting, see [PowerShell Remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <a name="experimental-features"></a><span data-ttu-id="2e0a2-138">Experimentelle Features</span><span class="sxs-lookup"><span data-stu-id="2e0a2-138">Experimental Features</span></span>

<span data-ttu-id="2e0a2-139">Weitere Informationen zu den experimentellen Features finden Sie unter [Verwenden experimenteller Features](../learn/experimental-features.md).</span><span class="sxs-lookup"><span data-stu-id="2e0a2-139">For more information about the Experimental Features, see [Using Experimental Features](../learn/experimental-features.md).</span></span>

<span data-ttu-id="2e0a2-140">Die folgenden experimentellen Features stellen in diesem Release nun Mainstreamfeatures dar:</span><span class="sxs-lookup"><span data-stu-id="2e0a2-140">The following experimental features are now mainstream features in this release:</span></span>

- [<span data-ttu-id="2e0a2-141">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="2e0a2-141">PSNullConditionalOperators</span></span>](../learn/experimental-features.md#psnullconditionaloperators)
- [<span data-ttu-id="2e0a2-142">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="2e0a2-142">PSUnixFileStat</span></span>](../learn/experimental-features.md#psunixfilestat)

<span data-ttu-id="2e0a2-143">Die folgenden experimentellen Features wurden in diesem Release hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="2e0a2-143">The following experimental features were added in this release:</span></span>

- [<span data-ttu-id="2e0a2-144">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="2e0a2-144">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>](../learn/experimental-features.md#microsoftpowershellutilitypsmanagebreakpointsinrunspace)
  - <span data-ttu-id="2e0a2-145">PowerShell 7.1 erweitert dieses experimentelle Feature, um allen `*-PSBreakpoint`-Cmdlets den **Runspace**-Parameter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-145">PowerShell 7.1 extends this experimental feature to add the **Runspace** parameter to all `*-PSBreakpoint` cmdlets.</span></span> <span data-ttu-id="2e0a2-146">Der **Runspace**-Parameter gibt ein **Runspace**-Objekt an, mit dem im angegebenen Runspace mit Haltepunkt	en interagiert wird.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-146">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

- <span data-ttu-id="2e0a2-147">[PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution): Dieses Feature ermöglicht es Ihnen, PowerShell-Anbieterpfade an native Befehle zu übergeben, die die PowerShell-Pfadsyntax nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-147">[PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution) - This feature allows you to pass PowerShell provider paths to native commands that don't support PowerShell path syntax.</span></span>

- <span data-ttu-id="2e0a2-148">[PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator): Wenn der linke Operand in einer `-replace`-Operatoranweisung keine Zeichenfolge ist, wird dieser Operand in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-148">[PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator) - When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span> <span data-ttu-id="2e0a2-149">Wenn das Feature aktiviert ist, werden für die Zeichenfolgenkonvertierung keine Kultureinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-149">With the feature enabled, the conversion does not use Culture settings for string conversion.</span></span>

- <span data-ttu-id="2e0a2-150">[PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) bildet die Grundlage für die Unterstützung zukünftiger Predictive IntelliSense-Plug-Ins.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-150">[PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) lays the groundwork to support future Predictive IntelliSense plug-ins.</span></span>

## <a name="breaking-changes-and-improvements"></a><span data-ttu-id="2e0a2-151">Breaking Changes und Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="2e0a2-151">Breaking Changes and Improvements</span></span>

- <span data-ttu-id="2e0a2-152">Fix `$?` darf nicht `$false` sein, wenn der native Befehl in `stderr` schreibt ([#13395](https://github.com/PowerShell/PowerShell/pull/13395))</span><span class="sxs-lookup"><span data-stu-id="2e0a2-152">Fix `$?` to not be `$false` when native command writes to `stderr` ([#13395](https://github.com/PowerShell/PowerShell/pull/13395))</span></span>

  <span data-ttu-id="2e0a2-153">Es kommt häufig vor, dass native Befehle ohne die Absicht in `stderr` schreiben, einen Fehler zu melden.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-153">It is common for native commands to write to `stderr` without intending to indicate a failure.</span></span>
  <span data-ttu-id="2e0a2-154">Mit dieser Änderung wird `$?` nur auf `$false` festgelegt, wenn der native Befehl auch einen Exitcode ungleich null aufweist.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-154">With this change `$?` is set to `$false` only when the native command also has a non-zero exit code.</span></span> <span data-ttu-id="2e0a2-155">Diese Änderung steht in keinem Zusammenhang mit dem experimentellen Feature `PSNotApplyErrorActionToStderr`.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-155">This change is unrelated to the experimental feature `PSNotApplyErrorActionToStderr`.</span></span>

- <span data-ttu-id="2e0a2-156">Veranlassen, dass `$ErrorActionPreference` sich nicht auf die `stderr`-Ausgabe nativer Befehle auswirkt ([#13361](https://github.com/PowerShell/PowerShell/pull/13361))</span><span class="sxs-lookup"><span data-stu-id="2e0a2-156">Make `$ErrorActionPreference` not affect `stderr` output of native commands ([#13361](https://github.com/PowerShell/PowerShell/pull/13361))</span></span>

  <span data-ttu-id="2e0a2-157">Es kommt häufig vor, dass native Befehle ohne die Absicht in `stderr` schreiben, einen Fehler zu melden.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-157">It is common for native commands to write to `stderr` without intending to indicate a failure.</span></span>
  <span data-ttu-id="2e0a2-158">Mit dieser Änderung wird die `stderr`-Ausgabe weiterhin in **ErrorRecord**-Objekten aufgezeichnet, die Runtime wendet `$ErrorActionPreference` jedoch nicht mehr an, wenn **ErrorRecord** aus einem nativen Befehl stammt.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-158">With this change, `stderr` output is still captured in **ErrorRecord** objects, but the runtime no longer applies `$ErrorActionPreference` if the **ErrorRecord** comes from a native command.</span></span>

- <span data-ttu-id="2e0a2-159">`-FromUnixTime` für `Get-Date` in `-UnixTimeSeconds` umbenannt, um die UNIX-Zeiteingabe zuzulassen ([#13084](https://github.com/PowerShell/PowerShell/pull/13084), mit bestem Dank an @aetos382)</span><span class="sxs-lookup"><span data-stu-id="2e0a2-159">Rename `-FromUnixTime` to `-UnixTimeSeconds` on `Get-Date` to allow Unix time input ([#13084](https://github.com/PowerShell/PowerShell/pull/13084)) (Thanks @aetos382!)</span></span>

  <span data-ttu-id="2e0a2-160">Der `-FromUnixTime`-Parameter wurde während 7.1-preview.2 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-160">The `-FromUnixTime` parameter was added during 7.1-preview.2.</span></span> <span data-ttu-id="2e0a2-161">Der Parameter wurde zwecks einer größeren Übereinstimmung mit dem Datentyp umbenannt.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-161">The parameter was renamed to better match the data type.</span></span> <span data-ttu-id="2e0a2-162">Dieser Parameter nimmt einen ganzzahligen Wert, der Datum und Uhrzeit seit dem 1 Januar 1970, 0:00:00, sekundengenau darstellt.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-162">This parameter takes an integer value that represents in seconds since January 1, 1970, 0:00:00.</span></span>

  <span data-ttu-id="2e0a2-163">In diesem Beispiel wird eine Unix-Zeitangabe (dargestellt durch die Anzahl von Sekunden seit dem 1970-01-01 0:00:00) in DateTime konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-163">This example converts a Unix time (represented by the number of seconds since 1970-01-01 0:00:00) to DateTime.</span></span>

  ```powershell
  Get-Date -UnixTimeSeconds 1577836800

  Wednesday, January 01, 2020 12:00:00 AM
  ```

- <span data-ttu-id="2e0a2-164">Explizit angegebenem benannten Parameter erlauben, denselben über das Splatting von Hashtabellen zu ersetzen (#13162)</span><span class="sxs-lookup"><span data-stu-id="2e0a2-164">Allow explicitly specified named parameter to supersede the same one from hashtable splatting (#13162)</span></span>

  <span data-ttu-id="2e0a2-165">Mit dieser Änderung werden die benannten Parameter aus dem Splatting an das Ende der Parameterliste verschoben, sodass sie erst nach dem Binden aller explizit angegebenen benannten Parameter gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-165">With this change, the named parameters from splatting are moved to the end of the parameter list so that they are bound after all explicitly specified named parameters are bound.</span></span> <span data-ttu-id="2e0a2-166">Die Parameterbindung für einfache Funktionen löst keinen Fehler aus, wenn ein angegebener benannter Parameter nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-166">Parameter binding for simple functions doesn't throw an error when a specified named parameter cannot be found.</span></span> <span data-ttu-id="2e0a2-167">Unbekannte benannte Parameter sind an den `$args`-Parameter der einfachen Funktion gebunden.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-167">Unknown named parameters are bound to the `$args` parameter of the simple function.</span></span> <span data-ttu-id="2e0a2-168">Durch Verschieben des Splattings an das Ende der Argumentliste wird die Reihenfolge geändert, in der die Parameter in `$args` angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-168">Moving splatting to the end of the argument list changes the order the parameters appears in `$args`.</span></span>

  <span data-ttu-id="2e0a2-169">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="2e0a2-169">For example:</span></span>

  ```powershell
  function SimpleTest {
      param(
          $Name,
          $Path
      )
      "Name: $Name; Path: $Path; Args: $args"
  }
  ```

  <span data-ttu-id="2e0a2-170">Im vorherigen Verhalten ist **MyPath** das dritte Argument in der Argumentliste und daher nicht an `-Path` gebunden.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-170">In the previous behavior, **MyPath** is not bound to `-Path` because it's the third argument in the argument list.</span></span> <span data-ttu-id="2e0a2-171">Aus diesem Grund wird MyPath zusammen mit `Blah = "World"` in $args platziert.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-171">## So it ends up being stuffed into '$args' along with `Blah = "World"`</span></span>

  ```powershell
  PS> $hash = @{ Name = "Hello"; Blah = "World" }
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: ; Args: -Blah: World MyPath
  ```

  <span data-ttu-id="2e0a2-172">Mit dieser Änderung werden die Argumente aus `@hash` an das Ende der Argumentliste verschoben.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-172">With this change, the arguments from `@hash` are moved to the end of the argument list.</span></span> <span data-ttu-id="2e0a2-173">**MyPath** wird zum ersten Argument in der Liste, sodass es an `-Path` gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-173">**MyPath** becomes the first argument in the list, so it is bound to `-Path`.</span></span>

  ```powershell
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: MyPath; Args: -Blah: World
  ```

- <span data-ttu-id="2e0a2-174">Umgestaltung des Parameters `-Qualifier` als nicht positionell für `Split-Path` ([#12960](https://github.com/PowerShell/PowerShell/pull/12960), mit bestem Dank an @yecril71pl)</span><span class="sxs-lookup"><span data-stu-id="2e0a2-174">Make the switch parameter `-Qualifier` not positional for `Split-Path` ([#12960](https://github.com/PowerShell/PowerShell/pull/12960)) (Thanks @yecril71pl!)</span></span>

- <span data-ttu-id="2e0a2-175">Auflösung des Arbeitsverzeichnisses als Literalpfad für `Start-Process`, wenn es nicht angegeben wird ([#11946](https://github.com/PowerShell/PowerShell/pull/11946), mit bestem Dank an @NoMoreFood)</span><span class="sxs-lookup"><span data-stu-id="2e0a2-175">Resolve the working directory as literal path for `Start-Process` when it's not specified ([#11946](https://github.com/PowerShell/PowerShell/pull/11946)) (Thanks @NoMoreFood!)</span></span>

- <span data-ttu-id="2e0a2-176">Umgestaltung des Parameters `-OutFile` in Web-Cmdlets, sodass er wie `-LiteralPath` funktioniert ([#11701](https://github.com/PowerShell/PowerShell/pull/11701), mit bestem Dank an @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="2e0a2-176">Make `-OutFile` parameter in web cmdlets to work like `-LiteralPath` ([#11701](https://github.com/PowerShell/PowerShell/pull/11701)) (Thanks @iSazonov!)</span></span>

- <span data-ttu-id="2e0a2-177">Korrektur der Bindung von Zeichenfolgenparametern für numerische Literale des Typs `BigInteger` ([#11634](https://github.com/PowerShell/PowerShell/pull/11634), mit bestem Dank an @vexx32)</span><span class="sxs-lookup"><span data-stu-id="2e0a2-177">Fix string parameter binding for `BigInteger` numeric literals ([#11634](https://github.com/PowerShell/PowerShell/pull/11634)) (Thanks @vexx32!)</span></span>

- <span data-ttu-id="2e0a2-178">Unter Windows wird mit `Start-Process` eine Prozessumgebung mit allen Umgebungsvariablen der aktuellen Sitzung erstellt, wobei mit `-UseNewEnvironment` eine neue Standardprozessumgebung geschaffen wird ([#10830](https://github.com/PowerShell/PowerShell/pull/10830), mit bestem Dank an @iSazonov)</span><span class="sxs-lookup"><span data-stu-id="2e0a2-178">On Windows, `Start-Process` creates a process environment with all the environment variables from current session, using `-UseNewEnvironment` creates a new default process environment ([#10830](https://github.com/PowerShell/PowerShell/pull/10830)) (Thanks @iSazonov!)</span></span>

- <span data-ttu-id="2e0a2-179">Zurückgegebenes Ergebnis nicht in `PSObject` umschließen, wenn `ScriptBlock` in einen Delegaten konvertiert wird ([#10619](https://github.com/PowerShell/PowerShell/pull/10619))</span><span class="sxs-lookup"><span data-stu-id="2e0a2-179">Do not wrap return result in `PSObject` when converting a `ScriptBlock` to a delegate ([#10619](https://github.com/PowerShell/PowerShell/pull/10619))</span></span>

  <span data-ttu-id="2e0a2-180">Wenn `ScriptBlock` in einen Delegattyp konvertiert wird, der im C#-Kontext verwendet werden soll, führt das Umschließen des Ergebnisses in `PSObject` zu unnötigen Problemen:</span><span class="sxs-lookup"><span data-stu-id="2e0a2-180">When a `ScriptBlock` is converted to a delegate type to be used in C# context, wrapping the result in a `PSObject` brings unneeded troubles:</span></span>

  - <span data-ttu-id="2e0a2-181">Wenn der Wert in den Rückgabetyp des Delegaten konvertiert wird, wird `PSObject` im Wesentlichen entpackt.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-181">When the value is converted to the delegate return type, the `PSObject` essentially gets unwrapped.</span></span> <span data-ttu-id="2e0a2-182">`PSObject` ist daher nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-182">So the `PSObject` is unneeded.</span></span>
  - <span data-ttu-id="2e0a2-183">Wenn der Rückgabetyp des Delegaten `object` ist, wird er in `PSObject` umschlossen, was die Verwendung in C#-Code erschwert.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-183">When the delegate return type is `object`, it gets wrapped in a `PSObject` making it hard to work with in C# code.</span></span>

  <span data-ttu-id="2e0a2-184">Nach dieser Änderung entspricht das zurückgegebene Objekt dem zugrunde liegenden Objekt.</span><span class="sxs-lookup"><span data-stu-id="2e0a2-184">After this change, the returned object is the underlying object.</span></span>
