---
description: Die Umgebungsvariable psmodulepath enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_PSModulePath?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Grundlegendes zu PSModulePath
ms.openlocfilehash: 580c7a1d61e481448e2f49f62fb7d089922e72b5
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524789"
---
# <a name="about-psmodulepath"></a><span data-ttu-id="53abc-104">Informationen über psmodulepath</span><span class="sxs-lookup"><span data-stu-id="53abc-104">About PSModulePath</span></span>

<span data-ttu-id="53abc-105">Die `$env:PSModulePath` Umgebungsvariable enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden.</span><span class="sxs-lookup"><span data-stu-id="53abc-105">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span> <span data-ttu-id="53abc-106">PowerShell durchsucht jeden Ordner rekursiv nach `.psd1` Modul `.psm1` Dateien (oder Dateien).</span><span class="sxs-lookup"><span data-stu-id="53abc-106">PowerShell recursively searches each folder for module (`.psd1` or `.psm1`) files.</span></span>

<span data-ttu-id="53abc-107">Standardmäßig sind die folgenden effektiven Speicherorte zugewiesen `$env:PSModulePath` :</span><span class="sxs-lookup"><span data-stu-id="53abc-107">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="53abc-108">System weite Speicherorte: diese Ordner enthalten Module, die mit PowerShell ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="53abc-108">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="53abc-109">Diese Module sind im Ordner gespeichert `$PSHOME\Modules` .</span><span class="sxs-lookup"><span data-stu-id="53abc-109">These modules are store in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="53abc-110">Dies ist auch der Speicherort, an dem die Windows-Verwaltungs Module installiert sind.</span><span class="sxs-lookup"><span data-stu-id="53abc-110">This is also the location where the Windows management modules are installed.</span></span>

- <span data-ttu-id="53abc-111">Vom Benutzer installierte Module: Dies sind Module, die vom Benutzer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="53abc-111">User-installed modules: These are modules installed by the user.</span></span>
  <span data-ttu-id="53abc-112">`Install-Module` verfügt über einen **Scope** -Parameter, mit dem Sie angeben können, ob das Modul für den aktuellen Benutzer oder für alle Benutzer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="53abc-112">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="53abc-113">Weitere Informationen finden Sie unter [Install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="53abc-113">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  - <span data-ttu-id="53abc-114">Unter Windows ist der Speicherort des benutzerspezifischen **CurrentUser** -Bereichs der `$HOME\Documents\PowerShell\Modules` Ordner.</span><span class="sxs-lookup"><span data-stu-id="53abc-114">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="53abc-115">Der Speicherort des **ALLUSERS** -Bereichs ist `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="53abc-115">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
  - <span data-ttu-id="53abc-116">Bei nicht-Windows-Systemen ist der Speicherort des benutzerspezifischen **CurrentUser** -Bereichs der `$HOME/.local/share/powershell/Modules` Ordner.</span><span class="sxs-lookup"><span data-stu-id="53abc-116">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="53abc-117">Der Speicherort des **ALLUSERS** -Bereichs ist `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="53abc-117">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

<span data-ttu-id="53abc-118">Außerdem können Setup Programme, die Module in anderen Verzeichnissen installieren, z. b. das Verzeichnis "Programme", ihre Speicherorte an den Wert von anfügen `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="53abc-118">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

> [!NOTE]
> <span data-ttu-id="53abc-119">Unter Windows ist der benutzerspezifische Speicherort der `PowerShell\Modules` Ordner im Ordner " **Dokumente** " in Ihrem Benutzerprofil.</span><span class="sxs-lookup"><span data-stu-id="53abc-119">On Windows, the user-specific location is the `PowerShell\Modules` folder located in the **Documents** folder in your user profile.</span></span> <span data-ttu-id="53abc-120">Der spezifische Pfad dieses Standorts variiert je nach Version von Windows und ob Sie die Ordner Umleitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="53abc-120">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="53abc-121">Microsoft onedrive kann auch den Speicherort des Ordners " **Dokumente** " ändern.</span><span class="sxs-lookup"><span data-stu-id="53abc-121">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span> <span data-ttu-id="53abc-122">Sie können den Speicherort des Ordners " **Dokumente** " mithilfe des folgenden Befehls überprüfen: `[Environment]::GetFolderPath('MyDocuments')` .</span><span class="sxs-lookup"><span data-stu-id="53abc-122">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

## <a name="modifying-psmodulepath"></a><span data-ttu-id="53abc-123">Ändern von psmodulepath</span><span class="sxs-lookup"><span data-stu-id="53abc-123">Modifying PSModulePath</span></span>

<span data-ttu-id="53abc-124">Um die Standardmodul Verzeichnisse für die aktuelle Sitzung zu ändern, verwenden Sie das folgende Befehls Format, um den Wert der `PSModulePath` Umgebungsvariablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="53abc-124">To change the default module directories for the current session, use the following command format to change the value of the `PSModulePath` environment variable.</span></span>

<span data-ttu-id="53abc-125">Wenn Sie z. b. das `C:\Program Files\Fabrikam\Modules` Verzeichnis dem Wert der psmodulepath-Umgebungsvariablen hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="53abc-125">For example, to add the `C:\Program Files\Fabrikam\Modules` directory to the value of the PSModulePath environment variable, type:</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath+";C:\Program Files\Fabrikam\Modules"
```

<span data-ttu-id="53abc-126">Das Semikolon ( `;` ) im Befehl trennt den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="53abc-126">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span> <span data-ttu-id="53abc-127">Auf nicht-Windows-Plattformen trennt der Doppelpunkt ( `:` ) die Pfad Positionen in der Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="53abc-127">On non-Windows platforms, the colon (`:`) separates the path locations in the environment variable.</span></span>

<span data-ttu-id="53abc-128">Wenn Sie den Wert von `PSModulePath` in jeder Sitzung ändern möchten, fügen Sie den vorherigen Befehl zu Ihrem PowerShell-Profil hinzu, oder verwenden Sie die Methode "\* **tenvironmentvariable** " der **Umgebungs** Klasse.</span><span class="sxs-lookup"><span data-stu-id="53abc-128">To change the value of `PSModulePath` in every session, add the previous command to your PowerShell profile or use the **SetEnvironmentVariable** method of the **Environment** class.</span></span>

<span data-ttu-id="53abc-129">Der folgende Befehl verwendet die **GetEnvironmentVariable** -Methode, um die Computer Einstellung von `PSModulePath` und die Methode " **enumervironmentvariable** " zum Hinzufügen des `C:\Program Files\Fabrikam\Modules` Pfads zum Wert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="53abc-129">The following command uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'Machine')
```

<span data-ttu-id="53abc-130">Zum Hinzufügen eines Pfads zur Benutzereinstellung ändern Sie den Zielwert in **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="53abc-130">To add a path to the user setting, change the target value to **User**.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'User')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'User')
```

