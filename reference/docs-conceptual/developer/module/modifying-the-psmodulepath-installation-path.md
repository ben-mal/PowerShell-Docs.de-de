---
ms.date: 03/12/2021
ms.topic: reference
title: Ändern des Installationspfads PSModulePath
description: Ändern des Installationspfads PSModulePath
ms.openlocfilehash: 1bea1e8ed20f55352cc9b4270e95cf7f0f7e2faa
ms.sourcegitcommit: 2560a122fe3a85ea762c3af6f1cba9e237512b2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103412886"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="0e685-103">Ändern des Installationspfads PSModulePath</span><span class="sxs-lookup"><span data-stu-id="0e685-103">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="0e685-104">Die `PSModulePath` Umgebungsvariable speichert die Pfade zu den Speicherorten der Module, die auf dem Datenträger installiert sind.</span><span class="sxs-lookup"><span data-stu-id="0e685-104">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="0e685-105">PowerShell verwendet diese Variable, um Module zu suchen, wenn der Benutzer nicht den vollständigen Pfad zu einem Modul angibt.</span><span class="sxs-lookup"><span data-stu-id="0e685-105">PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="0e685-106">Die Pfade in dieser Variablen werden in der Reihenfolge durchsucht, in der Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0e685-106">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="0e685-107">Wenn PowerShell gestartet `PSModulePath` wird, wird als System Umgebungsvariable mit dem folgenden Standardwert erstellt: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` unter Windows und `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` unter Linux oder Mac sowie `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e685-107">When PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` on Windows and `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` on Linux or Mac, and `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` for Windows PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="0e685-108">Der benutzerspezifische **CurrentUser** -Speicherort ist der `WindowsPowerShell\Modules` Ordner im Speicherort der **Dokumente** in Ihrem Benutzerprofil.</span><span class="sxs-lookup"><span data-stu-id="0e685-108">The user-specific **CurrentUser** location is the `WindowsPowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="0e685-109">Der spezifische Pfad dieses Standorts variiert je nach Version von Windows und ob Sie die Ordner Umleitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e685-109">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="0e685-110">Standardmäßig ist dieser Speicherort unter Windows 10 `$HOME\Documents\WindowsPowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="0e685-110">By default, on Windows 10, that location is `$HOME\Documents\WindowsPowerShell\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="0e685-111">So zeigen Sie die psmodulepath-Variable an</span><span class="sxs-lookup"><span data-stu-id="0e685-111">To view the PSModulePath variable</span></span>

<span data-ttu-id="0e685-112">Geben Sie den folgenden Befehl ein, um die in der Variablen angegebenen Pfade anzuzeigen `PSModulePath` :</span><span class="sxs-lookup"><span data-stu-id="0e685-112">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="0e685-113">So fügen Sie der psmodulepath-Variablen Speicherorte hinzu</span><span class="sxs-lookup"><span data-stu-id="0e685-113">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="0e685-114">Um dieser Variablen Pfade hinzuzufügen, verwenden Sie eine der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="0e685-114">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="0e685-115">Wenn Sie einen temporären Wert hinzufügen möchten, der nur für die aktuelle Sitzung verfügbar ist, führen Sie den folgenden Befehl in der Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="0e685-115">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- <span data-ttu-id="0e685-116">Wenn Sie einen persistenten Wert hinzufügen möchten, der immer verfügbar ist, wenn eine Sitzung geöffnet wird, fügen Sie den obigen Befehl einer PowerShell-Profil Datei ( `$PROFILE` ) hinzu ></span><span class="sxs-lookup"><span data-stu-id="0e685-116">To add a persistent value that is available whenever a session is opened, add the above command to a PowerShell profile file (`$PROFILE`)></span></span>

  <span data-ttu-id="0e685-117">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span><span class="sxs-lookup"><span data-stu-id="0e685-117">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>

- <span data-ttu-id="0e685-118">Um der Registrierung eine persistente Variable hinzuzufügen, erstellen Sie eine neue Benutzer Umgebungsvariable `PSModulePath` mit dem Namen, indem Sie im Dialogfeld **System Eigenschaften** den Umgebungsvariablen-Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e685-118">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="0e685-119">Verwenden Sie die .NET-Methode " [stenvironmentvariable](/dotnet/api/system.environment.setenvironmentvariable) " in der [System. Environment](/dotnet/api/system.environment) -Klasse, um eine persistente Variable mithilfe eines Skripts hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0e685-119">To add a persistent variable by using a script, use the .Net method [SetEnvironmentVariable](/dotnet/api/system.environment.setenvironmentvariable) on the [System.Environment](/dotnet/api/system.environment) class.</span></span> <span data-ttu-id="0e685-120">Mit dem folgenden Skript wird z. b `C:\Program Files\Fabrikam\Module` . der Pfad zum Wert der `PSModulePath` Umgebungsvariablen für den Computer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0e685-120">For example, the following script adds the `C:\Program Files\Fabrikam\Module` path to the value of the `PSModulePath` environment variable for the computer.</span></span> <span data-ttu-id="0e685-121">Um den Pfad zur Benutzer `PSModulePath` Umgebungsvariablen hinzuzufügen, legen Sie für das Ziel den Wert "User" fest.</span><span class="sxs-lookup"><span data-stu-id="0e685-121">To add the path to the user `PSModulePath` environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

<span data-ttu-id="0e685-122">Sie können auch die `PSModulePath` Werte in der `powershell.config.json` Konfigurationsdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="0e685-122">You may also set the `PSModulePath` values in the `powershell.config.json` configuration file.</span></span> <span data-ttu-id="0e685-123">Weitere Informationen finden Sie unter [about_PowerShell_Config](/powershell/module/microsoft.powershell.core/about/about_powershell_config#psmodulepath).</span><span class="sxs-lookup"><span data-stu-id="0e685-123">For more information, see [about_PowerShell_Config](/powershell/module/microsoft.powershell.core/about/about_powershell_config#psmodulepath).</span></span>

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="0e685-124">So entfernen Sie Speicherorte aus dem psmodulepath</span><span class="sxs-lookup"><span data-stu-id="0e685-124">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="0e685-125">Sie können Pfade aus der Variablen entfernen, indem Sie ähnliche Methoden verwenden: z. b. `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"`</span><span class="sxs-lookup"><span data-stu-id="0e685-125">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"`</span></span>
<span data-ttu-id="0e685-126">entfernt den Pfad " **c:\modulepath** " aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0e685-126">will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e685-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e685-127">See Also</span></span>

[<span data-ttu-id="0e685-128">Schreiben eines Windows PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="0e685-128">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="0e685-129">about_Modules</span><span class="sxs-lookup"><span data-stu-id="0e685-129">about_Modules</span></span>](/powershell/module/microsoft.powershell.core/about/about_modules)
