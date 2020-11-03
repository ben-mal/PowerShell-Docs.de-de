---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSRoleCapabilityFile
ms.openlocfilehash: 274f860f86918b7d4b7cb621afde836edbb42fa5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217455"
---
# <span data-ttu-id="2e216-103">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="2e216-103">New-PSRoleCapabilityFile</span></span>

## <span data-ttu-id="2e216-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2e216-104">SYNOPSIS</span></span>
<span data-ttu-id="2e216-105">Erstellt eine Datei, die einen Satz von Funktionen definiert, die durch eine Sitzungs Konfiguration verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2e216-105">Creates a file that defines a set of capabilities to be exposed through a session configuration.</span></span>

## <span data-ttu-id="2e216-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e216-106">SYNTAX</span></span>

```
New-PSRoleCapabilityFile [-Path] <String> [-Guid <Guid>] [-Author <String>] [-Description <String>]
 [-CompanyName <String>] [-Copyright <String>] [-ModulesToImport <Object[]>] [-VisibleAliases <String[]>]
 [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>] [-VisibleExternalCommands <String[]>]
 [-VisibleProviders <String[]>] [-ScriptsToProcess <String[]>] [-AliasDefinitions <IDictionary[]>]
 [-FunctionDefinitions <IDictionary[]>] [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="2e216-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2e216-107">DESCRIPTION</span></span>

<span data-ttu-id="2e216-108">Mit dem- `New-PSRoleCapabilityFile` Cmdlet wird eine Datei erstellt, die eine Reihe von Benutzer Funktionen definiert, die durch Sitzungs Konfigurationsdateien verfügbar gemacht werden können.</span><span class="sxs-lookup"><span data-stu-id="2e216-108">The `New-PSRoleCapabilityFile` cmdlet creates a file that defines a set of user capabilities that can be exposed through session configuration files.</span></span> <span data-ttu-id="2e216-109">Dazu gehört auch die Bestimmung, welche Cmdlets, Funktionen und Skripts für Benutzer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2e216-109">This includes determining which cmdlets, functions, and scripts are available to users.</span></span> <span data-ttu-id="2e216-110">Die Funktions Datei ist eine lesbare Textdatei, die eine Hash Tabelle mit Sitzungs Konfigurations Eigenschaften und-Werten enthält.</span><span class="sxs-lookup"><span data-stu-id="2e216-110">The capability file is a human-readable text file that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="2e216-111">Die Datei weist die Dateinamenerweiterung. psrc auf und kann von mehr als einer Sitzungs Konfiguration verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e216-111">The file has a .psrc file name extension, and can be used by more than one session configuration.</span></span>

<span data-ttu-id="2e216-112">Alle Parameter von `New-PSRoleCapabilityFile` sind mit Ausnahme des **path** -Parameters optional, der den Dateipfad für die Datei angibt.</span><span class="sxs-lookup"><span data-stu-id="2e216-112">All the parameters of `New-PSRoleCapabilityFile` are optional except for the **Path** parameter, which specifies the file path for the file.</span></span> <span data-ttu-id="2e216-113">Wenn Sie beim Ausführen des Cmdlets keinen Parameter einschließen, wird der entsprechende Schlüssel in der Sitzungs Konfigurationsdatei auskommentiert, es sei denn, dies ist in der Parameter Beschreibung angegeben.</span><span class="sxs-lookup"><span data-stu-id="2e216-113">If you do not include a parameter when you run the cmdlet, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span> <span data-ttu-id="2e216-114">Wenn Sie z. b. keinen **assemblyoload** -Parameter einschließen, wird dieser Abschnitt der Sitzungs Konfigurationsdatei auskommentiert.</span><span class="sxs-lookup"><span data-stu-id="2e216-114">For example, if you do not include the **AssembliesToLoad** parameter then that section of the session configuration file is commented out.</span></span>

<span data-ttu-id="2e216-115">Wenn Sie die Rollen Funktions Datei in einer Sitzungs Konfiguration verwenden möchten, platzieren Sie die Datei zunächst in einem Unterordner **rolecapability** eines gültigen PowerShell-Modul Ordners.</span><span class="sxs-lookup"><span data-stu-id="2e216-115">To use the role capability file in a session configuration, first place the file in a **RoleCapabilities** subfolder of a valid PowerShell module folder.</span></span> <span data-ttu-id="2e216-116">Verweisen Sie dann im Feld " **roledefinitions** " in einer PowerShell-Sitzungs Konfigurationsdatei (PSSC-Datei) mit dem Namen auf die Datei.</span><span class="sxs-lookup"><span data-stu-id="2e216-116">Then reference the file by name in the **RoleDefinitions** field in a PowerShell Session Configuration (.pssc) file.</span></span>

<span data-ttu-id="2e216-117">Dieses Cmdlet wurde in Windows PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2e216-117">This cmdlet was introduced in Windows PowerShell 5.0.</span></span>

## <span data-ttu-id="2e216-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2e216-118">EXAMPLES</span></span>

### <span data-ttu-id="2e216-119">Beispiel 1: Erstellen einer leeren Rollen Funktions Datei</span><span class="sxs-lookup"><span data-stu-id="2e216-119">Example 1: Create a blank role capability file</span></span>

<span data-ttu-id="2e216-120">In diesem Beispiel wird eine neue Rollen Funktions Datei erstellt, in der die Standardwerte (leer) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e216-120">This example creates a new role capability file that uses the default (blank) values.</span></span> <span data-ttu-id="2e216-121">Die Datei kann später in einem Text-Editor bearbeitet werden, um diese Konfigurationseinstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2e216-121">The file can later be edited in a text editor to change these configuration settings.</span></span>

```powershell
New-PSRoleCapabilityFile -Path ".\ExampleFile.psrc"
```

### <span data-ttu-id="2e216-122">Beispiel 2: Erstellen einer Rollen Funktions Datei, die Benutzern das Neustarten von Diensten und VDI-Computern ermöglicht</span><span class="sxs-lookup"><span data-stu-id="2e216-122">Example 2: Create a role capability file allowing users to restart services and any VDI computer</span></span>

<span data-ttu-id="2e216-123">In diesem Beispiel wird eine Beispiel Rollen Funktions Datei erstellt, mit der Benutzerdienste und Computer, die einem bestimmten Namensmuster entsprechen, neu starten können.</span><span class="sxs-lookup"><span data-stu-id="2e216-123">This example creates a sample role capability file that enables users to restart services and computers that match a specific name pattern.</span></span> <span data-ttu-id="2e216-124">Die namens Filterung wird durch Festlegen des **validatepattern** -Parameters auf den regulären Ausdruck definiert `VDI\d+` .</span><span class="sxs-lookup"><span data-stu-id="2e216-124">Name filtering is defined by setting the **ValidatePattern** parameter to the regular expression `VDI\d+`.</span></span>

```powershell
$roleParameters = @{
    Path = ".\Maintenance.psrc"
    Author = "User01"
    CompanyName = "Fabrikam Corporation"
    Description = "This role enables users to restart any service and restart any VDI computer."
    ModulesToImport = "Microsoft.PowerShell.Core"
    VisibleCmdlets = "Restart-Service", @{
                      Name = "Restart-Computer"
                      Parameters = @{ Name = "ComputerName"; ValidatePattern = "VDI\d+" }
    }
}
New-PSRoleCapabilityFile @roleParameters
```

## <span data-ttu-id="2e216-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e216-125">PARAMETERS</span></span>

### <span data-ttu-id="2e216-126">-Aliasdefinitionen</span><span class="sxs-lookup"><span data-stu-id="2e216-126">-AliasDefinitions</span></span>

<span data-ttu-id="2e216-127">Fügt die angegebenen Aliase zu Sitzungen hinzu, die die Rollen Funktions Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e216-127">Adds the specified aliases to sessions that use the role capability file.</span></span> <span data-ttu-id="2e216-128">Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:</span><span class="sxs-lookup"><span data-stu-id="2e216-128">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="2e216-129">Name.</span><span class="sxs-lookup"><span data-stu-id="2e216-129">Name.</span></span> <span data-ttu-id="2e216-130">Name des Alias.</span><span class="sxs-lookup"><span data-stu-id="2e216-130">Name of the alias.</span></span> <span data-ttu-id="2e216-131">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e216-131">This key is required.</span></span>
- <span data-ttu-id="2e216-132">Wert.</span><span class="sxs-lookup"><span data-stu-id="2e216-132">Value.</span></span> <span data-ttu-id="2e216-133">Der Befehl, den der Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="2e216-133">The command that the alias represents.</span></span> <span data-ttu-id="2e216-134">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e216-134">This key is required.</span></span>
- <span data-ttu-id="2e216-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e216-135">Description.</span></span> <span data-ttu-id="2e216-136">Eine Textzeichenfolge, die den Alias beschreibt.</span><span class="sxs-lookup"><span data-stu-id="2e216-136">A text string that describes the alias.</span></span> <span data-ttu-id="2e216-137">Dieser Schlüssel ist optional.</span><span class="sxs-lookup"><span data-stu-id="2e216-137">This key is optional.</span></span>
- <span data-ttu-id="2e216-138">Optionen.</span><span class="sxs-lookup"><span data-stu-id="2e216-138">Options.</span></span> <span data-ttu-id="2e216-139">Aliasoptionen.</span><span class="sxs-lookup"><span data-stu-id="2e216-139">Alias options.</span></span> <span data-ttu-id="2e216-140">Dieser Schlüssel ist optional.</span><span class="sxs-lookup"><span data-stu-id="2e216-140">This key is optional.</span></span> <span data-ttu-id="2e216-141">Der Standardwert lautet „Keine“.</span><span class="sxs-lookup"><span data-stu-id="2e216-141">The default value is None.</span></span> <span data-ttu-id="2e216-142">Die zulässigen Werte für diesen Parameter lauten: None, Read Only, Constant, private oder allscope.</span><span class="sxs-lookup"><span data-stu-id="2e216-142">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="2e216-143">Beispiel: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span><span class="sxs-lookup"><span data-stu-id="2e216-143">For example: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e216-144">-Assemliestoload</span><span class="sxs-lookup"><span data-stu-id="2e216-144">-AssembliesToLoad</span></span>

<span data-ttu-id="2e216-145">Gibt die Assemblys an, die in die Sitzungen geladen werden sollen, die die Rollen Funktions Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e216-145">Specifies the assemblies to load into the sessions that use the role capability file.</span></span>

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

### <span data-ttu-id="2e216-146">-Autor</span><span class="sxs-lookup"><span data-stu-id="2e216-146">-Author</span></span>

<span data-ttu-id="2e216-147">Gibt den Benutzer an, der die Rollen Funktions Datei erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="2e216-147">Specifies the user that created the role capability file.</span></span>

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

### <span data-ttu-id="2e216-148">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="2e216-148">-CompanyName</span></span>

<span data-ttu-id="2e216-149">Identifiziert das Unternehmen, das die Rollen Funktions Datei erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="2e216-149">Identifies the company that created the role capability file.</span></span>
<span data-ttu-id="2e216-150">Der Standardwert ist Unknown (Unbekannt).</span><span class="sxs-lookup"><span data-stu-id="2e216-150">The default value is Unknown.</span></span>

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

### <span data-ttu-id="2e216-151">-Copyright</span><span class="sxs-lookup"><span data-stu-id="2e216-151">-Copyright</span></span>

<span data-ttu-id="2e216-152">Gibt ein Copyright für die Rollen Funktions Datei an.</span><span class="sxs-lookup"><span data-stu-id="2e216-152">Specifies a copyright for the role capability file.</span></span> <span data-ttu-id="2e216-153">Wenn Sie diesen Parameter weglassen, `New-PSRoleCapabilityFile` generiert eine Copyright Anweisung mit dem Wert des **Author** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="2e216-153">If you omit this parameter, `New-PSRoleCapabilityFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="2e216-154">-Description</span><span class="sxs-lookup"><span data-stu-id="2e216-154">-Description</span></span>