<span data-ttu-id="53abc-131">Weitere Informationen zu den Methoden der **System. Environment** -Klasse finden Sie unter [Umgebungs Methoden](/dotnet/api/system.environment).</span><span class="sxs-lookup"><span data-stu-id="53abc-131">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="powershell-psmodulepath-construction"></a><span data-ttu-id="53abc-132">PowerShell psmodulepath-Konstruktion</span><span class="sxs-lookup"><span data-stu-id="53abc-132">PowerShell PSModulePath construction</span></span>

<span data-ttu-id="53abc-133">Der Wert von `$env:PSModulePath` wird bei jedem Start von PowerShell erstellt.</span><span class="sxs-lookup"><span data-stu-id="53abc-133">The value of `$env:PSModulePath` is constructed each time PowerShell starts.</span></span>
<span data-ttu-id="53abc-134">Der Wert variiert je nach Version von PowerShell und dessen Start.</span><span class="sxs-lookup"><span data-stu-id="53abc-134">The value varies by version of PowerShell and how it is launched.</span></span>

### <a name="windows-powershell-startup"></a><span data-ttu-id="53abc-135">Windows PowerShell-Start</span><span class="sxs-lookup"><span data-stu-id="53abc-135">Windows PowerShell startup</span></span>

<span data-ttu-id="53abc-136">Windows PowerShell verwendet die folgende Logik, um `PSModulePath` beim Start zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="53abc-136">Windows PowerShell uses the following logic to construct the `PSModulePath` at startup:</span></span>

