---
title: Ändern des psmodulepath-Installations Pfads | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 795f2bd52aeceddd3c0ca092d0c0cf2ef44bcf23
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784842"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="1e306-102">Ändern des Installationspfads PSModulePath</span><span class="sxs-lookup"><span data-stu-id="1e306-102">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="1e306-103">Die `PSModulePath` Umgebungsvariable speichert die Pfade zu den Speicherorten der Module, die auf dem Datenträger installiert sind.</span><span class="sxs-lookup"><span data-stu-id="1e306-103">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="1e306-104">PowerShell verwendet diese Variable, um Module zu suchen, wenn der Benutzer nicht den vollständigen Pfad zu einem Modul angibt.</span><span class="sxs-lookup"><span data-stu-id="1e306-104">PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="1e306-105">Die Pfade in dieser Variablen werden in der Reihenfolge durchsucht, in der Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1e306-105">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="1e306-106">Wenn PowerShell gestartet `PSModulePath` wird, wird als System Umgebungsvariable mit dem folgenden Standardwert erstellt: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` unter Windows und `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` unter Linux oder Mac sowie `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e306-106">When PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` on Windows and `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` on Linux or Mac, and `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` for Windows PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="1e306-107">Der benutzerspezifische **CurrentUser** -Speicherort ist der `WindowsPowerShell\Modules` Ordner im Speicherort der **Dokumente** in Ihrem Benutzerprofil.</span><span class="sxs-lookup"><span data-stu-id="1e306-107">The user-specific **CurrentUser** location is the `WindowsPowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="1e306-108">Der spezifische Pfad dieses Standorts variiert je nach Version von Windows und ob Sie die Ordner Umleitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e306-108">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="1e306-109">Standardmäßig ist dieser Speicherort unter Windows 10 `$HOME\Documents\WindowsPowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="1e306-109">By default, on Windows 10, that location is `$HOME\Documents\WindowsPowerShell\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="1e306-110">So zeigen Sie die psmodulepath-Variable an</span><span class="sxs-lookup"><span data-stu-id="1e306-110">To view the PSModulePath variable</span></span>

<span data-ttu-id="1e306-111">Geben Sie den folgenden Befehl ein, um die in der Variablen angegebenen Pfade anzuzeigen `PSModulePath` :</span><span class="sxs-lookup"><span data-stu-id="1e306-111">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="1e306-112">So fügen Sie der psmodulepath-Variablen Speicherorte hinzu</span><span class="sxs-lookup"><span data-stu-id="1e306-112">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="1e306-113">Um dieser Variablen Pfade hinzuzufügen, verwenden Sie eine der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="1e306-113">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="1e306-114">Wenn Sie einen temporären Wert hinzufügen möchten, der nur für die aktuelle Sitzung verfügbar ist, führen Sie den folgenden Befehl in der Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="1e306-114">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- <span data-ttu-id="1e306-115">Wenn Sie einen persistenten Wert hinzufügen möchten, der immer verfügbar ist, wenn eine Sitzung geöffnet wird, fügen Sie den obigen Befehl einer PowerShell-Profil Datei ( `$PROFILE` ) hinzu ></span><span class="sxs-lookup"><span data-stu-id="1e306-115">To add a persistent value that is available whenever a session is opened, add the above command to a PowerShell profile file (`$PROFILE`)></span></span>

  <span data-ttu-id="1e306-116">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span><span class="sxs-lookup"><span data-stu-id="1e306-116">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>

- <span data-ttu-id="1e306-117">Um der Registrierung eine persistente Variable hinzuzufügen, erstellen Sie eine neue Benutzer Umgebungsvariable `PSModulePath` mit dem Namen, indem Sie im Dialogfeld **System Eigenschaften** den Umgebungsvariablen-Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e306-117">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="1e306-118">Verwenden Sie die .NET-Methode " [stenvironmentvariable](/dotnet/api/system.environment.setenvironmentvariable) " in der [System. Environment](/dotnet/api/system.environment) -Klasse, um eine persistente Variable mithilfe eines Skripts hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1e306-118">To add a persistent variable by using a script, use the .Net method [SetEnvironmentVariable](/dotnet/api/system.environment.setenvironmentvariable) on the [System.Environment](/dotnet/api/system.environment) class.</span></span> <span data-ttu-id="1e306-119">Mit dem folgenden Skript wird z. b `C:\Program Files\Fabrikam\Module` . der Pfad zum Wert der `PSModulePath` Umgebungsvariablen für den Computer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1e306-119">For example, the following script adds the `C:\Program Files\Fabrikam\Module` path to the value of the `PSModulePath` environment variable for the computer.</span></span> <span data-ttu-id="1e306-120">Um den Pfad zur Benutzer `PSModulePath` Umgebungsvariablen hinzuzufügen, legen Sie für das Ziel den Wert "User" fest.</span><span class="sxs-lookup"><span data-stu-id="1e306-120">To add the path to the user `PSModulePath` environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="1e306-121">So entfernen Sie Speicherorte aus dem psmodulepath</span><span class="sxs-lookup"><span data-stu-id="1e306-121">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="1e306-122">Sie können Pfade aus der Variablen entfernen, indem Sie ähnliche Methoden verwenden: beispielsweise `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` wird der Pfad " **c:\modulepath** " aus der aktuellen Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="1e306-122">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e306-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e306-123">See Also</span></span>

[<span data-ttu-id="1e306-124">Schreiben eines Windows PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="1e306-124">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="1e306-125">about_Modules</span><span class="sxs-lookup"><span data-stu-id="1e306-125">about_Modules</span></span>](/powershell/module/microsoft.powershell.core/about/about_modules)