<span data-ttu-id="2e216-155">Gibt eine Beschreibung für die Rollen Funktions Datei an.</span><span class="sxs-lookup"><span data-stu-id="2e216-155">Specifies a description for the role capability file.</span></span>

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

### <span data-ttu-id="2e216-156">-Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="2e216-156">-EnvironmentVariables</span></span>

<span data-ttu-id="2e216-157">Gibt die Umgebungsvariablen für Sitzungen an, die diese Rollen Funktions Datei verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="2e216-157">Specifies the environment variables for sessions that expose this role capability file.</span></span> <span data-ttu-id="2e216-158">Geben Sie eine Hashtabelle ein, in der die Schlüssel die Namen der Umgebungsvariablen und die Werte die Werte der Umgebungsvariablen sind.</span><span class="sxs-lookup"><span data-stu-id="2e216-158">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="2e216-159">Beispiel: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span><span class="sxs-lookup"><span data-stu-id="2e216-159">For example: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e216-160">-Formatstoprocess</span><span class="sxs-lookup"><span data-stu-id="2e216-160">-FormatsToProcess</span></span>

<span data-ttu-id="2e216-161">Gibt die Formatierungs Dateien (. ps1xml) an, die in Sitzungen ausgeführt werden, in denen die Rollen Funktions Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e216-161">Specifies the formatting files (.ps1xml) that run in sessions that use the role capability file.</span></span> <span data-ttu-id="2e216-162">Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad der Formatierungs Dateien sein.</span><span class="sxs-lookup"><span data-stu-id="2e216-162">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

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

