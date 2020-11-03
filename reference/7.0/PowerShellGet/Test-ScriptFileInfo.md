---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/test-scriptfileinfo?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ScriptFileInfo
ms.openlocfilehash: 24e2ac0c7bd9652c406e05259c57181b373b75f8
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209940"
---
# <span data-ttu-id="8ff34-103">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="8ff34-103">Test-ScriptFileInfo</span></span>

## <span data-ttu-id="8ff34-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8ff34-104">SYNOPSIS</span></span>
<span data-ttu-id="8ff34-105">Überprüft einen Kommentar Block für ein Skript.</span><span class="sxs-lookup"><span data-stu-id="8ff34-105">Validates a comment block for a script.</span></span>

## <span data-ttu-id="8ff34-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8ff34-106">SYNTAX</span></span>

### <span data-ttu-id="8ff34-107">Pathparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="8ff34-107">PathParameterSet (Default)</span></span>

```
Test-ScriptFileInfo [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="8ff34-108">Literalpathparameterset</span><span class="sxs-lookup"><span data-stu-id="8ff34-108">LiteralPathParameterSet</span></span>

```
Test-ScriptFileInfo -LiteralPath <String> [<CommonParameters>]
```

## <span data-ttu-id="8ff34-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8ff34-109">DESCRIPTION</span></span>

<span data-ttu-id="8ff34-110">Das Cmdlet " **Test-scriptfileinfo** " überprüft den Kommentar Block am Anfang eines Skripts, das mit dem Cmdlet "Publish-Script" veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="8ff34-110">The **Test-ScriptFileInfo** cmdlet validates the comment block at the beginning of a script that will be published with the Publish-Script cmdlet.</span></span>
<span data-ttu-id="8ff34-111">Wenn der Kommentar Block einen Fehler aufweist, gibt dieses Cmdlet Informationen dazu zurück, wo sich der Fehler befindet oder wie er korrigiert wird.</span><span class="sxs-lookup"><span data-stu-id="8ff34-111">If the comment block has an error, this cmdlet returns information about where the error is located or how to correct it.</span></span>

## <span data-ttu-id="8ff34-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8ff34-112">EXAMPLES</span></span>

### <span data-ttu-id="8ff34-113">Beispiel 1: Testen einer Skriptdatei</span><span class="sxs-lookup"><span data-stu-id="8ff34-113">Example 1: Test a script file</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "C:\temp\temp_scripts\New-ScriptFile.ps1"
Version    Name                      Author               Description
-------    ----                      ------               -----------
1.0        New-ScriptFile            pattif               my new script file test
```

<span data-ttu-id="8ff34-114">Mit diesem Befehl wird die New-ScriptFile.ps1 Skriptdatei getestet, und die Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ff34-114">This command tests the New-ScriptFile.ps1 script file and displays the results.</span></span>
<span data-ttu-id="8ff34-115">Die Skriptdatei enthält gültige Metadaten.</span><span class="sxs-lookup"><span data-stu-id="8ff34-115">The script file includes valid metadata.</span></span>

