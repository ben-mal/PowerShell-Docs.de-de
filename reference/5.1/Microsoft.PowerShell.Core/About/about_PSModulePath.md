---
description: Die Umgebungsvariable psmodulepath enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_PSModulePath?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Grundlegendes zu PSModulePath
ms.openlocfilehash: 60373e534fb319195c187b8cb26c6aabc0f3b8b7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222668"
---
# <a name="about-psmodulepath"></a><span data-ttu-id="af5fc-104">Informationen über psmodulepath</span><span class="sxs-lookup"><span data-stu-id="af5fc-104">About PSModulePath</span></span>

<span data-ttu-id="af5fc-105">Die `$env:PSModulePath` Umgebungsvariable enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden.</span><span class="sxs-lookup"><span data-stu-id="af5fc-105">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="af5fc-106">Standardmäßig sind die folgenden effektiven Speicherorte zugewiesen `$env:PSModulePath` :</span><span class="sxs-lookup"><span data-stu-id="af5fc-106">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="af5fc-107">System weite Speicherorte: diese Ordner enthalten Module, die mit PowerShell ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="af5fc-107">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="af5fc-108">Diese Module sind im Ordner gespeichert `$PSHOME\Modules` .</span><span class="sxs-lookup"><span data-stu-id="af5fc-108">These modules are store in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="af5fc-109">Dies ist auch der Speicherort, an dem die Windows-Verwaltungs Module installiert sind.</span><span class="sxs-lookup"><span data-stu-id="af5fc-109">This is also the location where the Windows management modules are installed.</span></span>

- <span data-ttu-id="af5fc-110">Vom Benutzer installierte Module: Dies sind Module, die vom Benutzer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="af5fc-110">User-installed modules: These are modules installed by the user.</span></span>
  <span data-ttu-id="af5fc-111">`Install-Module` verfügt über einen **Scope** -Parameter, mit dem Sie angeben können, ob das Modul für den aktuellen Benutzer oder für alle Benutzer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="af5fc-111">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="af5fc-112">Weitere Informationen finden Sie unter [Install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="af5fc-112">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  - <span data-ttu-id="af5fc-113">Unter Windows ist der Speicherort des benutzerspezifischen **CurrentUser** -Bereichs der `$HOME\Documents\PowerShell\Modules` Ordner.</span><span class="sxs-lookup"><span data-stu-id="af5fc-113">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="af5fc-114">Der Speicherort des **ALLUSERS** -Bereichs ist `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="af5fc-114">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
  - <span data-ttu-id="af5fc-115">Bei nicht-Windows-Systemen ist der Speicherort des benutzerspezifischen **CurrentUser** -Bereichs der `$HOME/.local/share/powershell/Modules` Ordner.</span><span class="sxs-lookup"><span data-stu-id="af5fc-115">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="af5fc-116">Der Speicherort des **ALLUSERS** -Bereichs ist `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="af5fc-116">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

<span data-ttu-id="af5fc-117">Außerdem können Setup Programme, die Module in anderen Verzeichnissen installieren, z. b. das Verzeichnis "Programme", ihre Speicherorte an den Wert von anfügen `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="af5fc-117">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

> [!NOTE]
> <span data-ttu-id="af5fc-118">Unter Windows ist der benutzerspezifische Speicherort der `PowerShell\Modules` Ordner im Ordner " **Dokumente** " in Ihrem Benutzerprofil.</span><span class="sxs-lookup"><span data-stu-id="af5fc-118">On Windows, the user-specific location is the `PowerShell\Modules` folder located in the **Documents** folder in your user profile.</span></span> <span data-ttu-id="af5fc-119">Der spezifische Pfad dieses Standorts variiert je nach Version von Windows und ob Sie die Ordner Umleitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="af5fc-119">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="af5fc-120">Microsoft onedrive kann auch den Speicherort des Ordners " **Dokumente** " ändern.</span><span class="sxs-lookup"><span data-stu-id="af5fc-120">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span> <span data-ttu-id="af5fc-121">Sie können den Speicherort des Ordners " **Dokumente** " mithilfe des folgenden Befehls überprüfen: `[Environment]::GetFolderPath('MyDocuments')` .</span><span class="sxs-lookup"><span data-stu-id="af5fc-121">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

## <a name="modifying-psmodulepath"></a><span data-ttu-id="af5fc-122">Ändern von psmodulepath</span><span class="sxs-lookup"><span data-stu-id="af5fc-122">Modifying PSModulePath</span></span>

<span data-ttu-id="af5fc-123">Um die Standardmodul Verzeichnisse für die aktuelle Sitzung zu ändern, verwenden Sie das folgende Befehls Format, um den Wert der `PSModulePath` Umgebungsvariablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="af5fc-123">To change the default module directories for the current session, use the following command format to change the value of the `PSModulePath` environment variable.</span></span>

<span data-ttu-id="af5fc-124">Wenn Sie z. b. das `C:\Program Files\Fabrikam\Modules` Verzeichnis dem Wert der psmodulepath-Umgebungsvariablen hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="af5fc-124">For example, to add the `C:\Program Files\Fabrikam\Modules` directory to the value of the PSModulePath environment variable, type:</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath+";C:\Program Files\Fabrikam\Modules"
```

<span data-ttu-id="af5fc-125">Das Semikolon ( `;` ) im Befehl trennt den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="af5fc-125">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span> <span data-ttu-id="af5fc-126">Auf nicht-Windows-Plattformen trennt der Doppelpunkt ( `:` ) die Pfad Positionen in der Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="af5fc-126">On non-Windows platforms, the colon (`:`) separates the path locations in the environment variable.</span></span>

<span data-ttu-id="af5fc-127">Wenn Sie den Wert von `PSModulePath` in jeder Sitzung ändern möchten, fügen Sie den vorherigen Befehl zu Ihrem PowerShell-Profil hinzu, oder verwenden Sie die Methode "\* **tenvironmentvariable** " der **Umgebungs** Klasse.</span><span class="sxs-lookup"><span data-stu-id="af5fc-127">To change the value of `PSModulePath` in every session, add the previous command to your PowerShell profile or use the **SetEnvironmentVariable** method of the **Environment** class.</span></span>

<span data-ttu-id="af5fc-128">Der folgende Befehl verwendet die **GetEnvironmentVariable** -Methode, um die Computer Einstellung von `PSModulePath` und die Methode " **enumervironmentvariable** " zum Hinzufügen des `C:\Program Files\Fabrikam\Modules` Pfads zum Wert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="af5fc-128">The following command uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'Machine')
```

<span data-ttu-id="af5fc-129">Zum Hinzufügen eines Pfads zur Benutzereinstellung ändern Sie den Zielwert in **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="af5fc-129">To add a path to the user setting, change the target value to **User**.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'User')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'User')
```

