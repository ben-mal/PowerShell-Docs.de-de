---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/test-scriptfileinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ScriptFileInfo
ms.openlocfilehash: 35de1c9b7c975a68ac2f5a01c97a78eeef6d1184
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596354"
---
# <span data-ttu-id="bfa90-102">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="bfa90-102">Test-ScriptFileInfo</span></span>

## <span data-ttu-id="bfa90-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bfa90-103">SYNOPSIS</span></span>
<span data-ttu-id="bfa90-104">Überprüft einen Kommentar Block für ein Skript.</span><span class="sxs-lookup"><span data-stu-id="bfa90-104">Validates a comment block for a script.</span></span>

## <span data-ttu-id="bfa90-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bfa90-105">SYNTAX</span></span>

### <span data-ttu-id="bfa90-106">Pathparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="bfa90-106">PathParameterSet (Default)</span></span>

```
Test-ScriptFileInfo [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="bfa90-107">Literalpathparameterset</span><span class="sxs-lookup"><span data-stu-id="bfa90-107">LiteralPathParameterSet</span></span>

```
Test-ScriptFileInfo -LiteralPath <String> [<CommonParameters>]
```

## <span data-ttu-id="bfa90-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bfa90-108">DESCRIPTION</span></span>

<span data-ttu-id="bfa90-109">Das Cmdlet " **Test-scriptfileinfo** " überprüft den Kommentar Block am Anfang eines Skripts, das mit dem Cmdlet "Publish-Script" veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="bfa90-109">The **Test-ScriptFileInfo** cmdlet validates the comment block at the beginning of a script that will be published with the Publish-Script cmdlet.</span></span>
<span data-ttu-id="bfa90-110">Wenn der Kommentar Block einen Fehler aufweist, gibt dieses Cmdlet Informationen dazu zurück, wo sich der Fehler befindet oder wie er korrigiert wird.</span><span class="sxs-lookup"><span data-stu-id="bfa90-110">If the comment block has an error, this cmdlet returns information about where the error is located or how to correct it.</span></span>

## <span data-ttu-id="bfa90-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bfa90-111">EXAMPLES</span></span>

### <span data-ttu-id="bfa90-112">Beispiel 1: Testen einer Skriptdatei</span><span class="sxs-lookup"><span data-stu-id="bfa90-112">Example 1: Test a script file</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "C:\temp\temp_scripts\New-ScriptFile.ps1"
Version    Name                      Author               Description
-------    ----                      ------               -----------
1.0        New-ScriptFile            pattif               my new script file test
```

<span data-ttu-id="bfa90-113">Mit diesem Befehl wird die New-ScriptFile.ps1 Skriptdatei getestet, und die Ergebnisse werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bfa90-113">This command tests the New-ScriptFile.ps1 script file and displays the results.</span></span>
<span data-ttu-id="bfa90-114">Die Skriptdatei enthält gültige Metadaten.</span><span class="sxs-lookup"><span data-stu-id="bfa90-114">The script file includes valid metadata.</span></span>

### <span data-ttu-id="bfa90-115">Beispiel 2: Testen einer Skriptdatei mit Werten für alle Metadateneigenschaften</span><span class="sxs-lookup"><span data-stu-id="bfa90-115">Example 2: Test a script file that has values for all metadata properties</span></span>

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

<span data-ttu-id="bfa90-116">Dieser Befehl testet die Skriptdatei Test-Runbook.ps1 und verwendet den Pipeline-Operator, um die Ergebnisse an das Format-List-Cmdlet zu übergeben, um die Ergebnisse zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="bfa90-116">This command tests the script file Test-Runbook.ps1 and uses the pipeline operator to pass the results to the Format-List cmdlet to format the results.</span></span>

### <span data-ttu-id="bfa90-117">Beispiel 3: Testen einer Skriptdatei ohne Metadaten</span><span class="sxs-lookup"><span data-stu-id="bfa90-117">Example 3: Test a script file that has no metadata</span></span>

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

<span data-ttu-id="bfa90-118">Mit diesem Befehl wird die Skriptdatei Hello-World.ps1 getestet, der keine Metadaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bfa90-118">This command tests the script file Hello-World.ps1, which has no metadata associated with it.</span></span>

## <span data-ttu-id="bfa90-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bfa90-119">PARAMETERS</span></span>

### <span data-ttu-id="bfa90-120">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="bfa90-120">-LiteralPath</span></span>

<span data-ttu-id="bfa90-121">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="bfa90-121">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="bfa90-122">Im Gegensatz zum *path* -Parameter wird der Wert des *literalpath* -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="bfa90-122">Unlike the *Path* parameter, the value of the *LiteralPath* parameter is used exactly as it is entered.</span></span>
<span data-ttu-id="bfa90-123">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="bfa90-123">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="bfa90-124">Wenn der Pfad Escapezeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="bfa90-124">If the path includes escape characters, enclose them in single quotation marks.</span></span>
<span data-ttu-id="bfa90-125">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="bfa90-125">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="bfa90-126">-Path</span><span class="sxs-lookup"><span data-stu-id="bfa90-126">-Path</span></span>

<span data-ttu-id="bfa90-127">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="bfa90-127">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="bfa90-128">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bfa90-128">Wildcards are permitted.</span></span>
<span data-ttu-id="bfa90-129">Der Standardspeicherort ist das aktuelle Verzeichnis (.).</span><span class="sxs-lookup"><span data-stu-id="bfa90-129">The default location is the current directory (.).</span></span>

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

### <span data-ttu-id="bfa90-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bfa90-130">CommonParameters</span></span>

<span data-ttu-id="bfa90-131">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bfa90-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bfa90-132">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bfa90-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bfa90-133">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bfa90-133">INPUTS</span></span>

### <span data-ttu-id="bfa90-134">System.String</span><span class="sxs-lookup"><span data-stu-id="bfa90-134">System.String</span></span>

## <span data-ttu-id="bfa90-135">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bfa90-135">OUTPUTS</span></span>

### <span data-ttu-id="bfa90-136">System.Object</span><span class="sxs-lookup"><span data-stu-id="bfa90-136">System.Object</span></span>

## <span data-ttu-id="bfa90-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bfa90-137">NOTES</span></span>

## <span data-ttu-id="bfa90-138">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bfa90-138">RELATED LINKS</span></span>

[<span data-ttu-id="bfa90-139">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="bfa90-139">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="bfa90-140">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="bfa90-140">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="bfa90-141">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="bfa90-141">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)

