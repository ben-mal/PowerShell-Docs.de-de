---
description: Konfigurationsdateien für PowerShell Core, die die Registrierungs Konfiguration ersetzen.
Locale: en-US
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Config
ms.openlocfilehash: 7190484832958e778a21e6d2cc91771587bffdbf
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599451"
---
# <a name="about-powershell-config"></a><span data-ttu-id="53ef0-103">Informationen zur PowerShell-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="53ef0-103">About PowerShell Config</span></span>

## <a name="short-description"></a><span data-ttu-id="53ef0-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="53ef0-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="53ef0-105">Konfigurationsdateien für PowerShell Core, die die Registrierungs Konfiguration ersetzen.</span><span class="sxs-lookup"><span data-stu-id="53ef0-105">Configuration files for PowerShell Core, replacing Registry configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="53ef0-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="53ef0-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="53ef0-107">Die `powershell.config.json` Datei enthält Konfigurationseinstellungen für PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="53ef0-107">The `powershell.config.json` file contains configuration settings for PowerShell Core.</span></span> <span data-ttu-id="53ef0-108">Diese Konfiguration wird von PowerShell beim Start geladen.</span><span class="sxs-lookup"><span data-stu-id="53ef0-108">PowerShell loads this configuration at startup.</span></span> <span data-ttu-id="53ef0-109">Die Einstellungen können auch zur Laufzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-109">The settings can also be modified at runtime.</span></span> <span data-ttu-id="53ef0-110">Zuvor wurden diese Einstellungen in der Windows-Registrierung für PowerShell gespeichert, sind aber jetzt in einer Datei enthalten, um die Konfiguration unter macOS und Linux zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="53ef0-110">Previously, these settings were stored in the Windows Registry for PowerShell, but are now contained in a file to enable configuration on macOS and Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="53ef0-111">Wenn die `powershell.config.json` Datei eine ungültige JSON-Datei enthält, kann PowerShell keine interaktive Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="53ef0-111">If the `powershell.config.json` file contains invalid JSON PowerShell cannot start an interactive session.</span></span>
> <span data-ttu-id="53ef0-112">Wenn dies der Fall ist, müssen Sie die Konfigurationsdatei korrigieren.</span><span class="sxs-lookup"><span data-stu-id="53ef0-112">If this occurs, you must fix the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="53ef0-113">Nicht erkannte Schlüssel oder ungültige Werte in der Konfigurationsdatei werden automatisch ignoriert.</span><span class="sxs-lookup"><span data-stu-id="53ef0-113">Unrecognized keys or invalid values in the configuration file will be silently ignored.</span></span>

### <a name="allusers-shared-configuration"></a><span data-ttu-id="53ef0-114">Konfiguration von ALLUSERS (Shared)</span><span class="sxs-lookup"><span data-stu-id="53ef0-114">AllUsers (shared) configuration</span></span>

<span data-ttu-id="53ef0-115">Eine `powershell.config.json` Datei im `$PSHOME` Verzeichnis definiert die Konfiguration für alle PowerShell-Kern Sitzungen, die von dieser PowerShell Core-Installation ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-115">A `powershell.config.json` file in the `$PSHOME` directory defines the configuration for all PowerShell Core sessions running from that PowerShell Core installation.</span></span>

> [!NOTE]
> <span data-ttu-id="53ef0-116">Der `$PSHOME` Speicherort wird als dasselbe Verzeichnis wie die ausführende System.Management.Automation.dll Assembly definiert.</span><span class="sxs-lookup"><span data-stu-id="53ef0-116">The `$PSHOME` location is defined as the same directory as the executing System.Management.Automation.dll assembly.</span></span> <span data-ttu-id="53ef0-117">Dies gilt auch für gehostete PowerShell SDK-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="53ef0-117">This applies to hosted PowerShell SDK instances as well.</span></span>

### <a name="currentuser-per-user-configurations"></a><span data-ttu-id="53ef0-118">CurrentUser-Konfigurationen (pro Benutzer)</span><span class="sxs-lookup"><span data-stu-id="53ef0-118">CurrentUser (per-user) configurations</span></span>

