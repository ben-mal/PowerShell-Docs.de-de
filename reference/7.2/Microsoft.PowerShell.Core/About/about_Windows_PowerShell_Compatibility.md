---
description: Beschreibt die Windows PowerShell-Kompatibilitäts Funktionalität für PowerShell 7.
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_Compatibility
ms.openlocfilehash: 3a7605765da8c17bad2d98a1d3fc3f7cc96f57b8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599627"
---
# <a name="about-windows-powershell-compatibility"></a><span data-ttu-id="fa6a0-103">Informationen zur Windows PowerShell-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="fa6a0-103">About Windows PowerShell compatibility</span></span>

## <a name="short-description"></a><span data-ttu-id="fa6a0-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa6a0-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="fa6a0-105">Beschreibt die Windows PowerShell-Kompatibilitäts Funktionalität für PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-105">Describes the Windows PowerShell Compatibility functionality for PowerShell 7.</span></span>

## <a name="long-description"></a><span data-ttu-id="fa6a0-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa6a0-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="fa6a0-107">Wenn das Modul Manifest nicht anzeigt, dass das Modul mit PowerShell Core kompatibel ist, werden die Module im `%windir%\system32\WindowsPowerShell\v1.0\Modules` Ordner in Windows PowerShell 5,1 Process by Windows PowerShell Compatibility Feature geladen.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-107">Unless the module manifest indicates that module is compatible with PowerShell Core, modules in the `%windir%\system32\WindowsPowerShell\v1.0\Modules` folder are loaded in a background Windows PowerShell 5.1 process by Windows PowerShell Compatibility feature.</span></span>

### <a name="using-the-compatibility-feature"></a><span data-ttu-id="fa6a0-108">Verwenden des Kompatibilitäts Features</span><span class="sxs-lookup"><span data-stu-id="fa6a0-108">Using the Compatibility feature</span></span>

<span data-ttu-id="fa6a0-109">Wenn das erste Modul mithilfe der Windows PowerShell-Kompatibilitäts Funktion importiert wird, erstellt PowerShell eine Remote Sitzung mit dem Namen `WinPSCompatSession` , die in einem Windows PowerShell 5,1-Hintergrundprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-109">When the first module is imported using Windows PowerShell Compatibility feature, PowerShell creates a remote session named `WinPSCompatSession` that is running in a background Windows PowerShell 5.1 process.</span></span> <span data-ttu-id="fa6a0-110">Dieser Prozess wird erstellt, wenn die Kompatibilitäts Funktion das erste Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-110">This process is created when the Compatibility feature imports the first module.</span></span> <span data-ttu-id="fa6a0-111">Der Prozess wird geschlossen, wenn das letzte Modul entfernt wird (mithilfe von `Remove-Module` ) oder wenn der PowerShell-Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-111">The process is closed when the last such module is removed (using `Remove-Module`) or when PowerShell process exits.</span></span>

<span data-ttu-id="fa6a0-112">Die in der Sitzung geladenen Module `WinPSCompatSession` werden über implizites Remoting verwendet und in der aktuellen PowerShell-Sitzung reflektiert.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-112">The modules loaded in the `WinPSCompatSession` session are used via implicit remoting and reflected into current PowerShell session.</span></span> <span data-ttu-id="fa6a0-113">Dies ist die gleiche Transportmethode, die für PowerShell-Aufträge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-113">This is the same transport method used for PowerShell jobs.</span></span>

<span data-ttu-id="fa6a0-114">Wenn ein Modul in die Sitzung importiert wird `WinPSCompatSession` , generiert implizites Remoting ein Proxy Modul im Verzeichnis des Benutzers `$env:Temp` und importiert dieses Proxy Modul in die aktuelle PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-114">When a module is imported into the `WinPSCompatSession` session, implicit remoting generates a proxy module in the user's `$env:Temp` directory and imports this proxy module into current PowerShell session.</span></span> <span data-ttu-id="fa6a0-115">Dadurch kann PowerShell erkennen, dass das Modul mithilfe der Windows PowerShell-Kompatibilitäts Funktion geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-115">This allows PowerShell to detect that the module was loaded using Windows PowerShell Compatibility functionality.</span></span>

<span data-ttu-id="fa6a0-116">Nachdem die Sitzung erstellt wurde, kann Sie für Vorgänge verwendet werden, die für deserialisierte Objekte nicht ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-116">Once the session is created, it can be used for operations that don't work correctly on deserialized objects.</span></span> <span data-ttu-id="fa6a0-117">Die gesamte Pipeline wird in Windows PowerShell ausgeführt, und nur das endgültige Ergebnis wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-117">The entire pipeline is executed in Windows PowerShell and only the final result is returned.</span></span> <span data-ttu-id="fa6a0-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fa6a0-118">For example:</span></span>

```powershell
$s = Get-PSSession -Name WinPSCompatSession
Invoke-Command -Session $s -ScriptBlock {
  "Running in Windows PowerShell version $($PSVersionTable.PSVersion)"
}
```

