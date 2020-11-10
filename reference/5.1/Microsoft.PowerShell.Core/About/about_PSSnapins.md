---
description: Beschreibt Windows PowerShell-Snap-Ins und zeigt, wie Sie verwendet und verwaltet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSnapins
ms.openlocfilehash: 494b3275e4fe8a3aacdc358317950542962957cf
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388891"
---
# <a name="about-pssnapins"></a><span data-ttu-id="18b20-104">Informationen zu pssnapins</span><span class="sxs-lookup"><span data-stu-id="18b20-104">About PSSnapins</span></span>

## <a name="short-description"></a><span data-ttu-id="18b20-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="18b20-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="18b20-106">Beschreibt Windows PowerShell-Snap-Ins und zeigt, wie Sie verwendet und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="18b20-106">Describes  Windows PowerShell snap-ins and shows how to use and manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="18b20-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="18b20-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="18b20-108">Ein Windows PowerShell-Snap-in ist eine Microsoft .NET FrameworkAssembly, die Windows PowerShell-Anbieter und- \/ Cmdlets oder-Cmdlets enthält.</span><span class="sxs-lookup"><span data-stu-id="18b20-108">A Windows PowerShell snap-in is a Microsoft .NET Framework assembly that contains Windows PowerShell providers and\/or cmdlets.</span></span> <span data-ttu-id="18b20-109">Windows PowerShell umfasst eine Reihe von einfachen Snap-Ins, aber Sie können die Leistungsfähigkeit und den Wert von Windows PowerShell erweitern, indem Sie Snap-Ins hinzufügen, die Anbieter und Cmdlets enthalten, die Sie erstellen oder von anderen Benutzern erhalten.</span><span class="sxs-lookup"><span data-stu-id="18b20-109">Windows PowerShell includes a set of basic snap-ins, but you can extend the power and value of Windows PowerShell by adding snap-ins that contain providers and cmdlets that you create or get from others.</span></span>

<span data-ttu-id="18b20-110">Wenn Sie ein Snap-in hinzufügen, sind die darin enthaltenen Cmdlets und Anbieter sofort für die Verwendung in der aktuellen Sitzung verfügbar, aber die Änderung wirkt sich nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="18b20-110">When you add a snap-in, the cmdlets and providers that it contains are immediately available for use in the current session, but the change affects only the current session.</span></span>

<span data-ttu-id="18b20-111">Um das Snap-in zu allen zukünftigen Sitzungen hinzuzufügen, speichern Sie es in Ihrem Windows PowerShell-Profil.</span><span class="sxs-lookup"><span data-stu-id="18b20-111">To add the snap-in to all future sessions, save it in your Windows PowerShell profile.</span></span> <span data-ttu-id="18b20-112">Sie können auch das Cmdlet "Export-Console" verwenden, um die Snap-in-Namen in einer Konsolen Datei zu speichern und Sie dann in zukünftigen Sitzungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="18b20-112">You can also use the Export-Console cmdlet to save the snap-in names to a console file and then use it in future sessions.</span></span> <span data-ttu-id="18b20-113">Sie können sogar mehrere Konsolen Dateien mit jeweils einem anderen Satz von Snap-Ins speichern.</span><span class="sxs-lookup"><span data-stu-id="18b20-113">You can even save multiple console files, each with a different set of snap-ins.</span></span>