<span data-ttu-id="53ef0-119">Sie können PowerShell auch pro Benutzer konfigurieren, indem Sie die Datei im Benutzer Bereichs-Konfigurationsverzeichnis platzieren.</span><span class="sxs-lookup"><span data-stu-id="53ef0-119">You can also configure PowerShell on a per-user basis by placing the file in the user-scope configuration directory.</span></span> <span data-ttu-id="53ef0-120">Das Benutzer Konfigurationsverzeichnis kann mit dem Befehl plattformübergreifend gefunden werden `Split-Path $PROFILE.CurrentUserCurrentHost` .</span><span class="sxs-lookup"><span data-stu-id="53ef0-120">The user configuration directory can be found across platforms with the command `Split-Path $PROFILE.CurrentUserCurrentHost`.</span></span>

## <a name="general-configuration-settings"></a><span data-ttu-id="53ef0-121">Allgemeine Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="53ef0-121">General configuration settings</span></span>

### <a name="executionpolicy"></a><span data-ttu-id="53ef0-122">ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="53ef0-122">ExecutionPolicy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53ef0-123">Diese Konfiguration gilt nur für Windows-Plattformen.</span><span class="sxs-lookup"><span data-stu-id="53ef0-123">This configuration only applies on Windows platforms.</span></span>

<span data-ttu-id="53ef0-124">Konfiguriert die Ausführungs Richtlinie für PowerShell-Sitzungen und bestimmt, welche Skripts ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="53ef0-124">Configures the execution policy for PowerShell sessions, determining what scripts can be run.</span></span> <span data-ttu-id="53ef0-125">Standardmäßig verwendet PowerShell die vorhandene Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="53ef0-125">By default, PowerShell uses the existing execution policy.</span></span>

<span data-ttu-id="53ef0-126">Bei ALLUSERS-Konfigurationen wird dadurch die **LocalMachine** -Ausführungs Richtlinie festgelegt.</span><span class="sxs-lookup"><span data-stu-id="53ef0-126">For AllUsers configurations, this sets the **LocalMachine** execution policy.</span></span>
<span data-ttu-id="53ef0-127">Bei CurrentUser-Konfigurationen wird die **CurrentUser** -Ausführungs Richtlinie festgelegt.</span><span class="sxs-lookup"><span data-stu-id="53ef0-127">For CurrentUser configurations, this sets the **CurrentUser** execution policy.</span></span>

> [!NOTE]
> <span data-ttu-id="53ef0-128">Das- [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) Cmdlet ändert diese Einstellung in der ALLUSERS-Konfigurationsdatei, wenn Sie mit aufgerufen `-Scope LocalMachine` wird, und ändert diese Einstellung in der CurrentUser-Konfigurationsdatei, wenn Sie mit aufgerufen wird `-Scope CurrentUser` .</span><span class="sxs-lookup"><span data-stu-id="53ef0-128">The [`Set-ExecutionPolicy`](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy) cmdlet modifies this setting in the AllUsers configuration file when invoked with `-Scope LocalMachine`, and modifies this setting in the CurrentUser configuration file when invoked with `-Scope CurrentUser`.</span></span>

```Schema
"<shell-id>:ExecutionPolicy": "<execution-policy>"
```

<span data-ttu-id="53ef0-129">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="53ef0-129">Where:</span></span>

- <span data-ttu-id="53ef0-130">`<shell-id>` bezieht sich auf die ID des aktuellen PowerShell-Hosts.</span><span class="sxs-lookup"><span data-stu-id="53ef0-130">`<shell-id>` refers to the ID of the current PowerShell host.</span></span>
  <span data-ttu-id="53ef0-131">Für den normalen PowerShell-Kern lautet der Wert `Microsoft.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="53ef0-131">For normal PowerShell Core, this is `Microsoft.PowerShell`.</span></span>
  <span data-ttu-id="53ef0-132">In einer beliebigen PowerShell-Sitzung können Sie diese mithilfe von ermitteln `$ShellId` .</span><span class="sxs-lookup"><span data-stu-id="53ef0-132">In any PowerShell session, you can discover it with `$ShellId`.</span></span>
- <span data-ttu-id="53ef0-133">`<execution-policy>` verweist auf einen gültigen Namen für die Ausführungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="53ef0-133">`<execution-policy>` refers to a valid execution policy name.</span></span>

<span data-ttu-id="53ef0-134">Im folgenden Beispiel wird die Ausführungs Richtlinie von PowerShell auf festgelegt `RemoteSigned` .</span><span class="sxs-lookup"><span data-stu-id="53ef0-134">The following example sets the execution policy of PowerShell to `RemoteSigned`.</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "RemoteSigned"
}
```

