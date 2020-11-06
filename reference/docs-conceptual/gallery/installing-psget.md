---
ms.date: 09/19/2019
title: Installieren von PowerShellGet
description: In diesem Artikel wird erläutert, wie Sie das Modul PowerShellGet in verschiedenen PowerShell-Versionen installieren.
ms.openlocfilehash: 06ec331446849784bb8464912fbce0e5a940823f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662148"
---
# <a name="installing-powershellget"></a><span data-ttu-id="24d5b-103">Installieren von PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="24d5b-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="24d5b-104">PowerShellGet ist ein Modul, das zum Lieferumfang der folgenden Releases gehört:</span><span class="sxs-lookup"><span data-stu-id="24d5b-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="24d5b-105">[Windows 10](https://www.microsoft.com/windows) oder höher</span><span class="sxs-lookup"><span data-stu-id="24d5b-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="24d5b-106">[Windows Server 2016](/windows-server/windows-server) oder höher</span><span class="sxs-lookup"><span data-stu-id="24d5b-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="24d5b-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) oder höher</span><span class="sxs-lookup"><span data-stu-id="24d5b-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="24d5b-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="24d5b-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="24d5b-109">Herunterladen der neuesten Version aus dem PowerShell-Katalog</span><span class="sxs-lookup"><span data-stu-id="24d5b-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="24d5b-110">Bevor Sie **PowerShellGet** aktualisieren, sollten Sie immer den neuesten **NuGet** -Anbieter installieren.</span><span class="sxs-lookup"><span data-stu-id="24d5b-110">Before updating **PowerShellGet** , you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="24d5b-111">Führen Sie hierzu den folgenden Befehl in einer PowerShell-Sitzung mit erhöhten Rechten aus.</span><span class="sxs-lookup"><span data-stu-id="24d5b-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="24d5b-112">Für Systeme mit PowerShell 5.0 (oder höher) können Sie das neueste PowerShellGet-Modul installieren</span><span class="sxs-lookup"><span data-stu-id="24d5b-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="24d5b-113">Zum Installieren von PowerShellGet führen Sie unter Windows 10, Windows Server 2016 auf einem beliebigen System mit WMF 5.0 oder 5.1 oder auf einem beliebigen System mit PowerShell 6 den folgenden Befehl aus einer PowerShell-Sitzung mit erhöhten Rechten aus.</span><span class="sxs-lookup"><span data-stu-id="24d5b-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
```

<span data-ttu-id="24d5b-114">Verwenden Sie `Update-Module`, um neuere Versionen zu beziehen.</span><span class="sxs-lookup"><span data-stu-id="24d5b-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a><span data-ttu-id="24d5b-115">Computer mit PowerShell 3.0 oder PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="24d5b-115">For computers running PowerShell 3.0 or PowerShell 4.0</span></span>

<span data-ttu-id="24d5b-116">Diese Anweisungen gelten für Computer, auf denen die **PackageManagement-Vorschauversion** oder keine Version von **PowerShellGet** installiert ist.</span><span class="sxs-lookup"><span data-stu-id="24d5b-116">These instructions apply to computers that have the **PackageManagement Preview** installed or don't have any version of **PowerShellGet** installed.</span></span>

<span data-ttu-id="24d5b-117">Das Cmdlet `Save-Module` wird in beiden Anweisungssätzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="24d5b-117">The `Save-Module` cmdlet is used in both sets of instructions.</span></span> <span data-ttu-id="24d5b-118">`Save-Module` lädt ein Modul und alle Abhängigkeiten aus einem registrierten Repository herunter und speichert sie.</span><span class="sxs-lookup"><span data-stu-id="24d5b-118">`Save-Module` downloads and saves a module and any dependencies from a registered repository.</span></span> <span data-ttu-id="24d5b-119">Die neueste Version des Moduls wird in einem bestimmten Pfad auf dem lokalen Computer gespeichert, wird aber nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="24d5b-119">The module's most current version is saved to a specified path on the local computer, but isn't installed.</span></span> <span data-ttu-id="24d5b-120">Kopieren Sie die in Modulen gespeicherten Ordner in `$env:ProgramFiles\WindowsPowerShell\Modules`, um die Module in PowerShell 3.0 oder 4.0 zu installieren.</span><span class="sxs-lookup"><span data-stu-id="24d5b-120">To install the modules in PowerShell 3.0 or 4.0, copy the module saved folders to `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="24d5b-121">Weitere Informationen finden Sie unter [Save-Module](/powershell/module/PowershellGet/Save-Module).</span><span class="sxs-lookup"><span data-stu-id="24d5b-121">For more information, see [Save-Module](/powershell/module/PowershellGet/Save-Module).</span></span>

