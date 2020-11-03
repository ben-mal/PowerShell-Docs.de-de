---
description: Beschreibt die Windows PowerShell-Kompatibilitäts Funktionalität für PowerShell 7.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_Compatibility
ms.openlocfilehash: 777dab1cce4329958337a7c0857b0d712b4387a9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222380"
---
# <a name="about-windows-powershell-compatibility"></a><span data-ttu-id="95b0e-104">Informationen zur Windows PowerShell-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="95b0e-104">About Windows PowerShell compatibility</span></span>

## <a name="short-description"></a><span data-ttu-id="95b0e-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="95b0e-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="95b0e-106">Beschreibt die Windows PowerShell-Kompatibilitäts Funktionalität für PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="95b0e-106">Describes the Windows PowerShell Compatibility functionality for PowerShell 7.</span></span>

## <a name="long-description"></a><span data-ttu-id="95b0e-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="95b0e-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="95b0e-108">Wenn das Modul Manifest nicht anzeigt, dass das Modul mit PowerShell Core kompatibel ist, werden die Module im `%windir%\system32\WindowsPowerShell\v1.0\Modules` Ordner in Windows PowerShell 5,1 Process by Windows PowerShell Compatibility Feature geladen.</span><span class="sxs-lookup"><span data-stu-id="95b0e-108">Unless the module manifest indicates that module is compatible with PowerShell Core, modules in the `%windir%\system32\WindowsPowerShell\v1.0\Modules` folder are loaded in a background Windows PowerShell 5.1 process by Windows PowerShell Compatibility feature.</span></span>

### <a name="using-the-compatibility-feature"></a><span data-ttu-id="95b0e-109">Verwenden des Kompatibilitäts Features</span><span class="sxs-lookup"><span data-stu-id="95b0e-109">Using the Compatibility feature</span></span>

<span data-ttu-id="95b0e-110">Wenn das erste Modul mithilfe der Windows PowerShell-Kompatibilitäts Funktion importiert wird, erstellt PowerShell eine Remote Sitzung mit dem Namen `WinPSCompatSession` , die in einem Windows PowerShell 5,1-Hintergrundprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="95b0e-110">When the first module is imported using Windows PowerShell Compatibility feature, PowerShell creates a remote session named `WinPSCompatSession` that is running in a background Windows PowerShell 5.1 process.</span></span> <span data-ttu-id="95b0e-111">Dieser Prozess wird erstellt, wenn die Kompatibilitäts Funktion das erste Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="95b0e-111">This process is created when the Compatibility feature imports the first module.</span></span> <span data-ttu-id="95b0e-112">Der Prozess wird geschlossen, wenn das letzte Modul entfernt wird (mithilfe von `Remove-Module` ) oder wenn der PowerShell-Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="95b0e-112">The process is closed when the last such module is removed (using `Remove-Module`) or when PowerShell process exits.</span></span>

<span data-ttu-id="95b0e-113">Die in der Sitzung geladenen Module `WinPSCompatSession` werden über implizites Remoting verwendet und in der aktuellen PowerShell-Sitzung reflektiert.</span><span class="sxs-lookup"><span data-stu-id="95b0e-113">The modules loaded in the `WinPSCompatSession` session are used via implicit remoting and reflected into current PowerShell session.</span></span> <span data-ttu-id="95b0e-114">Dies ist die gleiche Transportmethode, die für PowerShell-Aufträge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="95b0e-114">This is the same transport method used for PowerShell jobs.</span></span>

<span data-ttu-id="95b0e-115">Wenn ein Modul in die Sitzung importiert wird `WinPSCompatSession` , generiert implizites Remoting ein Proxy Modul im Verzeichnis des Benutzers `$env:Temp` und importiert dieses Proxy Modul in die aktuelle PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="95b0e-115">When a module is imported into the `WinPSCompatSession` session, implicit remoting generates a proxy module in the user's `$env:Temp` directory and imports this proxy module into current PowerShell session.</span></span> <span data-ttu-id="95b0e-116">Dadurch kann PowerShell erkennen, dass das Modul mithilfe der Windows PowerShell-Kompatibilitäts Funktion geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="95b0e-116">This allows PowerShell to detect that the module was loaded using Windows PowerShell Compatibility functionality.</span></span>

<span data-ttu-id="95b0e-117">Nachdem die Sitzung erstellt wurde, kann Sie für Vorgänge verwendet werden, die für deserialisierte Objekte nicht ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="95b0e-117">Once the session is created, it can be used for operations that don't work correctly on deserialized objects.</span></span> <span data-ttu-id="95b0e-118">Die gesamte Pipeline wird in Windows PowerShell ausgeführt, und nur das endgültige Ergebnis wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95b0e-118">The entire pipeline is executed in Windows PowerShell and only the final result is returned.</span></span> <span data-ttu-id="95b0e-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="95b0e-119">For example:</span></span>

```powershell
$s = Get-PSSession -Name WinPSCompatSession
Invoke-Command -Session $s -ScriptBlock {
  "Running in Windows PowerShell version $($PSVersionTable.PSVersion)"
}
```