<span data-ttu-id="af5fc-130">Weitere Informationen zu den Methoden der **System. Environment** -Klasse finden Sie unter [Umgebungs Methoden](/dotnet/api/system.environment).</span><span class="sxs-lookup"><span data-stu-id="af5fc-130">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="powershell-psmodulepath-construction"></a><span data-ttu-id="af5fc-131">PowerShell psmodulepath-Konstruktion</span><span class="sxs-lookup"><span data-stu-id="af5fc-131">PowerShell PSModulePath construction</span></span>

<span data-ttu-id="af5fc-132">Der Wert von `$env:PSModulePath` wird bei jedem Start von PowerShell erstellt.</span><span class="sxs-lookup"><span data-stu-id="af5fc-132">The value of `$env:PSModulePath` is constructed each time PowerShell starts.</span></span>
<span data-ttu-id="af5fc-133">Der Wert variiert je nach Version von PowerShell und dessen Start.</span><span class="sxs-lookup"><span data-stu-id="af5fc-133">The value varies by version of PowerShell and how it is launched.</span></span>

### <a name="windows-powershell-startup"></a><span data-ttu-id="af5fc-134">Windows PowerShell-Start</span><span class="sxs-lookup"><span data-stu-id="af5fc-134">Windows PowerShell startup</span></span>

<span data-ttu-id="af5fc-135">Windows PowerShell verwendet die folgende Logik, um `PSModulePath` beim Start zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="af5fc-135">Windows PowerShell uses the following logic to construct the `PSModulePath` at startup:</span></span>