> [!NOTE]
> <span data-ttu-id="24d5b-122">PowerShell 3.0 und PowerShell 4.0 unterstützten nur eine Version eines Moduls</span><span class="sxs-lookup"><span data-stu-id="24d5b-122">PowerShell 3.0 and PowerShell 4.0 only supported one version of a module.</span></span> <span data-ttu-id="24d5b-123">Ab PowerShell 5.0 werden Module in `<modulename>\<version>` installiert.</span><span class="sxs-lookup"><span data-stu-id="24d5b-123">Starting in PowerShell 5.0, modules are installed in `<modulename>\<version>`.</span></span> <span data-ttu-id="24d5b-124">Dadurch können Sie mehrere Versionen nebeneinander installieren.</span><span class="sxs-lookup"><span data-stu-id="24d5b-124">This allows you to install multiple versions side-by-side.</span></span> <span data-ttu-id="24d5b-125">Nachdem Sie das Modul mithilfe von `Save-Module` heruntergeladen haben, müssen Sie wie in den nachfolgenden Anweisungen beschrieben die Dateien aus `<modulename>\<version>` in den Ordner `<modulename>` auf dem Zielcomputer kopieren.</span><span class="sxs-lookup"><span data-stu-id="24d5b-125">After downloading the module using `Save-Module` you must copy the files from the `<modulename>\<version>` to the `<modulename>` folder on the destination machine, as shown in the instructions below.</span></span>

#### <a name="preparatory-step-on-computers-running-powershell-30"></a><span data-ttu-id="24d5b-126">Vorbereitungsschritt für Computer, auf denen PowerShell 3.0 ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="24d5b-126">Preparatory Step on computers running PowerShell 3.0</span></span>

<span data-ttu-id="24d5b-127">Wenn Sie die Anweisungen in den folgenden Abschnitten ausführen, werden die Module im Verzeichnis `$env:ProgramFiles\WindowsPowerShell\Modules` installiert.</span><span class="sxs-lookup"><span data-stu-id="24d5b-127">The instructions in the sections below install the modules in directory `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>
<span data-ttu-id="24d5b-128">In PowerShell 3.0 wird dieses Verzeichnis in `$env:PSModulePath` standardmäßig nicht aufgeführt. Damit die Module automatisch geladen werden, müssen Sie das Verzeichnis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="24d5b-128">In PowerShell 3.0, this directory isn't listed in `$env:PSModulePath` by default, so you'll need to add it in order for the modules to be auto-loaded.</span></span>

<span data-ttu-id="24d5b-129">Öffnen Sie eine PowerShell-Sitzung mit erhöhten Rechten, und führen Sie den folgenden Befehl aus (der in künftigen Sitzungen übernommen wird):</span><span class="sxs-lookup"><span data-stu-id="24d5b-129">Open an elevated PowerShell session and run the following command (which will take effect in future sessions):</span></span>

```powershell
[Environment]::SetEnvironmentVariable(
  'PSModulePath',
  ((([Environment]::GetEnvironmentVariable('PSModulePath', 'Machine') -split ';') + "$env:ProgramFiles\WindowsPowerShell\Modules") -join ';'),
  'Machine'
)
```

#### <a name="computers-with-the-packagemanagement-preview-installed"></a><span data-ttu-id="24d5b-130">Computer mit installierter PackageManagement-Vorschauversion</span><span class="sxs-lookup"><span data-stu-id="24d5b-130">Computers with the PackageManagement Preview installed</span></span>

> [!NOTE]
> <span data-ttu-id="24d5b-131">Die PackageManagement-Vorschauversion war eine herunterladbare Komponente, mit der PowerShellGet für die PowerShell-Versionen 3 und 4 verfügbar gemacht wurde. Diese Version ist jedoch nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="24d5b-131">PackageManagement Preview was a downloadable component that made PowerShellGet available to PowerShell versions 3 and 4, but it is no longer available.</span></span>
> <span data-ttu-id="24d5b-132">Führen Sie `Get-Module -ListAvailable PowerShellGet` aus, um zu testen, ob diese Komponente auf einem bestimmten Computer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="24d5b-132">To test if it was installed on a given computer, run `Get-Module -ListAvailable PowerShellGet`.</span></span>

1. <span data-ttu-id="24d5b-133">Verwenden Sie aus einer PowerShell-Sitzung `Save-Module`, um die aktuelle Version von **PowerShellGet** herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="24d5b-133">From a PowerShell session, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="24d5b-134">Es werden zwei Ordner heruntergeladen: **PowerShellGet** und **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="24d5b-134">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="24d5b-135">Jeder Ordner enthält einen Unterordner mit einer Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="24d5b-135">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="24d5b-136">Stellen Sie sicher, dass die Module **PowerShellGet** und **PackageManagement** nicht in anderen Prozessen geladen sind.</span><span class="sxs-lookup"><span data-stu-id="24d5b-136">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>

1. <span data-ttu-id="24d5b-137">Öffnen Sie die PowerShell-Konsole erneut mit erhöhten Rechten, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="24d5b-137">Reopen the PowerShell console with elevated permissions and run the following command.</span></span>

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     Remove-Item $targetDir\* -Recurse -Force
     Copy-Item C:\LocalFolder\$_\*\* $targetDir\ -Recurse -Force
   }
   ```

