---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PSSnapin
ms.openlocfilehash: 5adba912d91369250ee9891ee2bb2ca0f8cba796
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212124"
---
# <span data-ttu-id="d6861-103">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="d6861-103">Add-PSSnapin</span></span>

## <span data-ttu-id="d6861-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d6861-104">SYNOPSIS</span></span>
<span data-ttu-id="d6861-105">Fügt ein oder mehrere Windows PowerShell-Snap-Ins zur aktuellen Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="d6861-105">Adds one or more Windows PowerShell snap-ins to the current session.</span></span>

## <span data-ttu-id="d6861-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d6861-106">SYNTAX</span></span>

```
Add-PSSnapin [-Name] <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="d6861-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d6861-107">DESCRIPTION</span></span>

<span data-ttu-id="d6861-108">Mit dem- `Add-PSSnapin` Cmdlet werden registrierte Windows PowerShell-Snap-Ins zur aktuellen Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d6861-108">The `Add-PSSnapin` cmdlet adds registered Windows PowerShell snap-ins to the current session.</span></span> <span data-ttu-id="d6861-109">Nach dem Hinzufügen der Snap-Ins können Sie die von den Snap-Ins unterstützten Cmdlets und Anbieter in der aktuellen Sitzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6861-109">After the snap-ins are added, you can use the cmdlets and providers that the snap-ins support in the current session.</span></span>

<span data-ttu-id="d6861-110">Fügen Sie `Add-PSSnapin` Ihrem Windows PowerShell-Profil einen Befehl hinzu, um das Snap-in zu allen zukünftigen Windows PowerShell-Sitzungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6861-110">To add the snap-in to all future Windows PowerShell sessions, add an `Add-PSSnapin` command to your Windows PowerShell profile.</span></span> <span data-ttu-id="d6861-111">Weitere Informationen finden Sie unter [about_Profiles](about/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d6861-111">For more information, see [about_Profiles](about/about_Profiles.md).</span></span>

<span data-ttu-id="d6861-112">Ab Windows PowerShell 3.0 sind die in Windows PowerShell enthaltenen Hauptbefehle in Module gepackt.</span><span class="sxs-lookup"><span data-stu-id="d6861-112">Beginning in Windows PowerShell 3.0, the core commands that are included in Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="d6861-113">Eine Ausnahme ist das Snap-In **Microsoft.PowerShell.Core** (PSSnapin).</span><span class="sxs-lookup"><span data-stu-id="d6861-113">The exception is **Microsoft.PowerShell.Core** , which is a snap-in (PSSnapin).</span></span>
<span data-ttu-id="d6861-114">Standardmäßig wird nur das **Microsoft.PowerShell.Core** -Snap-In der Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d6861-114">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span> <span data-ttu-id="d6861-115">Module werden bei der ersten Verwendung automatisch importiert, und Sie können das Cmdlet "Import-Module" verwenden, um Sie zu importieren.</span><span class="sxs-lookup"><span data-stu-id="d6861-115">Modules are imported automatically on first use and you can use the Import-Module cmdlet to import them.</span></span>

## <span data-ttu-id="d6861-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d6861-116">EXAMPLES</span></span>

### <span data-ttu-id="d6861-117">Beispiel 1: Hinzufügen von Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="d6861-117">Example 1: Add snap-ins</span></span>

```powershell
PS C:\> Add-PSSnapIn -Name Microsoft.Exchange, Microsoft.Windows.AD
```

<span data-ttu-id="d6861-118">Dieser Befehl fügt die Microsoft Exchange- und Active Directory-Snap-Ins zur aktuellen Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="d6861-118">This command adds the Microsoft Exchange and Active Directory snap-ins to the current session.</span></span>

### <span data-ttu-id="d6861-119">Beispiel 2: Hinzufügen aller registrierten Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="d6861-119">Example 2: Add all the registered snap-ins</span></span>

```powershell
PS C:\> Get-PSSnapin -Registered | Add-PSSnapin -Passthru
```

<span data-ttu-id="d6861-120">Dieser Befehl fügt alle registrierten Windows PowerShell-Snap-Ins zur Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="d6861-120">This command adds all of the registered Windows PowerShell snap-ins to the session.</span></span> <span data-ttu-id="d6861-121">Er verwendet das Cmdlet "Get-PSSnapin" mit dem **registrierten** Parameter, um Objekte zu erhalten, die die einzelnen registrierten Snap-Ins darstellen. Der Pipeline Operator (|) übergibt das Ergebnis an `Add-PSSnapin` , wodurch Sie der Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d6861-121">It uses the Get-PSSnapin cmdlet with the **Registered** parameter to get objects representing each of the registered snap-ins. The pipeline operator (|) passes the result to `Add-PSSnapin`, which adds them to the session.</span></span> <span data-ttu-id="d6861-122">Der **passthru** -Parameter gibt Objekte zurück, die die einzelnen hinzugefügten Snap-Ins darstellen.</span><span class="sxs-lookup"><span data-stu-id="d6861-122">The **PassThru** parameter returns objects that represent each of the added snap-ins.</span></span>

### <span data-ttu-id="d6861-123">Beispiel 3: Registrieren eines Snap-Ins und Hinzufügen des Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="d6861-123">Example 3: Register a snap-in and add it</span></span>

<span data-ttu-id="d6861-124">Der erste Befehl ruft Snap-Ins ab, die der aktuellen Sitzung hinzugefügt wurden, die die mit Windows PowerShell installierten Snap-Ins enthalten.</span><span class="sxs-lookup"><span data-stu-id="d6861-124">The first command gets snap-ins that have been added to the current session that include the snap-ins that are installed with Windows PowerShell.</span></span> <span data-ttu-id="d6861-125">In diesem Beispiel wird ManagementFeatures nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6861-125">In this example, ManagementFeatures is not returned.</span></span> <span data-ttu-id="d6861-126">Dies gibt an, dass es nicht zur Sitzung hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6861-126">This indicates that it has not been added to the session.</span></span>

<span data-ttu-id="d6861-127">Der zweite Befehl ruft Snap-Ins ab, die auf Ihrem System registriert wurden, einschließlich derjenigen, die der Sitzung bereits hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="d6861-127">The second command gets snap-ins that have been registered on your system, which includes those that have already been added to the session.</span></span> <span data-ttu-id="d6861-128">Es sind keine Snap-Ins enthalten, die mit Windows PowerShell installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d6861-128">It does not include the snap-ins that are installed with Windows PowerShell.</span></span> <span data-ttu-id="d6861-129">In diesem Fall gibt der Befehl keine Snap-Ins zurück. Dies gibt an, dass der Managementfeatures-Snap-in nicht auf dem System registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="d6861-129">In this case, the command does not return any snap-ins. This indicates that the ManagementFeatures snapin has not been registered on the system.</span></span>

<span data-ttu-id="d6861-130">Mit dem dritten Befehl wird der Alias "installutil" für den Pfad des Tools "installutil" in .NET Framework erstellt.</span><span class="sxs-lookup"><span data-stu-id="d6861-130">The third command creates an alias, installutil, for the path of the InstallUtil tool in .NET Framework.</span></span>

<span data-ttu-id="d6861-131">Der vierte Befehl verwendet das Tool installutil, um das Snap-in zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d6861-131">The fourth command uses the InstallUtil tool to register the snap-in.</span></span> <span data-ttu-id="d6861-132">Mit dem Befehl wird der Pfad ManagementCmdlets.dll, der Dateiname oder der Modulname des Snap-Ins angegeben.</span><span class="sxs-lookup"><span data-stu-id="d6861-132">The command specifies the path of ManagementCmdlets.dll, the filename or module name of the snap-in.</span></span>

<span data-ttu-id="d6861-133">Der fünfte Befehl ist identisch mit dem zweiten Befehl.</span><span class="sxs-lookup"><span data-stu-id="d6861-133">The fifth command is the same as the second command.</span></span> <span data-ttu-id="d6861-134">Dieses Mal wird er verwendet, um zu überprüfen, ob das ManagementCmdlets-Snap-In registriert ist.</span><span class="sxs-lookup"><span data-stu-id="d6861-134">This time, you use it to verify that the ManagementCmdlets snap-in is registered.</span></span>

<span data-ttu-id="d6861-135">Der sechste Befehl verwendet das `Add-PSSnapin` Cmdlet, um der Sitzung das Management Features-Snap-in hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6861-135">The sixth command uses the `Add-PSSnapin` cmdlet to add the ManagementFeatures snap-in to the session.</span></span> <span data-ttu-id="d6861-136">Der Befehl gibt den Namen des Snap-Ins (ManagementFeatures) und nicht den Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="d6861-136">It specifies the name of the snap-in, ManagementFeatures, not the file name.</span></span>

<span data-ttu-id="d6861-137">Um sicherzustellen, dass das Snap-in der Sitzung hinzugefügt wird, verwendet der siebte Befehl den **Module** -Parameter des Get-Command Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d6861-137">To verify that the snap-in is added to the session, the seventh command uses the **Module** parameter of the Get-Command cmdlet.</span></span> <span data-ttu-id="d6861-138">Der Parameter zeigt die Elemente an, die durch ein Snap-In oder ein Modul zur Sitzung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="d6861-138">It displays the items that were added to the session by a snap-in or module.</span></span>

<span data-ttu-id="d6861-139">Sie können auch die **PSSnapIn** -Eigenschaft des-Objekts verwenden, das vom `Get-Command` Cmdlet zurückgegeben wird, um das Snap-in oder Modul zu suchen, von dem ein Cmdlet stammt.</span><span class="sxs-lookup"><span data-stu-id="d6861-139">You can also use the **PSSnapin** property of the object that the `Get-Command` cmdlet returns to find the snap-in or module in which a cmdlet originated.</span></span> <span data-ttu-id="d6861-140">Der achte Befehl verwendet die Punkt Notation, um den Wert der PSSnapIn-Eigenschaft des Set-Alias-Cmdlets zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d6861-140">The eighth command uses dot notation to find the value of the PSSnapin property of the Set-Alias cmdlet.</span></span>

```powershell
PS C:\> Get-PSSnapin
PS C:\> Get-PSSnapin -Registered
PS C:\> Set-Alias installutil $env:windir\Microsoft.NET\Framework\v2.0.50727\installutil.exe
PS C:\> installutil C:\Dev\Management\ManagementCmdlets.dll
PS C:\> Get-PSSnapin -Registered
PS C:\> add-pssnapin ManagementFeatures
PS C:\> Get-Command -Module ManagementFeatures
PS C:\> (Get-Command Set-Alias).pssnapin
```

<span data-ttu-id="d6861-141">In diesem Beispiel wird veranschaulicht, wie ein Snap-In im System registriert und dann der Sitzung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d6861-141">This example demonstrates the process of registering a snap-in on your system and then adding it to your session.</span></span> <span data-ttu-id="d6861-142">Er verwendet Managementfeatures, ein fiktives Snap-in, das in einer Datei mit dem Namen ManagementCmdlets.dll implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="d6861-142">It uses ManagementFeatures, a fictitious snap-in implemented in a file that is named ManagementCmdlets.dll.</span></span>

## <span data-ttu-id="d6861-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d6861-143">PARAMETERS</span></span>

### <span data-ttu-id="d6861-144">-Name</span><span class="sxs-lookup"><span data-stu-id="d6861-144">-Name</span></span>

<span data-ttu-id="d6861-145">Gibt den Namen des Snap-Ins an.</span><span class="sxs-lookup"><span data-stu-id="d6861-145">Specifies the name of the snap-in.</span></span> <span data-ttu-id="d6861-146">Dies ist der Name, nicht Assemblyname oder ModuleName.</span><span class="sxs-lookup"><span data-stu-id="d6861-146">This is the Name, not the AssemblyName or ModuleName.</span></span> <span data-ttu-id="d6861-147">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d6861-147">Wildcards are permitted.</span></span>

<span data-ttu-id="d6861-148">Geben Sie ein, um die Namen der registrierten Snap-Ins auf Ihrem System zu ermitteln `Get-PSSnapin -Registered` .</span><span class="sxs-lookup"><span data-stu-id="d6861-148">To find the names of the registered snap-ins on your system, type `Get-PSSnapin -Registered`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="d6861-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d6861-149">-PassThru</span></span>

<span data-ttu-id="d6861-150">Gibt an, dass dieses Cmdlet ein Objekt zurückgibt, das die einzelnen hinzugefügten Snap-Ins darstellt.</span><span class="sxs-lookup"><span data-stu-id="d6861-150">Indicates that this cmdlet returns an object that represents each added snap-in.</span></span> <span data-ttu-id="d6861-151">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="d6861-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d6861-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d6861-152">CommonParameters</span></span>

<span data-ttu-id="d6861-153">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d6861-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d6861-154">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d6861-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d6861-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d6861-155">INPUTS</span></span>

### <span data-ttu-id="d6861-156">Keine</span><span class="sxs-lookup"><span data-stu-id="d6861-156">None</span></span>
<span data-ttu-id="d6861-157">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="d6861-157">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="d6861-158">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d6861-158">OUTPUTS</span></span>

### <span data-ttu-id="d6861-159">None oder System. Management. Automation. pssnapininfo</span><span class="sxs-lookup"><span data-stu-id="d6861-159">None or System.Management.Automation.PSSnapInInfo</span></span>

<span data-ttu-id="d6861-160">Dieses Cmdlet gibt ein pssnapininfo-Objekt zurück, das das Snap-in darstellt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="d6861-160">This cmdlet returns a PSSnapInInfo object that represents the snap-in if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="d6861-161">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="d6861-161">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d6861-162">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d6861-162">NOTES</span></span>

* <span data-ttu-id="d6861-163">Ab Windows PowerShell 3.0 sind die mit Windows PowerShell installierten Hauptbefehle in Module gepackt.</span><span class="sxs-lookup"><span data-stu-id="d6861-163">Beginning in Windows PowerShell 3.0, the core commands that are installed with Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="d6861-164">In Windows PowerShell 2,0 und in Host Programmen, die in neueren Versionen von Windows PowerShell ältere Sitzungen erstellen, werden die Hauptbefehle in Snap-Ins (pssnapins) gepackt.</span><span class="sxs-lookup"><span data-stu-id="d6861-164">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of Windows PowerShell, the core commands are packaged in snap-ins (PSSnapins).</span></span> <span data-ttu-id="d6861-165">Die Ausnahme ist **Microsoft. PowerShell. Core** , bei der es sich immer um ein Snap-in handelt.</span><span class="sxs-lookup"><span data-stu-id="d6861-165">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="d6861-166">Remote Sitzungen, wie z. b. diejenigen, die mit dem Cmdlet "New-PSSession" gestartet werden, sind auch ältere Sitzungen, die Core-Snap-Ins enthalten.</span><span class="sxs-lookup"><span data-stu-id="d6861-166">Also, remote sessions, such as those started by the New-PSSession cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="d6861-167">Weitere Informationen über die **CreateDefault2** -Methode, die Sitzungen im neueren Stil mit Kernmodulen erstellt, finden Sie unter [CreateDefault2-Methode](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="d6861-167">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

* <span data-ttu-id="d6861-168">Weitere Informationen zu Snap-Ins finden Sie unter [about_PSSnapins](About/about_PSSnapins.md) und [Erstellen eines Windows PowerShell-Snap-](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in)ins.</span><span class="sxs-lookup"><span data-stu-id="d6861-168">For more information about snap-ins, see [about_PSSnapins](About/about_PSSnapins.md) and [How to Create a Windows PowerShell Snap-in](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in).</span></span>
* <span data-ttu-id="d6861-169">`Add-PSSnapin` Fügt das Snap-in nur zur aktuellen Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="d6861-169">`Add-PSSnapin` adds the snap-in only to the current session.</span></span> <span data-ttu-id="d6861-170">Um das Snap-In zu allen Windows PowerShell-Sitzungen hinzuzufügen, fügen Sie es zu Ihrem Windows PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="d6861-170">To add the snap-in to all Windows PowerShell sessions, add it to your Windows PowerShell profile.</span></span> <span data-ttu-id="d6861-171">Weitere Informationen finden Sie unter „about_Profiles“.</span><span class="sxs-lookup"><span data-stu-id="d6861-171">For more information, see about_Profiles.</span></span>
* <span data-ttu-id="d6861-172">Sie können ein beliebiges Snap-in hinzufügen, das mit dem Installationsprogramm für Microsoft .NET Framework registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="d6861-172">You can add any snap-in that has been registered using the Microsoft .NET Framework install utility.</span></span> <span data-ttu-id="d6861-173">Weitere Informationen finden Sie unter [Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="d6861-173">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>
* <span data-ttu-id="d6861-174">Zum erhalten einer Liste von Snap-Ins, die auf Ihrem Computer registriert sind, geben Sie ein `Get-PSSnapin -Registered` .</span><span class="sxs-lookup"><span data-stu-id="d6861-174">To get a list of snap-ins that are registered on your computer, type `Get-PSSnapin -Registered`.</span></span>
* <span data-ttu-id="d6861-175">Vor dem Hinzufügen eines Snap-Ins `Add-PSSnapin` überprüft die Version des Snap-Ins, um zu überprüfen, ob es mit der aktuellen Version von Windows PowerShell kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="d6861-175">Before adding a snap-in, `Add-PSSnapin` checks the version of the snap-in to verify that it is compatible with the current version of Windows PowerShell.</span></span> <span data-ttu-id="d6861-176">Wenn das Snap-In die Versionsprüfung nicht besteht, meldet Windows PowerShell einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="d6861-176">If the snap-in fails the version check, Windows PowerShell reports an error.</span></span>

## <span data-ttu-id="d6861-177">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d6861-177">RELATED LINKS</span></span>

[<span data-ttu-id="d6861-178">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="d6861-178">Get-PSSnapin</span></span>](Get-PSSnapin.md)

[<span data-ttu-id="d6861-179">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="d6861-179">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
