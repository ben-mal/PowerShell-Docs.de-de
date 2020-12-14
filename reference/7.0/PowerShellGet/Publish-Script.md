---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: 26fc71546c03fbb49bf8824f6779e6b6371daa0e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891140"
---
# <span data-ttu-id="894b5-103">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="894b5-103">Publish-Script</span></span>

## <span data-ttu-id="894b5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="894b5-104">SYNOPSIS</span></span>
<span data-ttu-id="894b5-105">Veröffentlicht ein Skript.</span><span class="sxs-lookup"><span data-stu-id="894b5-105">Publishes a script.</span></span>

## <span data-ttu-id="894b5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="894b5-106">SYNTAX</span></span>

### <span data-ttu-id="894b5-107">Pathparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="894b5-107">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="894b5-108">Literalpathparameterset</span><span class="sxs-lookup"><span data-stu-id="894b5-108">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="894b5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="894b5-109">DESCRIPTION</span></span>

<span data-ttu-id="894b5-110">`Publish-Script`Mit dem-Cmdlet wird das angegebene Skript im Onlinekatalog veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="894b5-110">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="894b5-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="894b5-111">EXAMPLES</span></span>

### <span data-ttu-id="894b5-112">Beispiel 1: Erstellen einer Skriptdatei, Hinzufügen von Inhalt zu dieser und veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="894b5-112">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="894b5-113">Das- `New-ScriptFileInfo` Cmdlet erstellt eine Skriptdatei mit dem Namen `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="894b5-113">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="894b5-114">`Get-Content` zeigt den Inhalt von an `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="894b5-114">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="894b5-115">`Add-Content`Mit dem-Cmdlet werden eine Funktion und ein Workflow zu hinzugefügt `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="894b5-115">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

```powershell
$newScriptInfo = @{
  Path = 'D:\ScriptSharingDemo\Demo-Script.ps1'
  Version = '1.0'
  Author = 'author@contoso.com'
  Description = "my test script file description goes here"
}
New-ScriptFileInfo @newScriptInfo
Get-Content -Path $newScriptInfo.Path
```

```Output
<#PSScriptInfo

.VERSION 1.0

.AUTHOR pattif@microsoft.com

.COMPANYNAME

.COPYRIGHT

.TAGS

.LICENSEURI

.PROJECTURI

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES
#>

<#
.DESCRIPTION
 my test script file description goes here
#>
Param()
```

```powershell
Add-Content -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Value @"

Function Demo-ScriptFunction { 'Demo-ScriptFunction' }

Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }

Demo-ScriptFunction
Demo-ScriptWorkflow
"@
Test-ScriptFileInfo -Path D:\ScriptSharingDemo\Demo-Script.ps1
```

```Output
Version    Name                 Author                   Description
-------    ----                 ------                   -----------
1.0        Demo-Script          author@contoso.com       my test script file description goes here
```

```powershell
Publish-Script -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Repository LocalRepo1
Find-Script -Repository LocalRepo1 -Name "Demo-Script"
```

```Output
Version    Name                 Type       Repository    Description
-------    ----                 ----       ----------    -----------
1.0        Demo-Script          Script     LocalRepo1    my test script file description goes here
```

