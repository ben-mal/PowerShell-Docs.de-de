---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-modulemanifest?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ModuleManifest
ms.openlocfilehash: 50a3d85b3d598653a03bc6bf8e82c249bba42759
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211972"
---
# <span data-ttu-id="9bc29-103">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="9bc29-103">New-ModuleManifest</span></span>

## <span data-ttu-id="9bc29-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="9bc29-104">SYNOPSIS</span></span>
<span data-ttu-id="9bc29-105">Erstellt ein neues Modulmanifest.</span><span class="sxs-lookup"><span data-stu-id="9bc29-105">Creates a new module manifest.</span></span>

## <span data-ttu-id="9bc29-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9bc29-106">SYNTAX</span></span>

### <span data-ttu-id="9bc29-107">Alle</span><span class="sxs-lookup"><span data-stu-id="9bc29-107">All</span></span>

```
New-ModuleManifest [-Path] <string> [-NestedModules <Object[]>] [-Guid <guid>] [-Author <string>]
 [-CompanyName <string>] [-Copyright <string>] [-RootModule <string>] [-ModuleVersion <version>]
 [-Description <string>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-PowerShellVersion <version>] [-ClrVersion <version>] [-DotNetFrameworkVersion <version>]
 [-PowerShellHostName <string>] [-PowerShellHostVersion <version>] [-RequiredModules <Object[]>]
 [-TypesToProcess <string[]>] [-FormatsToProcess <string[]>] [-ScriptsToProcess <string[]>]
 [-RequiredAssemblies <string[]>] [-FileList <string[]>] [-ModuleList <Object[]>]
 [-FunctionsToExport <string[]>] [-AliasesToExport <string[]>] [-VariablesToExport <string[]>]
 [-CmdletsToExport <string[]>] [-DscResourcesToExport <string[]>] [-CompatiblePSEditions <string[]>]
 [-PrivateData <Object>] [-Tags <string[]>] [-ProjectUri <uri>] [-LicenseUri <uri>] [-IconUri <uri>]
 [-ReleaseNotes <string>] [-HelpInfoUri <string>] [-PassThru] [-DefaultCommandPrefix <string>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9bc29-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9bc29-108">DESCRIPTION</span></span>

<span data-ttu-id="9bc29-109">Das- `New-ModuleManifest` Cmdlet erstellt eine neue Modul Manifest- `.psd1` Datei (), füllt ihre Werte auf und speichert die Manifest-Datei im angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="9bc29-109">The `New-ModuleManifest` cmdlet creates a new module manifest (`.psd1`) file, populates its values, and saves the manifest file in the specified path.</span></span>

<span data-ttu-id="9bc29-110">Modulautoren können dieses Cmdlet verwenden, um ein Manifest für ihr Modul zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-110">Module authors can use this cmdlet to create a manifest for their module.</span></span> <span data-ttu-id="9bc29-111">Ein Modul Manifest ist eine `.psd1` Datei, die eine Hash Tabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="9bc29-111">A module manifest is a `.psd1` file that contains a hash table.</span></span> <span data-ttu-id="9bc29-112">Die Schlüssel und Werte in der Hashtabelle beschreiben den Inhalt und die Attribute des Moduls, definieren die erforderlichen Komponenten und bestimmen, wie die Komponenten verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-112">The keys and values in the hash table describe the contents and attributes of the module, define the prerequisites, and determine how the components are processed.</span></span> <span data-ttu-id="9bc29-113">Manifeste sind für ein Modul nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9bc29-113">Manifests aren't required for a module.</span></span>

<span data-ttu-id="9bc29-114">`New-ModuleManifest` erstellt ein Manifest, das alle häufig verwendeten Manifestressourcen enthält, sodass Sie die Standardausgabe als Manifest-Vorlage verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9bc29-114">`New-ModuleManifest` creates a manifest that includes all the commonly used manifest keys, so you can use the default output as a manifest template.</span></span> <span data-ttu-id="9bc29-115">Um Werte hinzuzufügen oder zu ändern oder Modulschlüssel hinzuzufügen, die von diesem Cmdlet nicht hinzugefügt werden, öffnen Sie die resultierende Datei in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="9bc29-115">To add or change values, or to add module keys that this cmdlet doesn't add, open the resulting file in a text editor.</span></span>

<span data-ttu-id="9bc29-116">Jeder Parameter, mit Ausnahme von **path** und **passthru** , erstellt einen Modul Manifest-Schlüssel und seinen Wert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-116">Each parameter, except for **Path** and **PassThru** , creates a module manifest key and its value.</span></span>
<span data-ttu-id="9bc29-117">In einem Modulmanifest ist nur der **ModuleVersion** -Schlüssel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9bc29-117">In a module manifest, only the **ModuleVersion** key is required.</span></span> <span data-ttu-id="9bc29-118">Wenn Sie nicht in der Parameter Beschreibung angegeben sind, erstellt, wenn Sie einen Parameter aus dem Befehl weglassen, `New-ModuleManifest` eine Kommentar Zeichenfolge für den zugeordneten Wert, der keine Auswirkung hat.</span><span class="sxs-lookup"><span data-stu-id="9bc29-118">Unless specified in the parameter description, if you omit a parameter from the command, `New-ModuleManifest` creates a comment string for the associated value that has no effect.</span></span>

<span data-ttu-id="9bc29-119">In PowerShell 2,0 werden `New-ModuleManifest` Sie zusätzlich zu den erforderlichen Parameterwerten aufgefordert, die Werte der häufig verwendeten Parameter anzugeben, die nicht im Befehl angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="9bc29-119">In PowerShell 2.0, `New-ModuleManifest` prompts you for the values of commonly used parameters that aren't specified in the command, in addition to required parameter values.</span></span> <span data-ttu-id="9bc29-120">Ab PowerShell 3,0 werden `New-ModuleManifest` nur dann aufgefordert, wenn erforderliche Parameterwerte angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-120">Beginning in PowerShell 3.0, `New-ModuleManifest` prompts only when required parameter values aren't specified.</span></span>

<span data-ttu-id="9bc29-121">Wenn Sie beabsichtigen, das Modul im PowerShell-Katalog zu veröffentlichen, muss das Manifest Werte für bestimmte Eigenschaften enthalten.</span><span class="sxs-lookup"><span data-stu-id="9bc29-121">If you are planning to publish your module in the PowerShell Gallery, the manifest must contain values for certain properties.</span></span> <span data-ttu-id="9bc29-122">Weitere Informationen finden Sie unter [erforderliche Metadaten für Elemente, die auf dem PowerShell-Katalog](/powershell/scripting/gallery/how-to/publishing-packages/publishing-a-package#required-metadata-for-items-published-to-the-powershell-gallery) in der Katalog Dokumentation veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-122">For more information, see [Required metadata for items published to the PowerShell Gallery](/powershell/scripting/gallery/how-to/publishing-packages/publishing-a-package#required-metadata-for-items-published-to-the-powershell-gallery) in the Gallery documentation.</span></span>

## <span data-ttu-id="9bc29-123">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="9bc29-123">EXAMPLES</span></span>

### <span data-ttu-id="9bc29-124">Beispiel 1: Erstellen eines neuen Modul Manifests</span><span class="sxs-lookup"><span data-stu-id="9bc29-124">Example 1 - Create a new module manifest</span></span>

<span data-ttu-id="9bc29-125">In diesem Beispiel wird ein neues Modul Manifest in der Datei erstellt, die durch den **path** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9bc29-125">This example creates a new module manifest in the file that is specified by the **Path** parameter.</span></span>
<span data-ttu-id="9bc29-126">Der **passthru** -Parameter sendet die Ausgabe an die Pipeline und an die Datei.</span><span class="sxs-lookup"><span data-stu-id="9bc29-126">The **PassThru** parameter sends the output to the pipeline and to the file.</span></span>

<span data-ttu-id="9bc29-127">Die Ausgabe zeigt die Standardwerte aller Schlüssel im Manifest.</span><span class="sxs-lookup"><span data-stu-id="9bc29-127">The output shows the default values of all keys in the manifest.</span></span>

```powershell
New-ModuleManifest -Path C:\ps-test\Test-Module\Test-Module.psd1 -PassThru
```

```Output
#
# Module manifest for module 'Test-Module'
#
# Generated by: ContosoAdmin
#
# Generated on: 1/22/2019
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '1.0'