### <span data-ttu-id="2e216-163">-Functiondefinitions</span><span class="sxs-lookup"><span data-stu-id="2e216-163">-FunctionDefinitions</span></span>

<span data-ttu-id="2e216-164">Fügt den Sitzungen, die die Rollen Funktion verfügbar machen, die angegebenen Funktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="2e216-164">Adds the specified functions to sessions that expose the role capability.</span></span> <span data-ttu-id="2e216-165">Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:</span><span class="sxs-lookup"><span data-stu-id="2e216-165">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="2e216-166">Name.</span><span class="sxs-lookup"><span data-stu-id="2e216-166">Name.</span></span> <span data-ttu-id="2e216-167">Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="2e216-167">Name of the function.</span></span> <span data-ttu-id="2e216-168">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e216-168">This key is required.</span></span>
- <span data-ttu-id="2e216-169">ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="2e216-169">ScriptBlock.</span></span> <span data-ttu-id="2e216-170">Funktionstext.</span><span class="sxs-lookup"><span data-stu-id="2e216-170">Function body.</span></span> <span data-ttu-id="2e216-171">Geben Sie einen Skriptblock ein.</span><span class="sxs-lookup"><span data-stu-id="2e216-171">Enter a script block.</span></span> <span data-ttu-id="2e216-172">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e216-172">This key is required.</span></span>
- <span data-ttu-id="2e216-173">Optionen.</span><span class="sxs-lookup"><span data-stu-id="2e216-173">Options.</span></span> <span data-ttu-id="2e216-174">Funktionsoptionen.</span><span class="sxs-lookup"><span data-stu-id="2e216-174">Function options.</span></span> <span data-ttu-id="2e216-175">Dieser Schlüssel ist optional.</span><span class="sxs-lookup"><span data-stu-id="2e216-175">This key is optional.</span></span> <span data-ttu-id="2e216-176">Der Standardwert lautet „Keine“.</span><span class="sxs-lookup"><span data-stu-id="2e216-176">The default value is None.</span></span> <span data-ttu-id="2e216-177">Die zulässigen Werte für diesen Parameter sind "None", "Read only", "Constant", "private" oder "allscope".</span><span class="sxs-lookup"><span data-stu-id="2e216-177">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="2e216-178">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2e216-178">For example:</span></span>

