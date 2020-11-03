---
description: Hier wird beschrieben, wie Sie in PowerShell auf Windows-Umgebungsvariablen zugreifen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_variables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Environment_Variables
ms.openlocfilehash: c954ee6e783b7926dbcd05a3e08b6b9b5cf9bc25
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222071"
---
# <a name="about-environment-variables"></a><span data-ttu-id="65b31-104">Informationen zu Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="65b31-104">About Environment Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="65b31-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="65b31-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="65b31-106">Hier wird beschrieben, wie Sie in PowerShell auf Windows-Umgebungsvariablen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="65b31-106">Describes how to access Windows environment variables in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="65b31-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="65b31-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="65b31-108">Umgebungsvariablen speichern Informationen über die Betriebssystemumgebung.</span><span class="sxs-lookup"><span data-stu-id="65b31-108">Environment variables store information about the operating system environment.</span></span> <span data-ttu-id="65b31-109">Diese Informationen umfassen Details wie den Betriebssystem Pfad, die Anzahl der Prozessoren, die vom Betriebssystem verwendet werden, und den Speicherort der temporären Ordner.</span><span class="sxs-lookup"><span data-stu-id="65b31-109">This information includes details such as the operating system path, the number of processors used by the operating system, and the location of temporary folders.</span></span>

<span data-ttu-id="65b31-110">In den Umgebungsvariablen werden Daten gespeichert, die vom Betriebssystem und anderen Programmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65b31-110">The environment variables store data that is used by the operating system and other programs.</span></span> <span data-ttu-id="65b31-111">Die `WINDIR` Umgebungsvariable enthält z. b. den Speicherort des Windows-Installationsverzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="65b31-111">For example, the `WINDIR` environment variable contains the location of the Windows installation directory.</span></span> <span data-ttu-id="65b31-112">Programme können den Wert dieser Variablen Abfragen, um zu bestimmen, wo sich die Dateien des Windows-Betriebssystems befinden.</span><span class="sxs-lookup"><span data-stu-id="65b31-112">Programs can query the value of this variable to determine where Windows operating system files are located.</span></span>

<span data-ttu-id="65b31-113">PowerShell kann auf Umgebungsvariablen auf allen unterstützten Betriebssystemplattformen zugreifen und diese verwalten.</span><span class="sxs-lookup"><span data-stu-id="65b31-113">PowerShell can access and manage environment variables in any of the supported operating system platforms.</span></span> <span data-ttu-id="65b31-114">Der PowerShell-Umgebungs Anbieter vereinfacht diesen Prozess, indem er die Anzeige und Änderung von Umgebungsvariablen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="65b31-114">The PowerShell environment provider simplifies this process by making it easy to view and change environment variables.</span></span>

<span data-ttu-id="65b31-115">Umgebungsvariablen werden im Gegensatz zu anderen Variablen Typen in PowerShell von untergeordneten Prozessen geerbt, wie z. b. lokalen Hintergrund Aufträgen und den Sitzungen, in denen Modulmember ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="65b31-115">Environment variables, unlike other types of variables in PowerShell, are inherited by child processes, such as local background jobs and the sessions in which module members run.</span></span> <span data-ttu-id="65b31-116">Dadurch eignen sich Umgebungsvariablen gut zum Speichern von Werten, die in über-und untergeordneten Prozessen benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="65b31-116">This makes environment variables well suited to storing values that are needed in both parent and child processes.</span></span>

## <a name="using-and-changing-environment-variables"></a><span data-ttu-id="65b31-117">Verwenden und Ändern von Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="65b31-117">Using and changing environment variables</span></span>

<span data-ttu-id="65b31-118">Unter Windows können Umgebungsvariablen in drei Bereichen definiert werden:</span><span class="sxs-lookup"><span data-stu-id="65b31-118">On Windows, environment variables can be defined in three scopes:</span></span>

- <span data-ttu-id="65b31-119">Computerbereich (oder System)</span><span class="sxs-lookup"><span data-stu-id="65b31-119">Machine (or System) scope</span></span>
- <span data-ttu-id="65b31-120">Benutzerbereich</span><span class="sxs-lookup"><span data-stu-id="65b31-120">User scope</span></span>
- <span data-ttu-id="65b31-121">Prozessbereich</span><span class="sxs-lookup"><span data-stu-id="65b31-121">Process scope</span></span>

