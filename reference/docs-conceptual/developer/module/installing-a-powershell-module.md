---
ms.date: 09/13/2016
ms.topic: reference
title: Installieren eines PowerShell-Moduls
description: Installieren eines PowerShell-Moduls
ms.openlocfilehash: 3c7a4413168934ca4de1912c9615a6ae0fc45788
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645338"
---
# <a name="installing-a-powershell-module"></a><span data-ttu-id="a806e-103">Installieren eines PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="a806e-103">Installing a PowerShell Module</span></span>

<span data-ttu-id="a806e-104">Nachdem Sie das PowerShell-Modul erstellt haben, möchten Sie das Modul wahrscheinlich auf einem System installieren, damit Sie oder andere es benutzen können.</span><span class="sxs-lookup"><span data-stu-id="a806e-104">After you have created your PowerShell module, you will likely want to install the module on a system, so that you or others may use it.</span></span> <span data-ttu-id="a806e-105">Im Allgemeinen müssen Sie hierzu die Moduldateien (d. h. die PSM1- oder binäre Assemblydatei, das Modulmanifest und alle zugehörigen Dateien) in ein Verzeichnis auf diesem Computer kopieren.</span><span class="sxs-lookup"><span data-stu-id="a806e-105">Generally speaking, this consists of copying the module files (ie, the .psm1, or the binary assembly, the module manifest, and any other associated files) onto a directory on that computer.</span></span> <span data-ttu-id="a806e-106">Bei einem sehr kleinen Projekt kann dies so einfach sein wie das Kopieren und Einfügen der Dateien mit Windows Explorer auf einem einzelnen Remotecomputer. Bei größeren Lösungen sollten Sie jedoch einen komplexeren Installationsprozess verwenden.</span><span class="sxs-lookup"><span data-stu-id="a806e-106">For a very small project, this may be as simple as copying and pasting the files with Windows Explorer onto a single remote computer; however, for larger solutions you may wish to use a more sophisticated installation process.</span></span> <span data-ttu-id="a806e-107">Unabhängig davon, wie Sie Ihr Modul auf das System übertragen, kann PowerShell eine Reihe von Techniken verwenden, mit denen Benutzer Ihre Module suchen und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a806e-107">Regardless of how you get your module onto the system, PowerShell can use a number of techniques that will let users find and use your modules.</span></span> <span data-ttu-id="a806e-108">Das Hauptproblem bei der Installation besteht daher darin, sicherzustellen, dass PowerShell das Modul finden kann.</span><span class="sxs-lookup"><span data-stu-id="a806e-108">Therefore, the main issue for installation is ensuring that PowerShell will be able to find your module.</span></span> <span data-ttu-id="a806e-109">Weitere Informationen finden Sie unter [Importieren eines PowerShell-Moduls](./importing-a-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="a806e-109">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="rules-for-installing-modules"></a><span data-ttu-id="a806e-110">Regeln für die Installation von Modulen</span><span class="sxs-lookup"><span data-stu-id="a806e-110">Rules for Installing Modules</span></span>

<span data-ttu-id="a806e-111">Die folgenden Informationen beziehen sich auf alle Module einschließlich derer, die Sie zur eigenen Verwendung erstellen, der Module, die Sie von anderen Anbietern erhalten, sowie Module, die Sie an andere Benutzer verteilen.</span><span class="sxs-lookup"><span data-stu-id="a806e-111">The following information pertains to all modules, including modules that you create for your own use, modules that you get from other parties, and modules that you distribute to others.</span></span>

### <a name="install-modules-in-psmodulepath"></a><span data-ttu-id="a806e-112">Installieren von Modulen in PSModulePath</span><span class="sxs-lookup"><span data-stu-id="a806e-112">Install Modules in PSModulePath</span></span>

<span data-ttu-id="a806e-113">Installieren Sie nach Möglichkeit alle Module in einem Pfad, der in der **PSModulePath**-Umgebungsvariablen aufgeführt ist, oder fügen Sie den Modulpfad dem Wert der **PSModulePath**-Umgebungsvariablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="a806e-113">Whenever possible, install all modules in a path that is listed in the **PSModulePath** environment variable or add the module path to the **PSModulePath** environment variable value.</span></span>