# Supported PSEditions
# CompatiblePSEditions = @()

# ID used to uniquely identify this module
GUID = '47179120-0bcb-4f14-8d80-f4560107f85c'

# Author of this module
Author = 'ContosoAdmin'

# Company or vendor of this module
CompanyName = 'Unknown'

# Copyright statement for this module
Copyright = '(c) 2019 ContosoAdmin. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the Windows PowerShell engine required by this module
# PowerShellVersion = ''

# Name of the Windows PowerShell host required by this module
# PowerShellHostName = ''

# Minimum version of the Windows PowerShell host required by this module
# PowerShellHostVersion = ''

# Minimum version of Microsoft .NET Framework required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# DotNetFrameworkVersion = ''

# Minimum version of the common language runtime (CLR) required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# CLRVersion = ''

# Processor architecture (None, X86, Amd64) required by this module
# ProcessorArchitecture = ''

# Modules that must be imported into the global environment prior to importing this module
# RequiredModules = @()

# Assemblies that must be loaded prior to importing this module
# RequiredAssemblies = @()

# Script files (.ps1) that are run in the caller's environment prior to importing this module.
# ScriptsToProcess = @()

# Type files (.ps1xml) to be loaded when importing this module
# TypesToProcess = @()

# Format files (.ps1xml) to be loaded when importing this module
# FormatsToProcess = @()

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
# NestedModules = @()

# Functions to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no functions to export.
FunctionsToExport = @()

# Cmdlets to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no cmdlets to export.
CmdletsToExport = @()

# Variables to export from this module
VariablesToExport = '*'

# Aliases to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no aliases to export.
AliasesToExport = @()

# DSC resources to export from this module
# DscResourcesToExport = @()

# List of all modules packaged with this module
# ModuleList = @()

# List of all files packaged with this module
# FileList = @()

# Private data to pass to the module specified in RootModule/ModuleToProcess. This may also contain a PSData hashtable with additional module metadata used by PowerShell.
PrivateData = @{

    PSData = @{

        # Tags applied to this module. These help with module discovery in online galleries.
        # Tags = @()

        # A URL to the license for this module.
        # LicenseUri = ''

        # A URL to the main website for this project.
        # ProjectUri = ''

        # A URL to an icon representing this module.
        # IconUri = ''

        # ReleaseNotes of this module
        # ReleaseNotes = ''

    } # End of PSData hashtable

} # End of PrivateData hashtable

# HelpInfo URI of this module
# HelpInfoURI = ''

# Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix.
# DefaultCommandPrefix = ''

}
```

### <span data-ttu-id="9bc29-128">Beispiel 2: Erstellen eines neuen Manifests mit einigen vorab aufgefüllten Einstellungen</span><span class="sxs-lookup"><span data-stu-id="9bc29-128">Example 2 - Create a new manifest with some prepopulated settings</span></span>

<span data-ttu-id="9bc29-129">Dieses Beispiel erstellt ein neues Modul Manifest.</span><span class="sxs-lookup"><span data-stu-id="9bc29-129">This example creates a new module manifest.</span></span> <span data-ttu-id="9bc29-130">Er verwendet die Parameter **PowerShellVersion** und **AliasesToExport** , um Werte zu den entsprechenden Manifest-Schlüsseln hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-130">It uses the **PowerShellVersion** and **AliasesToExport** parameters to add values to the corresponding manifest keys.</span></span>

```powershell
New-ModuleManifest -PowerShellVersion 1.0 -AliasesToExport JKBC, DRC, TAC -Path C:\ps-test\ManifestTest.psd1
```

### <span data-ttu-id="9bc29-131">Beispiel 3: Erstellen eines Manifests, das andere Module erfordert</span><span class="sxs-lookup"><span data-stu-id="9bc29-131">Example 3 - Create a manifest that requires other modules</span></span>

<span data-ttu-id="9bc29-132">In diesem Beispiel wird ein Zeichen folgen Format verwendet, um den Namen des **bitstransfer** -Moduls anzugeben, und das Hash Tabellenformat, um den Namen, eine **GUID** und eine Version des **psscheduledjob** -Moduls anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9bc29-132">This example uses a string format to specify the name of the **BitsTransfer** module and the hash table format to specify the name, a **GUID** , and a version of the **PSScheduledJob** module.</span></span>

```powershell
$moduleSettings = @{
  RequiredModules = ("BitsTransfer", @{
    ModuleName="PSScheduledJob"
    ModuleVersion="1.0.0.0";
    GUID="50cdb55f-5ab7-489f-9e94-4ec21ff51e59"
  })
  Path = 'C:\ps-test\ManifestTest.psd1'
}
New-ModuleManifest @moduleSettings
```

<span data-ttu-id="9bc29-133">In diesem Beispiel wird gezeigt, wie die Zeichen folgen-und Hash Tabellen Formate des **modulelist** -, Requirements **dmodules** -und **netstedmodules** -Parameters verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-133">This example shows how to use the string and hash table formats of the **ModuleList** , **RequiredModules** , and **NestedModules** parameter.</span></span> <span data-ttu-id="9bc29-134">Sie können Zeichenfolgen und Hashtabellen in demselben Parameterwert kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9bc29-134">You can combine strings and hash tables in the same parameter value.</span></span>

### <span data-ttu-id="9bc29-135">Beispiel 4: Erstellen eines Manifests, das aktualisierbare Hilfe unterstützt</span><span class="sxs-lookup"><span data-stu-id="9bc29-135">Example 4 - Create a manifest that supports updateable help</span></span>

<span data-ttu-id="9bc29-136">In diesem Beispiel wird der **helpinfouri** -Parameter verwendet, um im Modul Manifest einen **helpinfouri** -Schlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-136">This example uses the **HelpInfoUri** parameter to create a **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="9bc29-137">Der Wert des-Parameters und der Schlüssel müssen mit " **http** " oder " **https** " beginnen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-137">The value of the parameter and the key must begin with **http** or **https** .</span></span> <span data-ttu-id="9bc29-138">Dieser Wert zeigt dem „Aktualisierbare Hilfe“-System, wo die HelpInfo-XML-Informationsdatei für das Modul zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="9bc29-138">This value tells the Updatable Help system where to find the HelpInfo XML updatable help information file for the module.</span></span>

```powershell
$moduleSettings = @{
  HelpInfoUri = 'http://https://go.microsoft.com/fwlink/?LinkID=603'
  Path = 'C:\ps-test\ManifestTest.psd1'
}
New-ModuleManifest @moduleSettings
```

<span data-ttu-id="9bc29-139">Weitere Informationen zur aktualisierbaren Hilfe finden Sie unter [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="9bc29-139">For information about Updatable Help, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="9bc29-140">Informationen zur helpinfo-XML-Datei finden Sie [unter unterstützen der aktualisierbaren Hilfe](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="9bc29-140">For information about the HelpInfo XML file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

### <span data-ttu-id="9bc29-141">Beispiel 5: erhalten von Modul Informationen</span><span class="sxs-lookup"><span data-stu-id="9bc29-141">Example 5 - Getting module information</span></span>

<span data-ttu-id="9bc29-142">Dieses Beispiel zeigt, wie die Konfigurationswerte eines Moduls angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-142">This example shows how to get the configuration values of a module.</span></span> <span data-ttu-id="9bc29-143">Die Werte im Modul Manifest werden in den Werten der Eigenschaften des Modul Objekts wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="9bc29-143">The values in the module manifest are reflected in the values of properties of the module object.</span></span>

<span data-ttu-id="9bc29-144">Das- `Get-Module` Cmdlet wird verwendet, um das **Microsoft. PowerShell. Diagnostics** -Modul mit dem **List** -Parameter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9bc29-144">The `Get-Module` cmdlet is used to get the **Microsoft.PowerShell.Diagnostics** module using the **List** parameter.</span></span> <span data-ttu-id="9bc29-145">Der Befehl sendet das Modul an das `Format-List` Cmdlet, um alle Eigenschaften und Werte des Modul Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-145">The command sends the module to the `Format-List` cmdlet to display all properties and values of the module object.</span></span>

```powershell
Get-Module Microsoft.PowerShell.Diagnostics -List | Format-List -Property *
```

```Output
LogPipelineExecutionDetails : False
Name                        : Microsoft.PowerShell.Diagnostics
Path                        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Microsoft.PowerShell.Diagnostics\Micro
                              soft.PowerShell.Diagnostics.psd1