### <span data-ttu-id="8ff34-116">Beispiel 2: Testen einer Skriptdatei mit Werten für alle Metadateneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8ff34-116">Example 2: Test a script file that has values for all metadata properties</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Test-Runbook.ps1" | Format-List *
Name                       : Test-Runbook
Path                       : D:\code\Test-Runbook.ps1
ScriptBase                 : D:\code
ReleaseNotes               : {contoso script now supports following features, Feature 1, Feature 2, Feature 3...}
Version                    : 1.0
Guid                       : eb246b19-17da-4392-8c89-7c280f69ad0e
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
Tags                       : {Tag1, Tag2, Tag3}
LicenseUri                 : https://contoso.com/License
ProjectUri                 : https://contoso.com/
IconUri                    : https://contoso.com/MyScriptIcon
ExternalModuleDependencies : ExternalModule1
RequiredScripts            : {Start-WFContosoServer, Stop-ContosoServerScript}
ExternalScriptDependencies : Stop-ContosoServerScript
Description                : Contoso Script example
RequiredModules            : {RequiredModule1, @{ ModuleName = 'RequiredModule2'; ModuleVersion = '1.0' }, @{ ModuleName = 'RequiredModule3'; RequiredVersion = '2.0' }, ExternalModule1}
ExportedCommands           : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-Workflow...}
ExportedFunctions          : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-AdvPSCmdlet}
ExportedWorkflows          : My-Workflow
```

<span data-ttu-id="8ff34-117">Dieser Befehl testet die Skriptdatei Test-Runbook.ps1 und verwendet den Pipeline-Operator, um die Ergebnisse an das Format-List-Cmdlet zu übergeben, um die Ergebnisse zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="8ff34-117">This command tests the script file Test-Runbook.ps1 and uses the pipeline operator to pass the results to the Format-List cmdlet to format the results.</span></span>

### <span data-ttu-id="8ff34-118">Beispiel 3: Testen einer Skriptdatei ohne Metadaten</span><span class="sxs-lookup"><span data-stu-id="8ff34-118">Example 3: Test a script file that has no metadata</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Hello-World.ps1"
Test-ScriptFileInfo : Script 'D:\code\Hello-World.ps1' is missing required metadata properties. Verify that the script file has Version, Description
and Author properties. You can use the Update-ScriptFileInfo or New-ScriptFileInfo cmdlet to add or update the PSScriptInfo to the script file.
At line:1 char:1
+ Test-ScriptFileInfo D:\code\Hello-World.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidArgument: (D:\code\Hello-World.ps1:String) [Test-ScriptFileInfo], ArgumentException

+ FullyQualifiedErrorId : MissingRequiredPSScriptInfoProperties,Test-ScriptFile
```

<span data-ttu-id="8ff34-119">Mit diesem Befehl wird die Skriptdatei Hello-World.ps1 getestet, der keine Metadaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8ff34-119">This command tests the script file Hello-World.ps1, which has no metadata associated with it.</span></span>

## <span data-ttu-id="8ff34-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8ff34-120">PARAMETERS</span></span>

### <span data-ttu-id="8ff34-121">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="8ff34-121">-LiteralPath</span></span>

<span data-ttu-id="8ff34-122">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="8ff34-122">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="8ff34-123">Im Gegensatz zum *path* -Parameter wird der Wert des *literalpath* -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8ff34-123">Unlike the *Path* parameter, the value of the *LiteralPath* parameter is used exactly as it is entered.</span></span>
<span data-ttu-id="8ff34-124">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="8ff34-124">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="8ff34-125">Wenn der Pfad Escapezeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="8ff34-125">If the path includes escape characters, enclose them in single quotation marks.</span></span>
<span data-ttu-id="8ff34-126">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="8ff34-126">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8ff34-127">-Path</span><span class="sxs-lookup"><span data-stu-id="8ff34-127">-Path</span></span>

<span data-ttu-id="8ff34-128">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="8ff34-128">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="8ff34-129">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8ff34-129">Wildcards are permitted.</span></span>
<span data-ttu-id="8ff34-130">Der Standardspeicherort ist das aktuelle Verzeichnis (.).</span><span class="sxs-lookup"><span data-stu-id="8ff34-130">The default location is the current directory (.).</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="8ff34-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8ff34-131">CommonParameters</span></span>

<span data-ttu-id="8ff34-132">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8ff34-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8ff34-133">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8ff34-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8ff34-134">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8ff34-134">INPUTS</span></span>

### <span data-ttu-id="8ff34-135">System.String</span><span class="sxs-lookup"><span data-stu-id="8ff34-135">System.String</span></span>

## <span data-ttu-id="8ff34-136">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8ff34-136">OUTPUTS</span></span>

### <span data-ttu-id="8ff34-137">System.Object</span><span class="sxs-lookup"><span data-stu-id="8ff34-137">System.Object</span></span>

## <span data-ttu-id="8ff34-138">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8ff34-138">NOTES</span></span>

## <span data-ttu-id="8ff34-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8ff34-139">RELATED LINKS</span></span>

[<span data-ttu-id="8ff34-140">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="8ff34-140">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="8ff34-141">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="8ff34-141">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="8ff34-142">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="8ff34-142">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