<span data-ttu-id="a806e-114">Die **PSModulePath**-Umgebungsvariable ($Env:PSModulePath) enthält die Speicherorte von Windows PowerShell-Modulen.</span><span class="sxs-lookup"><span data-stu-id="a806e-114">The **PSModulePath** environment variable ($Env:PSModulePath) contains the locations of Windows PowerShell modules.</span></span> <span data-ttu-id="a806e-115">Cmdlets suchen Module auf Basis des Werts dieser Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="a806e-115">Cmdlets rely on the value of this environment variable to find modules.</span></span>

<span data-ttu-id="a806e-116">Standardmäßig enthält der Wert der Umgebungsvariablen **PSModulePath** die folgenden System- und Benutzermodulverzeichnisse. Sie können den Wert jedoch ergänzen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a806e-116">By default, the **PSModulePath** environment variable value contains the following system and user module directories, but you can add to and edit the value.</span></span>

- <span data-ttu-id="a806e-117">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span><span class="sxs-lookup"><span data-stu-id="a806e-117">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span></span>

  > [!WARNING]
  > <span data-ttu-id="a806e-118">Dieser Speicherort ist für Module reserviert, die mit Windows ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="a806e-118">This location is reserved for modules that ship with Windows.</span></span> <span data-ttu-id="a806e-119">Installieren Sie keine Module an diesem Speicherort.</span><span class="sxs-lookup"><span data-stu-id="a806e-119">Do not install modules to this location.</span></span>

- <span data-ttu-id="a806e-120">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Dokumente\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="a806e-120">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span></span>

- <span data-ttu-id="a806e-121">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="a806e-121">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span></span>

  <span data-ttu-id="a806e-122">Verwenden Sie einen der folgenden Befehle, um den Wert der **PSModulePath**-Umgebungsvariablen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a806e-122">To get the value of the **PSModulePath** environment variable, use either of the following commands.</span></span>

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  <span data-ttu-id="a806e-123">Verwenden Sie das folgende Befehlsformat, um dem Wert der **PSModulePath**-Umgebungsvariablen einen Modulpfad hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a806e-123">To add a module path to value of the **PSModulePath** environment variable value, use the following command format.</span></span> <span data-ttu-id="a806e-124">Dieses Format verwendet die **SetEnvironmentVariable**-Methode der **System.Environment**-Klasse, um der Umgebungsvariablen **PSModulePath** einen sitzungsunabhängigen Pfad hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a806e-124">This format uses the **SetEnvironmentVariable** method of the **System.Environment** class to make a session-independent change to the **PSModulePath** environment variable.</span></span>

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > <span data-ttu-id="a806e-125">Nachdem Sie **PSModulePath** den Pfad hinzugefügt haben, sollten Sie eine Nachricht über die Änderung an die Umgebung übertragen.</span><span class="sxs-lookup"><span data-stu-id="a806e-125">Once you have added the path to **PSModulePath**, you should broadcast an environment message about the change.</span></span> <span data-ttu-id="a806e-126">Das Übertragen der Änderung ermöglicht anderen Anwendungen wie der Shell, die Änderung zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="a806e-126">Broadcasting the change allows other applications, such as the shell, to pick up the change.</span></span> <span data-ttu-id="a806e-127">Um die Änderung zu übertragen, lassen Sie Ihren Produktinstallationscode eine **WM_SETTINGCHANGE**-Nachricht senden, wobei `lParam` auf die Zeichenfolge „Environment“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a806e-127">To broadcast the change, have your product installation code send a **WM_SETTINGCHANGE** message with `lParam` set to the string "Environment".</span></span> <span data-ttu-id="a806e-128">Stellen Sie sicher, dass Sie die Nachricht übertragen, nachdem der Modulinstallationscode **PSModulePath** aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="a806e-128">Be sure to send the message after your module installation code has updated **PSModulePath**.</span></span>

### <a name="use-the-correct-module-directory-name"></a><span data-ttu-id="a806e-129">Verwenden des richtigen Modulverzeichnisnamens</span><span class="sxs-lookup"><span data-stu-id="a806e-129">Use the Correct Module Directory Name</span></span>