- <span data-ttu-id="53abc-137">Wenn `PSModulePath` nicht vorhanden ist, kombinieren Sie **CurrentUser** , **ALLUSERS** und die `$PSHOME` Module-Pfade.</span><span class="sxs-lookup"><span data-stu-id="53abc-137">If `PSModulePath` doesn't exist, combine **CurrentUser** , **AllUsers** , and the `$PSHOME` modules paths</span></span>
- <span data-ttu-id="53abc-138">Wenn `PSModulePath` vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="53abc-138">If `PSModulePath` does exist:</span></span>
  - <span data-ttu-id="53abc-139">Wenn `PSModulePath` den `$PSHOME` Modulpfad enthält:</span><span class="sxs-lookup"><span data-stu-id="53abc-139">If `PSModulePath` contains `$PSHOME` modules path:</span></span>
    - <span data-ttu-id="53abc-140">Der **ALLUSERS** -Modulpfad wird vor dem `$PSHOME` Modulpfad eingefügt.</span><span class="sxs-lookup"><span data-stu-id="53abc-140">**AllUsers** modules path is inserted before `$PSHOME` modules path</span></span>
  - <span data-ttu-id="53abc-141">woanders</span><span class="sxs-lookup"><span data-stu-id="53abc-141">else:</span></span>
    - <span data-ttu-id="53abc-142">Verwenden Sie einfach `PSModulePath` wie definiert, da der Benutzer den Speicherort absichtlich entfernt hat. `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="53abc-142">Just use `PSModulePath` as defined since the user deliberately removed the `$PSHOME` location</span></span>

<span data-ttu-id="53abc-143">Der **CurrentUser** -Modulpfad wird nur vorangestellt, wenn der Benutzerbereich `$env:PSModulePath` nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="53abc-143">The **CurrentUser** module path is prefixed only if User scope `$env:PSModulePath` doesn't exist.</span></span> <span data-ttu-id="53abc-144">Andernfalls wird der Benutzerbereich `$env:PSModulePath` wie definiert verwendet.</span><span class="sxs-lookup"><span data-stu-id="53abc-144">Otherwise, the User scope `$env:PSModulePath` is used as defined.</span></span>

### <a name="powershell-core-6-startup"></a><span data-ttu-id="53abc-145">Starten von PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="53abc-145">PowerShell Core 6 startup</span></span>

<span data-ttu-id="53abc-146">PowerShell Core 6 verwendet keinen Inhalt von, `$env:PSModulePath` Wenn er erkennt, dass er von PowerShell gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="53abc-146">PowerShell Core 6 doesn't use contents of `$env:PSModulePath` if it detects it was started from PowerShell.</span></span> <span data-ttu-id="53abc-147">Sie überschreibt Sie mit:</span><span class="sxs-lookup"><span data-stu-id="53abc-147">It overwrites it with:</span></span>

- <span data-ttu-id="53abc-148">**CurrentUser** -Modulpfad + **ALLUSERS** Modulpfad + `$PSHOME` Modulpfad + Windows PowerShell- `$PSHOME` Modulpfad.</span><span class="sxs-lookup"><span data-stu-id="53abc-148">**CurrentUser** modules path + **AllUsers** modules path + `$PSHOME` modules path + Windows PowerShell `$PSHOME` modules path.</span></span>

### <a name="powershell-7-startup"></a><span data-ttu-id="53abc-149">PowerShell 7-Start</span><span class="sxs-lookup"><span data-stu-id="53abc-149">PowerShell 7 startup</span></span>

<span data-ttu-id="53abc-150">In Windows verwendet ein neuer Prozess bei den meisten Umgebungsvariablen nur dann diesen Wert, wenn die Variable im Benutzerbereich vorhanden ist, auch wenn eine Variable mit dem gleichen Namen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="53abc-150">In Windows, for most environment variables, if the User-scoped variable exists, a new process uses that value only even if a Machine-scoped variable of the same name exists.</span></span>

<span data-ttu-id="53abc-151">In PowerShell 7 `PSModulePath` wird ähnlich wie die `Path` Umgebungsvariable unter Windows behandelt.</span><span class="sxs-lookup"><span data-stu-id="53abc-151">In PowerShell 7, `PSModulePath` is treated similar to how the `Path` environment variable is treated on Windows.</span></span> <span data-ttu-id="53abc-152">Unter Windows `Path` wird von anderen Umgebungsvariablen anders behandelt.</span><span class="sxs-lookup"><span data-stu-id="53abc-152">On Windows, `Path` is treated differently from other environment variables.</span></span> <span data-ttu-id="53abc-153">Wenn ein Prozess gestartet wird, kombiniert Windows den Benutzer bezogenen Bereich `Path` mit dem Computerbereich `Path` .</span><span class="sxs-lookup"><span data-stu-id="53abc-153">When a process is started, Windows combines the User-scoped `Path` with the Machine-scoped `Path`.</span></span>

- <span data-ttu-id="53abc-154">Abrufen des Benutzer bezogenen Bereichs `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="53abc-154">Retrieve the User-scoped `PSModulePath`</span></span>
- <span data-ttu-id="53abc-155">Mit der vom Prozess geerbten `PSModulePath` Umgebungsvariablen vergleichen</span><span class="sxs-lookup"><span data-stu-id="53abc-155">Compare to process inherited `PSModulePath` environment variable</span></span>
  - <span data-ttu-id="53abc-156">Wenn derselbe:</span><span class="sxs-lookup"><span data-stu-id="53abc-156">If the same:</span></span>
    - <span data-ttu-id="53abc-157">Fügen Sie die **ALLUSERS** am `PSModulePath` Ende der Semantik der `Path` Umgebungsvariablen an.</span><span class="sxs-lookup"><span data-stu-id="53abc-157">Append the **AllUsers** `PSModulePath` to the end following the semantics of the `Path` environment variable</span></span>
    - <span data-ttu-id="53abc-158">Der Windows- `System32` Pfad stammt von dem definierten Computer `PSModulePath` und muss daher nicht explizit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="53abc-158">The Windows `System32` path comes from the machine defined `PSModulePath` so does not need to be added explicitly</span></span>
  - <span data-ttu-id="53abc-159">Wenn dies anders ist, sollten Sie so behandeln, als ob der Benutzer es explizit geändert hat und **ALLUSERS**`PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="53abc-159">If different, treat as though user explicitly modified it and don't append **AllUsers** `PSModulePath`</span></span>
- <span data-ttu-id="53abc-160">Präfix mit PS7 User, System und `$PSHOME` path in dieser Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="53abc-160">Prefix with PS7 User, System, and `$PSHOME` paths in that order</span></span>
  - <span data-ttu-id="53abc-161">Wenn `powershell.config.json` einen Benutzerbereich enthält `PSModulePath` , verwenden Sie diesen anstelle der Standardeinstellung für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="53abc-161">If `powershell.config.json` contains a user scoped `PSModulePath`, use that instead of the default for the user</span></span>
  - <span data-ttu-id="53abc-162">Wenn `powershell.config.json` ein Systembereich enthält `PSModulePath` , verwenden Sie diesen anstelle des standardmäßigen für das System.</span><span class="sxs-lookup"><span data-stu-id="53abc-162">If `powershell.config.json` contains a system scoped `PSModulePath`, use that instead of the default for the system</span></span>

<span data-ttu-id="53abc-163">UNIX-Systeme haben keine Trennung von Benutzer-und System Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="53abc-163">Unix systems don't have a separation of User and System environment variables.</span></span>
<span data-ttu-id="53abc-164">`PSModulePath` wird geerbt, und die PS7-spezifischen Pfade haben das Präfix, wenn Sie nicht bereits definiert sind.</span><span class="sxs-lookup"><span data-stu-id="53abc-164">`PSModulePath` is inherited and the PS7-specific paths are prefixed if not already defined.</span></span>

### <a name="starting-windows-powershell-from-powershell-7"></a><span data-ttu-id="53abc-165">Starten von Windows PowerShell über PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="53abc-165">Starting Windows PowerShell from PowerShell 7</span></span>

<span data-ttu-id="53abc-166">In dieser Erläuterung bedeutet _Windows PowerShell_ sowohl `powershell.exe` als auch `powershell_ise.exe` .</span><span class="sxs-lookup"><span data-stu-id="53abc-166">For this discussion, _Windows PowerShell_ means both `powershell.exe` and `powershell_ise.exe`.</span></span>

<span data-ttu-id="53abc-167">Der Wert von `$env:PSModulePath` wird `WinPSModulePath` mit den folgenden Änderungen in kopiert:</span><span class="sxs-lookup"><span data-stu-id="53abc-167">The value of `$env:PSModulePath` is copied to `WinPSModulePath` with the following modifications:</span></span>

- <span data-ttu-id="53abc-168">Remove PS7 the User Module Path</span><span class="sxs-lookup"><span data-stu-id="53abc-168">Remove PS7 the User module path</span></span>
- <span data-ttu-id="53abc-169">Remove PS7 the System Module Path</span><span class="sxs-lookup"><span data-stu-id="53abc-169">Remove PS7 the System module path</span></span>
- <span data-ttu-id="53abc-170">Remove PS7 der `$PSHOME` Modulpfad</span><span class="sxs-lookup"><span data-stu-id="53abc-170">Remove PS7 the `$PSHOME` module path</span></span>

<span data-ttu-id="53abc-171">Die PS7-Pfade werden entfernt, sodass PS7-Module nicht in Windows PowerShell geladen werden.</span><span class="sxs-lookup"><span data-stu-id="53abc-171">The PS7 paths are removed so that PS7 modules don't get loaded in Windows PowerShell.</span></span> <span data-ttu-id="53abc-172">Der `WinPSModulePath` Wert wird beim Starten von Windows PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="53abc-172">The `WinPSModulePath` value is used when starting Windows PowerShell.</span></span>

### <a name="starting-powershell-7-from-windows-powershell"></a><span data-ttu-id="53abc-173">Starten von PowerShell 7 über Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53abc-173">Starting PowerShell 7 from Windows PowerShell</span></span>

<span data-ttu-id="53abc-174">Der Start von PowerShell 7 wird unverändert fortgesetzt, und es werden die von Windows PowerShell hinzugefügten Pfade geerbt.</span><span class="sxs-lookup"><span data-stu-id="53abc-174">The PowerShell 7 startup continues as-is with the addition of inheriting paths that Windows PowerShell added.</span></span> <span data-ttu-id="53abc-175">Da die PS7-spezifischen Pfade mit einem Präfix versehen sind, gibt es kein funktionales Problem.</span><span class="sxs-lookup"><span data-stu-id="53abc-175">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

### <a name="starting-powershell-6-from-powershell-7"></a><span data-ttu-id="53abc-176">Starten von PowerShell 6 von PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="53abc-176">Starting PowerShell 6 from PowerShell 7</span></span>

<span data-ttu-id="53abc-177">PowerShell Core 6 überschreibt `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="53abc-177">PowerShell Core 6 overwrites `$env:PSModulePath`.</span></span> <span data-ttu-id="53abc-178">Es werden keine Änderungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="53abc-178">No changes are made.</span></span>

