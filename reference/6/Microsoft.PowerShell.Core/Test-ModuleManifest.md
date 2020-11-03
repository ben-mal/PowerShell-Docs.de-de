---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-modulemanifest?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ModuleManifest
ms.openlocfilehash: 03f32d798a9e7ec1e58cdeb4ddf5d30edccd2490
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217159"
---
# <span data-ttu-id="5cf58-103">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="5cf58-103">Test-ModuleManifest</span></span>

## <span data-ttu-id="5cf58-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5cf58-104">SYNOPSIS</span></span>
<span data-ttu-id="5cf58-105">Überprüft, ob eine Modulmanifestdatei den Inhalt eines Moduls genau beschreibt.</span><span class="sxs-lookup"><span data-stu-id="5cf58-105">Verifies that a module manifest file accurately describes the contents of a module.</span></span>

## <span data-ttu-id="5cf58-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5cf58-106">SYNTAX</span></span>

```
Test-ModuleManifest [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="5cf58-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5cf58-107">DESCRIPTION</span></span>

<span data-ttu-id="5cf58-108">Mit dem **Test-modulemanifest** -Cmdlet wird überprüft, ob sich die in der Modul Manifest-Datei (. psd1) aufgeführten Dateien tatsächlich in den angegebenen Pfaden befinden.</span><span class="sxs-lookup"><span data-stu-id="5cf58-108">The **Test-ModuleManifest** cmdlet verifies that the files that are listed in the module manifest (.psd1) file are actually in the specified paths.</span></span>

<span data-ttu-id="5cf58-109">Dieses Cmdlet soll Modulautoren beim Testen von Manifestdateien unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5cf58-109">This cmdlet is designed to help module authors test their manifest files.</span></span>
<span data-ttu-id="5cf58-110">Modul Benutzer können dieses Cmdlet auch in Skripts und Befehlen verwenden, um Fehler zu erkennen, bevor Skripts ausgeführt werden, die vom Modul abhängen.</span><span class="sxs-lookup"><span data-stu-id="5cf58-110">Module users can also use this cmdlet in scripts and commands to detect errors before they run scripts that depend on the module.</span></span>

<span data-ttu-id="5cf58-111">**Test-modulemanifest** gibt ein Objekt zurück, das das Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="5cf58-111">**Test-ModuleManifest** returns an object that represents the module.</span></span>
<span data-ttu-id="5cf58-112">Dabei handelt es sich um denselben Objekttyp, den Get-Module zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5cf58-112">This is the same type of object that Get-Module returns.</span></span>
<span data-ttu-id="5cf58-113">Wenn Dateien nicht an den im Manifest angegebenen Speicherorten vorhanden sind, generiert das Cmdlet einen Fehler für jede fehlende Datei.</span><span class="sxs-lookup"><span data-stu-id="5cf58-113">If any files are not in the locations specified in the manifest, the cmdlet also generates an error for each missing file.</span></span>

## <span data-ttu-id="5cf58-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5cf58-114">EXAMPLES</span></span>

### <span data-ttu-id="5cf58-115">Beispiel 1: Testen eines Manifests</span><span class="sxs-lookup"><span data-stu-id="5cf58-115">Example 1: Test a manifest</span></span>

```powershell
test-ModuleManifest -Path "$pshome\Modules\TestModule.psd1"
```

<span data-ttu-id="5cf58-116">Dieser Befehl testet das Modulmanifest „TestModule.psd1“.</span><span class="sxs-lookup"><span data-stu-id="5cf58-116">This command tests the TestModule.psd1 module manifest.</span></span>

### <span data-ttu-id="5cf58-117">Beispiel 2: Testen eines Manifests mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="5cf58-117">Example 2: Test a manifest by using the pipeline</span></span>

```powershell
"$pshome\Modules\TestModule.psd1" | test-modulemanifest
```

```Output
Test-ModuleManifest : The specified type data file 'C:\Windows\System32\Wi
ndowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml' could not be processed because the file was not found. Please correct the path and try again.
At line:1 char:34
+ "$pshome\Modules\TestModule.psd1" | test-modulemanifest <<<<
+ CategoryInfo          : ResourceUnavailable: (C:\Windows\System32\WindowsPowerShell\v1.0\Modules\TestModule\TestTypes.ps1xml:String) [Test-ModuleManifest], FileNotFoundException
+ FullyQualifiedErrorId : Modules_TypeDataFileNotFound,Microsoft.PowerShell.Commands.TestModuleManifestCommandName