- <span data-ttu-id="af5fc-136">Wenn `PSModulePath` nicht vorhanden ist, kombinieren Sie **CurrentUser** , **ALLUSERS** und die `$PSHOME` Module-Pfade.</span><span class="sxs-lookup"><span data-stu-id="af5fc-136">If `PSModulePath` doesn't exist, combine **CurrentUser** , **AllUsers** , and the `$PSHOME` modules paths</span></span>
- <span data-ttu-id="af5fc-137">Wenn `PSModulePath` vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="af5fc-137">If `PSModulePath` does exist:</span></span>
  - <span data-ttu-id="af5fc-138">Wenn `PSModulePath` den `$PSHOME` Modulpfad enthält:</span><span class="sxs-lookup"><span data-stu-id="af5fc-138">If `PSModulePath` contains `$PSHOME` modules path:</span></span>
    - <span data-ttu-id="af5fc-139">Der **ALLUSERS** -Modulpfad wird vor dem `$PSHOME` Modulpfad eingefügt.</span><span class="sxs-lookup"><span data-stu-id="af5fc-139">**AllUsers** modules path is inserted before `$PSHOME` modules path</span></span>
  - <span data-ttu-id="af5fc-140">woanders</span><span class="sxs-lookup"><span data-stu-id="af5fc-140">else:</span></span>
    - <span data-ttu-id="af5fc-141">Verwenden Sie einfach `PSModulePath` wie definiert, da der Benutzer den Speicherort absichtlich entfernt hat. `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="af5fc-141">Just use `PSModulePath` as defined since the user deliberately removed the `$PSHOME` location</span></span>

<span data-ttu-id="af5fc-142">Der **CurrentUser** -Modulpfad wird nur vorangestellt, wenn der Benutzerbereich `$env:PSModulePath` nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="af5fc-142">The **CurrentUser** module path is prefixed only if User scope `$env:PSModulePath` doesn't exist.</span></span> <span data-ttu-id="af5fc-143">Andernfalls wird der Benutzerbereich `$env:PSModulePath` wie definiert verwendet.</span><span class="sxs-lookup"><span data-stu-id="af5fc-143">Otherwise, the User scope `$env:PSModulePath` is used as defined.</span></span>

### <a name="powershell-core-6-startup"></a><span data-ttu-id="af5fc-144">Starten von PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="af5fc-144">PowerShell Core 6 startup</span></span>

<span data-ttu-id="af5fc-145">PowerShell Core 6 verwendet keinen Inhalt von, `$env:PSModulePath` Wenn er erkennt, dass er von PowerShell gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="af5fc-145">PowerShell Core 6 doesn't use contents of `$env:PSModulePath` if it detects it was started from PowerShell.</span></span> <span data-ttu-id="af5fc-146">Sie überschreibt Sie mit:</span><span class="sxs-lookup"><span data-stu-id="af5fc-146">It overwrites it with:</span></span>

- <span data-ttu-id="af5fc-147">**CurrentUser** -Modulpfad + **ALLUSERS** Modulpfad + `$PSHOME` Modulpfad + Windows PowerShell- `$PSHOME` Modulpfad.</span><span class="sxs-lookup"><span data-stu-id="af5fc-147">**CurrentUser** modules path + **AllUsers** modules path + `$PSHOME` modules path + Windows PowerShell `$PSHOME` modules path.</span></span>

### <a name="powershell-7-startup"></a><span data-ttu-id="af5fc-148">PowerShell 7-Start</span><span class="sxs-lookup"><span data-stu-id="af5fc-148">PowerShell 7 startup</span></span>

<span data-ttu-id="af5fc-149">In Windows verwendet ein neuer Prozess bei den meisten Umgebungsvariablen nur dann diesen Wert, wenn die Variable im Benutzerbereich vorhanden ist, auch wenn eine Variable mit dem gleichen Namen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="af5fc-149">In Windows, for most environment variables, if the User-scoped variable exists, a new process uses that value only even if a Machine-scoped variable of the same name exists.</span></span>

<span data-ttu-id="af5fc-150">In PowerShell 7 `PSModulePath` wird ähnlich wie die `Path` Umgebungsvariable unter Windows behandelt.</span><span class="sxs-lookup"><span data-stu-id="af5fc-150">In PowerShell 7, `PSModulePath` is treated similar to how the `Path` environment variable is treated on Windows.</span></span> <span data-ttu-id="af5fc-151">Unter Windows `Path` wird von anderen Umgebungsvariablen anders behandelt.</span><span class="sxs-lookup"><span data-stu-id="af5fc-151">On Windows, `Path` is treated differently from other environment variables.</span></span> <span data-ttu-id="af5fc-152">Wenn ein Prozess gestartet wird, kombiniert Windows den Benutzer bezogenen Bereich `Path` mit dem Computerbereich `Path` .</span><span class="sxs-lookup"><span data-stu-id="af5fc-152">When a process is started, Windows combines the User-scoped `Path` with the Machine-scoped `Path`.</span></span>

- <span data-ttu-id="af5fc-153">Abrufen des Benutzer bezogenen Bereichs `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="af5fc-153">Retrieve the User-scoped `PSModulePath`</span></span>
- <span data-ttu-id="af5fc-154">Mit der vom Prozess geerbten `PSModulePath` Umgebungsvariablen vergleichen</span><span class="sxs-lookup"><span data-stu-id="af5fc-154">Compare to process inherited `PSModulePath` environment variable</span></span>
  - <span data-ttu-id="af5fc-155">Wenn derselbe:</span><span class="sxs-lookup"><span data-stu-id="af5fc-155">If the same:</span></span>
    - <span data-ttu-id="af5fc-156">Fügen Sie die **ALLUSERS** am `PSModulePath` Ende der Semantik der `Path` Umgebungsvariablen an.</span><span class="sxs-lookup"><span data-stu-id="af5fc-156">Append the **AllUsers** `PSModulePath` to the end following the semantics of the `Path` environment variable</span></span>
    - <span data-ttu-id="af5fc-157">Der Windows- `System32` Pfad stammt von dem definierten Computer `PSModulePath` und muss daher nicht explizit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="af5fc-157">The Windows `System32` path comes from the machine defined `PSModulePath` so does not need to be added explicitly</span></span>
  - <span data-ttu-id="af5fc-158">Wenn dies anders ist, sollten Sie so behandeln, als ob der Benutzer es explizit geändert hat und **ALLUSERS**`PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="af5fc-158">If different, treat as though user explicitly modified it and don't append **AllUsers** `PSModulePath`</span></span>
- <span data-ttu-id="af5fc-159">Präfix mit PS7 User, System und `$PSHOME` path in dieser Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="af5fc-159">Prefix with PS7 User, System, and `$PSHOME` paths in that order</span></span>
  - <span data-ttu-id="af5fc-160">Wenn `powershell.config.json` einen Benutzerbereich enthält `PSModulePath` , verwenden Sie diesen anstelle der Standardeinstellung für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="af5fc-160">If `powershell.config.json` contains a user scoped `PSModulePath`, use that instead of the default for the user</span></span>
  - <span data-ttu-id="af5fc-161">Wenn `powershell.config.json` ein Systembereich enthält `PSModulePath` , verwenden Sie diesen anstelle des standardmäßigen für das System.</span><span class="sxs-lookup"><span data-stu-id="af5fc-161">If `powershell.config.json` contains a system scoped `PSModulePath`, use that instead of the default for the system</span></span>

<span data-ttu-id="af5fc-162">UNIX-Systeme haben keine Trennung von Benutzer-und System Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="af5fc-162">Unix systems don't have a separation of User and System environment variables.</span></span>
<span data-ttu-id="af5fc-163">`PSModulePath` wird geerbt, und die PS7-spezifischen Pfade haben das Präfix, wenn Sie nicht bereits definiert sind.</span><span class="sxs-lookup"><span data-stu-id="af5fc-163">`PSModulePath` is inherited and the PS7-specific paths are prefixed if not already defined.</span></span>

### <a name="starting-windows-powershell-from-powershell-7"></a><span data-ttu-id="af5fc-164">Starten von Windows PowerShell über PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="af5fc-164">Starting Windows PowerShell from PowerShell 7</span></span>

<span data-ttu-id="af5fc-165">In dieser Erläuterung bedeutet _Windows PowerShell_ sowohl `powershell.exe` als auch `powershell_ise.exe` .</span><span class="sxs-lookup"><span data-stu-id="af5fc-165">For this discussion, _Windows PowerShell_ means both `powershell.exe` and `powershell_ise.exe`.</span></span>

<span data-ttu-id="af5fc-166">Der Wert von `$env:PSModulePath` wird `WinPSModulePath` mit den folgenden Änderungen in kopiert:</span><span class="sxs-lookup"><span data-stu-id="af5fc-166">The value of `$env:PSModulePath` is copied to `WinPSModulePath` with the following modifications:</span></span>

- <span data-ttu-id="af5fc-167">Remove PS7 the User Module Path</span><span class="sxs-lookup"><span data-stu-id="af5fc-167">Remove PS7 the User module path</span></span>
- <span data-ttu-id="af5fc-168">Remove PS7 the System Module Path</span><span class="sxs-lookup"><span data-stu-id="af5fc-168">Remove PS7 the System module path</span></span>
- <span data-ttu-id="af5fc-169">Remove PS7 der `$PSHOME` Modulpfad</span><span class="sxs-lookup"><span data-stu-id="af5fc-169">Remove PS7 the `$PSHOME` module path</span></span>

<span data-ttu-id="af5fc-170">Die PS7-Pfade werden entfernt, sodass PS7-Module nicht in Windows PowerShell geladen werden.</span><span class="sxs-lookup"><span data-stu-id="af5fc-170">The PS7 paths are removed so that PS7 modules don't get loaded in Windows PowerShell.</span></span> <span data-ttu-id="af5fc-171">Der `WinPSModulePath` Wert wird beim Starten von Windows PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="af5fc-171">The `WinPSModulePath` value is used when starting Windows PowerShell.</span></span>

### <a name="starting-powershell-7-from-windows-powershell"></a><span data-ttu-id="af5fc-172">Starten von PowerShell 7 über Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af5fc-172">Starting PowerShell 7 from Windows PowerShell</span></span>

<span data-ttu-id="af5fc-173">Der Start von PowerShell 7 wird unverändert fortgesetzt, und es werden die von Windows PowerShell hinzugefügten Pfade geerbt.</span><span class="sxs-lookup"><span data-stu-id="af5fc-173">The PowerShell 7 startup continues as-is with the addition of inheriting paths that Windows PowerShell added.</span></span> <span data-ttu-id="af5fc-174">Da die PS7-spezifischen Pfade mit einem Präfix versehen sind, gibt es kein funktionales Problem.</span><span class="sxs-lookup"><span data-stu-id="af5fc-174">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

### <a name="starting-powershell-6-from-powershell-7"></a><span data-ttu-id="af5fc-175">Starten von PowerShell 6 von PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="af5fc-175">Starting PowerShell 6 from PowerShell 7</span></span>

<span data-ttu-id="af5fc-176">PowerShell Core 6 überschreibt `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="af5fc-176">PowerShell Core 6 overwrites `$env:PSModulePath`.</span></span> <span data-ttu-id="af5fc-177">Es werden keine Änderungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="af5fc-177">No changes are made.</span></span>