<span data-ttu-id="894b5-116">Das- `Test-ScriptFileInfo` Cmdlet überprüft `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="894b5-116">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="894b5-117">Das- `Publish-Script` Cmdlet veröffentlicht das Skript im **LocalRepo1** -Repository.</span><span class="sxs-lookup"><span data-stu-id="894b5-117">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="894b5-118">Die letzte Collection</span><span class="sxs-lookup"><span data-stu-id="894b5-118">Finally.</span></span> <span data-ttu-id="894b5-119">`Find-Script` wird verwendet, um `Demo-Script.ps1` im **LocalRepo1** -Repository nach zu suchen.</span><span class="sxs-lookup"><span data-stu-id="894b5-119">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="894b5-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="894b5-120">PARAMETERS</span></span>

### <span data-ttu-id="894b5-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="894b5-121">-Confirm</span></span>

<span data-ttu-id="894b5-122">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="894b5-122">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="894b5-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="894b5-123">-Credential</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="894b5-124">-Force</span><span class="sxs-lookup"><span data-stu-id="894b5-124">-Force</span></span>

<span data-ttu-id="894b5-125">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="894b5-125">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="894b5-126">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="894b5-126">-LiteralPath</span></span>

<span data-ttu-id="894b5-127">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="894b5-127">Specifies a path to one or more locations.</span></span> <span data-ttu-id="894b5-128">Im Gegensatz zum **path** -Parameter wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="894b5-128">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="894b5-129">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="894b5-129">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="894b5-130">Wenn der Pfad Escapezeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="894b5-130">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="894b5-131">Einfache Anführungszeichen veranlassen Windows PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="894b5-131">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="894b5-132">-Nugetapikey</span><span class="sxs-lookup"><span data-stu-id="894b5-132">-NuGetApiKey</span></span>

<span data-ttu-id="894b5-133">Gibt den API-Schlüssel an, den Sie zum Veröffentlichen eines Skripts im Onlinekatalog verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="894b5-133">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="894b5-134">Der API-Schlüssel ist Teil Ihres Profils im Onlinekatalog.</span><span class="sxs-lookup"><span data-stu-id="894b5-134">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="894b5-135">Weitere Informationen finden Sie unter [Verwalten von API-Schlüsseln](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span><span class="sxs-lookup"><span data-stu-id="894b5-135">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

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

### <span data-ttu-id="894b5-136">-Path</span><span class="sxs-lookup"><span data-stu-id="894b5-136">-Path</span></span>

<span data-ttu-id="894b5-137">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="894b5-137">Specifies a path to one or more locations.</span></span> <span data-ttu-id="894b5-138">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="894b5-138">Wildcards are permitted.</span></span> <span data-ttu-id="894b5-139">Der Standardspeicherort ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="894b5-139">The default location is the current directory.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: Named
Default value: <Current location>
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="894b5-140">-Repository</span><span class="sxs-lookup"><span data-stu-id="894b5-140">-Repository</span></span>

<span data-ttu-id="894b5-141">Gibt den anzeigen Amen eines Repository an, das durch Ausführen von registriert wurde `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="894b5-141">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

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

### <span data-ttu-id="894b5-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="894b5-142">-WhatIf</span></span>

<span data-ttu-id="894b5-143">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="894b5-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="894b5-144">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="894b5-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="894b5-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="894b5-145">CommonParameters</span></span>

<span data-ttu-id="894b5-146">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="894b5-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="894b5-147">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="894b5-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="894b5-148">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="894b5-148">INPUTS</span></span>

### <span data-ttu-id="894b5-149">System.String</span><span class="sxs-lookup"><span data-stu-id="894b5-149">System.String</span></span>

### <span data-ttu-id="894b5-150">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="894b5-150">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="894b5-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="894b5-151">OUTPUTS</span></span>

### <span data-ttu-id="894b5-152">System.Object</span><span class="sxs-lookup"><span data-stu-id="894b5-152">System.Object</span></span>

## <span data-ttu-id="894b5-153">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="894b5-153">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="894b5-154">Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1.</span><span class="sxs-lookup"><span data-stu-id="894b5-154">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="894b5-155">Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="894b5-155">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="894b5-156">Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="894b5-156">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="894b5-157">Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.</span><span class="sxs-lookup"><span data-stu-id="894b5-157">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="894b5-158">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="894b5-158">RELATED LINKS</span></span>

[<span data-ttu-id="894b5-159">Find-Script</span><span class="sxs-lookup"><span data-stu-id="894b5-159">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="894b5-160">Install-Script</span><span class="sxs-lookup"><span data-stu-id="894b5-160">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="894b5-161">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="894b5-161">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="894b5-162">Save-Script</span><span class="sxs-lookup"><span data-stu-id="894b5-162">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="894b5-163">Update-Script</span><span class="sxs-lookup"><span data-stu-id="894b5-163">Update-Script</span></span>](Update-Script.md)