Definition                  :
Description                 :
Guid                        : ca046f10-ca64-4740-8ff9-2565dba61a4f
HelpInfoUri                 : https://go.microsoft.com/fwlink/?LinkID=210596
ModuleBase                  : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Microsoft.PowerShell.Diagnostics
PrivateData                 :
Version                     : 3.0.0.0
ModuleType                  : Manifest
Author                      : Microsoft Corporation
AccessMode                  : ReadWrite
ClrVersion                  : 4.0
CompanyName                 : Microsoft Corporation
Copyright                   : Microsoft Corporation. All rights reserved.
DotNetFrameworkVersion      :
ExportedFunctions           : {}
ExportedCmdlets             : {[Get-WinEvent, Get-WinEvent], [Get-Counter, Get-Counter], [Import-Counter,
                              Import-Counter], [Export-Counter, Export-Counter]...}
ExportedCommands            : {[Get-WinEvent, Get-WinEvent], [Get-Counter, Get-Counter], [Import-Counter,
                              Import-Counter], [Export-Counter, Export-Counter]...}
FileList                    : {}
ModuleList                  : {}
NestedModules               : {}
PowerShellHostName          :
PowerShellHostVersion       :
PowerShellVersion           : 3.0
ProcessorArchitecture       : None
Scripts                     : {}
RequiredAssemblies          : {}
RequiredModules             : {}
RootModule                  :
ExportedVariables           : {}
ExportedAliases             : {}
ExportedWorkflows           : {}
SessionState                :
OnRemove                    :
ExportedFormatFiles         : {C:\Windows\system32\WindowsPowerShell\v1.0\Event.format.ps1xml,
                              C:\Windows\system32\WindowsPowerShell\v1.0\Diagnostics.format.ps1xml}