<span data-ttu-id="53ef0-135">In Windows finden Sie die entsprechenden Registrierungsschlüssel `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` unter `HKEY_LOCAL_MACHINE` und `HKEY_CURRENT_USER` .</span><span class="sxs-lookup"><span data-stu-id="53ef0-135">In Windows, the equivalent registry keys can be found in `\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell` under `HKEY_LOCAL_MACHINE` and `HKEY_CURRENT_USER`.</span></span>

### <a name="psmodulepath"></a><span data-ttu-id="53ef0-136">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="53ef0-136">PSModulePath</span></span>

<span data-ttu-id="53ef0-137">Überschreibt eine psmodulepath-Komponente für diese PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="53ef0-137">Overrides a PSModulePath component for this PowerShell session.</span></span> <span data-ttu-id="53ef0-138">Wenn die Konfiguration für den aktuellen Benutzer gilt, legt den CurrentUser-Modulpfad fest.</span><span class="sxs-lookup"><span data-stu-id="53ef0-138">If the configuration is for the current user, sets the CurrentUser module path.</span></span> <span data-ttu-id="53ef0-139">Wenn die Konfiguration für alle Benutzer gilt, wird der alluser-Modulpfad von festgelegt.</span><span class="sxs-lookup"><span data-stu-id="53ef0-139">If the configuration is for all users, sets the AllUser module path.</span></span>

> [!WARNING]
> <span data-ttu-id="53ef0-140">Wenn Sie einen AllUsers-oder CurrentUser-Modulpfad hier konfigurieren, wird der Bereichs bezogene Installationsort für PowerShellGet-Module wie " [Install-Module](/powershell/module/powershellget/install-module)" nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="53ef0-140">Configuring an AllUsers or CurrentUser module path here will not change the scoped installation location for PowerShellGet modules like [Install-Module](/powershell/module/powershellget/install-module).</span></span>
> <span data-ttu-id="53ef0-141">Diese Cmdlets verwenden immer die *Standard* Modul Pfade.</span><span class="sxs-lookup"><span data-stu-id="53ef0-141">These cmdlets always use the *default* module paths.</span></span>

