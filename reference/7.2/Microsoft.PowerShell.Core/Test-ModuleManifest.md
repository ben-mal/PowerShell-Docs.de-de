---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/test-modulemanifest?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ModuleManifest
ms.openlocfilehash: c86a7253335b91011d2eb225bc53d1c5cc671aff
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603119"
---
# <span data-ttu-id="578e8-102">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="578e8-102">Test-ModuleManifest</span></span>

## <span data-ttu-id="578e8-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="578e8-103">SYNOPSIS</span></span>
<span data-ttu-id="578e8-104">Überprüft, ob eine Modulmanifestdatei den Inhalt eines Moduls genau beschreibt.</span><span class="sxs-lookup"><span data-stu-id="578e8-104">Verifies that a module manifest file accurately describes the contents of a module.</span></span>

## <span data-ttu-id="578e8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="578e8-105">SYNTAX</span></span>

```
Test-ModuleManifest [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="578e8-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="578e8-106">DESCRIPTION</span></span>

<span data-ttu-id="578e8-107">Mit dem **Test-modulemanifest** -Cmdlet wird überprüft, ob sich die in der Modul Manifest-Datei (. psd1) aufgeführten Dateien tatsächlich in den angegebenen Pfaden befinden.</span><span class="sxs-lookup"><span data-stu-id="578e8-107">The **Test-ModuleManifest** cmdlet verifies that the files that are listed in the module manifest (.psd1) file are actually in the specified paths.</span></span>

<span data-ttu-id="578e8-108">Dieses Cmdlet soll Modulautoren beim Testen von Manifestdateien unterstützen.</span><span class="sxs-lookup"><span data-stu-id="578e8-108">This cmdlet is designed to help module authors test their manifest files.</span></span>
<span data-ttu-id="578e8-109">Modul Benutzer können dieses Cmdlet auch in Skripts und Befehlen verwenden, um Fehler zu erkennen, bevor Skripts ausgeführt werden, die vom Modul abhängen.</span><span class="sxs-lookup"><span data-stu-id="578e8-109">Module users can also use this cmdlet in scripts and commands to detect errors before they run scripts that depend on the module.</span></span>

<span data-ttu-id="578e8-110">**Test-modulemanifest** gibt ein Objekt zurück, das das Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="578e8-110">**Test-ModuleManifest** returns an object that represents the module.</span></span>
<span data-ttu-id="578e8-111">Dabei handelt es sich um denselben Objekttyp, den Get-Module zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="578e8-111">This is the same type of object that Get-Module returns.</span></span>
<span data-ttu-id="578e8-112">Wenn Dateien nicht an den im Manifest angegebenen Speicherorten vorhanden sind, generiert das Cmdlet einen Fehler für jede fehlende Datei.</span><span class="sxs-lookup"><span data-stu-id="578e8-112">If any files are not in the locations specified in the manifest, the cmdlet also generates an error for each missing file.</span></span>

## <span data-ttu-id="578e8-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="578e8-113">EXAMPLES</span></span>

### <span data-ttu-id="578e8-114">Beispiel 1: Testen eines Manifests</span><span class="sxs-lookup"><span data-stu-id="578e8-114">Example 1: Test a manifest</span></span>

```powershell
test-ModuleManifest -Path "$pshome\Modules\TestModule.psd1"
```

<span data-ttu-id="578e8-115">Dieser Befehl testet das Modulmanifest „TestModule.psd1“.</span><span class="sxs-lookup"><span data-stu-id="578e8-115">This command tests the TestModule.psd1 module manifest.</span></span>

### <span data-ttu-id="578e8-116">Beispiel 2: Testen eines Manifests mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="578e8-116">Example 2: Test a manifest by using the pipeline</span></span>

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

<span data-ttu-id="578e8-117">Dieser Befehl verwendet einen Pipeline Operator (|), um eine Pfad Zeichenfolge an **Test-modulemanifest** zu senden.</span><span class="sxs-lookup"><span data-stu-id="578e8-117">This command uses a pipeline operator (|) to send a path string to **Test-ModuleManifest**.</span></span>

<span data-ttu-id="578e8-118">Die Befehlsausgabe zeigt einen Testfehler, da die im Manifest aufgeführte Datei „TestTypes.ps1xml“ nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="578e8-118">The command output shows that the test failed, because the TestTypes.ps1xml file, which was listed in the manifest, was not found.</span></span>

### <span data-ttu-id="578e8-119">Beispiel 3: Schreiben einer Funktion zum Testen eines Modul Manifests</span><span class="sxs-lookup"><span data-stu-id="578e8-119">Example 3: Write a function to test a module manifest</span></span>

```powershell
function Test-ManifestBool ($path)
```

```Output
{$a = dir $path | Test-ModuleManifest -ErrorAction SilentlyContinue; $?}
```

<span data-ttu-id="578e8-120">Diese Funktion ist wie **Test-modulemanifest**, gibt jedoch einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="578e8-120">This function is like **Test-ModuleManifest**, but it returns a Boolean value.</span></span>
<span data-ttu-id="578e8-121">Die Funktion gibt $true zurück, wenn das Manifest den Test erfolgreich durchlaufen hat, und $false andernfalls.</span><span class="sxs-lookup"><span data-stu-id="578e8-121">The function returns $True if the manifest passed the test and $False otherwise.</span></span>

<span data-ttu-id="578e8-122">Die Funktion verwendet das Get-ChildItem Cmdlet Alias = dir, um das von der $PATH Variable angegebene Modul Manifest zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="578e8-122">The function uses the Get-ChildItem cmdlet, alias = dir, to get the module manifest specified by the $path variable.</span></span>
<span data-ttu-id="578e8-123">Der Befehl verwendet einen Pipeline Operator (|), um das Datei Objekt an **Test-modulemanifest** zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="578e8-123">The command uses a pipeline operator (|) to pass the file object to **Test-ModuleManifest**.</span></span>

<span data-ttu-id="578e8-124">**Test-modulemanifest** verwendet den allgemeinen *ErrorAction* -Parameter mit dem Wert SilentlyContinue, um die Anzeige von Fehlern zu unterdrücken, die der Befehl generiert.</span><span class="sxs-lookup"><span data-stu-id="578e8-124">**Test-ModuleManifest** uses the *ErrorAction* common parameter with a value of SilentlyContinue to suppress the display of any errors that the command generates.</span></span>
<span data-ttu-id="578e8-125">Außerdem wird das von **Test-modulemanifest** zurückgegebene **psmoduleinfo** -Objekt in der $a Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="578e8-125">It also saves the **PSModuleInfo** object that **Test-ModuleManifest** returns in the $a variable.</span></span>
<span data-ttu-id="578e8-126">Daher wird das-Objekt nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="578e8-126">Therefore, the object is not displayed.</span></span>

<span data-ttu-id="578e8-127">In einem separaten Befehl zeigt die Funktion den Wert des $?</span><span class="sxs-lookup"><span data-stu-id="578e8-127">Then, in a separate command, the function displays the value of the $?</span></span>
<span data-ttu-id="578e8-128">Automatische Variable.</span><span class="sxs-lookup"><span data-stu-id="578e8-128">automatic variable.</span></span>
<span data-ttu-id="578e8-129">Wenn der vorherige Befehl keinen Fehler generiert, zeigt der Befehl $true an, und $false andernfalls.</span><span class="sxs-lookup"><span data-stu-id="578e8-129">If the previous command generates no error, the command displays $True, and $False otherwise.</span></span>

<span data-ttu-id="578e8-130">Sie können diese Funktion in bedingten Anweisungen verwenden, z. b. solche, die einem **Import-Module** -Befehl vorangestellt sind, oder einen Befehl, der das Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="578e8-130">You can use this function in conditional statements, such as those that might precede an **Import-Module** command or a command that uses the module.</span></span>

## <span data-ttu-id="578e8-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="578e8-131">PARAMETERS</span></span>

### <span data-ttu-id="578e8-132">-Path</span><span class="sxs-lookup"><span data-stu-id="578e8-132">-Path</span></span>

<span data-ttu-id="578e8-133">Gibt einen Pfad und einen Dateinamen für die Manifest-Datei an.</span><span class="sxs-lookup"><span data-stu-id="578e8-133">Specifies a path and file name for the manifest file.</span></span>
<span data-ttu-id="578e8-134">Geben Sie einen optionalen Pfad und Namen der Modul Manifest-Datei mit der Dateinamenerweiterung ". psd1" ein.</span><span class="sxs-lookup"><span data-stu-id="578e8-134">Enter an optional path and name of the module manifest file that has the .psd1 file name extension.</span></span>
<span data-ttu-id="578e8-135">Der Standardspeicherort ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="578e8-135">The default location is the current directory.</span></span>
<span data-ttu-id="578e8-136">Platzhalter Zeichen werden unterstützt, müssen jedoch in eine einzelne Modul Manifest-Datei aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="578e8-136">Wildcard characters are supported, but must resolve to a single module manifest file.</span></span>
<span data-ttu-id="578e8-137">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="578e8-137">This parameter is required.</span></span>
<span data-ttu-id="578e8-138">Sie können einen Pfad auch an **Test-modulemanifest** weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="578e8-138">You can also pipe a path to **Test-ModuleManifest**.</span></span>

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

### <span data-ttu-id="578e8-139">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="578e8-139">CommonParameters</span></span>

<span data-ttu-id="578e8-140">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="578e8-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="578e8-141">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="578e8-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="578e8-142">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="578e8-142">INPUTS</span></span>

### <span data-ttu-id="578e8-143">System.String</span><span class="sxs-lookup"><span data-stu-id="578e8-143">System.String</span></span>

<span data-ttu-id="578e8-144">Sie können den Pfad zu einem Modul Manifest an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="578e8-144">You can pipe the path to a module manifest to this cmdlet.</span></span>

## <span data-ttu-id="578e8-145">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="578e8-145">OUTPUTS</span></span>

### <span data-ttu-id="578e8-146">System. Management. Automation. psmoduleinfo</span><span class="sxs-lookup"><span data-stu-id="578e8-146">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="578e8-147">Dieses Cmdlet gibt ein **psmoduleinfo** -Objekt zurück, das das Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="578e8-147">This cmdlet returns a **PSModuleInfo** object that represents the module.</span></span>
<span data-ttu-id="578e8-148">Dieses Objekt wird auch dann zurückgegeben, wenn das Manifest Fehler aufweist.</span><span class="sxs-lookup"><span data-stu-id="578e8-148">It returns this object even if the manifest has errors.</span></span>

## <span data-ttu-id="578e8-149">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="578e8-149">NOTES</span></span>

## <span data-ttu-id="578e8-150">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="578e8-150">RELATED LINKS</span></span>

[<span data-ttu-id="578e8-151">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="578e8-151">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="578e8-152">Get-Module</span><span class="sxs-lookup"><span data-stu-id="578e8-152">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="578e8-153">Import-Module</span><span class="sxs-lookup"><span data-stu-id="578e8-153">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="578e8-154">New-Module</span><span class="sxs-lookup"><span data-stu-id="578e8-154">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="578e8-155">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="578e8-155">New-ModuleManifest</span></span>](New-ModuleManifest.md)

[<span data-ttu-id="578e8-156">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="578e8-156">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="578e8-157">about_Modules</span><span class="sxs-lookup"><span data-stu-id="578e8-157">about_Modules</span></span>](About/about_Modules.md)