`@{Name="Get-PowerShellProcess";ScriptBlock={Get-Process PowerShell};Options="AllScope"}`

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e216-179">-GUID</span><span class="sxs-lookup"><span data-stu-id="2e216-179">-Guid</span></span>

<span data-ttu-id="2e216-180">Gibt einen eindeutigen Bezeichner für die Rollen Funktions Datei an.</span><span class="sxs-lookup"><span data-stu-id="2e216-180">Specifies a unique identifier for the role capability file.</span></span> <span data-ttu-id="2e216-181">Wenn Sie diesen Parameter weglassen, `New-PSRoleCapabilityFile` generiert eine GUID für die Datei.</span><span class="sxs-lookup"><span data-stu-id="2e216-181">If you omit this parameter, `New-PSRoleCapabilityFile` generates a GUID for the file.</span></span> <span data-ttu-id="2e216-182">Geben Sie ein, um eine neue GUID in PowerShell zu erstellen `[guid]::NewGuid()` .</span><span class="sxs-lookup"><span data-stu-id="2e216-182">To create a new GUID in PowerShell, type `[guid]::NewGuid()`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e216-183">-Modulestoimport</span><span class="sxs-lookup"><span data-stu-id="2e216-183">-ModulesToImport</span></span>

<span data-ttu-id="2e216-184">Gibt die Module an, die automatisch in Sitzungen importiert werden, in denen die Rollen Funktions Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e216-184">Specifies the modules that are automatically imported into sessions that use the role capability file.</span></span> <span data-ttu-id="2e216-185">Standardmäßig sind alle Befehle in aufgelisteten Modulen sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2e216-185">By default, all the commands in listed modules are visible.</span></span> <span data-ttu-id="2e216-186">Bei Verwendung mit **visiblecmdlets** oder **visiblefunctions** können die von den angegebenen Modulen sichtbaren Befehle eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="2e216-186">When used with **VisibleCmdlets** or **VisibleFunctions** , the commands visible from the specified modules can be restricted.</span></span>