#### <a name="computers-without-powershellget"></a><span data-ttu-id="24d5b-138">Computer ohne PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="24d5b-138">Computers without PowerShellGet</span></span>

<span data-ttu-id="24d5b-139">Für Computer ohne installierte Version von **PowerShellGet** (Testen über `Get-Module -ListAvailable PowerShellGet`) wird zum Herunterladen der Module ein Computer benötigt, auf dem **PowerShellGet** installiert ist.</span><span class="sxs-lookup"><span data-stu-id="24d5b-139">For computers without any version of **PowerShellGet** installed (test with `Get-Module -ListAvailable PowerShellGet`), a computer with **PowerShellGet** installed is needed to download the modules.</span></span>

1. <span data-ttu-id="24d5b-140">Verwenden Sie `Save-Module` auf dem Computer, auf dem **PowerShellGet** installiert ist, um die aktuelle Version von **PowerShellGet** herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="24d5b-140">From the computer that has **PowerShellGet** installed, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="24d5b-141">Es werden zwei Ordner heruntergeladen: **PowerShellGet** und **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="24d5b-141">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="24d5b-142">Jeder Ordner enthält einen Unterordner mit einer Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="24d5b-142">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="24d5b-143">Kopieren Sie den entsprechenden Unterordner `<version>` in den Ordnern **PowerShellGet** und **PackageManagement** , und fügen Sie ihn auf dem Computer ohne **PowerShellGet** , der eine Sitzung mit erhöhten Rechten benötigt, in die Ordner `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` bzw. `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` ein.</span><span class="sxs-lookup"><span data-stu-id="24d5b-143">Copy the respective `<version>` subfolder in the **PowerShellGet** and **PackageManagement** folders to the computer that doesn't have **PowerShellGet** installed, into folders `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` respectively, which requires an elevated session.</span></span>

1. <span data-ttu-id="24d5b-144">Wenn Sie beispielsweise vom Zielcomputer über einen UNC-Pfad (z. B. `\\ws1\C$\LocalFolder`) auf den Downloadordner auf dem anderen Computer (z. B. `ws1`) zugreifen können, öffnen Sie eine PowerShell-Konsole mit erhöhten Rechten, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="24d5b-144">For instance, if you can access the download folder on the other computer, say `ws1`, from the target computer via a UNC path, say `\\ws1\C$\LocalFolder`, open a PowerShell console with elevated permissions and run the following command:</span></span>

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     $null = New-Item -Type Directory -Force $targetDir
     $fromComputer = 'ws1'  # Specify the name of the other computer here.
     Copy-Item \\$fromComputer\C$\LocalFolder\$_\*\* $targetDir -Recurse -Force
     if (-not (Get-ChildItem $targetDir)) { Throw "Copying failed." }
   }
   ```