<span data-ttu-id="a806e-130">Ein wohlgeformtes Modul ist ein Modul, das in einem Verzeichnis gespeichert ist, dessen Name mit dem Basisnamen mindestens einer Datei im Modulverzeichnis identisch ist.</span><span class="sxs-lookup"><span data-stu-id="a806e-130">A well-formed module is a module that is stored in a directory that has the same name as the base name of at least one file in the module directory.</span></span> <span data-ttu-id="a806e-131">Wenn ein Modul nicht wohlgeformt ist, wird es von Windows PowerShell nicht als Modul erkannt.</span><span class="sxs-lookup"><span data-stu-id="a806e-131">If a module is not well-formed, Windows PowerShell does not recognize it as a module.</span></span>

<span data-ttu-id="a806e-132">Der „Basisname“ einer Datei entspricht dem Dateinamen ohne Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="a806e-132">The "base name" of a file is the name without the file name extension.</span></span> <span data-ttu-id="a806e-133">In einem wohlgeformten Modul muss der Name des Verzeichnisses, das die Moduldateien enthält, mit dem Basisnamen mindestens einer Datei im Modul identisch sein.</span><span class="sxs-lookup"><span data-stu-id="a806e-133">In a well-formed module, the name of the directory that contains the module files must match the base name of at least one file in the module.</span></span>

<span data-ttu-id="a806e-134">Beispielsweise hat das Verzeichnis im Fabrikam-Beispielmodul, das die Moduldateien enthält, den Namen „Fabrikam“, und mindestens eine Datei hat den Basisnamen „Fabrikam“.</span><span class="sxs-lookup"><span data-stu-id="a806e-134">For example, in the sample Fabrikam module, the directory that contains the module files is named "Fabrikam" and at least one file has the "Fabrikam" base name.</span></span> <span data-ttu-id="a806e-135">In diesem Fall haben „Fabrikam.psd1“ und „Fabrikam.dll“ beide den Basisnamen „Fabrikam“.</span><span class="sxs-lookup"><span data-stu-id="a806e-135">In this case, both Fabrikam.psd1 and Fabrikam.dll have the "Fabrikam" base name.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a><span data-ttu-id="a806e-136">Auswirkungen einer falschen Installation</span><span class="sxs-lookup"><span data-stu-id="a806e-136">Effect of Incorrect Installation</span></span>

<span data-ttu-id="a806e-137">Wenn das Modul nicht wohlgeformt und sein Speicherort nicht im Wert der **PSModulePath**-Umgebungsvariablen enthalten ist, funktionieren grundlegende Ermittlungsfeatures von Windows PowerShell nicht, z. B. die folgenden.</span><span class="sxs-lookup"><span data-stu-id="a806e-137">If the module is not well-formed and its location is not included in the value of the **PSModulePath** environment variable, basic discovery features of Windows PowerShell, such as the following, do not work.</span></span>

- <span data-ttu-id="a806e-138">Das Feature „Module Auto-Loading“ kann das Modul nicht automatisch importieren.</span><span class="sxs-lookup"><span data-stu-id="a806e-138">The Module Auto-Loading feature cannot import the module automatically.</span></span>

- <span data-ttu-id="a806e-139">Der `ListAvailable`-Parameter des [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)-Cmdlets kann das Modul nicht finden.</span><span class="sxs-lookup"><span data-stu-id="a806e-139">The `ListAvailable` parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet cannot find the module.</span></span>

