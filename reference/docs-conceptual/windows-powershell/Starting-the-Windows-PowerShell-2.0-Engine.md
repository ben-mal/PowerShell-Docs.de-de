---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Verwenden der Windows PowerShell 2.0 Engine
description: Die Windows PowerShell 2.0-Engine soll nur zum Einsatz kommen, wenn ein vorhandenes Skript oder Hostprogramm nicht ausgeführt werden kann, da für Windows PowerShell 2.0 geschriebene und mit CLR 2.0 kompilierte Hostprogramme nicht ohne Änderungen ausgeführt werden können.
ms.openlocfilehash: 214b87b7314f31974801bb07f98ddea3b68008f0
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664008"
---
# <a name="using-the-windows-powershell-20-engine"></a><span data-ttu-id="e5b39-104">Verwenden der Windows PowerShell 2.0 Engine</span><span class="sxs-lookup"><span data-stu-id="e5b39-104">Using the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="e5b39-105">Windows PowerShell darauf ausgelegt, mit früheren Versionen abwärtskompatibel zu sein.</span><span class="sxs-lookup"><span data-stu-id="e5b39-105">Windows PowerShell is designed to be backward compatible with previous versions.</span></span> <span data-ttu-id="e5b39-106">Cmdlets, Anbieter, Snap-Ins, Module und Skripts, die für Windows PowerShell 2.0 geschrieben wurden, können unverändert in neueren Versionen von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e5b39-106">Cmdlets, providers, snap-ins, modules, and scripts written for Windows PowerShell 2.0 run unchanged in newer versions Windows PowerShell.</span></span> <span data-ttu-id="e5b39-107">In Microsoft .NET Framework 4 wurde jedoch die Richtlinie für die Laufzeitaktivierung geändert.</span><span class="sxs-lookup"><span data-stu-id="e5b39-107">However, Microsoft .NET Framework 4 changed the runtime activation policy.</span></span>
<span data-ttu-id="e5b39-108">Windows PowerShell-Hostprogramme, die für Windows PowerShell 2.0 geschrieben und mit Common Language Runtime (CLR) 2.0 kompiliert wurden, können nicht unverändert in neuen Versionen von Windows PowerShell ausgeführt werden, die mit CLR 4.0 (oder höher) kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="e5b39-108">Windows PowerShell host programs written for Windows PowerShell 2.0 and compiled with Common Language Runtime (CLR) 2.0 cannot run without modification in new versions Windows PowerShell that are compiled with CLR 4.0 (or higher).</span></span>

<span data-ttu-id="e5b39-109">Die Windows PowerShell 2.0 Engine sollte nur verwendet werden, wenn ein vorhandenes Skript oder Hostprogramm nicht ausgeführt werden kann, da es inkompatibel mit Windows PowerShell 5.1 ist.</span><span class="sxs-lookup"><span data-stu-id="e5b39-109">The Windows PowerShell 2.0 Engine is intended to be used only when an existing script or host program cannot run because it is incompatible with Windows PowerShell 5.1.</span></span> <span data-ttu-id="e5b39-110">Beispiele hierfür sind ältere Versionen von Exchange oder SQL Server-Modulen.</span><span class="sxs-lookup"><span data-stu-id="e5b39-110">Examples of this include older versions of Exchange or SQL Server modules.</span></span> <span data-ttu-id="e5b39-111">Solche Fälle sind allerdings eher selten.</span><span class="sxs-lookup"><span data-stu-id="e5b39-111">Such cases are expected to be rare.</span></span>

<span data-ttu-id="e5b39-112">Viele Programme, die Windows PowerShell 2.0 Engine benötigen, starten sie automatisch.</span><span class="sxs-lookup"><span data-stu-id="e5b39-112">Many programs that require the Windows PowerShell 2.0 Engine start it automatically.</span></span> <span data-ttu-id="e5b39-113">Diese Anweisungen gelten für die seltenen Fälle, in denen Sie die Engine manuell starten müssen.</span><span class="sxs-lookup"><span data-stu-id="e5b39-113">These instructions are included for the rare situations in which you need to start the engine manually.</span></span>

## <a name="deprecation-and-security-concerns"></a><span data-ttu-id="e5b39-114">Eingestellte Unterstützung und Sicherheitsaspekte</span><span class="sxs-lookup"><span data-stu-id="e5b39-114">Deprecation and security concerns</span></span>