ExportedTypeFiles           : {C:\Windows\system32\WindowsPowerShell\v1.0\GetEvent.types.ps1xml}
```

## <span data-ttu-id="9bc29-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9bc29-146">PARAMETERS</span></span>

### <span data-ttu-id="9bc29-147">-Aliasestoexport</span><span class="sxs-lookup"><span data-stu-id="9bc29-147">-AliasesToExport</span></span>

<span data-ttu-id="9bc29-148">Gibt die Aliase an, die das Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-148">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="9bc29-149">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9bc29-149">Wildcards are permitted.</span></span>

<span data-ttu-id="9bc29-150">Sie können diesen Parameter verwenden, um die Aliase einzuschränken, die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-150">You can use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="9bc29-151">Sie kann Aliase aus der Liste der exportierten Aliase entfernen, aber keine Aliase zur Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-151">It can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

<span data-ttu-id="9bc29-152">Wenn Sie diesen Parameter weglassen, wird `New-ModuleManifest` von ein **aliasestoexport** -Schlüssel mit dem Wert `*` (All) erstellt. Dies bedeutet, dass alle im Modul definierten Aliase vom Manifest exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-152">If you omit this parameter, `New-ModuleManifest` creates an **AliasesToExport** key with a value of `*` (all), meaning that all aliases defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9bc29-153">-Autor</span><span class="sxs-lookup"><span data-stu-id="9bc29-153">-Author</span></span>

<span data-ttu-id="9bc29-154">Gibt den Autor des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-154">Specifies the module author.</span></span>

<span data-ttu-id="9bc29-155">Wenn Sie diesen Parameter weglassen, `New-ModuleManifest` erstellt einen **Author** -Schlüssel mit dem Namen des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9bc29-155">If you omit this parameter, `New-ModuleManifest` creates an **Author** key with the name of the current user.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Name of the current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-156">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="9bc29-156">-ClrVersion</span></span>

<span data-ttu-id="9bc29-157">Gibt die für das Modul erforderliche Mindestversion der Common Language Runtime (CLR) von Microsoft .NET Framework an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-157">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-158">-Cmdletstoexport</span><span class="sxs-lookup"><span data-stu-id="9bc29-158">-CmdletsToExport</span></span>

<span data-ttu-id="9bc29-159">Gibt die Cmdlets an, die das Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-159">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="9bc29-160">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9bc29-160">Wildcards are permitted.</span></span>

<span data-ttu-id="9bc29-161">Sie können diesen Parameter verwenden, um die Cmdlets einzuschränken, die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-161">You can use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="9bc29-162">Cmdlets können aus der Liste der exportierten Cmdlets entfernt werden, Sie können jedoch keine Cmdlets zur Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-162">It can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

<span data-ttu-id="9bc29-163">Wenn Sie diesen Parameter weglassen, `New-ModuleManifest` erstellt einen **cmdletstoexport** -Schlüssel mit dem Wert `*` (alle), was bedeutet, dass alle im Modul definierten Cmdlets vom Manifest exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-163">If you omit this parameter, `New-ModuleManifest` creates a **CmdletsToExport** key with a value of `*` (all), meaning that all cmdlets defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9bc29-164">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="9bc29-164">-CompanyName</span></span>

<span data-ttu-id="9bc29-165">Gibt das Unternehmen oder den Hersteller an, der das Modul erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="9bc29-165">Identifies the company or vendor who created the module.</span></span>

<span data-ttu-id="9bc29-166">Wenn Sie diesen Parameter weglassen, `New-ModuleManifest` erstellt einen **CompanyName** -Schlüssel mit dem Wert "unknown".</span><span class="sxs-lookup"><span data-stu-id="9bc29-166">If you omit this parameter, `New-ModuleManifest` creates a **CompanyName** key with a value of "Unknown".</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "Unknown"
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-167">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9bc29-167">-Confirm</span></span>

<span data-ttu-id="9bc29-168">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-168">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-169">-Compatiblepseditions</span><span class="sxs-lookup"><span data-stu-id="9bc29-169">-CompatiblePSEditions</span></span>

<span data-ttu-id="9bc29-170">Gibt die kompatiblen pseditions des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-170">Specifies the module's compatible PSEditions.</span></span> <span data-ttu-id="9bc29-171">Weitere Informationen zu ppingdition finden Sie unter [Module mit kompatiblen PowerShell-Editionen](/powershell/scripting/gallery/concepts/module-psedition-support).</span><span class="sxs-lookup"><span data-stu-id="9bc29-171">For information about PSEdition, see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-172">-Copyright</span><span class="sxs-lookup"><span data-stu-id="9bc29-172">-Copyright</span></span>

<span data-ttu-id="9bc29-173">Gibt eine Urheberrechtserklärung für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-173">Specifies a copyright statement for the module.</span></span>

<span data-ttu-id="9bc29-174">Wenn Sie diesen Parameter weglassen, `New-ModuleManifest` erstellt einen **Copyright** Schlüssel mit dem Wert, `(c) <year> <username>. All rights reserved.` wobei `<year>` das aktuelle Jahr und `<username>` der Wert des **Author** -Schlüssels ist.</span><span class="sxs-lookup"><span data-stu-id="9bc29-174">If you omit this parameter, `New-ModuleManifest` creates a **Copyright** key with a value of `(c) <year> <username>. All rights reserved.` where `<year>` is the current year and `<username>` is the value of the **Author** key.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (c) <year> <username>. All rights reserved.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-175">-Description</span><span class="sxs-lookup"><span data-stu-id="9bc29-175">-Description</span></span>

<span data-ttu-id="9bc29-176">Beschreibt den Inhalt des Moduls.</span><span class="sxs-lookup"><span data-stu-id="9bc29-176">Describes the contents of the module.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-177">-Dotnetframeworkversion</span><span class="sxs-lookup"><span data-stu-id="9bc29-177">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="9bc29-178">Gibt die für das Modul erforderliche Mindestversion des Microsoft .NET Framework an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-178">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-179">-Dscresourcestoexport</span><span class="sxs-lookup"><span data-stu-id="9bc29-179">-DscResourcesToExport</span></span>

<span data-ttu-id="9bc29-180">Gibt die DSC-Ressourcen (DSC) an, die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-180">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="9bc29-181">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9bc29-181">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9bc29-182">-FileList</span><span class="sxs-lookup"><span data-stu-id="9bc29-182">-FileList</span></span>

<span data-ttu-id="9bc29-183">Gibt alle Elemente an, die im Modul enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9bc29-183">Specifies all items that are included in the module.</span></span>

<span data-ttu-id="9bc29-184">Dieser Schlüssel ist als Modulinventar konzipiert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-184">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="9bc29-185">Die im Schlüssel aufgeführten Dateien werden eingeschlossen, wenn das Modul veröffentlicht wird, aber alle Funktionen werden nicht automatisch exportiert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-185">The files listed in the key are included when the module is published, but any functions aren't automatically exported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-186">-Formatstoprocess</span><span class="sxs-lookup"><span data-stu-id="9bc29-186">-FormatsToProcess</span></span>

<span data-ttu-id="9bc29-187">Gibt die Formatierungs Dateien ( `.ps1xml` ) an, die beim Importieren des Moduls ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-187">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="9bc29-188">Wenn Sie ein Modul importieren, führt PowerShell das `Update-FormatData` Cmdlet mit den angegebenen Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="9bc29-188">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="9bc29-189">Da Formatierungs Dateien nicht Bereichs bezogen sind, wirken Sie sich auf alle Sitzungs Zustände in der Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="9bc29-189">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-190">-Functionstoexport</span><span class="sxs-lookup"><span data-stu-id="9bc29-190">-FunctionsToExport</span></span>

<span data-ttu-id="9bc29-191">Gibt die Funktionen an, die das Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-191">Specifies the functions that the module exports.</span></span> <span data-ttu-id="9bc29-192">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9bc29-192">Wildcards are permitted.</span></span>

<span data-ttu-id="9bc29-193">Sie können diesen Parameter verwenden, um die Funktionen einzuschränken, die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-193">You can use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="9bc29-194">Es kann Funktionen aus der Liste der exportierten Aliase entfernen, aber keine Funktionen zur Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-194">It can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

<span data-ttu-id="9bc29-195">Wenn Sie diesen Parameter weglassen, `New-ModuleManifest` erstellt einen **functionstoexport** -Schlüssel mit dem Wert `*` (All), was bedeutet, dass alle im Modul definierten Funktionen vom Manifest exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-195">If you omit this parameter, `New-ModuleManifest` creates an **FunctionsToExport** key with a value of `*` (all), meaning that all functions defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9bc29-196">-GUID</span><span class="sxs-lookup"><span data-stu-id="9bc29-196">-Guid</span></span>

<span data-ttu-id="9bc29-197">Gibt einen eindeutigen Bezeichner für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-197">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="9bc29-198">Die **GUID** kann verwendet werden, um zwischen Modulen mit demselben Namen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-198">The **GUID** can be used to distinguish among modules with the same name.</span></span>

<span data-ttu-id="9bc29-199">Wenn Sie diesen Parameter weglassen, `New-ModuleManifest` erstellt einen **GUID** -Schlüssel im Manifest und generiert eine **GUID** für den Wert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-199">If you omit this parameter, `New-ModuleManifest` creates a **GUID** key in the manifest and generates a **GUID** for the value.</span></span>

<span data-ttu-id="9bc29-200">Geben Sie ein, um eine neue **GUID** in PowerShell zu erstellen `[guid]::NewGuid()` .</span><span class="sxs-lookup"><span data-stu-id="9bc29-200">To create a new **GUID** in PowerShell, type `[guid]::NewGuid()`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: A GUID generated for the module
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-201">-Helpinfouri</span><span class="sxs-lookup"><span data-stu-id="9bc29-201">-HelpInfoUri</span></span>

<span data-ttu-id="9bc29-202">Gibt die Internetadresse der helpinfo-XML-Datei für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-202">Specifies the internet address of the HelpInfo XML file for the module.</span></span> <span data-ttu-id="9bc29-203">Geben Sie einen Uniform Resource Identifier (URI) ein, der mit **http** oder **https** beginnt.</span><span class="sxs-lookup"><span data-stu-id="9bc29-203">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https** .</span></span>

<span data-ttu-id="9bc29-204">Die helpinfo-XML-Datei unterstützt das Feature "aktualisierbare Hilfe", das in PowerShell 3,0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9bc29-204">The HelpInfo XML file supports the Updatable Help feature that was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="9bc29-205">Es enthält Informationen über den Speicherort der herunterladbaren Hilfedateien für das Modul und die Versionsnummern der neuesten Hilfedateien für jedes unterstützte Gebietsschema.</span><span class="sxs-lookup"><span data-stu-id="9bc29-205">It contains information about the location of downloadable help files for the module and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="9bc29-206">Weitere Informationen zur aktualisierbaren Hilfe finden Sie unter [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="9bc29-206">For information about Updatable Help, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="9bc29-207">Informationen zur helpinfo-XML-Datei finden Sie [unter unterstützen der aktualisierbaren Hilfe](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="9bc29-207">For information about the HelpInfo XML file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="9bc29-208">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9bc29-208">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-209">-Iconuri</span><span class="sxs-lookup"><span data-stu-id="9bc29-209">-IconUri</span></span>

<span data-ttu-id="9bc29-210">Gibt die URL eines Symbols für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-210">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="9bc29-211">Das angegebene Symbol wird auf der Katalog Webseite für das Modul angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9bc29-211">The specified icon is displayed on the gallery web page for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-212">-Licenaburi</span><span class="sxs-lookup"><span data-stu-id="9bc29-212">-LicenseUri</span></span>

<span data-ttu-id="9bc29-213">Gibt die URL der Lizenzierungs Bedingungen für das Modul an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-213">Specifies the URL of licensing terms for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-214">-Modulelist</span><span class="sxs-lookup"><span data-stu-id="9bc29-214">-ModuleList</span></span>

<span data-ttu-id="9bc29-215">Listet alle Module auf, die in diesem Modul enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9bc29-215">Lists all modules that are included in this module.</span></span>

<span data-ttu-id="9bc29-216">Geben Sie jeden Modulnamen als Zeichenfolge oder Hashtabelle mit den Schlüsseln **ModuleName** und **ModuleVersion** ein.</span><span class="sxs-lookup"><span data-stu-id="9bc29-216">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="9bc29-217">Die Hashtabelle kann auch einen optionalen **GUID** -Schlüssel haben.</span><span class="sxs-lookup"><span data-stu-id="9bc29-217">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="9bc29-218">Sie können Zeichenfolgen und Hashtabellen im Parameterwert kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9bc29-218">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="9bc29-219">Dieser Schlüssel ist als Modulinventar konzipiert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-219">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="9bc29-220">Die Module, die im Wert dieses Schlüssels aufgeführt sind, werden nicht automatisch verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="9bc29-220">The modules that are listed in the value of this key aren't automatically processed.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-221">-Moduleversion</span><span class="sxs-lookup"><span data-stu-id="9bc29-221">-ModuleVersion</span></span>

<span data-ttu-id="9bc29-222">Gibt die Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-222">Specifies the module's version.</span></span>

<span data-ttu-id="9bc29-223">Dieser Parameter ist nicht erforderlich, aber im Manifest ist ein **moduleversion** -Schlüssel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9bc29-223">This parameter isn't required, but a **ModuleVersion** key is required in the manifest.</span></span> <span data-ttu-id="9bc29-224">Wenn Sie diesen Parameter weglassen, `New-ModuleManifest` erstellt einen **moduleversion** -Schlüssel mit dem Wert 1,0.</span><span class="sxs-lookup"><span data-stu-id="9bc29-224">If you omit this parameter, `New-ModuleManifest` creates a **ModuleVersion** key with a value of 1.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1.0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-225">-Netstedmodules</span><span class="sxs-lookup"><span data-stu-id="9bc29-225">-NestedModules</span></span>

<span data-ttu-id="9bc29-226">Gibt Skript Module ( `.psm1` ) und binäre Module ( `.dll` ) an, die in den Sitzungs Status des Moduls importiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-226">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="9bc29-227">Die Dateien im Schlüssel " **netstedmodules** " werden in der Reihenfolge ausgeführt, in der Sie im Wert aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="9bc29-227">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="9bc29-228">Geben Sie jeden Modulnamen als Zeichenfolge oder Hashtabelle mit den Schlüsseln **ModuleName** und **ModuleVersion** ein.</span><span class="sxs-lookup"><span data-stu-id="9bc29-228">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="9bc29-229">Die Hashtabelle kann auch einen optionalen **GUID** -Schlüssel haben.</span><span class="sxs-lookup"><span data-stu-id="9bc29-229">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="9bc29-230">Sie können Zeichenfolgen und Hashtabellen im Parameterwert kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9bc29-230">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="9bc29-231">Geschachtelte Module enthalten i. d. R. Befehle, die das Stammmodul für die interne Verarbeitung benötigt.</span><span class="sxs-lookup"><span data-stu-id="9bc29-231">Typically, nested modules contain commands that the root module needs for its internal processing.</span></span>
<span data-ttu-id="9bc29-232">Standardmäßig werden die Befehle in den in der Liste eingefügten Modulen aus dem Sitzungs Status des Moduls in den Sitzungs Status des Aufrufers exportiert, das Stamm Modul kann jedoch die Befehle einschränken, die exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-232">By default, the commands in nested modules are exported from the module's session state into the caller's session state, but the root module can restrict the commands that it exports.</span></span> <span data-ttu-id="9bc29-233">Beispielsweise mithilfe eines- `Export-ModuleMember` Befehls.</span><span class="sxs-lookup"><span data-stu-id="9bc29-233">For example, by using an `Export-ModuleMember` command.</span></span>

<span data-ttu-id="9bc29-234">Im Modul Sitzungszustand sind die in der Modul Sitzung vorhandenen Module verfügbar, werden aber nicht von einem `Get-Module` Befehl im Sitzungszustand des Aufrufers zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9bc29-234">Nested modules in the module session state are available to the root module, but they aren't returned by a `Get-Module` command in the caller's session state.</span></span>

<span data-ttu-id="9bc29-235">Skripts ( `.ps1` ), die im Schlüssel " **netstedmodules** " aufgeführt sind, werden im Sitzungs Status des Moduls ausgeführt, nicht im Sitzungszustand des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="9bc29-235">Scripts (`.ps1`) that are listed in the **NestedModules** key are run in the module's session state, not in the caller's session state.</span></span> <span data-ttu-id="9bc29-236">Zum Ausführen eines Skripts im Sitzungsstatus des Aufrufers führen Sie den Namen der Skriptdatei im Wert des **ScriptsToProcess** -Schlüssels im Manifest auf.</span><span class="sxs-lookup"><span data-stu-id="9bc29-236">To run a script in the caller's session state, list the script file name in the value of the **ScriptsToProcess** key in the manifest.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-237">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9bc29-237">-PassThru</span></span>

<span data-ttu-id="9bc29-238">Schreibt das resultierende Modul Manifest in die Konsole und erstellt eine `.psd1` Datei.</span><span class="sxs-lookup"><span data-stu-id="9bc29-238">Writes the resulting module manifest to the console and creates a `.psd1` file.</span></span> <span data-ttu-id="9bc29-239">Standardmäßig generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9bc29-239">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-240">-Path</span><span class="sxs-lookup"><span data-stu-id="9bc29-240">-Path</span></span>

<span data-ttu-id="9bc29-241">Gibt den Pfad und Dateinamen des neuen Modulmanifests an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-241">Specifies the path and file name of the new module manifest.</span></span> <span data-ttu-id="9bc29-242">Geben Sie einen Pfad und einen Dateinamen mit einer `.psd1` Dateinamenerweiterung ein, z `$pshome\Modules\MyModule\MyModule.psd1` . b..</span><span class="sxs-lookup"><span data-stu-id="9bc29-242">Enter a path and file name with a `.psd1` file name extension, such as `$pshome\Modules\MyModule\MyModule.psd1`.</span></span> <span data-ttu-id="9bc29-243">Der **path** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9bc29-243">The **Path** parameter is required.</span></span>

<span data-ttu-id="9bc29-244">Wenn Sie den Pfad zu einer vorhandenen Datei angeben, wird `New-ModuleManifest` die Datei von ohne Warnung ersetzt, es sei denn, die Datei verfügt über das Attribut "schreibgeschützt".</span><span class="sxs-lookup"><span data-stu-id="9bc29-244">If you specify the path to an existing file, `New-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="9bc29-245">Das Manifest sollte sich im Verzeichnis des Moduls befinden, und der Name der Manifest-Datei muss mit dem Namen des Modul Verzeichnisses übereinstimmen, aber mit einer `.psd1` Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="9bc29-245">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` file name extension.</span></span>

> [!NOTE]
> <span data-ttu-id="9bc29-246">Sie können keine Variablen (z. b. oder) als `$PSHOME` `$HOME` Antwort auf eine Eingabeaufforderung für einen **path** -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-246">You cannot use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="9bc29-247">Um eine Variable zu verwenden, schließen Sie den **Path** -Parameter in den Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="9bc29-247">To use a variable, include the **Path** parameter in the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-248">-Powershellhostname</span><span class="sxs-lookup"><span data-stu-id="9bc29-248">-PowerShellHostName</span></span>

<span data-ttu-id="9bc29-249">Gibt den Namen des PowerShell-Host Programms an, das für das Modul erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9bc29-249">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="9bc29-250">Geben Sie den Namen des Host Programms ein, z. b. **Windows PowerShell ISE Host** oder **ConsoleHost** .</span><span class="sxs-lookup"><span data-stu-id="9bc29-250">Enter the name of the host program, such as **Windows PowerShell ISE Host** or **ConsoleHost** .</span></span> <span data-ttu-id="9bc29-251">Platzhalter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="9bc29-251">Wildcards aren't permitted.</span></span>

<span data-ttu-id="9bc29-252">Um den Namen eines Host Programms zu suchen, geben Sie im Programm ein `$Host.Name` .</span><span class="sxs-lookup"><span data-stu-id="9bc29-252">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-253">-Powershellhostversion</span><span class="sxs-lookup"><span data-stu-id="9bc29-253">-PowerShellHostVersion</span></span>

<span data-ttu-id="9bc29-254">Gibt die Mindestversion des PowerShell-Host Programms an, das mit dem Modul funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-254">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="9bc29-255">Geben Sie eine Versionsnummer an, z. B. 1.1.</span><span class="sxs-lookup"><span data-stu-id="9bc29-255">Enter a version number, such as 1.1.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-256">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="9bc29-256">-PowerShellVersion</span></span>

<span data-ttu-id="9bc29-257">Gibt die Mindestversion von PowerShell an, die mit diesem Modul funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-257">Specifies the minimum version of PowerShell that works with this module.</span></span> <span data-ttu-id="9bc29-258">Sie können z. b. 1,0, 2,0 oder 3,0 als Wert des Parameters eingeben.</span><span class="sxs-lookup"><span data-stu-id="9bc29-258">For example, you can enter 1.0, 2.0, or 3.0 as the parameter's value.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-259">-PRIVATEDATA</span><span class="sxs-lookup"><span data-stu-id="9bc29-259">-PrivateData</span></span>

<span data-ttu-id="9bc29-260">Gibt Daten an, die beim Importieren an das Modul übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-260">Specifies data that is passed to the module when it's imported.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-261">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="9bc29-261">-ProcessorArchitecture</span></span>

<span data-ttu-id="9bc29-262">Gibt die Prozessorarchitektur an, die das Modul erfordert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-262">Specifies the processor architecture that the module requires.</span></span> <span data-ttu-id="9bc29-263">Gültige Werte sind x86, amd64, ia64, MSIL und None (unbekannt oder nicht angegeben).</span><span class="sxs-lookup"><span data-stu-id="9bc29-263">Valid values are x86, AMD64, IA64, MSIL, and None (unknown or unspecified).</span></span>

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-264">-Projecturi</span><span class="sxs-lookup"><span data-stu-id="9bc29-264">-ProjectUri</span></span>

<span data-ttu-id="9bc29-265">Gibt die URL einer Webseite zu diesem Projekt an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-265">Specifies the URL of a web page about this project.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-266">-Releasenotes</span><span class="sxs-lookup"><span data-stu-id="9bc29-266">-ReleaseNotes</span></span>

<span data-ttu-id="9bc29-267">Gibt Anmerkungen zur Version an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-267">Specifies release notes.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-268">-Requirements dassemblys</span><span class="sxs-lookup"><span data-stu-id="9bc29-268">-RequiredAssemblies</span></span>

<span data-ttu-id="9bc29-269">Gibt die Assemblydateien ( `.dll` ) an, die das Modul erfordert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-269">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="9bc29-270">Geben Sie die Namen der Assemblydateien ein.</span><span class="sxs-lookup"><span data-stu-id="9bc29-270">Enter the assembly file names.</span></span>
<span data-ttu-id="9bc29-271">PowerShell lädt die angegebenen Assemblys vor dem Aktualisieren von Typen oder Formaten, dem Importieren von geschbten Modulen oder dem Importieren der Modul Datei, die im Wert des **rootmodule** -Schlüssels angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9bc29-271">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="9bc29-272">Verwenden Sie diesen Parameter, um alle Assemblys aufzulisten, die das Modul erfordert. Dazu gehören auch Assemblys, die geladen werden müssen, um alle Formatierungs- oder Typdateien zu aktualisieren, die in den **FormatsToProcess** - oder **TypesToProcess** -Schlüsseln aufgeführt sind, auch wenn diese Assemblys auch als binäre Module in den **NestedModules** -Schlüsseln aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="9bc29-272">Use this parameter to list all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-273">-Requirements dmodules</span><span class="sxs-lookup"><span data-stu-id="9bc29-273">-RequiredModules</span></span>

<span data-ttu-id="9bc29-274">Gibt die Module an, die im globalen Sitzungsstatus enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-274">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="9bc29-275">Wenn sich die erforderlichen Module nicht im globalen Sitzungs Status befinden, importiert PowerShell Sie.</span><span class="sxs-lookup"><span data-stu-id="9bc29-275">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="9bc29-276">Wenn die erforderlichen Module nicht verfügbar sind, `Import-Module` schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="9bc29-276">If the required modules aren't available, the `Import-Module` command fails.</span></span>

<span data-ttu-id="9bc29-277">Geben Sie jeden Modulnamen als Zeichenfolge oder Hashtabelle mit den Schlüsseln **ModuleName** und **ModuleVersion** ein.</span><span class="sxs-lookup"><span data-stu-id="9bc29-277">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="9bc29-278">Die Hashtabelle kann auch einen optionalen **GUID** -Schlüssel haben.</span><span class="sxs-lookup"><span data-stu-id="9bc29-278">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="9bc29-279">Sie können Zeichenfolgen und Hashtabellen im Parameterwert kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9bc29-279">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="9bc29-280">In PowerShell 2,0 `Import-Module` importiert erforderliche Module nicht automatisch.</span><span class="sxs-lookup"><span data-stu-id="9bc29-280">In PowerShell 2.0, `Import-Module` doesn't import required modules automatically.</span></span> <span data-ttu-id="9bc29-281">Es überprüft nur, ob sich die erforderlichen Module im globalen Sitzungsstatus befinden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-281">It just verifies that the required modules are in the global session state.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-282">-Scriptstoprocess</span><span class="sxs-lookup"><span data-stu-id="9bc29-282">-ScriptsToProcess</span></span>

<span data-ttu-id="9bc29-283">Gibt Skript `.ps1` Dateien () an, die im Sitzungszustand des Aufrufers ausgeführt werden, wenn das Modul importiert wird.</span><span class="sxs-lookup"><span data-stu-id="9bc29-283">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="9bc29-284">Sie können diese Skripte zur Vorbereitung einer Umgebung verwenden, wie Sie ein Anmeldeskript verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-284">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="9bc29-285">Um Skripte anzugeben, die im Sitzungsstatus des Moduls ausgeführt werden, verwenden Sie den **NestedModules** -Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="9bc29-285">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-286">-Tags</span><span class="sxs-lookup"><span data-stu-id="9bc29-286">-Tags</span></span>

<span data-ttu-id="9bc29-287">Gibt ein Array von-Tags an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-287">Specifies an array of tags.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-288">-Typestoprocess</span><span class="sxs-lookup"><span data-stu-id="9bc29-288">-TypesToProcess</span></span>

<span data-ttu-id="9bc29-289">Gibt die Typdateien ( `.ps1xml` ) an, die beim Importieren des Moduls ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-289">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="9bc29-290">Wenn Sie das Modul importieren, führt PowerShell das `Update-TypeData` Cmdlet mit den angegebenen Dateien aus.</span><span class="sxs-lookup"><span data-stu-id="9bc29-290">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="9bc29-291">Da Typdateien nicht Bereichs bezogen sind, wirken Sie sich auf alle Sitzungs Zustände in der Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="9bc29-291">Because type files aren't scoped, they affect all session states in the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-292">-Variablestoexport</span><span class="sxs-lookup"><span data-stu-id="9bc29-292">-VariablesToExport</span></span>

<span data-ttu-id="9bc29-293">Gibt die Variablen an, die das Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-293">Specifies the variables that the module exports.</span></span> <span data-ttu-id="9bc29-294">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="9bc29-294">Wildcards are permitted.</span></span>

<span data-ttu-id="9bc29-295">Sie können diesen Parameter verwenden, um die Variablen einzuschränken, die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-295">You can use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="9bc29-296">Sie kann Variablen aus der Liste der exportierten Variablen entfernen, aber keine Variablen zur Liste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-296">It can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

<span data-ttu-id="9bc29-297">Wenn Sie diesen Parameter weglassen, `New-ModuleManifest` erstellt einen **variablestoexport** -Schlüssel mit dem Wert `*` (All), was bedeutet, dass alle Variablen, die im Modul definiert sind, vom Manifest exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-297">If you omit this parameter, `New-ModuleManifest` creates a **VariablesToExport** key with a value of `*` (all), meaning that all variables defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9bc29-298">-Defaultcommandprefix</span><span class="sxs-lookup"><span data-stu-id="9bc29-298">-DefaultCommandPrefix</span></span>

<span data-ttu-id="9bc29-299">Gibt ein Präfix an, das den Substantiven aller Befehle im Modul vorangestellt wird, wenn Sie in eine Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-299">Specifies a prefix that is prepended to the nouns of all commands in the module when they're imported into a session.</span></span> <span data-ttu-id="9bc29-300">Geben Sie eine Präfixzeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="9bc29-300">Enter a prefix string.</span></span> <span data-ttu-id="9bc29-301">Präfixe verhindern Konflikte bei Befehlsnamen in der Sitzung eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9bc29-301">Prefixes prevent command name conflicts in a user's session.</span></span>

<span data-ttu-id="9bc29-302">Modul Benutzer können dieses Präfix überschreiben, indem Sie den **prefix** -Parameter des `Import-Module` Cmdlets angeben.</span><span class="sxs-lookup"><span data-stu-id="9bc29-302">Module users can override this prefix by specifying the **Prefix** parameter of the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="9bc29-303">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9bc29-303">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-304">-Rootmodule</span><span class="sxs-lookup"><span data-stu-id="9bc29-304">-RootModule</span></span>

<span data-ttu-id="9bc29-305">Gibt die primäre oder Stammdatei des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="9bc29-305">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="9bc29-306">Geben Sie den Dateinamen eines Skripts ( `.ps1` ), eines Skript Moduls ( `.psm1` ), eines Modul Manifests ( `.psd1` ), einer Assembly ( `.dll` ), einer Cmdlet-Definitions-XML-Datei ( `.cdxml` ) oder eines Workflows () ein `.xaml` .</span><span class="sxs-lookup"><span data-stu-id="9bc29-306">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest(`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="9bc29-307">Wenn das Modul importiert wird, werden die aus der Stammmodul-Datei exportierten Member in den Sitzungsstatus des Aufrufers importiert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-307">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="9bc29-308">Wenn ein Modul über eine Manifest-Datei verfügt und im **rootmodule** -Schlüssel keine Stammdatei festgelegt wurde, wird das Manifest zur primären Datei für das Modul, und das Modul wird zu einem Manifest-Modul (ModuleType = Manifest).</span><span class="sxs-lookup"><span data-stu-id="9bc29-308">If a module has a manifest file and no root file was designated in the **RootModule** key, the manifest becomes the primary file for the module, and the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="9bc29-309">Zum Exportieren von Membern aus- `.psm1` oder- `.dll` Dateien in einem Modul mit einem Manifest müssen die Namen dieser Dateien in den Werten der **rootmodule** -oder **netstedmodules** -Schlüssel im Manifest angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-309">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="9bc29-310">Andernfalls werden die Member nicht exportiert.</span><span class="sxs-lookup"><span data-stu-id="9bc29-310">Otherwise, their members aren't exported.</span></span>