<span data-ttu-id="fa6a0-119">Die Kompatibilitäts Funktion kann auf zwei Arten aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="fa6a0-119">The Compatibility feature can be invoked in two ways:</span></span>

- <span data-ttu-id="fa6a0-120">Explizites Importieren eines Moduls mit dem **usewindowspowershell** -Parameter</span><span class="sxs-lookup"><span data-stu-id="fa6a0-120">Explicitly by importing a module using the **UseWindowsPowerShell** parameter</span></span>

   ```powershell
   Import-Module -Name ScheduledTasks -UseWindowsPowerShell
   ```

- <span data-ttu-id="fa6a0-121">Implizites Importieren eines Windows PowerShell-Moduls nach Modulname,-Pfad oder-Authentifizierung über die Befehls Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-121">Implicitly by importing a Windows PowerShell module by module name, path, or autoloading via command discovery.</span></span>

   ```powershell
   Import-Module -Name ServerManager
   Get-AppLockerPolicy -Local
   ```

   <span data-ttu-id="fa6a0-122">Wenn das AppLocker-Modul nicht bereits geladen ist, wird es bei der Durchführung von authentifidiert  `Get-AppLockerPolicy` .</span><span class="sxs-lookup"><span data-stu-id="fa6a0-122">If not already loaded, the AppLocker module is autoloaded when you run  `Get-AppLockerPolicy`.</span></span>

<span data-ttu-id="fa6a0-123">Windows PowerShell-Kompatibilität blockiert das Laden von Modulen, die in der- `WindowsPowerShellCompatibilityModuleDenyList` Einstellung in der PowerShell-Konfigurationsdatei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-123">Windows PowerShell Compatibility blocks loading of modules that are listed in the `WindowsPowerShellCompatibilityModuleDenyList` setting in PowerShell configuration file.</span></span>

<span data-ttu-id="fa6a0-124">Der Standardwert dieser Einstellung lautet:</span><span class="sxs-lookup"><span data-stu-id="fa6a0-124">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityModuleDenyList":  [
   "PSScheduledJob","BestPractices","UpdateServices"
]
```

### <a name="managing-implicit-module-loading"></a><span data-ttu-id="fa6a0-125">Verwalten des impliziten Ladevorgangs von Modulen</span><span class="sxs-lookup"><span data-stu-id="fa6a0-125">Managing implicit module loading</span></span>

<span data-ttu-id="fa6a0-126">Verwenden Sie die `DisableImplicitWinCompat` Einstellung in einer PowerShell-Konfigurationsdatei, um implizites Import Verhalten des Windows PowerShell-Kompatibilitäts Features zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-126">To disable implicit import behavior of the Windows PowerShell Compatibility feature, use the `DisableImplicitWinCompat` setting in a PowerShell configuration file.</span></span> <span data-ttu-id="fa6a0-127">Diese Einstellung kann der Datei hinzugefügt werden `powershell.config.json` .</span><span class="sxs-lookup"><span data-stu-id="fa6a0-127">This setting can be added to the `powershell.config.json` file.</span></span> <span data-ttu-id="fa6a0-128">Weitere Informationen finden Sie unter [about_powershell_config](about_powershell_config.md).</span><span class="sxs-lookup"><span data-stu-id="fa6a0-128">For more information, see [about_powershell_config](about_powershell_config.md).</span></span>

<span data-ttu-id="fa6a0-129">In diesem Beispiel wird gezeigt, wie eine Konfigurationsdatei erstellt wird, die das implizite Modul Lade Feature der Windows PowerShell-Kompatibilität deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-129">This example shows how to create a configuration file that disables the implicit module-loading feature of Windows PowerShell Compatibility.</span></span>

```powershell
$ConfigPath = "$PSHOME\DisableWinCompat.powershell.config.json"
$ConfigJSON = ConvertTo-Json -InputObject @{
  "DisableImplicitWinCompat" = $true
  "Microsoft.PowerShell:ExecutionPolicy" = "RemoteSigned"
}
$ConfigJSON | Out-File -Force $ConfigPath
pwsh -settingsFile $ConfigPath
```

<span data-ttu-id="fa6a0-130">Weitere Informationen zur Modul Kompatibilität finden Sie in der [PowerShell 7-Modul Kompatibilitäts](https://aka.ms/PSModuleCompat) Liste.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-130">For more the latest information about module compatibility, see the [PowerShell 7 module compatibility](https://aka.ms/PSModuleCompat) list.</span></span>

### <a name="managing-cmdlet-clobbering"></a><span data-ttu-id="fa6a0-131">Verwalten der Cmdlet-schreiben</span><span class="sxs-lookup"><span data-stu-id="fa6a0-131">Managing cmdlet clobbering</span></span>

<span data-ttu-id="fa6a0-132">Das Windows PowerShell-Kompatibilitäts Feature verwendet implizites Remoting zum Laden von Modulen im Kompatibilitätsmodus.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-132">The Windows PowerShell Compatibility feature uses implicit remoting to load modules in compatibility mode.</span></span> <span data-ttu-id="fa6a0-133">Das Ergebnis ist, dass Befehle, die vom Modul exportiert werden, Vorrang vor Befehlen desselben Namens in der aktuellen PowerShell 7-Sitzung haben.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-133">The result is that commands exported by the module take precedence over commands of the same name in the current PowerShell 7 session.</span></span> <span data-ttu-id="fa6a0-134">In der PowerShell-7.0.0-Version umfasste dies die Kernmodule, die mit PowerShell ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-134">In the PowerShell 7.0.0 release, this included the core modules that ship with PowerShell.</span></span>

<span data-ttu-id="fa6a0-135">In PowerShell 7,1 wurde das Verhalten so geändert, dass die folgenden PowerShell-Kernmodule nicht gemarshallt werden:</span><span class="sxs-lookup"><span data-stu-id="fa6a0-135">In PowerShell 7.1, the behavior was changed so that the following core PowerShell modules are not clobbered:</span></span>

- <span data-ttu-id="fa6a0-136">Microsoft. PowerShell. ConsoleHost</span><span class="sxs-lookup"><span data-stu-id="fa6a0-136">Microsoft.PowerShell.ConsoleHost</span></span>
- <span data-ttu-id="fa6a0-137">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="fa6a0-137">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="fa6a0-138">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="fa6a0-138">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="fa6a0-139">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="fa6a0-139">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="fa6a0-140">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="fa6a0-140">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="fa6a0-141">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="fa6a0-141">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="fa6a0-142">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="fa6a0-142">Microsoft.WSMan.Management</span></span>

<span data-ttu-id="fa6a0-143">PowerShell 7,1 hat außerdem die Möglichkeit zum Auflisten zusätzlicher Module hinzugefügt, die nicht durch den Kompatibilitätsmodus verdeckt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-143">PowerShell 7.1 also added the ability to list additional modules that should not be clobbered by compatibility mode.</span></span>

<span data-ttu-id="fa6a0-144">Sie können die `WindowsPowerShellCompatibilityNoClobberModuleList` Einstellung der PowerShell-Konfigurationsdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-144">You can add the `WindowsPowerShellCompatibilityNoClobberModuleList` setting to PowerShell configuration file.</span></span> <span data-ttu-id="fa6a0-145">Der Wert dieser Einstellung ist eine durch Trennzeichen getrennte Liste von Modulnamen.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-145">The value of this setting is a comma-separated list of module names.</span></span> <span data-ttu-id="fa6a0-146">Der Standardwert dieser Einstellung lautet:</span><span class="sxs-lookup"><span data-stu-id="fa6a0-146">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityNoClobberModuleList": [ ]
```