<span data-ttu-id="95b0e-120">Die Kompatibilitäts Funktion kann auf zwei Arten aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="95b0e-120">The Compatibility feature can be invoked in two ways:</span></span>

- <span data-ttu-id="95b0e-121">Explizites Importieren eines Moduls mit dem **usewindowspowershell** -Parameter</span><span class="sxs-lookup"><span data-stu-id="95b0e-121">Explicitly by importing a module using the **UseWindowsPowerShell** parameter</span></span>

   ```powershell
   Import-Module -Name ScheduledTasks -UseWindowsPowerShell
   ```

- <span data-ttu-id="95b0e-122">Implizites Importieren eines Windows PowerShell-Moduls nach Modulname,-Pfad oder-Authentifizierung über die Befehls Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="95b0e-122">Implicitly by importing a Windows PowerShell module by module name, path, or autoloading via command discovery.</span></span>

   ```powershell
   Import-Module -Name ServerManager
   Get-AppLockerPolicy -Local
   ```

   <span data-ttu-id="95b0e-123">Wenn das AppLocker-Modul nicht bereits geladen ist, wird es bei der Durchführung von authentifidiert  `Get-AppLockerPolicy` .</span><span class="sxs-lookup"><span data-stu-id="95b0e-123">If not already loaded, the AppLocker module is autoloaded when you run  `Get-AppLockerPolicy`.</span></span>

<span data-ttu-id="95b0e-124">Windows PowerShell-Kompatibilität blockiert das Laden von Modulen, die in der- `WindowsPowerShellCompatibilityModuleDenyList` Einstellung in der PowerShell-Konfigurationsdatei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="95b0e-124">Windows PowerShell Compatibility blocks loading of modules that are listed in the `WindowsPowerShellCompatibilityModuleDenyList` setting in PowerShell configuration file.</span></span>

<span data-ttu-id="95b0e-125">Der Standardwert dieser Einstellung lautet:</span><span class="sxs-lookup"><span data-stu-id="95b0e-125">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityModuleDenyList":  [
   "PSScheduledJob","BestPractices","UpdateServices"
]
```

### <a name="managing-implicit-module-loading"></a><span data-ttu-id="95b0e-126">Verwalten des impliziten Ladevorgangs von Modulen</span><span class="sxs-lookup"><span data-stu-id="95b0e-126">Managing implicit module loading</span></span>

<span data-ttu-id="95b0e-127">Verwenden Sie die `DisableImplicitWinCompat` Einstellung in einer PowerShell-Konfigurationsdatei, um implizites Import Verhalten des Windows PowerShell-Kompatibilitäts Features zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="95b0e-127">To disable implicit import behavior of the Windows PowerShell Compatibility feature, use the `DisableImplicitWinCompat` setting in a PowerShell configuration file.</span></span> <span data-ttu-id="95b0e-128">Diese Einstellung kann der Datei hinzugefügt werden `powershell.config.json` .</span><span class="sxs-lookup"><span data-stu-id="95b0e-128">This setting can be added to the `powershell.config.json` file.</span></span> <span data-ttu-id="95b0e-129">Weitere Informationen finden Sie unter [about_powershell_config](about_powershell_config.md).</span><span class="sxs-lookup"><span data-stu-id="95b0e-129">For more information, see [about_powershell_config](about_powershell_config.md).</span></span>

<span data-ttu-id="95b0e-130">In diesem Beispiel wird gezeigt, wie eine Konfigurationsdatei erstellt wird, die das implizite Modul Lade Feature der Windows PowerShell-Kompatibilität deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="95b0e-130">This example shows how to create a configuration file that disables the implicit module-loading feature of Windows PowerShell Compatibility.</span></span>

```powershell
$ConfigPath = "$PSHOME\DisableWinCompat.powershell.config.json"
$ConfigJSON = ConvertTo-Json -InputObject @{
  "DisableImplicitWinCompat" = $true
  "Microsoft.PowerShell:ExecutionPolicy" = "RemoteSigned"
}
$ConfigJSON | Out-File -Force $ConfigPath
pwsh -settingsFile $ConfigPath
```

<span data-ttu-id="95b0e-131">Weitere Informationen zur Modul Kompatibilität finden Sie in der [PowerShell 7-Modul Kompatibilitäts](https://aka.ms/PSModuleCompat) Liste.</span><span class="sxs-lookup"><span data-stu-id="95b0e-131">For more the latest information about module compatibility, see the [PowerShell 7 module compatibility](https://aka.ms/PSModuleCompat) list.</span></span>

### <a name="managing-cmdlet-clobbering"></a><span data-ttu-id="95b0e-132">Verwalten der Cmdlet-schreiben</span><span class="sxs-lookup"><span data-stu-id="95b0e-132">Managing cmdlet clobbering</span></span>

<span data-ttu-id="95b0e-133">Das Windows PowerShell-Kompatibilitäts Feature verwendet implizites Remoting zum Laden von Modulen im Kompatibilitätsmodus.</span><span class="sxs-lookup"><span data-stu-id="95b0e-133">The Windows PowerShell Compatibility feature uses implicit remoting to load modules in compatibility mode.</span></span> <span data-ttu-id="95b0e-134">Das Ergebnis ist, dass Befehle, die vom Modul exportiert werden, Vorrang vor Befehlen desselben Namens in der aktuellen PowerShell 7-Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="95b0e-134">The result is that commands exported by the module take precedence over commands of the same name in the current PowerShell 7 session.</span></span> <span data-ttu-id="95b0e-135">In der PowerShell-7.0.0-Version umfasste dies die Kernmodule, die mit PowerShell ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="95b0e-135">In the PowerShell 7.0.0 release, this included the core modules that ship with PowerShell.</span></span>

<span data-ttu-id="95b0e-136">In PowerShell 7,1 wurde das Verhalten so geändert, dass die folgenden PowerShell-Kernmodule nicht gemarshallt werden:</span><span class="sxs-lookup"><span data-stu-id="95b0e-136">In PowerShell 7.1, the behavior was changed so that the following core PowerShell modules are not clobbered:</span></span>

- <span data-ttu-id="95b0e-137">Microsoft. PowerShell. ConsoleHost</span><span class="sxs-lookup"><span data-stu-id="95b0e-137">Microsoft.PowerShell.ConsoleHost</span></span>
- <span data-ttu-id="95b0e-138">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="95b0e-138">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="95b0e-139">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="95b0e-139">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="95b0e-140">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="95b0e-140">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="95b0e-141">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="95b0e-141">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="95b0e-142">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="95b0e-142">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="95b0e-143">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="95b0e-143">Microsoft.WSMan.Management</span></span>

<span data-ttu-id="95b0e-144">PowerShell 7,1 hat außerdem die Möglichkeit zum Auflisten zusätzlicher Module hinzugefügt, die nicht durch den Kompatibilitätsmodus verdeckt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="95b0e-144">PowerShell 7.1 also added the ability to list additional modules that should not be clobbered by compatibility mode.</span></span>

<span data-ttu-id="95b0e-145">Sie können die `WindowsPowerShellCompatibilityNoClobberModuleList` Einstellung der PowerShell-Konfigurationsdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="95b0e-145">You can add the `WindowsPowerShellCompatibilityNoClobberModuleList` setting to PowerShell configuration file.</span></span> <span data-ttu-id="95b0e-146">Der Wert dieser Einstellung ist eine durch Trennzeichen getrennte Liste von Modulnamen.</span><span class="sxs-lookup"><span data-stu-id="95b0e-146">The value of this setting is a comma-separated list of module names.</span></span> <span data-ttu-id="95b0e-147">Der Standardwert dieser Einstellung lautet:</span><span class="sxs-lookup"><span data-stu-id="95b0e-147">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityNoClobberModuleList": [ ]
```