<span data-ttu-id="65b31-122">Der _Prozess_ Bereich enthält die Umgebungsvariablen, die im aktuellen Prozess oder in der PowerShell-Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="65b31-122">The _Process_ scope contains the environment variables available in the current process, or PowerShell session.</span></span> <span data-ttu-id="65b31-123">Diese Liste der Variablen wird vom übergeordneten Prozess geerbt und aus den Variablen in den Bereichen _Computer_ und _Benutzer_ erstellt.</span><span class="sxs-lookup"><span data-stu-id="65b31-123">This list of variables is inherited from the parent process and is constructed from the variables in the _Machine_ and _User_ scopes.</span></span> <span data-ttu-id="65b31-124">UNIX-basierte Plattformen verfügen nur über den _Prozess_ Bereich.</span><span class="sxs-lookup"><span data-stu-id="65b31-124">Unix-based platforms only have the _Process_ scope.</span></span>

<span data-ttu-id="65b31-125">Sie können die Werte von Umgebungsvariablen anzeigen und ändern, ohne ein Cmdlet zu verwenden, indem Sie eine Variablen Syntax mit dem Umgebungs Anbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="65b31-125">You can display and change the values of environment variables without using a cmdlet by using a variable syntax with the environment provider.</span></span> <span data-ttu-id="65b31-126">Verwenden Sie die folgende Syntax, um den Wert einer Umgebungsvariablen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="65b31-126">To display the value of an environment variable, use the following syntax:</span></span>

```
$Env:<variable-name>
```

<span data-ttu-id="65b31-127">Wenn Sie z. b. den Wert der `WINDIR` Umgebungsvariablen anzeigen möchten, geben Sie an der PowerShell-Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="65b31-127">For example, to display the value of the `WINDIR` environment variable, type the following command at the PowerShell command prompt:</span></span>

```powershell
$Env:windir
```

<span data-ttu-id="65b31-128">In dieser Syntax gibt das Dollarzeichen ( `$` ) eine Variable an, und der Laufwerks Name ( `Env:` ) gibt eine Umgebungsvariable an, gefolgt vom Variablennamen ( `windir` ).</span><span class="sxs-lookup"><span data-stu-id="65b31-128">In this syntax, the dollar sign (`$`) indicates a variable, and the drive name (`Env:`) indicates an environment variable followed by the variable name (`windir`).</span></span>

<span data-ttu-id="65b31-129">Wenn Sie Umgebungsvariablen in PowerShell ändern, wirkt sich die Änderung nur auf die aktuelle Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="65b31-129">When you change environment variables in PowerShell, the change affects only the current session.</span></span> <span data-ttu-id="65b31-130">Dieses Verhalten ähnelt dem Verhalten des `Set` Befehls in der Windows-Befehlsshell und des `Setenv` Befehls in UNIX-basierten Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="65b31-130">This behavior resembles the behavior of the `Set` command in the Windows Command Shell and the `Setenv` command in UNIX-based environments.</span></span> <span data-ttu-id="65b31-131">Wenn Sie Werte in den Bereichen Computer oder Benutzer ändern möchten, müssen Sie die Methoden der **System. Environment** -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="65b31-131">To change values in the Machine or User scopes, you must use the methods of the **System.Environment** class.</span></span>

<span data-ttu-id="65b31-132">Um Änderungen an Variablen im Computerbereich vorzunehmen, muss ebenfalls über die-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="65b31-132">To make changes to Machine-scoped variables, must also have permission.</span></span> <span data-ttu-id="65b31-133">Wenn Sie versuchen, einen Wert ohne ausreichende Berechtigungen zu ändern, schlägt der Befehl fehl, und PowerShell zeigt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="65b31-133">If you try to change a value without sufficient permission, the command fails and PowerShell displays an error.</span></span>

<span data-ttu-id="65b31-134">Sie können die Werte von Variablen ändern, ohne ein Cmdlet mit der folgenden Syntax zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="65b31-134">You can change the values of variables without using a cmdlet using the following syntax:</span></span>

```powershell
$Env:<variable-name> = "<new-value>"
```