Name              : TestModule
Path              : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule\TestModule.psd1
Description       :
Guid              : 6f0f1387-cd25-4902-b7b4-22cff6aefa7b
Version           : 1.0
ModuleBase        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\TestModule
ModuleType        : Manifest
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="5cf58-118">Dieser Befehl verwendet einen Pipeline Operator (|), um eine Pfad Zeichenfolge an **Test-modulemanifest** zu senden.</span><span class="sxs-lookup"><span data-stu-id="5cf58-118">This command uses a pipeline operator (|) to send a path string to **Test-ModuleManifest**.</span></span>

<span data-ttu-id="5cf58-119">Die Befehlsausgabe zeigt einen Testfehler, da die im Manifest aufgeführte Datei „TestTypes.ps1xml“ nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="5cf58-119">The command output shows that the test failed, because the TestTypes.ps1xml file, which was listed in the manifest, was not found.</span></span>

### <span data-ttu-id="5cf58-120">Beispiel 3: Schreiben einer Funktion zum Testen eines Modul Manifests</span><span class="sxs-lookup"><span data-stu-id="5cf58-120">Example 3: Write a function to test a module manifest</span></span>

```powershell
function Test-ManifestBool ($path)
```

```Output
{$a = dir $path | Test-ModuleManifest -ErrorAction SilentlyContinue; $?}
```

<span data-ttu-id="5cf58-121">Diese Funktion ist wie **Test-modulemanifest** , gibt jedoch einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="5cf58-121">This function is like **Test-ModuleManifest** , but it returns a Boolean value.</span></span>
<span data-ttu-id="5cf58-122">Die Funktion gibt $true zurück, wenn das Manifest den Test erfolgreich durchlaufen hat, und $false andernfalls.</span><span class="sxs-lookup"><span data-stu-id="5cf58-122">The function returns $True if the manifest passed the test and $False otherwise.</span></span>

<span data-ttu-id="5cf58-123">Die Funktion verwendet das Get-ChildItem Cmdlet Alias = dir, um das von der $PATH Variable angegebene Modul Manifest zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5cf58-123">The function uses the Get-ChildItem cmdlet, alias = dir, to get the module manifest specified by the $path variable.</span></span>
<span data-ttu-id="5cf58-124">Der Befehl verwendet einen Pipeline Operator (|), um das Datei Objekt an **Test-modulemanifest** zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="5cf58-124">The command uses a pipeline operator (|) to pass the file object to **Test-ModuleManifest**.</span></span>

<span data-ttu-id="5cf58-125">**Test-modulemanifest** verwendet den allgemeinen *ErrorAction* -Parameter mit dem Wert SilentlyContinue, um die Anzeige von Fehlern zu unterdrücken, die der Befehl generiert.</span><span class="sxs-lookup"><span data-stu-id="5cf58-125">**Test-ModuleManifest** uses the *ErrorAction* common parameter with a value of SilentlyContinue to suppress the display of any errors that the command generates.</span></span>
<span data-ttu-id="5cf58-126">Außerdem wird das von **Test-modulemanifest** zurückgegebene **psmoduleinfo** -Objekt in der $a Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5cf58-126">It also saves the **PSModuleInfo** object that **Test-ModuleManifest** returns in the $a variable.</span></span>
<span data-ttu-id="5cf58-127">Daher wird das-Objekt nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5cf58-127">Therefore, the object is not displayed.</span></span>

<span data-ttu-id="5cf58-128">In einem separaten Befehl zeigt die Funktion den Wert des $?</span><span class="sxs-lookup"><span data-stu-id="5cf58-128">Then, in a separate command, the function displays the value of the $?</span></span>
<span data-ttu-id="5cf58-129">Automatische Variable.</span><span class="sxs-lookup"><span data-stu-id="5cf58-129">automatic variable.</span></span>
<span data-ttu-id="5cf58-130">Wenn der vorherige Befehl keinen Fehler generiert, zeigt der Befehl $true an, und $false andernfalls.</span><span class="sxs-lookup"><span data-stu-id="5cf58-130">If the previous command generates no error, the command displays $True, and $False otherwise.</span></span>