<span data-ttu-id="18b20-114">Hinweis: Windows PowerShell-Snap-Ins (pssnapins) stehen zur Verwendung in Windows PowerShell 3,0 und Windows PowerShell 2,0 zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="18b20-114">NOTE: Windows PowerShell snap-ins (PSSnapins) are available for use in Windows PowerShell 3.0 and Windows PowerShell 2.0.</span></span> <span data-ttu-id="18b20-115">Sie werden möglicherweise in nachfolgenden Versionen geändert oder sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="18b20-115">They might be altered or unavailable in subsequent versions.</span></span> <span data-ttu-id="18b20-116">Verwenden Sie zum Packen von Windows PowerShell-Cmdlets und Anbietern Module.</span><span class="sxs-lookup"><span data-stu-id="18b20-116">To package Windows PowerShell cmdlets and providers, use modules.</span></span> <span data-ttu-id="18b20-117">Weitere Informationen zum Erstellen von Modulen und zum Umrechnen von Snap-Ins in Module finden Sie unter [Schreiben eines Windows PowerShell-Moduls](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="18b20-117">For information about creating modules and converting snap-ins to modules, see [Writing a Windows PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

### <a name="finding-snap-ins"></a><span data-ttu-id="18b20-118">Suchen von Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="18b20-118">FINDING SNAP-INS</span></span>

<span data-ttu-id="18b20-119">Um eine Liste der Windows PowerShell-Snap-Ins auf dem Computer zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="18b20-119">To get a list of the  Windows PowerShell snap-ins on your computer, type:</span></span>

```powershell
Get-PSSnapin
```

<span data-ttu-id="18b20-120">Um das Snap-in für jeden Windows PowerShell-Anbieter zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="18b20-120">To get the snap-in for each  Windows PowerShell provider, type:</span></span>

```powershell
Get-PSProvider | Format-List name, pssnapin
```

<span data-ttu-id="18b20-121">Um eine Liste der Cmdlets in einem Windows PowerShell-Snap-in zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="18b20-121">To get a list of the cmdlets in a  Windows PowerShell snap-in, type:</span></span>

```powershell
Get-Command -Module <snap-in_name>
```

### <a name="installing-a-snap-in"></a><span data-ttu-id="18b20-122">Installieren eines Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="18b20-122">INSTALLING A SNAP-IN</span></span>

<span data-ttu-id="18b20-123">Die integrierten Snap-Ins werden im System registriert und der Standard Sitzung beim Starten von Windows PowerShell hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="18b20-123">The built-in snap-ins are registered in the system and added to the default session when you start Windows PowerShell.</span></span> <span data-ttu-id="18b20-124">Sie müssen jedoch Snap-Ins registrieren, die Sie erstellen oder von anderen erhalten, und dann die Snap-Ins zur Sitzung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="18b20-124">However, you have to register snap-ins that you create or obtain from others and then add the snap-ins to your session.</span></span>

### <a name="registering-a-snap-in"></a><span data-ttu-id="18b20-125">Registrieren eines Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="18b20-125">REGISTERING A SNAP-IN</span></span>

<span data-ttu-id="18b20-126">Bei einem Windows PowerShell-Snap-in handelt es sich um ein Programm, das in einer .NET Framework Sprache geschrieben ist, die in eine DLL-Datei kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="18b20-126">A Windows PowerShell snap-in is a program written in a .NET Framework language that is compiled into a .dll file.</span></span> <span data-ttu-id="18b20-127">Wenn Sie die Anbieter und Cmdlets in einem Snap-in verwenden möchten, müssen Sie zuerst das Snap-in registrieren (es der Registrierung hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="18b20-127">To use the providers and cmdlets in a snap-in, you must first register the snap-in (add it to the registry).</span></span>

<span data-ttu-id="18b20-128">Die meisten Snap-Ins enthalten ein Installationsprogramm (eine exe-oder MSI-Datei), das die DLL-Datei für Sie registriert.</span><span class="sxs-lookup"><span data-stu-id="18b20-128">Most snap-ins include an installation program (an .exe or .msi file) that registers the .dll file for you.</span></span> <span data-ttu-id="18b20-129">Wenn Sie jedoch ein Snap-in als DLL-Datei erhalten, können Sie es auf Ihrem System registrieren.</span><span class="sxs-lookup"><span data-stu-id="18b20-129">However, if you receive a snap-in as a .dll file, you can register it on your system.</span></span> <span data-ttu-id="18b20-130">Weitere Informationen finden Sie unter [Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="18b20-130">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

<span data-ttu-id="18b20-131">Geben Sie Folgendes ein, um alle registrierten Snap-Ins auf Ihrem System zu erhalten oder um zu überprüfen, ob ein Snap-in registriert ist:</span><span class="sxs-lookup"><span data-stu-id="18b20-131">To get all the registered snap-ins on your system or to verify that a snap-in is registered, type:</span></span>

```powershell
Get-PSSnapin -registered
```

### <a name="adding-the-snap-in-to-the-current-session"></a><span data-ttu-id="18b20-132">Hinzufügen des Snap-Ins zur aktuellen Sitzung</span><span class="sxs-lookup"><span data-stu-id="18b20-132">ADDING THE SNAP-IN TO THE CURRENT SESSION</span></span>

<span data-ttu-id="18b20-133">Verwenden Sie das Cmdlet "Add-PsSnapin", um der aktuellen Sitzung ein registriertes Snap-in hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="18b20-133">To add a registered snap-in to the current session, use the Add-PsSnapin cmdlet.</span></span> <span data-ttu-id="18b20-134">Wenn Sie z. b. der Sitzung das Microsoft SQL Server-Snap-in hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="18b20-134">For example, to add the Microsoft SQL Server snap-in to the session, type:</span></span>

```powershell
Add-PSSnapin sql
```

<span data-ttu-id="18b20-135">Nachdem der Befehl abgeschlossen wurde, sind die Anbieter und Cmdlets im Snap-in in der Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="18b20-135">After the command is completed, the providers and cmdlets in the snap-in are available in the session.</span></span> <span data-ttu-id="18b20-136">Sie sind jedoch nur in der aktuellen Sitzung verfügbar, sofern Sie Sie nicht speichern.</span><span class="sxs-lookup"><span data-stu-id="18b20-136">However, they are available only in the current session unless you save them.</span></span>

### <a name="saving-the-snap-ins"></a><span data-ttu-id="18b20-137">Speichern der Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="18b20-137">SAVING THE SNAP-INS</span></span>

<span data-ttu-id="18b20-138">Wenn Sie in zukünftigen Windows PowerShell-Sitzungen ein Snap-in verwenden möchten, fügen Sie dem Windows PowerShell-Profil den Befehl Add-PsSnapin hinzu.</span><span class="sxs-lookup"><span data-stu-id="18b20-138">To use a snap-in in future Windows PowerShell sessions, add the Add-PsSnapin command to your Windows PowerShell profile.</span></span> <span data-ttu-id="18b20-139">Oder exportieren Sie die Snap-in-Namen in eine Konsolen Datei.</span><span class="sxs-lookup"><span data-stu-id="18b20-139">Or, export the snap-in names to a console file.</span></span>

<span data-ttu-id="18b20-140">Wenn Sie den Add-PSSnapin Befehl zu Ihrem Profil hinzufügen, steht er in allen zukünftigen Windows PowerShell-Sitzungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="18b20-140">If you add the Add-PSSnapin command to your profile, it is available in all future Windows PowerShell sessions.</span></span> <span data-ttu-id="18b20-141">Wenn Sie die Namen der Snap-Ins in Ihrer Sitzung exportieren, können Sie die Exportdatei nur verwenden, wenn Sie die Snap-Ins benötigen.</span><span class="sxs-lookup"><span data-stu-id="18b20-141">If you export the names of the snap-ins in your session, you can use the export file only when you need the snap-ins.</span></span>

<span data-ttu-id="18b20-142">Um den Add-PsSnapin Befehl dem Windows PowerShell-Profil hinzuzufügen, öffnen Sie das Profil, fügen Sie den Befehl ein, oder geben Sie ihn ein, und speichern Sie dann das Profil.</span><span class="sxs-lookup"><span data-stu-id="18b20-142">To add the Add-PsSnapin command to your Windows PowerShell profile, open your profile, paste or type the command, and then save the profile.</span></span> <span data-ttu-id="18b20-143">Weitere Informationen finden Sie unter „about_Profiles“.</span><span class="sxs-lookup"><span data-stu-id="18b20-143">For more information, see about_Profiles.</span></span>

<span data-ttu-id="18b20-144">Um die Snap-Ins aus einer Sitzung in der Konsolen Datei (. psc1) zu speichern, verwenden Sie das Cmdlet "Export-Console".</span><span class="sxs-lookup"><span data-stu-id="18b20-144">To save the snap-ins from a session in console file (.psc1), use the Export-Console cmdlet.</span></span> <span data-ttu-id="18b20-145">Wenn Sie z. b. die Snap-Ins in der aktuellen Sitzungs Konfiguration in der newconsole. psc1-Datei im aktuellen Verzeichnis speichern möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="18b20-145">For example, to save the snap-ins in the current session configuration to the NewConsole.psc1 file in the current directory, type:</span></span>

```powershell
Export-Console NewConsole
```

<span data-ttu-id="18b20-146">Weitere Informationen finden Sie unter Export-Console.</span><span class="sxs-lookup"><span data-stu-id="18b20-146">For more information, see Export-Console.</span></span>

### <a name="opening-windows-powershell-with-a-console-file"></a><span data-ttu-id="18b20-147">Öffnen von Windows PowerShell mit einer Konsolen Datei</span><span class="sxs-lookup"><span data-stu-id="18b20-147">OPENING WINDOWS POWERSHELL WITH A CONSOLE FILE</span></span>

<span data-ttu-id="18b20-148">Um eine Konsolen Datei zu verwenden, die das-Snap-in enthält, starten Sie Windows PowerShell (PowerShell.exe) über die Eingabeaufforderung in Cmd.exe oder in einer anderen Windows PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="18b20-148">To use a console file that includes the snap-in, start Windows PowerShell (PowerShell.exe) from the command prompt in Cmd.exe or in another Windows PowerShell session.</span></span> <span data-ttu-id="18b20-149">Verwenden Sie den Parameter PsConsoleFile, um die Konsolen Datei anzugeben, in der das Snap-in enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="18b20-149">Use the PsConsoleFile parameter to specify the console file that includes the snap-in.</span></span> <span data-ttu-id="18b20-150">Beispielsweise wird mit dem folgenden Befehl Windows PowerShell mit der newconsole. psc1-Konsolen Datei gestartet:</span><span class="sxs-lookup"><span data-stu-id="18b20-150">For example, the following command starts Windows PowerShell with the NewConsole.psc1 console file:</span></span>

```powershell
PowerShell.exe -psconsolefile NewConsole.psc1
```

<span data-ttu-id="18b20-151">Die Anbieter und Cmdlets im Snap-in sind jetzt für die Verwendung in der Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="18b20-151">The providers and cmdlets in the snapin are now available for use in the session.</span></span>

### <a name="removing-a-snap-in"></a><span data-ttu-id="18b20-152">Entfernen eines Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="18b20-152">REMOVING A SNAP-IN</span></span>

<span data-ttu-id="18b20-153">Verwenden Sie das Cmdlet "Remove-PsSnapin", um ein Windows PowerShell-Snap-in aus der aktuellen Sitzung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="18b20-153">To remove a Windows PowerShell snap-in from the current session, use the Remove-PsSnapin cmdlet.</span></span> <span data-ttu-id="18b20-154">Wenn Sie z. b. das SQL Server-Snap-in aus der aktuellen Sitzung entfernen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="18b20-154">For example, to remove the SQL Server snap-in from the current session, type:</span></span>

```powershell
Remove-PSSnapin sql
```

<span data-ttu-id="18b20-155">Mit diesem Cmdlet wird das Snap-in aus der Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="18b20-155">This cmdlet removes the snap-in from the session.</span></span> <span data-ttu-id="18b20-156">Das Snap-in ist weiterhin geladen, die Anbieter und Cmdlets, die es unterstützt, sind jedoch nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="18b20-156">The snap-in is still loaded, but the providers and cmdlets that it supports are no longer available.</span></span>

### <a name="built-in-commands"></a><span data-ttu-id="18b20-157">integrierte Befehle</span><span class="sxs-lookup"><span data-stu-id="18b20-157">BUILT-IN COMMANDS</span></span>

<span data-ttu-id="18b20-158">In Windows PowerShell 2,0 und älteren Host Programmen in Windows PowerShell 3,0 und höher werden die integrierten Befehle, die mit Windows PowerShell installiert werden, in Snap-Ins verpackt, die automatisch zu jeder Windows PowerShell-Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="18b20-158">In Windows PowerShell 2.0 and in older-style host programs in Windows PowerShell 3.0 and later, the built-in commands that are installed with Windows PowerShell are packaged in snap-ins that are added automatically to every Windows PowerShell session.</span></span>

<span data-ttu-id="18b20-159">Beginnend mit Windows PowerShell 3,0 in Host Programmen im neueren Stil, die Sitzungen mithilfe der initialsessionstate. CreateDefault2-Methode starten, werden die integrierten Befehle in Modulen verpackt.</span><span class="sxs-lookup"><span data-stu-id="18b20-159">Beginning in Windows PowerShell 3.0, in newer-style host programs -- those that start sessions by using the InitialSessionState.CreateDefault2 method -- the built-in commands are packaged in modules.</span></span> <span data-ttu-id="18b20-160">Die Ausnahme ist "Microsoft. PowerShell. Core", die immer als Snap-in angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="18b20-160">The exception is Microsoft.PowerShell.Core, which always appears as a snap-in.</span></span> <span data-ttu-id="18b20-161">Das Core-Snap-in ist standardmäßig in jeder Sitzung enthalten.</span><span class="sxs-lookup"><span data-stu-id="18b20-161">The Core snap-in is included in every session by default.</span></span> <span data-ttu-id="18b20-162">Die integrierten Module werden automatisch bei der ersten Verwendung geladen.</span><span class="sxs-lookup"><span data-stu-id="18b20-162">The built-in modules are loaded automatically on first-use.</span></span>

<span data-ttu-id="18b20-163">Hinweis: Remote Sitzungen, einschließlich Sitzungen, die mit dem Cmdlet "New-PSSession" gestartet werden, sind Sitzungen älterer Sitzungen, in denen die integrierten Befehle in Snap-Ins verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="18b20-163">NOTE: Remote sessions, including sessions that are started by using the New-PSSession cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="18b20-164">Die folgenden Snap-Ins (oder Module) werden mit Windows PowerShell installiert.</span><span class="sxs-lookup"><span data-stu-id="18b20-164">The following snap-ins (or modules) are installed with Windows PowerShell.</span></span>

- <span data-ttu-id="18b20-165">Microsoft. PowerShell. Core: enthält Anbieter und Cmdlets, die zum Verwalten der grundlegenden Features von Windows PowerShell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="18b20-165">Microsoft.PowerShell.Core - Contains providers and cmdlets used to manage the basic features of Windows PowerShell.</span></span> <span data-ttu-id="18b20-166">Es enthält die Dateisystem-, Registrierungs-, Alias-, Umgebungs-, Funktions-und Variablen Anbieter sowie grundlegende Cmdlets wie "Get-Help", "Get-Command" und "Get-History".</span><span class="sxs-lookup"><span data-stu-id="18b20-166">It includes the FileSystem, Registry, Alias, Environment, Function, and Variable providers and basic cmdlets like Get-Help, Get-Command, and Get-History.</span></span>

- <span data-ttu-id="18b20-167">Microsoft. PowerShell. Host: enthält Cmdlets, die vom Windows PowerShell-Host verwendet werden, z. b. Start-Transcript und das Abbrechen von Skripts.</span><span class="sxs-lookup"><span data-stu-id="18b20-167">Microsoft.PowerShell.Host - Contains cmdlets used by the Windows PowerShell host, such as Start-Transcript and Stop-Transcript.</span></span>

- <span data-ttu-id="18b20-168">Microsoft. PowerShell. Management: enthält Cmdlets, z. b. Get-Service und Get-ChildItem, die zum Verwalten von Windows-basierten Features verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="18b20-168">Microsoft.PowerShell.Management - Contains cmdlets such as Get-Service and Get-ChildItem that are used to manage Windows-based features.</span></span>

- <span data-ttu-id="18b20-169">Microsoft. PowerShell. Security: enthält den Zertifikat Anbieter und die Cmdlets, die zum Verwalten der Windows PowerShell-Sicherheit verwendet werden, z. b. "Get-ACL", "Get-AuthenticodeSignature" und "ConvertTo-SecureString".</span><span class="sxs-lookup"><span data-stu-id="18b20-169">Microsoft.PowerShell.Security - Contains the Certificate provider and cmdlets used to manage Windows PowerShell security, such as Get-Acl, Get-AuthenticodeSignature, and ConvertTo-SecureString.</span></span>

- <span data-ttu-id="18b20-170">Microsoft. PowerShell. Utility: enthält Cmdlets, die zum Bearbeiten von Objekten und Daten verwendet werden, z. b. "Get-Member", "Write-Host" und "Format-List".</span><span class="sxs-lookup"><span data-stu-id="18b20-170">Microsoft.PowerShell.Utility - Contains cmdlets used to manipulate objects and data, such as Get-Member, Write-Host, and Format-List.</span></span>

- <span data-ttu-id="18b20-171">Microsoft. WSMAN. Management: enthält den WSMAN-Anbieter und Cmdlets, die den Windows-Remoteverwaltung Dienst verwalten, z. b. Connect-WSMan und enable-wsmankredssp.</span><span class="sxs-lookup"><span data-stu-id="18b20-171">Microsoft.WSMan.Management - Contains the WSMan provider and cmdlets that manage the Windows Remote Management service, such as Connect-WSMan and Enable-WSManCredSSP.</span></span>

## <a name="logging-snap-in-events"></a><span data-ttu-id="18b20-172">Protokollieren von Snap-in-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="18b20-172">LOGGING SNAP-IN EVENTS</span></span>

<span data-ttu-id="18b20-173">Ab Windows PowerShell 3,0 können Sie Ausführungs Ereignisse für die Cmdlets in Windows PowerShell-Modulen und-Snap-Ins aufzeichnen, indem Sie die logpipelineexecutiondetails-Eigenschaft von Modulen und Snap-Ins auf "true" festlegen.</span><span class="sxs-lookup"><span data-stu-id="18b20-173">Beginning in Windows PowerShell 3.0, you can record execution events for the cmdlets in Windows PowerShell modules and snap-ins by setting the LogPipelineExecutionDetails property of modules and snap-ins to TRUE.</span></span> <span data-ttu-id="18b20-174">Weitere Informationen finden Sie unter [about_EventLogs](about_EventLogs.md).</span><span class="sxs-lookup"><span data-stu-id="18b20-174">For more information, see [about_EventLogs](about_EventLogs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="18b20-175">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="18b20-175">SEE ALSO</span></span>

[<span data-ttu-id="18b20-176">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="18b20-176">Add-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Add-PSSnapin)

[<span data-ttu-id="18b20-177">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="18b20-177">Get-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSnapin)

[<span data-ttu-id="18b20-178">Remove-PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="18b20-178">Remove-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSnapin)

[<span data-ttu-id="18b20-179">Export-Console</span><span class="sxs-lookup"><span data-stu-id="18b20-179">Export-Console</span></span>](xref:Microsoft.PowerShell.Core.Export-Console)

[<span data-ttu-id="18b20-180">Get-Command</span><span class="sxs-lookup"><span data-stu-id="18b20-180">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="18b20-181">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="18b20-181">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="18b20-182">about_Modules</span><span class="sxs-lookup"><span data-stu-id="18b20-182">about_Modules</span></span>](about_Modules.md)

## <a name="keywords"></a><span data-ttu-id="18b20-183">Keywords</span><span class="sxs-lookup"><span data-stu-id="18b20-183">KEYWORDS</span></span>

<span data-ttu-id="18b20-184">about_Snapins, about_Snap_ins, about_Snap-ins</span><span class="sxs-lookup"><span data-stu-id="18b20-184">about_Snapins, about_Snap_ins, about_Snap-ins</span></span>