<span data-ttu-id="65b31-135">Um z. b. `;c:\temp` an den Wert der `Path` Umgebungsvariablen anzufügen, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="65b31-135">For example, to append `;c:\temp` to the value of the `Path` environment variable, use the following syntax:</span></span>

```powershell
$Env:Path += ";c:\temp"
```

<span data-ttu-id="65b31-136">Unter Linux oder MacOS trennt der Doppelpunkt ( `:` ) im Befehl den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="65b31-136">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

```powershell
$Env:PATH += ":/usr/local/temp"
```

<span data-ttu-id="65b31-137">Sie können auch die Item-Cmdlets verwenden, z `Set-Item` `Remove-Item` . b., und, `Copy-Item` um die Werte von Umgebungsvariablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="65b31-137">You can also use the Item cmdlets, such as `Set-Item`, `Remove-Item`, and `Copy-Item` to change the values of environment variables.</span></span> <span data-ttu-id="65b31-138">Verwenden Sie z. b. die folgende Syntax, um das `Set-Item` Cmdlet zum Anfügen `;c:\temp` an den Wert der `Path` Umgebungsvariablen zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="65b31-138">For example, to use the `Set-Item` cmdlet to append `;c:\temp` to the value of the `Path` environment variable, use the following syntax:</span></span>

```powershell
Set-Item -Path Env:Path -Value ($Env:Path + ";C:\Temp")
```

<span data-ttu-id="65b31-139">In diesem Befehl wird der Wert in Klammern eingeschlossen, sodass er als Einheit interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="65b31-139">In this command, the value is enclosed in parentheses so that it is interpreted as a unit.</span></span>

## <a name="environment-variables-that-store-preferences"></a><span data-ttu-id="65b31-140">Umgebungsvariablen, die Einstellungen speichern</span><span class="sxs-lookup"><span data-stu-id="65b31-140">Environment variables that store preferences</span></span>