- <span data-ttu-id="a806e-140">Das [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)-Cmdlet kann das Modul nicht finden.</span><span class="sxs-lookup"><span data-stu-id="a806e-140">The [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet cannot find the module.</span></span> <span data-ttu-id="a806e-141">Zum Importieren des Moduls müssen Sie den vollständigen Pfad zur Stammmoduldatei oder zur Modulmanifestdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="a806e-141">To import the module, you must provide the full path to the root module file or module manifest file.</span></span>

  <span data-ttu-id="a806e-142">Weitere Features, wie z. B. die folgenden, funktionieren erst, wenn das Modul in die Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="a806e-142">Additional features, such as the following, do not work unless the module is imported into the session.</span></span> <span data-ttu-id="a806e-143">In wohlgeformten Modulen in der **PSModulePath**-Umgebungsvariablen funktionieren diese Features auch dann, wenn das Modul nicht in die Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="a806e-143">In well-formed modules in the **PSModulePath** environment variable, these features work even when the module is not imported into the session.</span></span>

- <span data-ttu-id="a806e-144">Das [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command)-Cmdlet kann keine Befehle im Modul finden.</span><span class="sxs-lookup"><span data-stu-id="a806e-144">The [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet cannot find commands in the module.</span></span>

- <span data-ttu-id="a806e-145">[Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)- und [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)-Cmdlet können Hilfe für das Modul nicht aktualisieren oder speichern.</span><span class="sxs-lookup"><span data-stu-id="a806e-145">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets cannot update or save help for the module.</span></span>

- <span data-ttu-id="a806e-146">Das [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command)-Cmdlet kann die Befehle im Modul nicht finden und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a806e-146">The [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet cannot find and display the commands in the module.</span></span>

  <span data-ttu-id="a806e-147">Die Befehle im Modul fehlen in Windows PowerShell Integrated Scripting Environment (ISE) im `Show-Command`-Fenster.</span><span class="sxs-lookup"><span data-stu-id="a806e-147">The commands in the module are missing from the `Show-Command` window in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="where-to-install-modules"></a><span data-ttu-id="a806e-148">Installationsort der Module</span><span class="sxs-lookup"><span data-stu-id="a806e-148">Where to Install Modules</span></span>

<span data-ttu-id="a806e-149">In diesem Abschnitt wird erläutert, wo Windows PowerShell-Module im Dateisystem installiert werden.</span><span class="sxs-lookup"><span data-stu-id="a806e-149">This section explains where in the file system to install Windows PowerShell modules.</span></span> <span data-ttu-id="a806e-150">Der Installationsort hängt davon ab, wie das Modul verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a806e-150">The location depends on how the module is used.</span></span>

### <a name="installing-modules-for-a-specific-user"></a><span data-ttu-id="a806e-151">Installieren von Modulen für einen bestimmten Benutzer</span><span class="sxs-lookup"><span data-stu-id="a806e-151">Installing Modules for a Specific User</span></span>

<span data-ttu-id="a806e-152">Wenn Sie ein eigenes Modul erstellen oder ein Modul von einer anderen Partei (z. B. einer Windows PowerShell-Communitywebsite) erhalten, und das Modul soll nur für Ihr Benutzerkonto verfügbar sein, installieren Sie das Modul in Ihrem benutzerspezifischen Modules-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a806e-152">If you create your own module or get a module from another party, such as a Windows PowerShell community website, and you want the module to be available for your user account only, install the module in your user-specific Modules directory.</span></span>

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

<span data-ttu-id="a806e-153">Das benutzerspezifische Modules-Verzeichnis wird standardmäßig dem Wert der **PSModulePath**-Umgebungsvariablen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a806e-153">The user-specific Modules directory is added to the value of the **PSModulePath** environment variable by default.</span></span>

### <a name="installing-modules-for-all-users-in-program-files"></a><span data-ttu-id="a806e-154">Installieren von Modulen für alle Benutzer in „Programme“</span><span class="sxs-lookup"><span data-stu-id="a806e-154">Installing Modules for all Users in Program Files</span></span>

<span data-ttu-id="a806e-155">Wenn Sie möchten, dass ein Modul für alle Benutzerkonten auf dem Computer verfügbar ist, installieren Sie das Modul im Speicherort „Programme“.</span><span class="sxs-lookup"><span data-stu-id="a806e-155">If you want a module to be available to all user accounts on the computer, install the module in the Program Files location.</span></span>

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> <span data-ttu-id="a806e-156">Der Speicherort „Programme“ wird dem Wert der Umgebungsvariablen PSModulePath in Windows PowerShell 4.0 und höher standardmäßig hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a806e-156">The Program Files location is added to the value of the PSModulePath environment variable by default in Windows PowerShell 4.0 and later.</span></span> <span data-ttu-id="a806e-157">Für frühere Versionen von Windows PowerShell können Sie den Speicherort „Programme“ (%ProgramFiles%\WindowsPowerShell\Modules) manuell erstellen und diesen Pfad der PSModulePath-Umgebungsvariablen wie oben beschrieben hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a806e-157">For earlier versions of Windows PowerShell, you can manually create the Program Files location (%ProgramFiles%\WindowsPowerShell\Modules) and add this path to your PSModulePath environment variable as described above.</span></span>

### <a name="installing-modules-in-a-product-directory"></a><span data-ttu-id="a806e-158">Installieren von Modulen in einem Produktverzeichnis</span><span class="sxs-lookup"><span data-stu-id="a806e-158">Installing Modules in a Product Directory</span></span>

<span data-ttu-id="a806e-159">Wenn Sie das Modul an andere Parteien verteilen, verwenden Sie den oben beschriebenen Standardspeicherort „Programme“, oder erstellen Sie ein eigenes unternehmens- oder produktspezifisches Unterverzeichnis des Verzeichnisses „%ProgramFiles%“.</span><span class="sxs-lookup"><span data-stu-id="a806e-159">If you are distributing the module to other parties, use the default Program Files location described above, or create your own company-specific or product-specific subdirectory of the %ProgramFiles% directory.</span></span>

<span data-ttu-id="a806e-160">Beispielsweise liefert das fiktive Unternehmen Fabrikam Technologies ein Windows PowerShell-Modul für sein Produkt Fabrikam Manager.</span><span class="sxs-lookup"><span data-stu-id="a806e-160">For example, Fabrikam Technologies, a fictitious company, is shipping a Windows PowerShell module for their Fabrikam Manager product.</span></span> <span data-ttu-id="a806e-161">Das Modulinstallationsprogramm erstellt im Produktunterverzeichnis „Fabrikam Manager“ ein Unterverzeichnis „Modules“.</span><span class="sxs-lookup"><span data-stu-id="a806e-161">Their module installer creates a Modules subdirectory in the Fabrikam Manager product subdirectory.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

<span data-ttu-id="a806e-162">Damit die Modulermittlungsfeatures des Windows PowerShell-Moduls das Fabrikam-Modul finden können, fügt das Fabrikam-Modulinstallationsprogramm den Speicherort des Moduls dem Wert der Umgebungsvariablen **PSModulePath** hinzu.</span><span class="sxs-lookup"><span data-stu-id="a806e-162">To enable the Windows PowerShell module discovery features to find the Fabrikam module, the Fabrikam module installer adds the module location to the value of the **PSModulePath** environment variable.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a><span data-ttu-id="a806e-163">Installieren von Modulen im Verzeichnis „Gemeinsame Dateien“</span><span class="sxs-lookup"><span data-stu-id="a806e-163">Installing Modules in the Common Files Directory</span></span>

<span data-ttu-id="a806e-164">Wenn ein Modul von mehreren Komponenten oder Versionen eines Produkts verwendet wird, installieren Sie das Modul in einem modulspezifischen Unterverzeichnis des Unterverzeichnisses „%ProgramFiles%\Gemeinsame Dateien\Modules“.</span><span class="sxs-lookup"><span data-stu-id="a806e-164">If a module is used by multiple components of a product or by multiple versions of a product, install the module in a module-specific subdirectory of the %ProgramFiles%\Common Files\Modules subdirectory.</span></span>

<span data-ttu-id="a806e-165">Im folgenden Beispiel wird das Modul „Fabrikam“ in einem Unterverzeichnis „Fabrikam“ des Unterverzeichnisses `%ProgramFiles%\Common Files\Modules` installiert.</span><span class="sxs-lookup"><span data-stu-id="a806e-165">In the following example, the Fabrikam module is installed in a Fabrikam subdirectory of the `%ProgramFiles%\Common Files\Modules` subdirectory.</span></span> <span data-ttu-id="a806e-166">Beachten Sie, dass sich jedes Modul in einem eigenen Unterverzeichnis des Unterverzeichnisses „Modules“ befindet.</span><span class="sxs-lookup"><span data-stu-id="a806e-166">Note that each module resides in its own subdirectory in the Modules subdirectory.</span></span>

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

<span data-ttu-id="a806e-167">Das Installationsprogramm stellt dann sicher, dass der Wert der **PSModulePath**-Umgebungsvariablen den Pfad des Unterverzeichnisses von „\Gemeinsame Dateien\Modules“ enthält.</span><span class="sxs-lookup"><span data-stu-id="a806e-167">Then, the installer assures the value of the **PSModulePath** environment variable includes the path of the common files modules subdirectory.</span></span>

```powershell
$m = $env:ProgramFiles + '\Common Files\Modules'
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$q = $p -split ';'
if ($q -notContains $m) {
    $q += ";$m"
}
$p = $q -join ';'
[Environment]::SetEnvironmentVariable("PSModulePath", $p)
```

## <a name="installing-multiple-versions-of-a-module"></a><span data-ttu-id="a806e-168">Installieren mehrerer Versionen eines Moduls</span><span class="sxs-lookup"><span data-stu-id="a806e-168">Installing Multiple Versions of a Module</span></span>

<span data-ttu-id="a806e-169">Wenn Sie mehrere Versionen desselben Moduls installieren möchten, verwenden Sie das folgende Verfahren.</span><span class="sxs-lookup"><span data-stu-id="a806e-169">To install multiple versions of the same module, use the following procedure.</span></span>

1. <span data-ttu-id="a806e-170">Erstellen Sie ein Verzeichnis für jede Version des Moduls.</span><span class="sxs-lookup"><span data-stu-id="a806e-170">Create a directory for each version of the module.</span></span> <span data-ttu-id="a806e-171">Fügen Sie die Versionsnummer in den Verzeichnisnamen ein.</span><span class="sxs-lookup"><span data-stu-id="a806e-171">Include the version number in the directory name.</span></span>
2. <span data-ttu-id="a806e-172">Erstellen Sie für jede Version des Moduls ein Modulmanifest.</span><span class="sxs-lookup"><span data-stu-id="a806e-172">Create a module manifest for each version of the module.</span></span> <span data-ttu-id="a806e-173">Geben Sie in den Wert des Schlüssels **ModuleVersion** im Manifest die Modulversionsnummer ein.</span><span class="sxs-lookup"><span data-stu-id="a806e-173">In the value of the **ModuleVersion** key in the manifest, enter the module version number.</span></span> <span data-ttu-id="a806e-174">Speichern Sie die Manifestdatei (PSD1) im versionsspezifischen Verzeichnis für das Modul.</span><span class="sxs-lookup"><span data-stu-id="a806e-174">Save the manifest file (.psd1) in the version-specific directory for the module.</span></span>
3. <span data-ttu-id="a806e-175">Fügen Sie den Stammordnerpfad des Moduls dem Wert der **PSModulePath**-Umgebungsvariablen hinzu, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a806e-175">Add the module root folder path to the value of the **PSModulePath** environment variable, as shown in the following examples.</span></span>

<span data-ttu-id="a806e-176">Um eine bestimmte Version des Moduls zu importieren, kann der Endbenutzer die Parameter `MinimumVersion` oder `RequiredVersion` des [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="a806e-176">To import a particular version of the module, the end-user can use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="a806e-177">Wenn das Modul „Fabrikam“ beispielsweise in den Versionen 8.0 und 9.0 verfügbar ist, könnte die Fabrikam-Modulverzeichnisstruktur wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="a806e-177">For example, if the Fabrikam module is available in versions 8.0 and 9.0, the Fabrikam module directory structure might resemble the following.</span></span>

 ```
C:\Program Files
Fabrikam Manager
  Fabrikam8
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "8.0")
      Fabrikam.dll (module assembly)
  Fabrikam9
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "9.0")
      Fabrikam.dll (module assembly)
```

<span data-ttu-id="a806e-178">Das Installationsprogramm fügt dem Wert der **PSModulePath**-Umgebungsvariablen beide Modulpfade hinzu.</span><span class="sxs-lookup"><span data-stu-id="a806e-178">The installer adds both of the module paths to the **PSModulePath** environment variable value.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

<span data-ttu-id="a806e-179">Wenn diese Schritte abgeschlossen sind, ruft der **ListAvailable**-Parameter des [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)-Cmdlets beide Fabrikam-Module ab.</span><span class="sxs-lookup"><span data-stu-id="a806e-179">When these steps are complete, the **ListAvailable** parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet gets both of the Fabrikam modules.</span></span> <span data-ttu-id="a806e-180">Wenn Sie ein bestimmtes Modul importieren möchten, verwenden Sie die Parameter `MinimumVersion` oder `RequiredVersion` des [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a806e-180">To import a particular module, use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="a806e-181">Wenn beide Module in dieselbe Sitzung importiert werden und die Module Cmdlets mit identischen Namen enthalten, sind die zuletzt importierten Cmdlets in der Sitzung gültig.</span><span class="sxs-lookup"><span data-stu-id="a806e-181">If both modules are imported into the same session, and the modules contain cmdlets with the same names, the cmdlets that are imported last are effective in the session.</span></span>

## <a name="handling-command-name-conflicts"></a><span data-ttu-id="a806e-182">Behandeln von Konflikten zwischen Befehlsnamen</span><span class="sxs-lookup"><span data-stu-id="a806e-182">Handling Command Name Conflicts</span></span>

<span data-ttu-id="a806e-183">Konflikte zwischen Befehlsnamen können auftreten, wenn die Befehle, die ein Modul exportiert, dieselben Namen wie die Befehle in der Benutzersitzung haben.</span><span class="sxs-lookup"><span data-stu-id="a806e-183">Command name conflicts can occur when the commands that a module exports have the same name as commands in the user's session.</span></span>

<span data-ttu-id="a806e-184">Wenn eine Sitzung zwei Befehle mit identischen Namen enthält, führt Windows PowerShell den Befehlstyp aus, der Vorrang hat.</span><span class="sxs-lookup"><span data-stu-id="a806e-184">When a session contains two commands that have the same name, Windows PowerShell runs the command type that takes precedence.</span></span> <span data-ttu-id="a806e-185">Wenn eine Sitzung zwei Befehle mit identischen Namen und identischem Typ enthält, führt Windows PowerShell den Befehl aus, der der Sitzung zuletzt hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="a806e-185">When a session contains two commands that have the same name and the same type, Windows PowerShell runs the command that was added to the session most recently.</span></span> <span data-ttu-id="a806e-186">Um einen Befehl auszuführen, der nicht standardmäßig ausgeführt wird, können Benutzer den Befehlsnamen mit dem Modulnamen qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="a806e-186">To run a command that is not run by default, users can qualify the command name with the module name.</span></span>

<span data-ttu-id="a806e-187">Wenn die Sitzung z. B. eine `Get-Date`-Funktion und das `Get-Date`-Cmdlet enthält, führt Windows PowerShell standardmäßig die Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="a806e-187">For example, if the session contains a `Get-Date` function and the `Get-Date` cmdlet, Windows PowerShell runs the function by default.</span></span> <span data-ttu-id="a806e-188">Um das Cmdlet auszuführen, stellen Sie dem Befehl den Namen des Moduls voran, z. B.:</span><span class="sxs-lookup"><span data-stu-id="a806e-188">To run the cmdlet, preface the command with the module name, such as:</span></span>

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

<span data-ttu-id="a806e-189">Um Namenskonflikte zu verhindern, können Modulentwickler den **DefaultCommandPrefix**-Schlüssel im Modulmanifest verwenden, um ein Nounpräfix für alle Befehle anzugeben, die aus dem Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="a806e-189">To prevent name conflicts, module authors can use the **DefaultCommandPrefix** key in the module manifest to specify a noun prefix for all commands exported from the module.</span></span>

<span data-ttu-id="a806e-190">Benutzer können den **Prefix**-Parameter des `Import-Module`-Cmdlets verwenden, um ein alternatives Präfix zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a806e-190">Users can use the **Prefix** parameter of the `Import-Module` cmdlet to use an alternate prefix.</span></span> <span data-ttu-id="a806e-191">Der Wert des **Prefix**-Parameters hat Vorrang vor dem Wert des **DefaultCommandPrefix**-Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="a806e-191">The value of the **Prefix** parameter takes precedence over the value of the **DefaultCommandPrefix** key.</span></span>

## <a name="see-also"></a><span data-ttu-id="a806e-192">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a806e-192">See Also</span></span>

[<span data-ttu-id="a806e-193">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="a806e-193">about_Command_Precedence</span></span>](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[<span data-ttu-id="a806e-194">Schreiben eines Windows PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="a806e-194">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