<span data-ttu-id="2e216-187">Jedes Modul, das im Wert dieses Parameters verwendet wird, kann durch eine Zeichenfolge oder eine Hash Tabelle dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2e216-187">Each module used in the value of this parameter can be represented by a string or by a hash table.</span></span> <span data-ttu-id="2e216-188">Eine Modul Zeichenfolge besteht nur aus dem Namen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="2e216-188">A module string consists only of the name of the module.</span></span> <span data-ttu-id="2e216-189">Eine Modul Hash Tabelle kann die Schlüssel " **ModuleName** ", " **moduleversion** " und " **GUID** " enthalten.</span><span class="sxs-lookup"><span data-stu-id="2e216-189">A module hash table can include **ModuleName** , **ModuleVersion** , and **GUID** keys.</span></span> <span data-ttu-id="2e216-190">Nur der **ModuleName** -Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e216-190">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="2e216-191">Beispielsweise besteht der folgende Wert aus einer Zeichenfolge und einer Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="2e216-191">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="2e216-192">Jede Kombination aus Zeichenfolgen und Hashtabellen, in beliebiger Reihenfolge, ist gültig.</span><span class="sxs-lookup"><span data-stu-id="2e216-192">Any combination of strings and hash tables, in any order, is valid.</span></span>

`"TroubleshootingPack", @{ModuleName="PSDiagnostics"; ModuleVersion="1.0.0.0";GUID="c61d6278-02a3-4618-ae37-a524d40a7f44"}`

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

### <span data-ttu-id="2e216-193">-Path</span><span class="sxs-lookup"><span data-stu-id="2e216-193">-Path</span></span>

<span data-ttu-id="2e216-194">Gibt den Pfad und den Dateinamen der Rollen Funktions Datei an.</span><span class="sxs-lookup"><span data-stu-id="2e216-194">Specifies the path and filename of the role capability file.</span></span> <span data-ttu-id="2e216-195">Die Datei muss eine Datei `.psrc` Namen Erweiterung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2e216-195">The file must have a `.psrc` filename extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e216-196">-Scriptstoprocess</span><span class="sxs-lookup"><span data-stu-id="2e216-196">-ScriptsToProcess</span></span>

<span data-ttu-id="2e216-197">Gibt Skripts an, die Sitzungen hinzugefügt werden, die die Rollen Funktions Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e216-197">Specifies scripts to add to sessions that use the role capability file.</span></span> <span data-ttu-id="2e216-198">Geben Sie den Pfad und die Dateinamen der Skripts ein.</span><span class="sxs-lookup"><span data-stu-id="2e216-198">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="2e216-199">Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad der Skript Dateinamen sein.</span><span class="sxs-lookup"><span data-stu-id="2e216-199">The value of this parameter must be a full or absolute path of the script file names.</span></span>

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

### <span data-ttu-id="2e216-200">-Typestoprocess</span><span class="sxs-lookup"><span data-stu-id="2e216-200">-TypesToProcess</span></span>