<span data-ttu-id="5cf58-131">Sie können diese Funktion in bedingten Anweisungen verwenden, z. b. solche, die einem **Import-Module** -Befehl vorangestellt sind, oder einen Befehl, der das Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="5cf58-131">You can use this function in conditional statements, such as those that might precede an **Import-Module** command or a command that uses the module.</span></span>

## <span data-ttu-id="5cf58-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5cf58-132">PARAMETERS</span></span>

### <span data-ttu-id="5cf58-133">-Path</span><span class="sxs-lookup"><span data-stu-id="5cf58-133">-Path</span></span>

<span data-ttu-id="5cf58-134">Gibt einen Pfad und einen Dateinamen für die Manifest-Datei an.</span><span class="sxs-lookup"><span data-stu-id="5cf58-134">Specifies a path and file name for the manifest file.</span></span>
<span data-ttu-id="5cf58-135">Geben Sie einen optionalen Pfad und Namen der Modul Manifest-Datei mit der Dateinamenerweiterung ". psd1" ein.</span><span class="sxs-lookup"><span data-stu-id="5cf58-135">Enter an optional path and name of the module manifest file that has the .psd1 file name extension.</span></span>
<span data-ttu-id="5cf58-136">Der Standardspeicherort ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5cf58-136">The default location is the current directory.</span></span>
<span data-ttu-id="5cf58-137">Platzhalter Zeichen werden unterstützt, müssen jedoch in eine einzelne Modul Manifest-Datei aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="5cf58-137">Wildcard characters are supported, but must resolve to a single module manifest file.</span></span>
<span data-ttu-id="5cf58-138">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5cf58-138">This parameter is required.</span></span>
<span data-ttu-id="5cf58-139">Sie können einen Pfad auch an **Test-modulemanifest** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="5cf58-139">You can also pipe a path to **Test-ModuleManifest**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="5cf58-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5cf58-140">CommonParameters</span></span>

<span data-ttu-id="5cf58-141">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5cf58-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5cf58-142">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5cf58-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5cf58-143">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5cf58-143">INPUTS</span></span>

### <span data-ttu-id="5cf58-144">System.String</span><span class="sxs-lookup"><span data-stu-id="5cf58-144">System.String</span></span>

<span data-ttu-id="5cf58-145">Sie können den Pfad zu einem Modul Manifest an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="5cf58-145">You can pipe the path to a module manifest to this cmdlet.</span></span>

## <span data-ttu-id="5cf58-146">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5cf58-146">OUTPUTS</span></span>

### <span data-ttu-id="5cf58-147">System. Management. Automation. psmoduleinfo</span><span class="sxs-lookup"><span data-stu-id="5cf58-147">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="5cf58-148">Dieses Cmdlet gibt ein **psmoduleinfo** -Objekt zurück, das das Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="5cf58-148">This cmdlet returns a **PSModuleInfo** object that represents the module.</span></span>
<span data-ttu-id="5cf58-149">Dieses Objekt wird auch dann zurückgegeben, wenn das Manifest Fehler aufweist.</span><span class="sxs-lookup"><span data-stu-id="5cf58-149">It returns this object even if the manifest has errors.</span></span>

## <span data-ttu-id="5cf58-150">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5cf58-150">NOTES</span></span>

## <span data-ttu-id="5cf58-151">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5cf58-151">RELATED LINKS</span></span>

[<span data-ttu-id="5cf58-152">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="5cf58-152">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="5cf58-153">Get-Module</span><span class="sxs-lookup"><span data-stu-id="5cf58-153">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="5cf58-154">Import-Module</span><span class="sxs-lookup"><span data-stu-id="5cf58-154">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="5cf58-155">New-Module</span><span class="sxs-lookup"><span data-stu-id="5cf58-155">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="5cf58-156">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="5cf58-156">New-ModuleManifest</span></span>](New-ModuleManifest.md)

[<span data-ttu-id="5cf58-157">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="5cf58-157">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="5cf58-158">about_Modules</span><span class="sxs-lookup"><span data-stu-id="5cf58-158">about_Modules</span></span>](About/about_Modules.md)