## <a name="limitations"></a><span data-ttu-id="95b0e-148">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="95b0e-148">Limitations</span></span>

<span data-ttu-id="95b0e-149">Windows PowerShell-Kompatibilitäts Funktion:</span><span class="sxs-lookup"><span data-stu-id="95b0e-149">The Windows PowerShell Compatibility functionality:</span></span>

1. <span data-ttu-id="95b0e-150">Funktioniert nur lokal auf Windows-Computern</span><span class="sxs-lookup"><span data-stu-id="95b0e-150">Only works locally on Windows computers</span></span>
1. <span data-ttu-id="95b0e-151">Erfordert Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="95b0e-151">Requires that Windows PowerShell 5.1</span></span>
1. <span data-ttu-id="95b0e-152">Arbeitet mit serialisierten Cmdlet-Parametern und Rückgabe Werten, nicht mit Live-Objekten.</span><span class="sxs-lookup"><span data-stu-id="95b0e-152">Operates on serialized cmdlet parameters and return values, not on live objects</span></span>
1. <span data-ttu-id="95b0e-153">Alle Module, die in die Windows PowerShell-Remoting-Sitzung importiert werden, verwenden denselben Runspace.</span><span class="sxs-lookup"><span data-stu-id="95b0e-153">All modules imported into the Windows PowerShell remoting session share the same runspace.</span></span>

## <a name="keywords"></a><span data-ttu-id="95b0e-154">Keywords</span><span class="sxs-lookup"><span data-stu-id="95b0e-154">Keywords</span></span>

<span data-ttu-id="95b0e-155">about_Windows_PowerShell_Compatibility</span><span class="sxs-lookup"><span data-stu-id="95b0e-155">about_Windows_PowerShell_Compatibility</span></span>

## <a name="see-also"></a><span data-ttu-id="95b0e-156">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="95b0e-156">See also</span></span>

[<span data-ttu-id="95b0e-157">about_Modules</span><span class="sxs-lookup"><span data-stu-id="95b0e-157">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="95b0e-158">Import-Module</span><span class="sxs-lookup"><span data-stu-id="95b0e-158">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