<span data-ttu-id="2e216-201">Gibt Typdateien (. ps1xml) an, die zu Sitzungen hinzugefügt werden sollen, die die Rollen Funktions Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e216-201">Specifies type files (.ps1xml) to add to sessions that use the role capability file.</span></span> <span data-ttu-id="2e216-202">Geben Sie die typdateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="2e216-202">Enter the type filenames.</span></span> <span data-ttu-id="2e216-203">Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad der typdateinamen sein.</span><span class="sxs-lookup"><span data-stu-id="2e216-203">The value of this parameter must be a full or absolute path of the type filenames.</span></span>

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

### <span data-ttu-id="2e216-204">-Variabledefinitionen</span><span class="sxs-lookup"><span data-stu-id="2e216-204">-VariableDefinitions</span></span>

<span data-ttu-id="2e216-205">Gibt Variablen an, die zu Sitzungen hinzugefügt werden, die die Rollen Funktions Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e216-205">Specifies variables to add to sessions that use the role capability file.</span></span> <span data-ttu-id="2e216-206">Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:</span><span class="sxs-lookup"><span data-stu-id="2e216-206">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="2e216-207">Name.</span><span class="sxs-lookup"><span data-stu-id="2e216-207">Name.</span></span> <span data-ttu-id="2e216-208">Name der Variable.</span><span class="sxs-lookup"><span data-stu-id="2e216-208">Name of the variable.</span></span> <span data-ttu-id="2e216-209">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e216-209">This key is required.</span></span>
- <span data-ttu-id="2e216-210">Wert.</span><span class="sxs-lookup"><span data-stu-id="2e216-210">Value.</span></span> <span data-ttu-id="2e216-211">Variablenwert.</span><span class="sxs-lookup"><span data-stu-id="2e216-211">Variable value.</span></span> <span data-ttu-id="2e216-212">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2e216-212">This key is required.</span></span>
- <span data-ttu-id="2e216-213">Optionen.</span><span class="sxs-lookup"><span data-stu-id="2e216-213">Options.</span></span> <span data-ttu-id="2e216-214">Variablenoptionen.</span><span class="sxs-lookup"><span data-stu-id="2e216-214">Variable options.</span></span> <span data-ttu-id="2e216-215">Dieser Schlüssel ist optional.</span><span class="sxs-lookup"><span data-stu-id="2e216-215">This key is optional.</span></span> <span data-ttu-id="2e216-216">Der Standardwert lautet „Keine“.</span><span class="sxs-lookup"><span data-stu-id="2e216-216">The default value is None.</span></span> <span data-ttu-id="2e216-217">Die zulässigen Werte für diesen Parameter sind "None", "Read only", "Constant", "private" oder "allscope".</span><span class="sxs-lookup"><span data-stu-id="2e216-217">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="2e216-218">Beispiel: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span><span class="sxs-lookup"><span data-stu-id="2e216-218">For example: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span></span>

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

### <span data-ttu-id="2e216-219">-Visiblealiases</span><span class="sxs-lookup"><span data-stu-id="2e216-219">-VisibleAliases</span></span>

<span data-ttu-id="2e216-220">Schränkt die Aliase in der Sitzung auf die Aliase ein, die im Wert dieses Parameters angegeben sind, sowie auf alle Aliase, die Sie im Parameter **Aliasdefinition** definieren.</span><span class="sxs-lookup"><span data-stu-id="2e216-220">Limits the aliases in the session to those aliases specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="2e216-221">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e216-221">Wildcard characters are supported.</span></span>
<span data-ttu-id="2e216-222">Standardmäßig sind alle Aliase, die von der PowerShell-Engine definiert werden, und alle Aliase, die von Modulen exportiert werden, in der Sitzung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2e216-222">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="2e216-223">Um z. b. die verfügbaren Aliase auf GM und GCM einzuschränken, verwenden Sie die folgende Syntax: `VisibleAliases="gcm", "gp"`</span><span class="sxs-lookup"><span data-stu-id="2e216-223">For example, to limit the available aliases to gm and gcm use this syntax: `VisibleAliases="gcm", "gp"`</span></span>

<span data-ttu-id="2e216-224">Wenn ein beliebiger **sichtbarer** Parameter in der Rollen Funktions Datei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2e216-224">When any **Visible** parameter is included in the role capability file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="2e216-225">-Visiblecmdlets</span><span class="sxs-lookup"><span data-stu-id="2e216-225">-VisibleCmdlets</span></span>