## <a name="limitations"></a><span data-ttu-id="fa6a0-147">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fa6a0-147">Limitations</span></span>

<span data-ttu-id="fa6a0-148">Windows PowerShell-Kompatibilitäts Funktion:</span><span class="sxs-lookup"><span data-stu-id="fa6a0-148">The Windows PowerShell Compatibility functionality:</span></span>

1. <span data-ttu-id="fa6a0-149">Funktioniert nur lokal auf Windows-Computern</span><span class="sxs-lookup"><span data-stu-id="fa6a0-149">Only works locally on Windows computers</span></span>
1. <span data-ttu-id="fa6a0-150">Erfordert Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="fa6a0-150">Requires that Windows PowerShell 5.1</span></span>
1. <span data-ttu-id="fa6a0-151">Arbeitet mit serialisierten Cmdlet-Parametern und Rückgabe Werten, nicht mit Live-Objekten.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-151">Operates on serialized cmdlet parameters and return values, not on live objects</span></span>
1. <span data-ttu-id="fa6a0-152">Alle Module, die in die Windows PowerShell-Remoting-Sitzung importiert werden, verwenden denselben Runspace.</span><span class="sxs-lookup"><span data-stu-id="fa6a0-152">All modules imported into the Windows PowerShell remoting session share the same runspace.</span></span>

## <a name="keywords"></a><span data-ttu-id="fa6a0-153">Keywords</span><span class="sxs-lookup"><span data-stu-id="fa6a0-153">Keywords</span></span>

<span data-ttu-id="fa6a0-154">about_Windows_PowerShell_Compatibility</span><span class="sxs-lookup"><span data-stu-id="fa6a0-154">about_Windows_PowerShell_Compatibility</span></span>

## <a name="see-also"></a><span data-ttu-id="fa6a0-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa6a0-155">See also</span></span>

[<span data-ttu-id="fa6a0-156">about_Modules</span><span class="sxs-lookup"><span data-stu-id="fa6a0-156">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="fa6a0-157">Import-Module</span><span class="sxs-lookup"><span data-stu-id="fa6a0-157">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