<span data-ttu-id="e5b39-115">Windows PowerShell 2.0 wurde im August 2017 eingestellt.</span><span class="sxs-lookup"><span data-stu-id="e5b39-115">Windows PowerShell 2.0 was deprecated in August, 2017.</span></span> <span data-ttu-id="e5b39-116">Weitere Informationen finden Sie in der [Ankündigung][] im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="e5b39-116">For more information, see the [announcement][] on the PowerShell blog.</span></span>

<span data-ttu-id="e5b39-117">In Windows PowerShell 2.0 fehlt eine beträchtliche Menge der Härtungs- und Sicherheitsfeatures, die in den Versionen 3, 4 und 5 hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="e5b39-117">Windows PowerShell 2.0 is missing a significant amount of the hardening and security features added in versions 3, 4, and 5.</span></span> <span data-ttu-id="e5b39-118">Es wird dringend empfohlen, dass Benutzer diese Version nicht verwenden, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e5b39-118">We highly, highly recommend that users not use it if they can help it.</span></span> <span data-ttu-id="e5b39-119">Weitere Informationen finden Sie unter [Ein Vergleich der Sicherheit von Shell- und Skriptsprachen][] und [PowerShell ♥ The Blue Team][blueteam].</span><span class="sxs-lookup"><span data-stu-id="e5b39-119">For more information, see [A Comparison of Shell and Scripting Language Security][] and [PowerShell ♥ the Blue Team][blueteam].</span></span>

## <a name="installing-and-enabling-required-programs"></a><span data-ttu-id="e5b39-120">Installieren und Aktivieren erforderlicher Programme</span><span class="sxs-lookup"><span data-stu-id="e5b39-120">Installing and Enabling Required Programs</span></span>