> [!NOTE]
> <span data-ttu-id="9bc29-311">In PowerShell 2,0 hieß dieser Schlüssel " **moduletoprocess** ".</span><span class="sxs-lookup"><span data-stu-id="9bc29-311">In PowerShell 2.0, this key was called **ModuleToProcess** .</span></span> <span data-ttu-id="9bc29-312">Sie können den Parameternamen " **rootmodule** " oder den Alias " **moduletoprocess** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-312">You can use the **RootModule** parameter name or its **ModuleToProcess** alias.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ModuleToProcess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-313">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9bc29-313">-WhatIf</span></span>

<span data-ttu-id="9bc29-314">Zeigt, was geschieht, wenn ausgeführt wird `New-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="9bc29-314">Shows what would happen if `New-ModuleManifest` runs.</span></span> <span data-ttu-id="9bc29-315">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9bc29-315">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9bc29-316">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9bc29-316">CommonParameters</span></span>

<span data-ttu-id="9bc29-317">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9bc29-317">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9bc29-318">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9bc29-318">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9bc29-319">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="9bc29-319">INPUTS</span></span>

### <span data-ttu-id="9bc29-320">Keine</span><span class="sxs-lookup"><span data-stu-id="9bc29-320">None</span></span>

<span data-ttu-id="9bc29-321">Eingaben können nicht an dieses Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="9bc29-321">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="9bc29-322">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="9bc29-322">OUTPUTS</span></span>

### <span data-ttu-id="9bc29-323">None or System.String</span><span class="sxs-lookup"><span data-stu-id="9bc29-323">None or System.String</span></span>

<span data-ttu-id="9bc29-324">Standardmäßig `New-ModuleManifest` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9bc29-324">By default, `New-ModuleManifest` doesn't generate any output.</span></span> <span data-ttu-id="9bc29-325">Wenn Sie jedoch den **passthru** -Parameter verwenden, wird ein **System. String** -Objekt generiert, das das Modul Manifest darstellt.</span><span class="sxs-lookup"><span data-stu-id="9bc29-325">However, if you use the **PassThru** parameter, it generates a **System.String** object representing the module manifest.</span></span>

## <span data-ttu-id="9bc29-326">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="9bc29-326">NOTES</span></span>

<span data-ttu-id="9bc29-327">`New-ModuleManifest` erstellt Modul Manifest ( `.psd1` )-Dateien, die als **UTF16** codiert sind.</span><span class="sxs-lookup"><span data-stu-id="9bc29-327">`New-ModuleManifest` creates module manifest (`.psd1`) files encoded as **UTF16** .</span></span>

<span data-ttu-id="9bc29-328">Modulmanifeste sind normalerweise optional.</span><span class="sxs-lookup"><span data-stu-id="9bc29-328">Module manifests are usually optional.</span></span> <span data-ttu-id="9bc29-329">Ein Modulmanifest ist jedoch erforderlich, wenn Sie eine Assembly exportieren möchten, die im globalen Assemblycache installiert ist.</span><span class="sxs-lookup"><span data-stu-id="9bc29-329">However, a module manifest is required to export an assembly that is installed in the global assembly cache.</span></span>

<span data-ttu-id="9bc29-330">Um Dateien im Verzeichnis hinzuzufügen oder zu ändern `$pshome\Modules` , starten Sie PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="9bc29-330">To add or change files in the `$pshome\Modules` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="9bc29-331">In PowerShell 2,0 waren viele Parameter von `New-ModuleManifest` obligatorisch, auch wenn Sie in einem Modul Manifest nicht erforderlich waren.</span><span class="sxs-lookup"><span data-stu-id="9bc29-331">In PowerShell 2.0, many parameters of `New-ModuleManifest` were mandatory, even though they weren't required in a module manifest.</span></span> <span data-ttu-id="9bc29-332">Ab PowerShell 3,0 ist nur der **path** -Parameter obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="9bc29-332">Beginning in PowerShell 3.0, only the **Path** parameter is mandatory.</span></span>

<span data-ttu-id="9bc29-333">Eine Sitzung ist eine Instanz der PowerShell-Ausführungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="9bc29-333">A session is an instance of the PowerShell execution environment.</span></span> <span data-ttu-id="9bc29-334">Eine Sitzung kann mindestens einen Sitzungsstatus haben.</span><span class="sxs-lookup"><span data-stu-id="9bc29-334">A session can have one or more session states.</span></span> <span data-ttu-id="9bc29-335">Standardmäßig weist eine Sitzung nur einen globalen Sitzungsstatus auf, jedes importierte Modul verfügt jedoch über einen eigenen Sitzungsstatus.</span><span class="sxs-lookup"><span data-stu-id="9bc29-335">By default, a session has only a global session state, but each imported module has its own session state.</span></span> <span data-ttu-id="9bc29-336">Sitzungsstatus erlauben das Ausführen der Befehle in einem Modul, ohne den globalen Sitzungsstatus zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="9bc29-336">Session states allow the commands in a module to run without affecting the global session state.</span></span>

<span data-ttu-id="9bc29-337">Der Sitzungszustand des Aufrufers ist der Sitzungs Status, in den ein Modul importiert wird.</span><span class="sxs-lookup"><span data-stu-id="9bc29-337">The caller's session state is the session state into which a module is imported.</span></span> <span data-ttu-id="9bc29-338">In der Regel verweist er auf den globalen Sitzungs Status. Wenn ein Modul jedoch ein Modul importiert, ist der Aufrufer das Modul, und der Sitzungszustand des Aufrufers ist der Sitzungs Status des Moduls.</span><span class="sxs-lookup"><span data-stu-id="9bc29-338">Typically, it refers to the global session state, but when a module imports nested modules, the caller is the module and the caller's session state is the module's session state.</span></span>

## <span data-ttu-id="9bc29-339">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="9bc29-339">RELATED LINKS</span></span>

[<span data-ttu-id="9bc29-340">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="9bc29-340">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="9bc29-341">Get-Module</span><span class="sxs-lookup"><span data-stu-id="9bc29-341">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="9bc29-342">Import-Module</span><span class="sxs-lookup"><span data-stu-id="9bc29-342">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="9bc29-343">New-Module</span><span class="sxs-lookup"><span data-stu-id="9bc29-343">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="9bc29-344">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="9bc29-344">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="9bc29-345">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="9bc29-345">Test-ModuleManifest</span></span>](Test-ModuleManifest.md)

[<span data-ttu-id="9bc29-346">about_Modules</span><span class="sxs-lookup"><span data-stu-id="9bc29-346">about_Modules</span></span>](./About/about_Modules.md)