<span data-ttu-id="2e216-226">Beschränkt die Cmdlets in der Sitzung auf jene, die im Wert dieses Parameters angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="2e216-226">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="2e216-227">Platzhalter Zeichen und qualifizierte Modulnamen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e216-227">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="2e216-228">Standardmäßig sind alle Cmdlets, die die Module in der Sitzung exportieren, in der Sitzung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2e216-228">By default, all cmdlets that the modules in the session export are visible in the session.</span></span> <span data-ttu-id="2e216-229">Verwenden Sie die **SessionType** - und **ModulesToImport** -Parameter, um zu bestimmen, welche Module und Snap-Ins in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e216-229">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="2e216-230">Wenn das Cmdlet von keinem Modul in **modulestoimport** verfügbar gemacht wird, wird `New-PSRoleCapabilityFile` versucht, das entsprechende Modul zu laden.</span><span class="sxs-lookup"><span data-stu-id="2e216-230">If no modules in **ModulesToImport** expose the cmdlet, `New-PSRoleCapabilityFile` tries to load the appropriate module.</span></span>

<span data-ttu-id="2e216-231">Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2e216-231">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="2e216-232">-Visibleexternalcommands</span><span class="sxs-lookup"><span data-stu-id="2e216-232">-VisibleExternalCommands</span></span>

<span data-ttu-id="2e216-233">Schränkt die externen Binärdateien, Skripts und Befehle, die in der Sitzung ausgeführt werden können, auf die Werte ein, die im Wert dieses Parameters angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2e216-233">Limits the external binaries, scripts and commands that can be executed in the session to those specified in the value of this parameter.</span></span>

<span data-ttu-id="2e216-234">Standardmäßig sind in dieser Sitzung keine externen Befehle sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2e216-234">By default, no external commands are visible in this session.</span></span>

<span data-ttu-id="2e216-235">Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2e216-235">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="2e216-236">-Visiblefunctions</span><span class="sxs-lookup"><span data-stu-id="2e216-236">-VisibleFunctions</span></span>

<span data-ttu-id="2e216-237">Schränkt die Funktionen in der Sitzung auf jene ein, die im Wert dieses Parameters angegeben sind, sowie auf alle Funktionen, die Sie im **functiondefinitions** -Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="2e216-237">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinitions** parameter.</span></span> <span data-ttu-id="2e216-238">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e216-238">Wildcard characters are supported.</span></span>

<span data-ttu-id="2e216-239">Standardmäßig sind alle Funktionen, die von Modulen in der Sitzung exportiert werden, in dieser Sitzung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2e216-239">By default, all functions exported by modules in the session are visible in that session.</span></span> <span data-ttu-id="2e216-240">Verwenden Sie die Parameter **SessionType** und **modulestoimport** , um zu bestimmen, welche Module in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e216-240">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="2e216-241">Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2e216-241">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="2e216-242">-Visibleproviders</span><span class="sxs-lookup"><span data-stu-id="2e216-242">-VisibleProviders</span></span>

<span data-ttu-id="2e216-243">Schränkt die PowerShell-Anbieter in der Sitzung auf die Werte ein, die im Wert dieses Parameters angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="2e216-243">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="2e216-244">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e216-244">Wildcard characters are supported.</span></span>

<span data-ttu-id="2e216-245">Standardmäßig sind alle Anbieter, die von einem Modul in der Sitzung exportiert werden, in der Sitzung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="2e216-245">By default, all providers exported by a module in the session are visible in the session.</span></span> <span data-ttu-id="2e216-246">Verwenden Sie die Parameter **SessionType** und **modulestoimport** , um zu bestimmen, welche Module in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e216-246">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="2e216-247">Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="2e216-247">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="2e216-248">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2e216-248">CommonParameters</span></span>

<span data-ttu-id="2e216-249">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2e216-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e216-250">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2e216-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e216-251">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2e216-251">INPUTS</span></span>

## <span data-ttu-id="2e216-252">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2e216-252">OUTPUTS</span></span>

## <span data-ttu-id="2e216-253">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2e216-253">NOTES</span></span>

## <span data-ttu-id="2e216-254">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2e216-254">RELATED LINKS</span></span>

[<span data-ttu-id="2e216-255">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="2e216-255">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="2e216-256">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="2e216-256">Get-PSSessionCapability</span></span>](Get-PSSessionCapability.md)