### <a name="starting-powershell-7-from-powershell-6"></a><span data-ttu-id="53abc-179">Starten von PowerShell 7 von PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="53abc-179">Starting PowerShell 7 from PowerShell 6</span></span>

<span data-ttu-id="53abc-180">Der Start von PowerShell 7 wird unverändert fortgesetzt, und es werden die von PowerShell Core 6 hinzugefügten Pfade geerbt.</span><span class="sxs-lookup"><span data-stu-id="53abc-180">The PowerShell 7 startup continues as-is with the addition of inheriting paths that PowerShell Core 6 added.</span></span> <span data-ttu-id="53abc-181">Da die PS7-spezifischen Pfade mit einem Präfix versehen sind, gibt es kein funktionales Problem.</span><span class="sxs-lookup"><span data-stu-id="53abc-181">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

## <a name="module-search-behavior"></a><span data-ttu-id="53abc-182">Modul Suchverhalten</span><span class="sxs-lookup"><span data-stu-id="53abc-182">Module search behavior</span></span>

<span data-ttu-id="53abc-183">PowerShell durchsucht rekursiv jeden Ordner in " **psmodulepath** " nach Modul `.psd1` Dateien (oder `.psm1` Dateien).</span><span class="sxs-lookup"><span data-stu-id="53abc-183">PowerShell recursively searches each folder in the **PSModulePath** for module (`.psd1` or `.psm1`) files.</span></span> <span data-ttu-id="53abc-184">Dieses Suchmuster ermöglicht das Installieren mehrerer Versionen desselben Moduls in verschiedenen Ordnern.</span><span class="sxs-lookup"><span data-stu-id="53abc-184">This search pattern allows multiple versions of the same module to be installed in different folders.</span></span> <span data-ttu-id="53abc-185">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="53abc-185">For example:</span></span>

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules\PowerShellGet

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----           8/14/2020  5:56 PM                1.0.0.1
d----           9/13/2019  3:53 PM                2.1.2
```

<span data-ttu-id="53abc-186">Standardmäßig lädt PowerShell die höchste Versionsnummer eines Moduls, wenn mehrere Versionen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="53abc-186">By default, PowerShell loads the highest version number of a module when multiple versions are found.</span></span> <span data-ttu-id="53abc-187">Verwenden Sie zum Laden einer bestimmten Version `Import-Module` mit dem **FullyQualifiedName** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="53abc-187">To load a specific version, use `Import-Module` with the **FullyQualifiedName** parameter.</span></span> <span data-ttu-id="53abc-188">Weitere Informationen finden Sie unter [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span><span class="sxs-lookup"><span data-stu-id="53abc-188">For more information, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="see-also"></a><span data-ttu-id="53abc-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53abc-189">See also</span></span>

- [<span data-ttu-id="53abc-190">about_Modules</span><span class="sxs-lookup"><span data-stu-id="53abc-190">about_Modules</span></span>](about_Modules.md)
- [<span data-ttu-id="53abc-191">Umgebungs Methoden</span><span class="sxs-lookup"><span data-stu-id="53abc-191">Environment Methods</span></span>](/dotnet/api/system.environment)