### <a name="starting-powershell-7-from-powershell-6"></a><span data-ttu-id="af5fc-178">Starten von PowerShell 7 von PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="af5fc-178">Starting PowerShell 7 from PowerShell 6</span></span>

<span data-ttu-id="af5fc-179">Der Start von PowerShell 7 wird unverändert fortgesetzt, und es werden die von PowerShell Core 6 hinzugefügten Pfade geerbt.</span><span class="sxs-lookup"><span data-stu-id="af5fc-179">The PowerShell 7 startup continues as-is with the addition of inheriting paths that PowerShell Core 6 added.</span></span> <span data-ttu-id="af5fc-180">Da die PS7-spezifischen Pfade mit einem Präfix versehen sind, gibt es kein funktionales Problem.</span><span class="sxs-lookup"><span data-stu-id="af5fc-180">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

## <a name="see-also"></a><span data-ttu-id="af5fc-181">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="af5fc-181">See also</span></span>

- [<span data-ttu-id="af5fc-182">about_Modules</span><span class="sxs-lookup"><span data-stu-id="af5fc-182">about_Modules</span></span>](about_Modules.md)
- [<span data-ttu-id="af5fc-183">Umgebungs Methoden</span><span class="sxs-lookup"><span data-stu-id="af5fc-183">Environment Methods</span></span>](/dotnet/api/system.environment)
