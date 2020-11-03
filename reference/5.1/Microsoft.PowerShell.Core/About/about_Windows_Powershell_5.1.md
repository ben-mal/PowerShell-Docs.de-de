---
description: Beschreibt die neuen Features, die in Windows PowerShell 5,1 enthalten sind.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/17/2018
online version: https://docs.microsoft.com/powershell/module/?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_5.1
ms.openlocfilehash: 567af048dd137c0287c6eba4ccc42a77055c0c92
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224908"
---
# <a name="about_windows_powershell_51"></a><span data-ttu-id="0fdf6-104">about_Windows_PowerShell_5.1</span><span class="sxs-lookup"><span data-stu-id="0fdf6-104">about_Windows_PowerShell_5.1</span></span>

## <a name="short-description"></a><span data-ttu-id="0fdf6-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0fdf6-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="0fdf6-106">Beschreibt die neuen Features, die in Windows PowerShell 5,1 enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-106">Describes new features that are included in Windows PowerShell 5.1.</span></span>

## <a name="long-description"></a><span data-ttu-id="0fdf6-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0fdf6-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="0fdf6-108">Windows PowerShell 5,1 umfasst wichtige neue Features, die die Verwendungsmöglichkeiten erweitern, die Benutzerfreundlichkeit verbessern und es Ihnen ermöglichen, die Steuerung und Verwaltung von Windows-basierten Umgebungen leichter und umfassender zu steuern.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-108">Windows PowerShell 5.1 includes significant new features that extend its use, improve its usability, and allow you to control and manage Windows-based environments more easily and comprehensively.</span></span>

<span data-ttu-id="0fdf6-109">Windows PowerShell 5,1 ist abwärts kompatibel.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-109">Windows PowerShell 5.1 is backward-compatible.</span></span> <span data-ttu-id="0fdf6-110">Cmdlets, Anbieter, Module, Snap-Ins, Skripts, Funktionen und Profile, die für Windows PowerShell 4,0, Windows PowerShell 3,0 und Windows PowerShell 2,0 entwickelt wurden, funktionieren im Allgemeinen ohne Änderungen in Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-110">Cmdlets, providers, modules, snap-ins, scripts, functions, and profiles that were designed for Windows PowerShell 4.0, Windows PowerShell 3.0, and Windows PowerShell 2.0 generally work in Windows PowerShell 5.1 without changes.</span></span>

- <span data-ttu-id="0fdf6-111">Neue Cmdlets: lokale Benutzer und Gruppen; Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="0fdf6-111">New cmdlets: local users and groups; Get-ComputerInfo</span></span>
- <span data-ttu-id="0fdf6-112">PowerShellGet-Verbesserungen wie z. B. die Durchsetzung von signierten Modulen und die Installation von JEA-Modulen</span><span class="sxs-lookup"><span data-stu-id="0fdf6-112">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="0fdf6-113">Bei PackageManagement wurde Unterstützung für Container, CBS-Setup, EXE-basiertes Setup und CAB-Pakete hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="0fdf6-113">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="0fdf6-114">Debuggingverbesserungen für DSC und PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="0fdf6-114">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="0fdf6-115">Sicherheitsverbesserungen wie u. a. die Durchsetzung von katalogsignierten Modulen vom Pullserver und bei Verwendung von PowerShellGet-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0fdf6-115">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="0fdf6-116">Antworten auf verschiedene Benutzeranfragen und zu Problemen</span><span class="sxs-lookup"><span data-stu-id="0fdf6-116">Responses to a number of user requests and issues</span></span>

<span data-ttu-id="0fdf6-117">Windows PowerShell 5,1 wird standardmäßig unter Windows Server 2016 und Windows 10 installiert.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-117">Windows PowerShell 5.1 is installed by default on Windows Server 2016 and Windows 10.</span></span> <span data-ttu-id="0fdf6-118">Informationen zum Installieren von Windows PowerShell 5,1 unter Windows Server 2012 R2, Windows 8.1 Enterprise oder Windows 8.1 pro finden Sie unter [Installieren und Konfigurieren von WMF 5,1](/powershell/scripting/wmf/setup/install-configure).</span><span class="sxs-lookup"><span data-stu-id="0fdf6-118">To install Windows PowerShell 5.1 on Windows Server 2012 R2, Windows 8.1 Enterprise, or Windows 8.1 Pro, see [Install and Configure WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span></span>
<span data-ttu-id="0fdf6-119">Achten Sie darauf, dass Sie die Download Details lesen und alle Systemanforderungen erfüllen, bevor Sie Windows Management Framework 5,1 installieren.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-119">Be sure to read the download details, and meet all system requirements, before you install Windows Management Framework 5.1.</span></span>

