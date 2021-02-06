---
ms.date: 07/10/2019
keywords: jea,powershell,security
title: JEA-Voraussetzungen
description: In diesem Artikel werden die Voraussetzungen erläutert, die erfüllt sein müssen, um JEA verwenden zu können.
ms.openlocfilehash: 5cc70a06887a2d0a840cc83117f865d3148056e1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501727"
---
# <a name="prerequisites"></a><span data-ttu-id="9e2a4-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9e2a4-104">Prerequisites</span></span>

<span data-ttu-id="9e2a4-105">„Just Enough Administration“ ist ein in PowerShell 5.0 und höher enthaltenes Feature.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-105">Just Enough Administration is a feature included in PowerShell 5.0 and higher.</span></span> <span data-ttu-id="9e2a4-106">In diesem Artikel werden die Voraussetzungen erläutert, die erfüllt sein müssen, um JEA verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-106">This article describes the prerequisites that must be satisfied to start using JEA.</span></span>

## <a name="check-which-version-of-powershell-is-installed"></a><span data-ttu-id="9e2a4-107">Überprüfen der installierten Version von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e2a4-107">Check which version of PowerShell is installed</span></span>

<span data-ttu-id="9e2a4-108">Überprüfen Sie die `$PSVersionTable`-Variable in einer Windows PowerShell-Aufforderung, um festzustellen, welche PowerShell-Version auf Ihrem System installiert ist.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-108">To check which version of PowerShell is installed on your system, check the `$PSVersionTable` variable in a Windows PowerShell prompt.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  1000
```

<span data-ttu-id="9e2a4-109">JEA ist mit PowerShell 5.0 oder höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-109">JEA is available with PowerShell 5.0 and higher.</span></span> <span data-ttu-id="9e2a4-110">Wenn Sie jedoch die vollständige Funktionalität nutzen möchten, empfehlen wir Ihnen die Installation der neuesten Version von PowerShell für Ihr Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-110">For full functionality, it's recommended that you install the latest version of PowerShell available for your system.</span></span> <span data-ttu-id="9e2a4-111">Die folgende Tabelle beschreibt die Verfügbarkeit von JEA unter Windows Server:</span><span class="sxs-lookup"><span data-stu-id="9e2a4-111">The following table describes JEA's availability on Windows Server:</span></span>

| <span data-ttu-id="9e2a4-112">Serverbetriebssystem</span><span class="sxs-lookup"><span data-stu-id="9e2a4-112">Server Operating System</span></span> |                <span data-ttu-id="9e2a4-113">JEA-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="9e2a4-113">JEA Availability</span></span>                |
| ----------------------- | ---------------------------------------------- |
| <span data-ttu-id="9e2a4-114">Windows Server 2016+</span><span class="sxs-lookup"><span data-stu-id="9e2a4-114">Windows Server 2016+</span></span>    | <span data-ttu-id="9e2a4-115">Vorinstalliert</span><span class="sxs-lookup"><span data-stu-id="9e2a4-115">Preinstalled</span></span>                                   |
| <span data-ttu-id="9e2a4-116">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9e2a4-116">Windows Server 2012 R2</span></span>  | <span data-ttu-id="9e2a4-117">Vollständige Funktionalität mit WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="9e2a4-117">Full functionality with WMF 5.1</span></span>                |
| <span data-ttu-id="9e2a4-118">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9e2a4-118">Windows Server 2012</span></span>     | <span data-ttu-id="9e2a4-119">Vollständige Funktionalität mit WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="9e2a4-119">Full functionality with WMF 5.1</span></span>                |
| <span data-ttu-id="9e2a4-120">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9e2a4-120">Windows Server 2008 R2</span></span>  | <span data-ttu-id="9e2a4-121">Reduzierte Funktionalität<sup>1</sup> mit WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="9e2a4-121">Reduced functionality<sup>1</sup> with WMF 5.1</span></span> |

<span data-ttu-id="9e2a4-122">Sie können JEA auch auf Ihrem Heim- oder Firmencomputer verwenden:</span><span class="sxs-lookup"><span data-stu-id="9e2a4-122">You can also use JEA on your home or work computer:</span></span>

| <span data-ttu-id="9e2a4-123">Clientbetriebssystem</span><span class="sxs-lookup"><span data-stu-id="9e2a4-123">Client Operating System</span></span> |                   <span data-ttu-id="9e2a4-124">JEA-Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="9e2a4-124">JEA Availability</span></span>                   |
| ----------------------- | ---------------------------------------------------- |
| <span data-ttu-id="9e2a4-125">Windows 10 1607+</span><span class="sxs-lookup"><span data-stu-id="9e2a4-125">Windows 10 1607+</span></span>        | <span data-ttu-id="9e2a4-126">Vorinstalliert</span><span class="sxs-lookup"><span data-stu-id="9e2a4-126">Preinstalled</span></span>                                         |
| <span data-ttu-id="9e2a4-127">Windows 10 1603, 1511</span><span class="sxs-lookup"><span data-stu-id="9e2a4-127">Windows 10 1603, 1511</span></span>   | <span data-ttu-id="9e2a4-128">Vorinstalliert, mit eingeschränkter Funktionalität<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9e2a4-128">Preinstalled, with reduced functionality<sup>2</sup></span></span> |
| <span data-ttu-id="9e2a4-129">Windows 10 1507</span><span class="sxs-lookup"><span data-stu-id="9e2a4-129">Windows 10 1507</span></span>         | <span data-ttu-id="9e2a4-130">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="9e2a4-130">Not available</span></span>                                        |
| <span data-ttu-id="9e2a4-131">Windows 8, 8.1</span><span class="sxs-lookup"><span data-stu-id="9e2a4-131">Windows 8, 8.1</span></span>          | <span data-ttu-id="9e2a4-132">Vollständige Funktionalität mit WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="9e2a4-132">Full functionality with WMF 5.1</span></span>                      |
| <span data-ttu-id="9e2a4-133">Windows 7</span><span class="sxs-lookup"><span data-stu-id="9e2a4-133">Windows 7</span></span>               | <span data-ttu-id="9e2a4-134">Reduzierte Funktionalität<sup>1</sup> mit WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="9e2a4-134">Reduced functionality<sup>1</sup> with WMF 5.1</span></span>       |

- <span data-ttu-id="9e2a4-135"><sup>1</sup> JEA kann nicht konfiguriert werden, um gruppenverwaltete Dienstkonten unter Windows Server 2008 R2 oder Windows 7 zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-135"><sup>1</sup> JEA can't be configured to use group-managed service accounts on Windows Server 2008 R2 or Windows 7.</span></span> <span data-ttu-id="9e2a4-136">Virtuelle Konten und andere JEA-Features *werden* unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-136">Virtual accounts and other JEA features *are* supported.</span></span>

- <span data-ttu-id="9e2a4-137"><sup>2</sup> Die folgenden JEA-Features werden in den Windows 10-Versionen 1511 und 1603 nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9e2a4-137"><sup>2</sup> The following JEA features aren't supported on Windows 10 versions 1511 and 1603:</span></span>

  - <span data-ttu-id="9e2a4-138">Ausführen als gruppenverwaltetes Dienstkonto</span><span class="sxs-lookup"><span data-stu-id="9e2a4-138">Running as a group-managed service account</span></span>
  - <span data-ttu-id="9e2a4-139">Bedingte Zugriffsregeln in Sitzungskonfigurationen</span><span class="sxs-lookup"><span data-stu-id="9e2a4-139">Conditional access rules in session configurations</span></span>
  - <span data-ttu-id="9e2a4-140">Das Benutzerlaufwerk</span><span class="sxs-lookup"><span data-stu-id="9e2a4-140">The user drive</span></span>
  - <span data-ttu-id="9e2a4-141">Gewähren des Zugriffs auf lokale Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="9e2a4-141">Granting access to local user accounts</span></span>

  <span data-ttu-id="9e2a4-142">Aktualisieren Sie Windows auf Version 1607 (Anniversary Update) oder höher, um Unterstützung für diese Features zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-142">To get support for these features, update Windows to version 1607 (Anniversary Update) or higher.</span></span>

### <a name="install-windows-management-framework"></a><span data-ttu-id="9e2a4-143">Installieren von Windows Management Framework</span><span class="sxs-lookup"><span data-stu-id="9e2a4-143">Install Windows Management Framework</span></span>

<span data-ttu-id="9e2a4-144">Wenn Sie eine ältere Version von PowerShell ausführen, müssen Sie Ihr System möglicherweise mit dem aktuellen Update von Windows Management Framework (WMF) aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-144">If you're running an older version of PowerShell, you may need to update your system with the latest Windows Management Framework (WMF) update.</span></span> <span data-ttu-id="9e2a4-145">Weitere Informationen finden Sie in der [WMF-Dokumentation](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="9e2a4-145">For more information, see the [WMF documentation](/powershell/scripting/wmf/overview).</span></span>

<span data-ttu-id="9e2a4-146">Es wird empfohlen, vor dem Upgrade aller Server die Kompatibilität Ihrer Workload mit WMF zu testen.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-146">It's recommended that you test your workload's compatibility with WMF before upgrading all of your servers.</span></span>

<span data-ttu-id="9e2a4-147">Windows 10-Benutzer sollten die neuesten Funktionsupdates zum Abrufen der aktuellen Version von Windows PowerShell installieren.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-147">Windows 10 users should install the latest feature updates to obtain the current version of Windows PowerShell.</span></span>

## <a name="enable-powershell-remoting"></a><span data-ttu-id="9e2a4-148">Aktivieren von PowerShell-Remoting</span><span class="sxs-lookup"><span data-stu-id="9e2a4-148">Enable PowerShell Remoting</span></span>

<span data-ttu-id="9e2a4-149">PowerShell-Remoting stellt die Grundlage für JEA dar.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-149">PowerShell Remoting provides the foundation on which JEA is built.</span></span> <span data-ttu-id="9e2a4-150">Sie müssen sicherstellen, dass PowerShell-Remoting aktiviert und ordnungsgemäß abgesichert ist, bevor Sie JEA verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-150">It's necessary to ensure PowerShell Remoting is enabled and properly secured before you can use JEA.</span></span> <span data-ttu-id="9e2a4-151">Weitere Informationen finden Sie im [Artikel zu WinRM-Sicherheit.](/powershell/scripting/learn/remoting/winrmsecurity)</span><span class="sxs-lookup"><span data-stu-id="9e2a4-151">For more information, see [WinRM Security](/powershell/scripting/learn/remoting/winrmsecurity).</span></span>

<span data-ttu-id="9e2a4-152">PowerShell-Remoting ist unter Windows Server 2012, 2012 R2 und 2016 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-152">PowerShell Remoting is enabled by default on Windows Server 2012, 2012 R2, and 2016.</span></span> <span data-ttu-id="9e2a4-153">Sie können PowerShell-Remoting aktivieren, indem Sie den folgenden Befehl in einem PowerShell-Fenster mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-153">You can enable PowerShell Remoting by running the following command in an elevated PowerShell window.</span></span>

```powershell
Enable-PSRemoting
```

## <a name="enable-powershell-module-and-script-block-logging-optional"></a><span data-ttu-id="9e2a4-154">Aktivieren der PowerShell-Modul- und Skriptblockprotokollierung (optional)</span><span class="sxs-lookup"><span data-stu-id="9e2a4-154">Enable PowerShell module and script block logging (optional)</span></span>

<span data-ttu-id="9e2a4-155">Die folgenden Schritte aktivieren die Protokollierung für alle PowerShell-Aktionen in Ihrem System.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-155">The following steps enable logging for all PowerShell actions on your system.</span></span> <span data-ttu-id="9e2a4-156">Für JEA ist die PowerShell-Modulprotokollierung nicht erforderlich. Es wird jedoch empfohlen, dass Sie die Protokollierung aktivieren, um sicherzustellen, dass von Benutzern ausgeführte Befehle zentral protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-156">PowerShell Module Logging isn't required for JEA, however it's recommended you turn on logging to ensure the commands users run are logged in a central location.</span></span>

<span data-ttu-id="9e2a4-157">Sie können die Richtlinien für die PowerShell-Modulprotokollierung mithilfe von Gruppenrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-157">You can configure the PowerShell Module Logging policy using Group Policy.</span></span>

1. <span data-ttu-id="9e2a4-158">Öffnen Sie den Editor für lokale Gruppenrichtlinien auf einer Arbeitsstation oder ein Gruppenrichtlinienobjekt in der Gruppenrichtlinien-Verwaltungskonsole auf einem Active Directory-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-158">Open the Local Group Policy Editor on a workstation or a Group Policy Object in the Group Policy Management Console on an Active Directory Domain Controller</span></span>
2. <span data-ttu-id="9e2a4-159">Navigieren Sie zu **Computerkonfiguration\\Administrative Vorlagen\\Windows-Komponenten\\Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-159">Navigate to **Computer Configuration\\Administrative Templates\\Windows Components\\Windows PowerShell**</span></span>
3. <span data-ttu-id="9e2a4-160">Doppelklicken Sie auf **Modulprotokollierung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-160">Double-click on **Turn on Module Logging**</span></span>
4. <span data-ttu-id="9e2a4-161">Klicken Sie auf **Aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-161">Click **Enabled**</span></span>
5. <span data-ttu-id="9e2a4-162">Klicken Sie im Abschnitt „Optionen“ neben den Modulnamen auf **Anzeigen**</span><span class="sxs-lookup"><span data-stu-id="9e2a4-162">In the Options section, click on **Show** next to Module Names</span></span>
6. <span data-ttu-id="9e2a4-163">Geben Sie `*` im Popupfenster ein, um Befehle aus allen Modulen zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-163">Type `*` in the pop-up window to log commands from all modules.</span></span>
7. <span data-ttu-id="9e2a4-164">Klicken Sie auf **OK**, um die Richtlinie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-164">Click **OK** to set the policy</span></span>
8. <span data-ttu-id="9e2a4-165">Doppelklicken Sie anschließend auf **Protokollierung von PowerShell-Skriptblöcken aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-165">Double-click on **Turn on PowerShell Script Block Logging**</span></span>
9. <span data-ttu-id="9e2a4-166">Klicken Sie auf **Aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-166">Click **Enabled**</span></span>
10. <span data-ttu-id="9e2a4-167">Klicken Sie auf **OK**, um die Richtlinie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-167">Click **OK** to set the policy</span></span>
11. <span data-ttu-id="9e2a4-168">(Nur in die Domäne eingebundene Computer:) Führen Sie `gpupdate` aus, oder warten Sie, bis die Gruppenrichtlinie die aktualisierte Richtlinie verarbeitet hat und diese Einstellungen anwendet.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-168">(On domain-joined machines only) Run `gpupdate` or wait for Group Policy to process the updated policy and apply the settings</span></span>

<span data-ttu-id="9e2a4-169">Sie können über eine Gruppenrichtlinie auch die systemweite PowerShell-Aufzeichnung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9e2a4-169">You can also enable system-wide PowerShell transcription through Group Policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9e2a4-170">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9e2a4-170">Next steps</span></span>

[<span data-ttu-id="9e2a4-171">Create a role capability file (Erstellen einer Rollenfunktionsdatei)</span><span class="sxs-lookup"><span data-stu-id="9e2a4-171">Create a role capability file</span></span>](role-capabilities.md)

[<span data-ttu-id="9e2a4-172">Create a session configuration file (Erstellen einer Sitzungskonfigurationsdatei)</span><span class="sxs-lookup"><span data-stu-id="9e2a4-172">Create a session configuration file</span></span>](session-configurations.md)

## <a name="see-also"></a><span data-ttu-id="9e2a4-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e2a4-173">See also</span></span>

[<span data-ttu-id="9e2a4-174">WinRM-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9e2a4-174">WinRM Security</span></span>](/powershell/scripting/learn/remoting/winrmsecurity)

[<span data-ttu-id="9e2a4-175">PowerShell ♥ das Blue Team</span><span class="sxs-lookup"><span data-stu-id="9e2a4-175">PowerShell ♥ the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)