<span data-ttu-id="65b31-141">PowerShell-Funktionen können Umgebungsvariablen verwenden, um Benutzereinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="65b31-141">PowerShell features can use environment variables to store user preferences.</span></span>
<span data-ttu-id="65b31-142">Diese Variablen funktionieren wie bevorzugte Variablen, werden jedoch von den untergeordneten Sitzungen der Sitzungen geerbt, in denen Sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="65b31-142">These variables work like preference variables, but they are inherited by child sessions of the sessions in which they are created.</span></span> <span data-ttu-id="65b31-143">Weitere Informationen zu Einstellungs Variablen finden Sie unter [about_preference_variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="65b31-143">For more information about preference variables, see [about_preference_variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="65b31-144">Zu den Umgebungsvariablen, die Einstellungen speichern, gehören:</span><span class="sxs-lookup"><span data-stu-id="65b31-144">The environment variables that store preferences include:</span></span>

- <span data-ttu-id="65b31-145">PSExecutionPolicyPreference</span><span class="sxs-lookup"><span data-stu-id="65b31-145">PSExecutionPolicyPreference</span></span>

  <span data-ttu-id="65b31-146">Speichert die Ausführungs Richtlinie, die für die aktuelle Sitzung festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="65b31-146">Stores the execution policy set for the current session.</span></span> <span data-ttu-id="65b31-147">Diese Umgebungsvariable ist nur vorhanden, wenn Sie eine Ausführungs Richtlinie für eine einzelne Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="65b31-147">This environment variable exists only when you set an execution policy for a single session.</span></span>
  <span data-ttu-id="65b31-148">Dies kann auf zwei verschiedene Arten erfolgen.</span><span class="sxs-lookup"><span data-stu-id="65b31-148">You can do this in two different ways.</span></span>

  - <span data-ttu-id="65b31-149">Starten Sie mithilfe des **ExecutionPolicy** -Parameters eine Sitzung von der Befehlszeile aus, um die Ausführungs Richtlinie für die Sitzung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="65b31-149">Start a session from the command line using the **ExecutionPolicy** parameter to set the execution policy for the session.</span></span>

  - <span data-ttu-id="65b31-150">Verwenden Sie das `Set-ExecutionPolicy`-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="65b31-150">Use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="65b31-151">Verwenden Sie den Scope-Parameter mit dem Wert "Process".</span><span class="sxs-lookup"><span data-stu-id="65b31-151">Use the Scope parameter with a value of "Process".</span></span>

    <span data-ttu-id="65b31-152">Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="65b31-152">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

- <span data-ttu-id="65b31-153">Psmoduleanalysiscachepath</span><span class="sxs-lookup"><span data-stu-id="65b31-153">PSModuleAnalysisCachePath</span></span>

  <span data-ttu-id="65b31-154">PowerShell bietet Kontrolle über die Datei, die zum Zwischenspeichern von Daten zu Modulen und ihren Cmdlets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="65b31-154">PowerShell provides control over the file that is used to cache data about modules and their cmdlets.</span></span> <span data-ttu-id="65b31-155">Der Cache wird beim Start während der Suche nach einem Befehl gelesen und in einem Hintergrund Thread geschrieben, wenn ein Modul importiert wird.</span><span class="sxs-lookup"><span data-stu-id="65b31-155">The cache is read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

  <span data-ttu-id="65b31-156">Der Standard Speicherort für den Cache lautet:</span><span class="sxs-lookup"><span data-stu-id="65b31-156">Default location of the cache is:</span></span>

  - <span data-ttu-id="65b31-157">Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`</span><span class="sxs-lookup"><span data-stu-id="65b31-157">Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`</span></span>
  - <span data-ttu-id="65b31-158">PowerShell 6,0 und höher: `$env:LOCALAPPDATA\Microsoft\PowerShell`</span><span class="sxs-lookup"><span data-stu-id="65b31-158">PowerShell 6.0 and higher: `$env:LOCALAPPDATA\Microsoft\PowerShell`</span></span>
  - <span data-ttu-id="65b31-159">Standardeinstellung für nicht-Windows: `~/.cache/powershell`</span><span class="sxs-lookup"><span data-stu-id="65b31-159">Non-Windows default: `~/.cache/powershell`</span></span>

  <span data-ttu-id="65b31-160">Der Standard Dateiname für den Cache ist `ModuleAnalysisCache` .</span><span class="sxs-lookup"><span data-stu-id="65b31-160">The default filename for the cache is `ModuleAnalysisCache`.</span></span> <span data-ttu-id="65b31-161">Wenn Sie mehrere Instanzen von PowerShell installiert haben, enthält der Dateiname ein hexadezimales Suffix, sodass pro Installation ein eindeutiger Dateiname vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="65b31-161">When you have multiple instances of PowerShell installed, the filename includes a hexadecimal suffix so that there is a a unique filename per installation.</span></span>

  > [!NOTE]
  > <span data-ttu-id="65b31-162">Wenn die Befehls Ermittlung nicht ordnungsgemäß funktioniert, z. b. wenn IntelliSense Befehle anzeigt, die nicht vorhanden sind, können Sie die Cachedatei löschen.</span><span class="sxs-lookup"><span data-stu-id="65b31-162">If command discovery isn't working correctly, for example Intellisense shows commands that don't exist, you can delete the cache file.</span></span> <span data-ttu-id="65b31-163">Der Cache wird beim nächsten Start von PowerShell neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="65b31-163">The cache is recreated the next time you start PowerShell.</span></span>

  <span data-ttu-id="65b31-164">Um den Standard Speicherort des Caches zu ändern, legen Sie die Umgebungsvariable vor dem Starten von PowerShell fest.</span><span class="sxs-lookup"><span data-stu-id="65b31-164">To change the default location of the cache, set the environment variable before starting PowerShell.</span></span> <span data-ttu-id="65b31-165">Änderungen an dieser Umgebungsvariablen wirken sich nur auf untergeordnete Prozesse aus.</span><span class="sxs-lookup"><span data-stu-id="65b31-165">Changes to this environment variable only affect child processes.</span></span> <span data-ttu-id="65b31-166">Der Wert muss einen vollständigen Pfad (samt Dateiname) definieren, in dem PowerShell die Berechtigung zum Erstellen und Schreiben von Dateien hat.</span><span class="sxs-lookup"><span data-stu-id="65b31-166">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span>

  <span data-ttu-id="65b31-167">Zum Deaktivieren des Dateicaches kann dieser Wert auf einen ungültigen Speicherort festgelegt werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65b31-167">To disable the file cache, set this value to an invalid location, for example:</span></span>

  ```powershell
  # `NUL` here is a special device on Windows that cannot be written to,
  # on non-Windows you would use `/dev/null`
  $env:PSModuleAnalysisCachePath = 'NUL'
  ```

  <span data-ttu-id="65b31-168">Dadurch wird der Pfad zum **NUL** -Gerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="65b31-168">This sets the path to the **NUL** device.</span></span> <span data-ttu-id="65b31-169">PowerShell kann nicht in den Pfad schreiben, aber es wird kein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="65b31-169">PowerShell can't write to the path but no error is returned.</span></span> <span data-ttu-id="65b31-170">Sie können die Fehler anzeigen, die mithilfe eines Tracers gemeldet werden:</span><span class="sxs-lookup"><span data-stu-id="65b31-170">You can see the errors reported using a tracer:</span></span>

  ```powershell
  Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
  ```

- <span data-ttu-id="65b31-171">Psdisablemoduleanalysiscachecleanup</span><span class="sxs-lookup"><span data-stu-id="65b31-171">PSDisableModuleAnalysisCacheCleanup</span></span>

  <span data-ttu-id="65b31-172">Wenn Sie den Modul Analyse Cache schreiben, prüft PowerShell, ob Module vorhanden sind, die nicht mehr vorhanden sind, um einen unnötig großen Cache zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="65b31-172">When writing out the module analysis cache, PowerShell checks for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="65b31-173">Manchmal sind diese Überprüfungen nicht wünschenswert. in diesem Fall können Sie Sie deaktivieren, indem Sie diesen Umgebungsvariablen Wert auf festlegen `1` .</span><span class="sxs-lookup"><span data-stu-id="65b31-173">Sometimes these checks are not desirable, in which case you can turn them off by setting this environment variable value to `1`.</span></span>

  <span data-ttu-id="65b31-174">Das Festlegen dieser Umgebungsvariablen tritt sofort im aktuellen Prozess in Kraft.</span><span class="sxs-lookup"><span data-stu-id="65b31-174">Setting this environment variable takes effect immediately in the current process.</span></span>

- <span data-ttu-id="65b31-175">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="65b31-175">PSModulePath</span></span>

  <span data-ttu-id="65b31-176">Die `$env:PSModulePath` Umgebungsvariable enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden.</span><span class="sxs-lookup"><span data-stu-id="65b31-176">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

  <span data-ttu-id="65b31-177">Standardmäßig sind die folgenden effektiven Speicherorte zugewiesen `$env:PSModulePath` :</span><span class="sxs-lookup"><span data-stu-id="65b31-177">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

  - <span data-ttu-id="65b31-178">System weite Speicherorte: diese Ordner enthalten Module, die mit PowerShell ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="65b31-178">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="65b31-179">Die Module werden am `$PSHOME\Modules` Speicherort gespeichert.</span><span class="sxs-lookup"><span data-stu-id="65b31-179">The modules are store in the `$PSHOME\Modules` location.</span></span> <span data-ttu-id="65b31-180">Außerdem ist dies der Speicherort, an dem die Windows-Verwaltungs Module installiert werden.</span><span class="sxs-lookup"><span data-stu-id="65b31-180">Also, This is the location where the Windows management modules are installed.</span></span>

  - <span data-ttu-id="65b31-181">Vom Benutzer installierte Module: Dies sind Module, die vom Benutzer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="65b31-181">User-installed modules: These are modules installed by the user.</span></span>
    <span data-ttu-id="65b31-182">`Install-Module` verfügt über einen **Scope** -Parameter, mit dem Sie angeben können, ob das Modul für den aktuellen Benutzer oder für alle Benutzer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="65b31-182">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="65b31-183">Weitere Informationen finden Sie unter [Install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="65b31-183">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

    - <span data-ttu-id="65b31-184">Unter Windows ist der Speicherort des benutzerspezifischen **CurrentUser** -Bereichs der `$HOME\Documents\PowerShell\Modules` Ordner.</span><span class="sxs-lookup"><span data-stu-id="65b31-184">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="65b31-185">Der Speicherort des **ALLUSERS** -Bereichs ist `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="65b31-185">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
    - <span data-ttu-id="65b31-186">Bei nicht-Windows-Systemen ist der Speicherort des benutzerspezifischen **CurrentUser** -Bereichs der `$HOME/.local/share/powershell/Modules` Ordner.</span><span class="sxs-lookup"><span data-stu-id="65b31-186">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="65b31-187">Der Speicherort des **ALLUSERS** -Bereichs ist `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="65b31-187">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

  <span data-ttu-id="65b31-188">Außerdem können Setup Programme, die Module in anderen Verzeichnissen installieren, z. b. das Verzeichnis "Programme", ihre Speicherorte an den Wert von anfügen `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="65b31-188">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

  <span data-ttu-id="65b31-189">Weitere Informationen finden Sie unter [about_PSModulePath](about_PSModulePath.md).</span><span class="sxs-lookup"><span data-stu-id="65b31-189">For more information, see [about_PSModulePath](about_PSModulePath.md).</span></span>

## <a name="managing-environment-variables"></a><span data-ttu-id="65b31-190">Verwalten von Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="65b31-190">Managing environment variables</span></span>

<span data-ttu-id="65b31-191">PowerShell bietet verschiedene Methoden zum Verwalten von Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="65b31-191">PowerShell provides several different methods for managing environment variables.</span></span>

- <span data-ttu-id="65b31-192">Das Umgebungs Anbieter Laufwerk</span><span class="sxs-lookup"><span data-stu-id="65b31-192">The Environment provider drive</span></span>
- <span data-ttu-id="65b31-193">Die Item-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="65b31-193">The Item cmdlets</span></span>
- <span data-ttu-id="65b31-194">Die .NET-Klasse " **System. Environment** "</span><span class="sxs-lookup"><span data-stu-id="65b31-194">The .NET **System.Environment** class</span></span>
- <span data-ttu-id="65b31-195">Unter Windows die System Steuerung</span><span class="sxs-lookup"><span data-stu-id="65b31-195">On Windows, the System Control Panel</span></span>

### <a name="using-the-environment-provider"></a><span data-ttu-id="65b31-196">Verwenden des Umgebungs Anbieters</span><span class="sxs-lookup"><span data-stu-id="65b31-196">Using the Environment provider</span></span>

<span data-ttu-id="65b31-197">Jede Umgebungsvariable wird durch eine Instanz der Klasse **System. Collections. ditionaryentry** dargestellt.</span><span class="sxs-lookup"><span data-stu-id="65b31-197">Each environment variable is represented by an instance of the **System.Collections.DictionaryEntry** class.</span></span> <span data-ttu-id="65b31-198">In jedem " **diktaryentry** "-Objekt ist der Name der Umgebungsvariablen der Wörterbuch Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="65b31-198">In each **DictionaryEntry** object, the name of the environment variable is the dictionary key.</span></span> <span data-ttu-id="65b31-199">Der Wert der Variablen ist der Wörterbuch Wert.</span><span class="sxs-lookup"><span data-stu-id="65b31-199">The value of the variable is the dictionary value.</span></span>

<span data-ttu-id="65b31-200">Verwenden Sie das-Cmdlet, um die Eigenschaften und Methoden des Objekts anzuzeigen, das eine Umgebungsvariable in PowerShell darstellt `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="65b31-200">To display the properties and methods of the object that represents an environment variable in PowerShell, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="65b31-201">Wenn Sie z. b. die Methoden und Eigenschaften aller Objekte im Laufwerk anzeigen möchten, geben Sie Folgendes ein `Env:` :</span><span class="sxs-lookup"><span data-stu-id="65b31-201">For example, to display the methods and properties of all the objects in the `Env:` drive, type:</span></span>

```powershell
Get-Item -Path Env:* | Get-Member
```

<span data-ttu-id="65b31-202">Mit dem PowerShell-Umgebungs Anbieter können Sie auf Umgebungsvariablen in einem PowerShell-Laufwerk ( `Env:` Laufwerk) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="65b31-202">The PowerShell Environment provider lets you access environment variables in a PowerShell drive (the `Env:` drive).</span></span> <span data-ttu-id="65b31-203">Dieses Laufwerk sieht in etwa wie ein Dateisystem Laufwerk aus.</span><span class="sxs-lookup"><span data-stu-id="65b31-203">This drive looks much like a file system drive.</span></span> <span data-ttu-id="65b31-204">Um zum Laufwerk zu wechseln, geben Sie Folgendes ein `Env:` :</span><span class="sxs-lookup"><span data-stu-id="65b31-204">To go to the `Env:` drive, type:</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="65b31-205">Verwenden Sie die Content-Cmdlets, um die Werte einer Umgebungsvariablen zu erhalten oder festzulegen.</span><span class="sxs-lookup"><span data-stu-id="65b31-205">Use the Content cmdlets to get or set the values of an environment variable.</span></span>

```powershell
PS Env:\> Set-Content -Path Test -Value 'Test value'
PS Env:\> Get-Content -Path Test
Test value
```

<span data-ttu-id="65b31-206">Sie können die Umgebungsvariablen auf dem `Env:` Laufwerk von einem beliebigen anderen PowerShell-Laufwerk anzeigen, und Sie können das `Env:` Laufwerk aufrufen, um die Umgebungsvariablen anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="65b31-206">You can view the environment variables in the `Env:` drive from any other PowerShell drive, and you can go into the `Env:` drive to view and change the environment variables.</span></span>

### <a name="using-item-cmdlets"></a><span data-ttu-id="65b31-207">Verwenden von Item-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="65b31-207">Using Item cmdlets</span></span>

<span data-ttu-id="65b31-208">Wenn Sie auf eine Umgebungsvariable verweisen, geben Sie den `Env:` Namen des Laufwerks gefolgt vom Namen der Variablen ein.</span><span class="sxs-lookup"><span data-stu-id="65b31-208">When you refer to an environment variable, type the `Env:` drive name followed by the name of the variable.</span></span> <span data-ttu-id="65b31-209">Wenn Sie z. b. den Wert der `COMPUTERNAME` Umgebungsvariablen anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="65b31-209">For example, to display the value of the `COMPUTERNAME` environment variable, type:</span></span>

```powershell
Get-ChildItem Env:Computername
```

<span data-ttu-id="65b31-210">Geben Sie Folgendes ein, um die Werte aller Umgebungsvariablen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="65b31-210">To display the values of all the environment variables, type:</span></span>

```powershell
Get-ChildItem Env:
```

<span data-ttu-id="65b31-211">Da Umgebungsvariablen keine untergeordneten Elemente aufweisen, ist die Ausgabe von `Get-Item` und `Get-ChildItem` identisch.</span><span class="sxs-lookup"><span data-stu-id="65b31-211">Because environment variables do not have child items, the output of `Get-Item` and `Get-ChildItem` is the same.</span></span>

<span data-ttu-id="65b31-212">Standardmäßig zeigt PowerShell die Umgebungsvariablen in der Reihenfolge an, in der Sie abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="65b31-212">By default, PowerShell displays the environment variables in the order in which it retrieves them.</span></span> <span data-ttu-id="65b31-213">Übergeben Sie die Ausgabe eines `Get-ChildItem` Befehls an das Cmdlet, um die Liste der Umgebungsvariablen nach dem Variablennamen zu sortieren `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="65b31-213">To sort the list of environment variables by variable name, pipe the output of a `Get-ChildItem` command to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="65b31-214">Geben Sie beispielsweise von einem beliebigen PowerShell-Laufwerk Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="65b31-214">For example, from any PowerShell drive, type:</span></span>

```powershell
Get-ChildItem Env: | Sort Name
```

<span data-ttu-id="65b31-215">Sie können auch mit dem- `Env:` Cmdlet auf das Laufwerk wechseln `Set-Location` :</span><span class="sxs-lookup"><span data-stu-id="65b31-215">You can also go into the `Env:` drive by using the `Set-Location` cmdlet:</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="65b31-216">Wenn Sie sich auf dem `Env:` Laufwerk befinden, können Sie den `Env:` Namen des Laufwerks aus dem Pfad weglassen.</span><span class="sxs-lookup"><span data-stu-id="65b31-216">When you are in the `Env:` drive, you can omit the `Env:` drive name from the path.</span></span> <span data-ttu-id="65b31-217">Wenn Sie z. b. alle Umgebungsvariablen anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="65b31-217">For example, to display all the environment variables, type:</span></span>

```powershell
PS Env:\> Get-ChildItem
```

<span data-ttu-id="65b31-218">Wenn Sie den Wert der `COMPUTERNAME` Variablen innerhalb des Laufwerks anzeigen möchten, geben Sie Folgendes ein `Env:` :</span><span class="sxs-lookup"><span data-stu-id="65b31-218">To display the value of the `COMPUTERNAME` variable from within the `Env:` drive, type:</span></span>

```powershell
PS Env:\> Get-ChildItem ComputerName
```

### <a name="saving-changes-to-environment-variables"></a><span data-ttu-id="65b31-219">Speichern von Änderungen an Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="65b31-219">Saving changes to environment variables</span></span>

<span data-ttu-id="65b31-220">Verwenden Sie die System Steuerung, um eine dauerhafte Änderung an einer Umgebungsvariablen unter Windows vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="65b31-220">To make a persistent change to an environment variable on Windows, use the System Control Panel.</span></span> <span data-ttu-id="65b31-221">Wählen Sie **Erweiterte System Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="65b31-221">Select **Advanced System Settings**.</span></span> <span data-ttu-id="65b31-222">Klicken Sie auf der Registerkarte **erweitert** auf **Umgebungs Variable...**. Sie können vorhandene Umgebungsvariablen im Bereich " **Benutzer** " und " **System** " (Computer) hinzufügen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="65b31-222">On the **Advanced** tab, click **Environment Variable...**. You can add or edit existing environment variables in the **User** and **System** (Machine) scopes.</span></span> <span data-ttu-id="65b31-223">Diese Werte werden von Windows in die Registrierung geschrieben, sodass Sie Sitzungs übergreifend und Systemneustarts beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="65b31-223">Windows writes these values to the Registry so that they persist across sessions and system restarts.</span></span>

<span data-ttu-id="65b31-224">Alternativ können Sie Umgebungsvariablen in Ihrem PowerShell-Profil hinzufügen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="65b31-224">Alternately, you can add or change environment variables in your PowerShell profile.</span></span> <span data-ttu-id="65b31-225">Diese Methode funktioniert für jede Version von PowerShell auf allen unterstützten Plattformen.</span><span class="sxs-lookup"><span data-stu-id="65b31-225">This method works for any version of PowerShell on any supported platform.</span></span>

### <a name="using-systemenvironment-methods"></a><span data-ttu-id="65b31-226">Verwenden von System. Environment-Methoden</span><span class="sxs-lookup"><span data-stu-id="65b31-226">Using System.Environment methods</span></span>

<span data-ttu-id="65b31-227">Die **System. Environment** -Klasse stellt die Methoden **GetEnvironmentVariable** und **ltenvironmentvariable** bereit, die es Ihnen ermöglichen, den Gültigkeitsbereich der Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="65b31-227">The **System.Environment** class provides **GetEnvironmentVariable** and **SetEnvironmentVariable** methods that allow you to specify the scope of the variable.</span></span>

<span data-ttu-id="65b31-228">Im folgenden Beispiel wird die **GetEnvironmentVariable** -Methode verwendet, um die Computer Einstellung von `PSModulePath` und die Methode "-Methode" zu erhalten, um den **SetEnvironmentVariable** `C:\Program Files\Fabrikam\Modules` Pfad zum Wert hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="65b31-228">The following example uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable("PSModulePath", $newpath, 'Machine')
```

<span data-ttu-id="65b31-229">Weitere Informationen zu den Methoden der **System. Environment** -Klasse finden Sie unter [Umgebungs Methoden](/dotnet/api/system.environment).</span><span class="sxs-lookup"><span data-stu-id="65b31-229">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="see-also"></a><span data-ttu-id="65b31-230">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="65b31-230">SEE ALSO</span></span>

- [<span data-ttu-id="65b31-231">Umgebung (Anbieter)</span><span class="sxs-lookup"><span data-stu-id="65b31-231">Environment (provider)</span></span>](../About/about_Environment_Provider.md)
- [<span data-ttu-id="65b31-232">about_Modules</span><span class="sxs-lookup"><span data-stu-id="65b31-232">about_Modules</span></span>](about_Modules.md)