<span data-ttu-id="53ef0-142">Wenn kein Wert festgelegt ist, wird der Standardwert für die jeweilige Modul Pfadkomponente verwendet.</span><span class="sxs-lookup"><span data-stu-id="53ef0-142">If no value is set, the default value for the respective module path component will be used.</span></span> <span data-ttu-id="53ef0-143">Weitere Informationen zu diesen Standardeinstellungen finden Sie unter [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) .</span><span class="sxs-lookup"><span data-stu-id="53ef0-143">See [about_Modules](./about_Modules.md#module-and-dsc-resource-locations-and-psmodulepath) for more details on these defaults.</span></span>

<span data-ttu-id="53ef0-144">Diese Einstellung ermöglicht die Verwendung von Umgebungsvariablen, indem Sie Sie `%` `"%HOME%\Documents\PowerShell\Modules"` auf die gleiche Weise wie cmd zwischen Zeichen einbetten.</span><span class="sxs-lookup"><span data-stu-id="53ef0-144">This setting allows environment variables to be used by embedding them between `%` characters, like `"%HOME%\Documents\PowerShell\Modules"`, in the same way as CMD allows.</span></span> <span data-ttu-id="53ef0-145">Diese Syntax gilt auch für Linux und macOS.</span><span class="sxs-lookup"><span data-stu-id="53ef0-145">This syntax also applies on Linux and macOS.</span></span> <span data-ttu-id="53ef0-146">Weiter unten finden Sie Beispiele dafür.</span><span class="sxs-lookup"><span data-stu-id="53ef0-146">See below for examples.</span></span>

```Schema
"PSModulePath": "<ps-module-path>"
```

<span data-ttu-id="53ef0-147">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="53ef0-147">Where:</span></span>

- <span data-ttu-id="53ef0-148">`<ps-module-path>` der absolute Pfad zu einem Modul Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="53ef0-148">`<ps-module-path>` is the absolute path to a module directory.</span></span> <span data-ttu-id="53ef0-149">Für alle Benutzerkonfigurationen ist dies das Verzeichnis "ALLUSERS Shared Module".</span><span class="sxs-lookup"><span data-stu-id="53ef0-149">For all user configurations, this is the AllUsers shared module directory.</span></span> <span data-ttu-id="53ef0-150">Bei aktuellen Benutzerkonfigurationen ist dies das CurrentUser-Modul Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="53ef0-150">For current user configurations, this is CurrentUser module directory.</span></span>

<span data-ttu-id="53ef0-151">Dieses Beispiel zeigt eine psmodulepath-Konfiguration für eine Windows-Umgebung:</span><span class="sxs-lookup"><span data-stu-id="53ef0-151">This example shows a PSModulePath configuration for a Windows environment:</span></span>

```json
{
  "PSModulePath": "C:\\Program Files\\PowerShell\\6\\Modules"
}
```

<span data-ttu-id="53ef0-152">Dieses Beispiel zeigt eine psmodulepath-Konfiguration für eine macOS-oder Linux-Umgebung:</span><span class="sxs-lookup"><span data-stu-id="53ef0-152">This example shows a PSModulePath configuration for a macOS or Linux environment:</span></span>

```json
{
  "PSModulePath": "/opt/powershell/6/Modules"
}
```

<span data-ttu-id="53ef0-153">Dieses Beispiel zeigt das Einbetten einer Umgebungsvariablen in eine psmodulepath-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="53ef0-153">This example shows embedding an environment variable in a PSModulePath configuration.</span></span> <span data-ttu-id="53ef0-154">Beachten Sie, dass `HOME` `/` dies unter Windows, macOS und Linux funktioniert, wenn die Umgebungsvariable und das Verzeichnis Trennzeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-154">Note that using the `HOME` environment variable and the `/` directory separator, this will work on Windows, macOS and Linux.</span></span>

```json
{
  "PSModulePath": "%HOME%/Documents/PowerShell/Modules"
}
```

<span data-ttu-id="53ef0-155">Dieses Beispiel zeigt das Einbetten einer Umgebungsvariablen in eine psmodulepath-Konfiguration, die nur unter macOS und Linux funktioniert:</span><span class="sxs-lookup"><span data-stu-id="53ef0-155">This example shows embedding an environment variable in a PSModulePath configuration that will only work on macOS and Linux:</span></span>

```json
{
  "PSModulePath": "%XDG_CONFIG_HOME%/powershell/Modules"
}
```

> [!NOTE]
> <span data-ttu-id="53ef0-156">PowerShell-Variablen können nicht in psmodulepath-Konfigurationen eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-156">PowerShell variables cannot be embedded in PSModulePath configurations.</span></span>
> <span data-ttu-id="53ef0-157">Bei psmodulepath-Konfigurationen unter Linux und macOS wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="53ef0-157">PSModulePath configurations on Linux and macOS are case-sensitive.</span></span> <span data-ttu-id="53ef0-158">Eine psmodulepath-Konfiguration muss gültige Verzeichnis Trennzeichen für die Plattform verwenden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-158">A PSModulePath configuration must use valid directory separators for the platform.</span></span> <span data-ttu-id="53ef0-159">Unter macOS und Linux bedeutet dies `/` .</span><span class="sxs-lookup"><span data-stu-id="53ef0-159">On macOS and Linux, this means `/`.</span></span> <span data-ttu-id="53ef0-160">Unter Windows funktionieren sowohl `/` als auch `\` .</span><span class="sxs-lookup"><span data-stu-id="53ef0-160">On Windows, both `/` and `\` will work.</span></span>

### <a name="experimentalfeatures"></a><span data-ttu-id="53ef0-161">Experiment Features</span><span class="sxs-lookup"><span data-stu-id="53ef0-161">ExperimentalFeatures</span></span>

<span data-ttu-id="53ef0-162">Die Namen der experimentellen Funktionen, die in PowerShell aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="53ef0-162">The names of the experimental features to enable in PowerShell.</span></span>
<span data-ttu-id="53ef0-163">Standardmäßig sind keine experimentellen Funktionen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="53ef0-163">By default, no experimental features are enabled.</span></span>
<span data-ttu-id="53ef0-164">Der Standardwert ist ein leeres Array.</span><span class="sxs-lookup"><span data-stu-id="53ef0-164">The default value is an empty array.</span></span>

```Schema
"ExperimentalFeatures": ["<experimental-feature-name>", ...]
```

<span data-ttu-id="53ef0-165">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="53ef0-165">Where:</span></span>

- <span data-ttu-id="53ef0-166">`<experimental-feature-name>` der Name eines experimentellen Features, das aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="53ef0-166">`<experimental-feature-name>` is the name of an experimental feature to enable.</span></span>

<span data-ttu-id="53ef0-167">Im folgenden Beispiel werden die experimentellen Funktionen **pvereinfachcitremoting** und **psugkürzen ationexpansion** aktiviert, wenn PowerShell gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="53ef0-167">The following example enables the **PSImplicitRemoting** and **PSUseAbbreviationExpansion** experimental features when PowerShell starts up.</span></span>

```json
{
  "ExperimentalFeatures": [
    "PSImplicitRemotingBatching",
    "PSUseAbbreviationExpansion"
  ]
}
```

<span data-ttu-id="53ef0-168">Weitere Informationen zu experimentellen Funktionen finden Sie unter [PowerShell RFC 29][RFC0029].</span><span class="sxs-lookup"><span data-stu-id="53ef0-168">For more information on experimental features, see [PowerShell RFC 29][RFC0029].</span></span>

## <a name="non-windows-logging-configuration"></a><span data-ttu-id="53ef0-169">Konfiguration der nicht-Windows-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="53ef0-169">Non-Windows logging configuration</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53ef0-170">Die Konfigurationsoptionen in diesem Abschnitt gelten nur für macOS und Linux.</span><span class="sxs-lookup"><span data-stu-id="53ef0-170">The configuration options in this section only apply to macOS and Linux.</span></span>
> <span data-ttu-id="53ef0-171">Die Protokollierung für Windows wird von der Windows-Ereignisanzeige verwaltet.</span><span class="sxs-lookup"><span data-stu-id="53ef0-171">Logging for Windows is managed by the Windows Event Viewer.</span></span>

<span data-ttu-id="53ef0-172">Die PowerShell-Protokollierung unter macOS und Linux kann in der PowerShell-Konfigurationsdatei konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-172">PowerShell's logging on macOS and Linux can be configured in the PowerShell configuration file.</span></span> <span data-ttu-id="53ef0-173">Eine vollständige Beschreibung der PowerShell-Protokollierung für nicht-Windows-Systeme finden Sie unter [Informationen zur Protokollierung](./about_Logging_Non-Windows.md).</span><span class="sxs-lookup"><span data-stu-id="53ef0-173">For a full description of PowerShell logging for non-Windows systems, see [About Logging](./about_Logging_Non-Windows.md).</span></span>

### <a name="logidentity"></a><span data-ttu-id="53ef0-174">Logidentity</span><span class="sxs-lookup"><span data-stu-id="53ef0-174">LogIdentity</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53ef0-175">Diese Einstellung kann nur in macOS und Linux verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-175">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="53ef0-176">Legt den Identitäts Namen fest, der zum Schreiben in das System Protokoll verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="53ef0-176">Sets the identity name used to write to the system log.</span></span> <span data-ttu-id="53ef0-177">Der Standardwert ist "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="53ef0-177">The default value is "powershell".</span></span>

```Schema
"LogIdentity": "<log-identity>"
```

<span data-ttu-id="53ef0-178">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="53ef0-178">Where:</span></span>

- <span data-ttu-id="53ef0-179">`<log-identity>` die Zeichen folgen Identität, die von PowerShell zum Schreiben in syslog verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="53ef0-179">`<log-identity>` is the string identity that PowerShell should use for writing to syslog.</span></span>

> [!NOTE]
> <span data-ttu-id="53ef0-180">Möglicherweise möchten Sie für jede andere Instanz von PowerShell, die Sie installiert haben, unterschiedliche **logidentity** -Werte haben.</span><span class="sxs-lookup"><span data-stu-id="53ef0-180">You may want to have different **LogIdentity** values for each different instance of PowerShell you have installed.</span></span>

<span data-ttu-id="53ef0-181">In diesem Beispiel konfigurieren wir die **logidentity** für eine Vorschauversion von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53ef0-181">In this example, we are configuring the **LogIdentity** for a preview release of PowerShell.</span></span>

```json
{
  "LogIdentity": "powershell-preview"
}
```

### <a name="loglevel"></a><span data-ttu-id="53ef0-182">LogLevel</span><span class="sxs-lookup"><span data-stu-id="53ef0-182">LogLevel</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53ef0-183">Diese Einstellung kann nur in macOS und Linux verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-183">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="53ef0-184">Gibt den minimalen Schweregrad an, mit dem PowerShell protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="53ef0-184">Specifies the minimum severity level at which PowerShell should log.</span></span>

```Schema
"LogLevel": "<log-level>|default"
```

<span data-ttu-id="53ef0-185">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="53ef0-185">Where:</span></span>

- <span data-ttu-id="53ef0-186">`<log-level>` ist einer dieser Werte:</span><span class="sxs-lookup"><span data-stu-id="53ef0-186">`<log-level>` is one of:</span></span>
  - <span data-ttu-id="53ef0-187">Always</span><span class="sxs-lookup"><span data-stu-id="53ef0-187">Always</span></span>
  - <span data-ttu-id="53ef0-188">Kritisch</span><span class="sxs-lookup"><span data-stu-id="53ef0-188">Critical</span></span>
  - <span data-ttu-id="53ef0-189">Fehler</span><span class="sxs-lookup"><span data-stu-id="53ef0-189">Error</span></span>
  - <span data-ttu-id="53ef0-190">Warnung</span><span class="sxs-lookup"><span data-stu-id="53ef0-190">Warning</span></span>
  - <span data-ttu-id="53ef0-191">Informational</span><span class="sxs-lookup"><span data-stu-id="53ef0-191">Informational</span></span>
  - <span data-ttu-id="53ef0-192">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="53ef0-192">Verbose</span></span>
  - <span data-ttu-id="53ef0-193">Debuggen</span><span class="sxs-lookup"><span data-stu-id="53ef0-193">Debug</span></span>

> [!NOTE]
> <span data-ttu-id="53ef0-194">Durch Festlegen einer Protokollebene werden alle darüber liegenden Protokoll Ebenen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="53ef0-194">Setting a the log level enables all log levels above it.</span></span>

<span data-ttu-id="53ef0-195">Wenn diese Einstellung auf **default** festgelegt wird, wird Sie als Standardwert interpretiert.</span><span class="sxs-lookup"><span data-stu-id="53ef0-195">Setting this setting to **default** will be interpreted as the default value.</span></span>
<span data-ttu-id="53ef0-196">Der Standardwert ist " **Information**".</span><span class="sxs-lookup"><span data-stu-id="53ef0-196">The default value is **Informational**.</span></span>

<span data-ttu-id="53ef0-197">Im folgenden Beispiel wird der Wert auf **verbose** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="53ef0-197">The following example sets the value to **Verbose**.</span></span>

```json
{
  "LogLevel": "Verbose"
}
```

### <a name="logchannels"></a><span data-ttu-id="53ef0-198">Logchannels</span><span class="sxs-lookup"><span data-stu-id="53ef0-198">LogChannels</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53ef0-199">Diese Einstellung kann nur in macOS und Linux verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-199">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="53ef0-200">Bestimmt, welche Protokollierungs Kanäle aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="53ef0-200">Determines which logging channels are enabled.</span></span>

```Schema
"LogChannels": "<log-channel>,..."
```

<span data-ttu-id="53ef0-201">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="53ef0-201">Where:</span></span>

- <span data-ttu-id="53ef0-202">`<log-channel>` ist einer dieser Werte:</span><span class="sxs-lookup"><span data-stu-id="53ef0-202">`<log-channel>` is one of:</span></span>
  - <span data-ttu-id="53ef0-203">Operational: protokolliert grundlegende Informationen zu PowerShell-Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="53ef0-203">Operational - logs basic information about PowerShell activities</span></span>
  - <span data-ttu-id="53ef0-204">Analytisch: protokolliert ausführlichere Diagnoseinformationen</span><span class="sxs-lookup"><span data-stu-id="53ef0-204">Analytic - logs more detailed diagnostic information</span></span>

<span data-ttu-id="53ef0-205">Der Standardwert ist **Operational**.</span><span class="sxs-lookup"><span data-stu-id="53ef0-205">The default value is **Operational**.</span></span> <span data-ttu-id="53ef0-206">Um beide Kanäle zu aktivieren, schließen Sie beide Werte als einzelne durch Trennzeichen getrennte Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="53ef0-206">To enable both channels, include both values as a single comma-separated string.</span></span> <span data-ttu-id="53ef0-207">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="53ef0-207">For example:</span></span>

```json
{
  "LogChannels": "Operational,Analytic"
}
```

### <a name="logkeywords"></a><span data-ttu-id="53ef0-208">Logschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="53ef0-208">LogKeywords</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53ef0-209">Diese Einstellung kann nur in macOS und Linux verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-209">This setting can only be used in macOS and Linux.</span></span>

<span data-ttu-id="53ef0-210">Bestimmt, welche Teile von PowerShell protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="53ef0-210">Determines which parts of PowerShell are logged.</span></span> <span data-ttu-id="53ef0-211">Standardmäßig sind alle Protokoll Schlüsselwörter aktiviert.</span><span class="sxs-lookup"><span data-stu-id="53ef0-211">By default, all log keywords are enabled.</span></span> <span data-ttu-id="53ef0-212">Um mehrere Schlüsselwörter zu aktivieren, Listen Sie die Werte in einer einzelnen durch Trennzeichen getrennten Zeichenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="53ef0-212">To enable multiple keywords, list the values in a single comma-separated string.</span></span>

```Schema
"LogKeywords": "<log-keyword>,..."
```

<span data-ttu-id="53ef0-213">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="53ef0-213">Where:</span></span>

- <span data-ttu-id="53ef0-214">`<log-keyword>` ist einer dieser Werte:</span><span class="sxs-lookup"><span data-stu-id="53ef0-214">`<log-keyword>` is one of:</span></span>
  - <span data-ttu-id="53ef0-215">Runspace-Runspace-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="53ef0-215">Runspace - runspace management</span></span>
  - <span data-ttu-id="53ef0-216">Pipeline-Pipeline Vorgänge</span><span class="sxs-lookup"><span data-stu-id="53ef0-216">Pipeline - pipeline operations</span></span>
  - <span data-ttu-id="53ef0-217">Protokoll Kommunikationsprotokoll-Behandlung, z. b. PSRP</span><span class="sxs-lookup"><span data-stu-id="53ef0-217">Protocol - communication protocol handling, such as PSRP</span></span>
  - <span data-ttu-id="53ef0-218">Transport-Transportschicht Unterstützung, z. b. ssh</span><span class="sxs-lookup"><span data-stu-id="53ef0-218">Transport - transport layer support, such as SSH</span></span>
  - <span data-ttu-id="53ef0-219">Host-PowerShell-Host Funktionen, z. b. Konsolen Interaktion</span><span class="sxs-lookup"><span data-stu-id="53ef0-219">Host - PowerShell host functionality, for example console interaction</span></span>
  - <span data-ttu-id="53ef0-220">Cmdlets: PowerShell-Cmdlets für Builtin</span><span class="sxs-lookup"><span data-stu-id="53ef0-220">Cmdlets -PowerShell builtin cmdlets</span></span>
  - <span data-ttu-id="53ef0-221">Serializer-Serialisierungslogik</span><span class="sxs-lookup"><span data-stu-id="53ef0-221">Serializer - serialization logic</span></span>
  - <span data-ttu-id="53ef0-222">Sitzung-PowerShell-Sitzungs Status</span><span class="sxs-lookup"><span data-stu-id="53ef0-222">Session - PowerShell session state</span></span>
  - <span data-ttu-id="53ef0-223">Managedplugin-WSMAN-Plug-in</span><span class="sxs-lookup"><span data-stu-id="53ef0-223">ManagedPlugin - WSMan plugin</span></span>

> [!NOTE]
> <span data-ttu-id="53ef0-224">Es wird im Allgemeinen empfohlen, diesen Wert nicht festzulegen, es sei denn, Sie versuchen, ein bestimmtes Verhalten in einem bekannten Bereich von PowerShell zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="53ef0-224">It is generally advised to leave this value unset unless you are trying to diagnose a specific behavior in a known part of PowerShell.</span></span>
> <span data-ttu-id="53ef0-225">Durch Ändern dieses Werts wird nur die Menge der protokollierten Informationen verringert.</span><span class="sxs-lookup"><span data-stu-id="53ef0-225">Changing this value only decreases the amount of information logged.</span></span>

<span data-ttu-id="53ef0-226">In diesem Beispiel wird die Protokollierung auf Runspace-Vorgänge, die Pipeline Logik und die Cmdlet-Verwendung beschränkt.</span><span class="sxs-lookup"><span data-stu-id="53ef0-226">This example limits the logging to runspace operations, pipeline logic, and cmdlet use.</span></span> <span data-ttu-id="53ef0-227">Alle anderen Protokollierungen werden weggelassen.</span><span class="sxs-lookup"><span data-stu-id="53ef0-227">All other logging will be omitted.</span></span>

```json
"LogKeywords": "Runspace,Pipeline,Cmdlets"
```

<!--

## Group policy configuration

### ScriptExecution

### ScriptBlockLogging

### ProtectedEventLogging

### Transcription

### UpdateableHelp

### ConsoleSessionConfiguration

-->

## <a name="more-example-configurations"></a><span data-ttu-id="53ef0-228">Weitere Beispielkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="53ef0-228">More example configurations</span></span>

### <a name="example-windows-configuration"></a><span data-ttu-id="53ef0-229">Windows-Beispielkonfiguration</span><span class="sxs-lookup"><span data-stu-id="53ef0-229">Example Windows configuration</span></span>

<span data-ttu-id="53ef0-230">Für diese Konfiguration sind mehr Einstellungen explizit festgelegt:</span><span class="sxs-lookup"><span data-stu-id="53ef0-230">This configuration has more settings explicitly set:</span></span>

- <span data-ttu-id="53ef0-231">Die Ausführungs Richtlinie für diese PowerShell-Installation ist `AllSigned`</span><span class="sxs-lookup"><span data-stu-id="53ef0-231">Execution policy for this PowerShell installation is `AllSigned`</span></span>
- <span data-ttu-id="53ef0-232">Der CurrentUser-Modulpfad wird auf ein Modul Verzeichnis auf einem freigegebenen Laufwerk festgelegt.</span><span class="sxs-lookup"><span data-stu-id="53ef0-232">The CurrentUser module path is set to a module directory on a shared drive</span></span>
- <span data-ttu-id="53ef0-233">Die `PSImplicitRemotingBatching` experimentelle Funktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="53ef0-233">The `PSImplicitRemotingBatching` experimental feature is enabled</span></span>

> [!NOTE]
> <span data-ttu-id="53ef0-234">Die `ExecutionPolicy` -und- `PSModulePath` Einstellungen können hier nur auf einer Windows-Plattform verwendet werden, da der Modulpfad `\` und `;` Trennzeichen verwendet, und die Ausführungs Richtlinie ist nicht `Unrestricted` (die einzige Richtlinie, die auf Unix-ähnlichen Plattformen zulässig ist).</span><span class="sxs-lookup"><span data-stu-id="53ef0-234">The `ExecutionPolicy` and `PSModulePath` settings here would only work on a Windows platform, since the module path uses `\` and `;` separator characters and the execution policy is not `Unrestricted` (the only policy allowed on UNIX-like platforms).</span></span>

```json
{
  "Microsoft.PowerShell.ExecutionPolicy": "AllSigned",
  "PSModulePath": "Z:\\Marisol's Shared Drive\\Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
}
```

### <a name="example-non-windows-configuration"></a><span data-ttu-id="53ef0-235">Beispiel für eine nicht-Windows-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="53ef0-235">Example non-Windows configuration</span></span>

<span data-ttu-id="53ef0-236">Diese Konfiguration legt eine Reihe von Optionen fest, die nur in macOS oder Linux funktionieren:</span><span class="sxs-lookup"><span data-stu-id="53ef0-236">This configuration sets a number of options that only work in macOS or Linux:</span></span>

- <span data-ttu-id="53ef0-237">Der CurrentUser-Modulpfad wird auf ein benutzerdefiniertes Modul Verzeichnis in festgelegt. `$HOME`</span><span class="sxs-lookup"><span data-stu-id="53ef0-237">The CurrentUser module path is set to a custom module directory in `$HOME`</span></span>
- <span data-ttu-id="53ef0-238">Das experimentelle **pvereinfachcitrefitingbatching** -Funktion ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="53ef0-238">The **PSImplicitRemotingBatching** experimental feature is enabled</span></span>
- <span data-ttu-id="53ef0-239">Der PowerShell-Protokolliergrad **ist für weitere Protokollierung auf ausführlich** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="53ef0-239">The PowerShell logging level is set to **Verbose**, for more logging</span></span>
- <span data-ttu-id="53ef0-240">Diese PowerShell-Installation schreibt mithilfe der **Home-PowerShell** -Identität in die Protokolle.</span><span class="sxs-lookup"><span data-stu-id="53ef0-240">This PowerShell installation writes to the logs using the **home-powershell** identity.</span></span>

```json
{
  "PSModulePath": "%HOME%/.powershell/Modules",
  "ExperimentalFeatures": ["PSImplicitRemotingBatching"],
  "LogLevel": "Verbose",
  "LogIdentity": "home-powershell"
}
```

## <a name="see-also"></a><span data-ttu-id="53ef0-241">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53ef0-241">See also</span></span>

[<span data-ttu-id="53ef0-242">Informationen zu Ausführungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="53ef0-242">About Execution Policies</span></span>](./about_Execution_Policies.md)

[<span data-ttu-id="53ef0-243">Informationen zu automatischen Variablen</span><span class="sxs-lookup"><span data-stu-id="53ef0-243">About Automatic Variables</span></span>](./about_Automatic_Variables.md)

[RFC0029]: https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md