<span data-ttu-id="0fdf6-120">Weitere Informationen zu Änderungen an Windows PowerShell 5,1 finden Sie unter [Neuerungen in Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).</span><span class="sxs-lookup"><span data-stu-id="0fdf6-120">You can also read about changes to Windows PowerShell 5.1 in [What's New in Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).</span></span>

## <a name="new-scenarios-and-features-in-wmf-51"></a><span data-ttu-id="0fdf6-121">Neue Szenarios und Features in WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="0fdf6-121">New Scenarios and Features in WMF 5.1</span></span>

> <span data-ttu-id="0fdf6-122">Hinweis: Diese Dokumentation ist vorläufig und kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-122">Note: This information is preliminary and subject to change.</span></span>

### <a name="powershell-editions"></a><span data-ttu-id="0fdf6-123">PowerShell-Editionen</span><span class="sxs-lookup"><span data-stu-id="0fdf6-123">PowerShell Editions</span></span>
<span data-ttu-id="0fdf6-124">Ab Version 5.1 ist PowerShell in verschiedenen Editionen verfügbar, die unterschiedliche Funktionen mitbringen und zu unterschiedlichen Plattformen kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-124">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="0fdf6-125">**Desktop-Edition:** Diese Edition basiert auf .NET Framework und bietet Kompatibilität mit PowerShell-Versionen, die auf Skripts und Module abzielen und unter vollwertigen Editionen von Windows ausgeführt werden, z. B. Server Core und Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-125">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="0fdf6-126">**Core-Edition:** Diese Edition basiert auf .NET Core und bietet Kompatibilität mit Skripts und Modulen für Versionen von PowerShell, die unter funktionsreduzierten Versionen von Windows wie Nano Server und Windows IoT ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-126">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

<span data-ttu-id="0fdf6-127">**Weitere Informationen zur Verwendung von PowerShell-Editionen**</span><span class="sxs-lookup"><span data-stu-id="0fdf6-127">**Learn more about using PowerShell Editions**</span></span>

- [<span data-ttu-id="0fdf6-128">Determine running edition of PowerShell using $PSVersionTable (Bestimmen der ausgeführten Edition von PowerShell mit $PSVersionTable)</span><span class="sxs-lookup"><span data-stu-id="0fdf6-128">Determine running edition of PowerShell using $PSVersionTable</span></span>](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [<span data-ttu-id="0fdf6-129">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter (Filtern von Get-Module-Ergebnissen nach CompatiblePSEditions mithilfe des PSEdition-Parameters)</span><span class="sxs-lookup"><span data-stu-id="0fdf6-129">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter</span></span>](/powershell/module/microsoft.powershell.core/get-module)
- [<span data-ttu-id="0fdf6-130">Verhindern der Ausführung von Skripts außer bei Ausführung in einer kompatiblen Edition von PowerShell</span><span class="sxs-lookup"><span data-stu-id="0fdf6-130">Prevent script execution unless run on a compatible edition of PowerShell</span></span>](/powershell/scripting/gallery/concepts/script-psedition-support)
- [<span data-ttu-id="0fdf6-131">Deklarieren der Kompatibilität eines Moduls mit bestimmten Versionen von PowerShell</span><span class="sxs-lookup"><span data-stu-id="0fdf6-131">Declare a module's compatibility to specific PowerShell versions</span></span>](/powershell/scripting/gallery/concepts/module-psedition-support)

### <a name="catalog-cmdlets"></a><span data-ttu-id="0fdf6-132">Katalog-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0fdf6-132">Catalog Cmdlets</span></span>

<span data-ttu-id="0fdf6-133">Dem [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640))-Modul wurden zwei neue Cmdlets hinzugefügt, die Windows-Katalogdateien generieren und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-133">Two new cmdlets have been added in the [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)) module; these generate and validate Windows catalog files.</span></span>

#### <a name="new-filecatalog"></a><span data-ttu-id="0fdf6-134">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="0fdf6-134">New-FileCatalog</span></span>

<span data-ttu-id="0fdf6-135">„New-FileCatalog“ erstellt eine Windows-Katalogdatei für eine Gruppe von Ordnern und Dateien.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-135">New-FileCatalog creates a Windows catalog file for set of folders and files.</span></span>
<span data-ttu-id="0fdf6-136">Diese Katalogdatei enthält die Hashes aller Dateien in bestimmten Pfaden.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-136">This catalog file contains hashes for all files in specified paths.</span></span> <span data-ttu-id="0fdf6-137">Benutzer können den Satz von Ordnern zusammen mit den entsprechenden Katalogdateien verteilen, die diese Ordner darstellen.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-137">Users can distribute the set of folders along with corresponding catalog file representing those folders.</span></span> <span data-ttu-id="0fdf6-138">Diese Informationen helfen bei der Überprüfung, ob seit der Erstellung des Katalogs Änderungen an den Ordnern vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-138">This information is useful to validate whether any changes have been made to the folders since catalog creation time.</span></span>

```
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>]
 [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="0fdf6-139">Die Katalogversionen 1 und 2 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-139">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="0fdf6-140">Version 1 verwendet den SHA1-Hashalgorithmus, um Dateihashes zu erstellen, Version 2 verwendet SHA256.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-140">Version 1 uses the SHA1 hashing algorithm to create file hashes; version 2 uses SHA256.</span></span> <span data-ttu-id="0fdf6-141">Katalogversion 2 wird weder auf *Windows Server 2008 R2* noch auf *Windows 7* unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-141">Catalog version 2 is not supported on *Windows Server 2008 R2* or *Windows 7*.</span></span> <span data-ttu-id="0fdf6-142">Daher sollten Sie die Katalogversion 2 mit *Windows 8* , *Windows Server 2012* und späteren Betriebssystemen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-142">You should use catalog version 2 on *Windows 8* , *Windows Server 2012* , and later operating systems.</span></span>

<span data-ttu-id="0fdf6-143">Melden Sie sich mit dem Cmdlet [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) an, um die Integrität der Katalogdatei zu überprüfen (im obigen Beispiel: „pester.cat“).</span><span class="sxs-lookup"><span data-stu-id="0fdf6-143">To verify the integrity of catalog file (Pester.cat in above example), sign it using [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) cmdlet.</span></span>

#### <a name="test-filecatalog"></a><span data-ttu-id="0fdf6-144">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="0fdf6-144">Test-FileCatalog</span></span>

<span data-ttu-id="0fdf6-145">„Test-FileCatalog“ überprüft den Katalog, der einen Satz von Ordnern darstellt.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-145">Test-FileCatalog validates the catalog representing a set of folders.</span></span>

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>]
 [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="0fdf6-146">Dieses Cmdlet vergleicht alle Dateihashes und deren im *Katalog* enthaltenen relativen Pfade mit denen auf dem *Datenträger*.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-146">This cmdlet compares all the files hashes and their relative paths found in *catalog* with ones on *disk*.</span></span> <span data-ttu-id="0fdf6-147">Wenn das Cmdlet eine Unstimmigkeit zwischen den Dateihashes und den Pfaden entdeckt, gibt es den Status *ValidationFailed* zurück.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-147">If it detects any mismatch between file hashes and paths it returns the status as *ValidationFailed*.</span></span> <span data-ttu-id="0fdf6-148">Benutzer können alle diese Informationen mithilfe des Parameters *-Detailed* abrufen.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-148">Users can retrieve all this information by using the *-Detailed* parameter.</span></span> <span data-ttu-id="0fdf6-149">Dieser Parameter zeigt in der Eigenschaft *Signature* auch den Signierstatus des Katalogs an, was dem Aufruf des Cmdlets [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) in der Katalogdatei entspricht.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-149">It also displays signing status of catalog in *Signature* property which is equivalent to calling [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) cmdlet on the catalog file.</span></span> <span data-ttu-id="0fdf6-150">Benutzer können außerdem jede Datei während der Überprüfung mithilfe des Parameters *-FilesToSkip* überspringen.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-150">Users can also skip any file during validation by using the *-FilesToSkip* parameter.</span></span>

### <a name="module-analysis-cache"></a><span data-ttu-id="0fdf6-151">Die Datei „ModuleAnalysisCache“</span><span class="sxs-lookup"><span data-stu-id="0fdf6-151">Module Analysis Cache</span></span>

<span data-ttu-id="0fdf6-152">Ab Version 5.1 bietet PowerShell Kontrolle über die Datei, die zum Zwischenspeichern von Daten zu einem Modul verwendet wird, z. B. der Befehle, die es exportiert.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-152">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="0fdf6-153">Standardmäßig wird dieser Cache in der Datei `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-153">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="0fdf6-154">Der Cache wird in der Regel beim Start der Suche nach einem Befehl gelesen und einige Zeit nach dem Import des Moduls in einem Hintergrundthread geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-154">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="0fdf6-155">Um den Standardspeicherort des Caches zu ändern, legen Sie die Umgebungsvariable `$env:PSModuleAnalysisCachePath` vor dem Starten von PowerShell fest.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-155">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span> <span data-ttu-id="0fdf6-156">Änderungen an dieser Umgebungsvariablen betreffen nur untergeordnete Prozesse.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-156">Changes to this environment variable will only affect children processes.</span></span> <span data-ttu-id="0fdf6-157">Der Wert muss einen vollständigen Pfad (samt Dateiname) definieren, in dem PowerShell die Berechtigung zum Erstellen und Schreiben von Dateien hat.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-157">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span> <span data-ttu-id="0fdf6-158">Zum Deaktivieren des Dateicaches kann dieser Wert auf einen ungültigen Speicherort festgelegt werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fdf6-158">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="0fdf6-159">Hiermit wird der Pfad auf ein ungültiges Gerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-159">This sets the path to an invalid device.</span></span> <span data-ttu-id="0fdf6-160">Wenn PowerShell nicht in den Pfad schreiben kann, wird keine Fehlermeldung zurückgegeben. Mithilfe eines Ablaufverfolgungstools können Sie jedoch einen Fehlerbericht anzeigen:</span><span class="sxs-lookup"><span data-stu-id="0fdf6-160">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression {
  Import-Module Microsoft.PowerShell.Management -Force
}
```

<span data-ttu-id="0fdf6-161">Bei der Ausgabe aus dem Cache sucht PowerShell nach Modulen, die nicht mehr vorhanden sind, um einen unnötig großen Cache zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-161">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="0fdf6-162">Mitunter sind diese Überprüfungen nicht wünschenswert, weshalb Sie sie deaktivieren können, indem Sie Folgendes festlegen:</span><span class="sxs-lookup"><span data-stu-id="0fdf6-162">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="0fdf6-163">Das Festlegen dieser Umgebungsvariablen wird im aktuellen Prozess sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-163">Setting this environment variable will take effect immediately in the current process.</span></span>

### <a name="specifying-module-version"></a><span data-ttu-id="0fdf6-164">Angeben der Modulversion</span><span class="sxs-lookup"><span data-stu-id="0fdf6-164">Specifying module version</span></span>

<span data-ttu-id="0fdf6-165">In WMF 5.1 verhält sich `using module` genauso wie andere modulbezogene Konstruktionen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-165">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span> <span data-ttu-id="0fdf6-166">Zuvor gab es keine Möglichkeit, eine bestimmte Modulversion anzugeben. Wenn mehrere Versionen vorhanden waren, führte dies zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-166">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>

<span data-ttu-id="0fdf6-167">In WMF 5.1:</span><span class="sxs-lookup"><span data-stu-id="0fdf6-167">In WMF 5.1:</span></span>

* <span data-ttu-id="0fdf6-168">Sie können den [Konstruktor „ModuleSpecification“ (Hashtabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor) verwenden.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-168">You can use [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor).</span></span>
  <span data-ttu-id="0fdf6-169">Diese Hashtabelle hat das gleiche Format wie `Get-Module -FullyQualifiedName`.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-169">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

  <span data-ttu-id="0fdf6-170">**Beispiel:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="0fdf6-170">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

* <span data-ttu-id="0fdf6-171">Wenn mehrere Versionen des Moduls vorhanden sind, verwendet PowerShell **dieselbe Auflösungslogik** wie `Import-Module` und gibt keinen Fehler zurück, was dem Verhalten von `Import-Module` und `Import-DscResource` entspricht.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-171">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>

### <a name="improvements-to-pester"></a><span data-ttu-id="0fdf6-172">Verbesserungen an Pester</span><span class="sxs-lookup"><span data-stu-id="0fdf6-172">Improvements to Pester</span></span>

<span data-ttu-id="0fdf6-173">In WMF 5,1 wurde die im Lieferumfang von PowerShell enthaltene Version von Pester von 3.3.5 auf 3.4.0 aktualisiert, mit dem Hinzufügen von GitHub [PR # 484](https://github.com/pester/Pester/pull/484), was ein besseres Verhalten für Pester auf Nano Server ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="0fdf6-173">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0, with the addition of GitHub [PR# 484](https://github.com/pester/Pester/pull/484), which enables better behavior for Pester on Nano Server.</span></span>

<span data-ttu-id="0fdf6-174">Überprüfen Sie die Veränderungen in Version 3.4.0 im Vergleich zu Version 3.3.5 durch Untersuchen der ChangeLog.md-Datei unter: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span><span class="sxs-lookup"><span data-stu-id="0fdf6-174">You can review the changes in versions 3.3.5 to 3.4.0 by inspecting the ChangeLog.md file at: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span></span>

## <a name="keywords"></a><span data-ttu-id="0fdf6-175">Keywords</span><span class="sxs-lookup"><span data-stu-id="0fdf6-175">KEYWORDS</span></span>

<span data-ttu-id="0fdf6-176">Neues in Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="0fdf6-176">What's New in Windows PowerShell 5.1</span></span>