<span data-ttu-id="e5b39-121">Aktivieren Sie Windows PowerShell 2.0 Engine und Microsoft .NET Framework 3.5 mit Service Pack 1, bevor Sie Windows PowerShell 2.0 Engine starten.</span><span class="sxs-lookup"><span data-stu-id="e5b39-121">Before starting the Windows PowerShell 2.0 Engine, enable the Windows PowerShell 2.0 Engine and Microsoft .NET Framework 3.5 with Service Pack 1.</span></span> <span data-ttu-id="e5b39-122">Anweisungen hierzu finden Sie unter [Installieren von Windows PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="e5b39-122">For instructions, see [Installing Windows PowerShell][].</span></span>

<span data-ttu-id="e5b39-123">Systeme, auf denen Windows Management Framework 3.0 oder höher installiert ist, verfügen über alle erforderlichen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="e5b39-123">Systems on which Windows Management Framework 3.0 or higher is installed have all of the required components.</span></span> <span data-ttu-id="e5b39-124">Es ist keine weitere Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5b39-124">No further configuration is necessary.</span></span> <span data-ttu-id="e5b39-125">Informationen zum Installieren von Windows Management Framework finden Sie unter [Installieren und Konfigurieren von WMF][].</span><span class="sxs-lookup"><span data-stu-id="e5b39-125">For information about installing Windows Management Framework, see [Install and configure WMF][].</span></span>

## <a name="how-to-start-the-windows-powershell-20-engine"></a><span data-ttu-id="e5b39-126">So starten Sie Windows PowerShell 2.0 Engine</span><span class="sxs-lookup"><span data-stu-id="e5b39-126">How to start the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="e5b39-127">Beim Starten von Windows PowerShell wird die neueste Version standardmäßig gestartet.</span><span class="sxs-lookup"><span data-stu-id="e5b39-127">When you start Windows PowerShell the newest version starts by default.</span></span> <span data-ttu-id="e5b39-128">Verwenden Sie den „Version“-Parameter von `PowerShell.exe`, um Windows PowerShell mit Windows PowerShell 2.0 Engine zu starten.</span><span class="sxs-lookup"><span data-stu-id="e5b39-128">To start Windows PowerShell with the Windows PowerShell 2.0 Engine, use the Version parameter of `PowerShell.exe`.</span></span> <span data-ttu-id="e5b39-129">Sie können den Befehl an jeder Eingabeaufforderung einschließlich Windows PowerShell und „Cmd.exe“ ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5b39-129">You can run the command at any command prompt, including Windows PowerShell and Cmd.exe.</span></span>

```
PowerShell.exe -Version 2
```

## <a name="how-to-start-a-remote-session-with-the-windows-powershell-20-engine"></a><span data-ttu-id="e5b39-130">So starten Sie eine Remotesitzung mit Windows PowerShell 2.0 Engine</span><span class="sxs-lookup"><span data-stu-id="e5b39-130">How to start a remote session with the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="e5b39-131">Erstellen Sie auf dem Remotecomputer eine Sitzungskonfiguration (auch _Endpunkt_ genannt), die Windows PowerShell 2.0 Engine lädt, um Windows PowerShell 2.0 Engine in einer Remotesitzung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e5b39-131">To run the Windows PowerShell 2.0 Engine in a remote session, create a session configuration (also known as an _endpoint_ ) on the remote computer that loads the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="e5b39-132">Die Sitzungskonfiguration wird auf dem Remotecomputer gespeichert und kann von jedem autorisierten Benutzer verwendet werden, um Sitzungen zu erstellen, die Windows PowerShell 2.0 Engine verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5b39-132">The session configuration is saved on the remote computer and can be used by any authorized user to create sessions that use the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="e5b39-133">Dies ist eine komplexe Aufgabe, die in der Regel von einem Systemadministrator ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e5b39-133">This is an advanced task that is typically performed by a system administrator.</span></span>

<span data-ttu-id="e5b39-134">Im folgenden Verfahren wird der **PSVersion** -Parameter des Cmdlets [Register-PSSessionConfiguration][] zum Erstellen einer Sitzungskonfiguration verwendet, die Windows PowerShell 2.0 Engine nutzt.</span><span class="sxs-lookup"><span data-stu-id="e5b39-134">The following procedure uses the **PSVersion** parameter of the [Register-PSSessionConfiguration][] cmdlet to create a session configuration that uses the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="e5b39-135">Sie können auch den **PowerShellVersion** -Parameter des Cmdlets [New-PSSessionConfigurationFile][] verwenden, um eine Sitzungskonfigurationsdatei für eine Sitzung zu erstellen, die Windows PowerShell 2.0 Engine lädt. Sie können auch den **PSVersion** -Parameter des Parameters [Set-PSSessionConfiguration][] verwenden, um eine Sitzungskonfiguration so zu ändern, dass Windows PowerShell 2.0 Engine verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e5b39-135">You can also use the **PowerShellVersion** parameter of the [New-PSSessionConfigurationFile][] cmdlet to create a session configuration file for a session that loads the Windows PowerShell 2.0 Engine and you can use the **PSVersion** parameter of the [Set-PSSessionConfiguration][] parameter to change a session configuration to use the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="e5b39-136">Weitere Informationen zu Sitzungskonfigurationsdateien finden Sie unter [about_Session_Configuration_Files][].</span><span class="sxs-lookup"><span data-stu-id="e5b39-136">For more information about session configuration files, see [about_Session_Configuration_Files][].</span></span>
<span data-ttu-id="e5b39-137">Informationen zu Sitzungskonfigurationen, einschließlich Einrichtung und Sicherheit, finden Sie unter [about_Session_Configurations][].</span><span class="sxs-lookup"><span data-stu-id="e5b39-137">For information about session configurations, including setup and security, see [about_Session_Configurations][].</span></span>

### <a name="to-start-a-remote-windows-powershell-20-session"></a><span data-ttu-id="e5b39-138">Gehen Sie folgendermaßen vor, um eine Remotesitzung von Windows PowerShell 2.0 zu starten</span><span class="sxs-lookup"><span data-stu-id="e5b39-138">To start a remote Windows PowerShell 2.0 session</span></span>

1. <span data-ttu-id="e5b39-139">Verwenden Sie den **PSVersion** -Parameter des Cmdlets `Register-PSSessionConfiguration` mit dem Wert `2.0`, um eine Sitzungskonfiguration zu erstellen, die Windows PowerShell 2.0 Engine erfordert.</span><span class="sxs-lookup"><span data-stu-id="e5b39-139">To create a session configuration that requires the Windows PowerShell 2.0 Engine, use the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet with a value of `2.0`.</span></span>
   <span data-ttu-id="e5b39-140">Führen Sie diesen Befehl auf dem Computer auf der Serverseite oder dem empfangenden Ende der Verbindung aus.</span><span class="sxs-lookup"><span data-stu-id="e5b39-140">Run this command on the computer at the "server side" or receiving end of the connection.</span></span>

   <span data-ttu-id="e5b39-141">Der folgende Befehl erstellt die PS2-Sitzungskonfiguration auf dem Computer „Server01“.</span><span class="sxs-lookup"><span data-stu-id="e5b39-141">The following sample command creates the PS2 session configuration on the Server01 computer.</span></span> <span data-ttu-id="e5b39-142">Starten Sie Windows PowerShell mit der Option **Als Administrator ausführen** , um diesen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e5b39-142">To run this command, start Windows PowerShell with the **Run as administrator** option.</span></span>

   ```powershell
   Register-PSSessionConfiguration -Name PS2 -PSVersion 2.0
   ```

1. <span data-ttu-id="e5b39-143">Zum Erstellen einer Sitzung auf dem Computer „Server01“, der die PS2-Sitzungskonfiguration nutzt, verwenden Sie den **ConfigurationName** -Parameter von Cmdlets, die eine Remotesitzung aufbauen, wie z. B. das Cmdlet „New-PSSession“.</span><span class="sxs-lookup"><span data-stu-id="e5b39-143">To create a session on the Server01 computer that uses the PS2 session configuration, use the **ConfigurationName** parameter of cmdlets that create a remote session, such as the \`New-PSSession cmdlet.</span></span>

   <span data-ttu-id="e5b39-144">Wenn eine Sitzung gestartet wird, die die Sitzungskonfiguration verwendet, wird Windows PowerShell 2.0 Engine automatisch in die Sitzung geladen.</span><span class="sxs-lookup"><span data-stu-id="e5b39-144">When a session that uses the session configuration starts, the Windows PowerShell 2.0 Engine is automatically loaded into the session.</span></span>

   <span data-ttu-id="e5b39-145">Der folgende Befehl erstellt eine Sitzung auf dem Computer „Server01“, die die PS2-Sitzungskonfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5b39-145">The following command starts a session on the Server01 computer that uses the PS2 session configuration.</span></span> <span data-ttu-id="e5b39-146">Der Befehl speichert die Sitzung in der Variablen `$s`.</span><span class="sxs-lookup"><span data-stu-id="e5b39-146">The command saves the session in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -ComputerName Server01 -ConfigurationName PS2
   ```

## <a name="how-to-start-a-background-job-with-the-windows-powershell-20-engine"></a><span data-ttu-id="e5b39-147">So starten Sie einen Hintergrundauftrags mit Windows PowerShell 2.0 Engine</span><span class="sxs-lookup"><span data-stu-id="e5b39-147">How to start a background job with the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="e5b39-148">Verwenden Sie den **PSVersion** -Parameter des Cmdlets [Start-Job][] zum Starten eines Hintergrundauftrags mit Windows PowerShell 2.0 Engine.</span><span class="sxs-lookup"><span data-stu-id="e5b39-148">To start a background job with the Windows PowerShell 2.0 Engine, use the **PSVersion** parameter of the [Start-Job][] cmdlet.</span></span>

<span data-ttu-id="e5b39-149">Der folgende Befehl startet einen Hintergrundauftrag mit Windows PowerShell 2.0 Engine</span><span class="sxs-lookup"><span data-stu-id="e5b39-149">The following command starts a background job with the Windows PowerShell 2.0 Engine</span></span>

```powershell
Start-Job {Get-Process} -PSVersion 2.0
```

<span data-ttu-id="e5b39-150">Weitere Informationen zu Hintergrundaufträgen finden Sie unter [about_Jobs][].</span><span class="sxs-lookup"><span data-stu-id="e5b39-150">For more information about background jobs, see [about_Jobs][].</span></span>

<!-- link references -->
[Ankündigung]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[announcement]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[Ein Vergleich der Sicherheit von Shell- und Skriptsprachen]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/
[A Comparison of Shell and Scripting Language Security]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/
[blueteam]: https://devblogs.microsoft.com/powershell/powershell-the-blue-team/
[Installieren von Windows PowerShell]: install/Installing-Windows-PowerShell.md
[Installing Windows PowerShell]: install/Installing-Windows-PowerShell.md
[Installieren und Konfigurieren von WMF]: wmf/setup/install-configure.md
[Install and configure WMF]: wmf/setup/install-configure.md
[Register-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration
[New-PSSessionConfigurationFile]: /powershell/module/Microsoft.PowerShell.Core/New-PSSessionConfigurationFile
[Set-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration
[about_Session_Configuration_Files]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configuration_Files
[about_Session_Configurations]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configurations
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[about_Jobs]: /powershell/module/microsoft.powershell.core/about/about_jobs
