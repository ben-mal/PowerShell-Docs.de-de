---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/import-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IseSnippet
ms.openlocfilehash: 810be675fc593f665ccc6f3d5b86ac2f6b633863
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212383"
---
# <span data-ttu-id="63a84-103">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="63a84-103">Import-IseSnippet</span></span>

## <span data-ttu-id="63a84-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="63a84-104">SYNOPSIS</span></span>
<span data-ttu-id="63a84-105">Importiert ISE-Codeausschnitte in die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="63a84-105">Imports ISE snippets into the current session</span></span>

## <span data-ttu-id="63a84-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="63a84-106">SYNTAX</span></span>

### <span data-ttu-id="63a84-107">Fromfolder (Standard)</span><span class="sxs-lookup"><span data-stu-id="63a84-107">FromFolder (Default)</span></span>

```
Import-IseSnippet [-Path] <String> [-Recurse] [<CommonParameters>]
```

### <span data-ttu-id="63a84-108">Frommodule</span><span class="sxs-lookup"><span data-stu-id="63a84-108">FromModule</span></span>

```
Import-IseSnippet [-Recurse] -Module <String> [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="63a84-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="63a84-109">DESCRIPTION</span></span>

<span data-ttu-id="63a84-110">Mit dem- `Import-IseSnippet` Cmdlet werden wiederverwendbare Textausschnitte aus einem Modul oder einem Verzeichnis in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="63a84-110">The `Import-IseSnippet` cmdlet imports reusable text "snippets" from a module or a directory into the current session.</span></span> <span data-ttu-id="63a84-111">Die Ausschnitte sind sofort für die Verwendung in Windows PowerShell ISE verfügbar.</span><span class="sxs-lookup"><span data-stu-id="63a84-111">The snippets are immediately available for use in Windows PowerShell ISE.</span></span> <span data-ttu-id="63a84-112">Dieses Cmdlet funktioniert nur in Windows PowerShell Integrated Scripting Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="63a84-112">This cmdlet works only in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="63a84-113">Um die importierten Ausschnitte anzuzeigen und zu verwenden, klicken Sie im Menü Windows PowerShell ISE **Bearbeiten** auf Code **Ausschnitte starten** , oder drücken Sie <kbd>STRG</kbd> + <kbd>J</kbd>.</span><span class="sxs-lookup"><span data-stu-id="63a84-113">To view and use the imported snippets, from the Windows PowerShell ISE **Edit** menu, click **Start Snippets** or press <kbd>Ctrl</kbd>+<kbd>J</kbd>.</span></span>

<span data-ttu-id="63a84-114">Importierte Codeausschnitte sind nur in der aktuellen Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="63a84-114">Imported snippets are available only in the current session.</span></span> <span data-ttu-id="63a84-115">Um die Code Ausschnitte in alle Windows PowerShell ISE Sitzungen zu importieren, fügen Sie `Import-IseSnippet` Ihrem Windows PowerShell-Profil einen Befehl hinzu, oder kopieren Sie die codeausschnittsdateien in das lokale Verzeichnis "Snippets" `$home\Documents\WindowsPowershell\Snippets` .</span><span class="sxs-lookup"><span data-stu-id="63a84-115">To import the snippets into all Windows PowerShell ISE sessions, add an `Import-IseSnippet` command to your Windows PowerShell profile or copy the snippet files to your local snippets directory `$home\Documents\WindowsPowershell\Snippets`.</span></span>

<span data-ttu-id="63a84-116">Um Ausschnitte zu importieren, müssen Sie in der Ausschnitt-XML-Datei für Windows PowerShell ISE Ausschnitte ordnungsgemäß formatiert und in Snippet.ps1XML-Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="63a84-116">To import snippets, they must be properly formatted in the snippet XML for Windows PowerShell ISE snippets and saved in Snippet.ps1xml files.</span></span> <span data-ttu-id="63a84-117">Um berechtigte Ausschnitte zu erstellen, verwenden Sie das- `New-IseSnippet` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="63a84-117">To create eligible snippets, use the `New-IseSnippet` cmdlet.</span></span> <span data-ttu-id="63a84-118">`New-IseSnippet` erstellt eine `<SnippetTitle>.Snippets.ps1xml` Datei im `$home\Documents\WindowsPowerShell\Snippets` Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="63a84-118">`New-IseSnippet` creates a `<SnippetTitle>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span> <span data-ttu-id="63a84-119">Sie können die Codeausschnitte in das Verzeichnis „Snippets“ eines Windows PowerShell-Moduls oder in ein beliebiges anderen Verzeichnis verschieben oder kopieren.</span><span class="sxs-lookup"><span data-stu-id="63a84-119">You can move or copy the snippets to the Snippets directory of a Windows PowerShell module, or to any other directory.</span></span>

<span data-ttu-id="63a84-120">`Get-IseSnippet`Mit dem-Cmdlet, das vom Benutzer erstellte Code Ausschnitte im Verzeichnis "local Snippets" abruft, werden keine importierten Ausschnitte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="63a84-120">The `Get-IseSnippet` cmdlet, which gets user-created snippets in the local snippets directory, does not get imported snippets.</span></span>

<span data-ttu-id="63a84-121">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="63a84-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="63a84-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="63a84-122">EXAMPLES</span></span>

### <span data-ttu-id="63a84-123">Beispiel 1: Importieren von Ausschnitten aus einem Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="63a84-123">Example 1: Import snippets from a directory</span></span>

<span data-ttu-id="63a84-124">In diesem Beispiel werden die Code Ausschnitte aus dem `\\Server01\Public\Snippets` Verzeichnis in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="63a84-124">This example imports the snippets from the `\\Server01\Public\Snippets` directory into the current session.</span></span> <span data-ttu-id="63a84-125">Er verwendet den **recurse** -Parameter, um Code Ausschnitte aus allen Unterverzeichnissen des Verzeichnisses "Snippets" abzurufen.</span><span class="sxs-lookup"><span data-stu-id="63a84-125">It uses the **Recurse** parameter to get snippets from all subdirectories of the Snippets directory.</span></span>

```powershell
Import-IseSnippet -Path \\Server01\Public\Snippets -Recurse
```

### <span data-ttu-id="63a84-126">Beispiel 2: Importieren von Ausschnitten aus einem Modul</span><span class="sxs-lookup"><span data-stu-id="63a84-126">Example 2: Import snippets from a module</span></span>

<span data-ttu-id="63a84-127">In diesem Beispiel werden die Code Ausschnitte aus dem **snippetmodule** -Modul importiert.</span><span class="sxs-lookup"><span data-stu-id="63a84-127">This example imports the snippets from the **SnippetModule** module.</span></span> <span data-ttu-id="63a84-128">Der Befehl verwendet den **listavailable** -Parameter, um die Code Ausschnitte zu importieren, auch wenn das **snippetmodule** -Modul nicht in die Sitzung des Benutzers importiert wird, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="63a84-128">The command uses the **ListAvailable** parameter to import the snippets even if the **SnippetModule** module is not imported into the user's session when the command runs.</span></span>

```powershell
Import-IseSnippet -Module SnippetModule -ListAvailable
```

### <span data-ttu-id="63a84-129">Beispiel 3: Suchen von Code Ausschnitten in Modulen</span><span class="sxs-lookup"><span data-stu-id="63a84-129">Example 3: Find snippets in modules</span></span>

<span data-ttu-id="63a84-130">In diesem Beispiel werden Ausschnitte in allen installierten Modulen in der psmodulepath-Umgebungsvariablen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="63a84-130">This example gets snippets in all installed modules in the PSModulePath environment variable.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$_.fullname}
```

### <span data-ttu-id="63a84-131">Beispiel 4: Importieren aller Modul Ausschnitte</span><span class="sxs-lookup"><span data-stu-id="63a84-131">Example 4: Import all module snippets</span></span>

<span data-ttu-id="63a84-132">In diesem Beispiel werden alle Ausschnitte aus allen installierten Modulen in die aktuelle Sitzung importiert.</span><span class="sxs-lookup"><span data-stu-id="63a84-132">This example imports all snippets from all installed modules into the current session.</span></span> <span data-ttu-id="63a84-133">In der Regel müssen Sie keinen Befehl wie diesen ausführen, da Module mit Code `Import-IseSnippet` Ausschnitten das Cmdlet verwenden, um Sie beim Importieren des Moduls für Sie zu importieren.</span><span class="sxs-lookup"><span data-stu-id="63a84-133">Typically, you don't need to run a command like this because modules that have snippets will use the `Import-IseSnippet` cmdlet to import them for you when the module is imported.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$psise.CurrentPowerShellTab.Snippets.Load($_)}
```

### <span data-ttu-id="63a84-134">Beispiel 5: Kopieren aller Modul Ausschnitte</span><span class="sxs-lookup"><span data-stu-id="63a84-134">Example 5: Copy all module snippets</span></span>

<span data-ttu-id="63a84-135">In diesem Beispiel werden die Ausschnitt Dateien aus allen installierten Modulen in das Verzeichnis "Snippets" des aktuellen Benutzers kopiert.</span><span class="sxs-lookup"><span data-stu-id="63a84-135">This example copies the snippet files from all installed modules into the Snippets directory of the current user.</span></span> <span data-ttu-id="63a84-136">Im Gegensatz zu importierten Codeausschnitten, die nur die aktuelle Sitzung betreffen, sind die kopierten Codeausschnitte in jeder Windows PowerShell ISE-Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="63a84-136">Unlike imported snippets, which affect only the current session, copied snippets are available in every Windows PowerShell ISE session.</span></span>

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    Copy-Item -Destination $home\Documents\WindowsPowerShell\Snippets
```

## <span data-ttu-id="63a84-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="63a84-137">PARAMETERS</span></span>

### <span data-ttu-id="63a84-138">-Listavailable</span><span class="sxs-lookup"><span data-stu-id="63a84-138">-ListAvailable</span></span>

<span data-ttu-id="63a84-139">Gibt an, dass dieses Cmdlet Code Ausschnitte aus Modulen abruft, die auf dem Computer installiert sind, selbst wenn die Module nicht in die aktuelle Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="63a84-139">Indicates that this cmdlet gets snippets from modules that are installed on the computer, even if the modules are not imported into the current session.</span></span> <span data-ttu-id="63a84-140">Wenn dieser Parameter ausgelassen wird und das vom **Modul** Parameter angegebene Modul nicht in die aktuelle Sitzung importiert wird, schlägt der Versuch fehl, die Ausschnitte aus dem Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="63a84-140">If this parameter is omitted, and the module that is specified by the **Module** parameter is not imported into the current session, the attempt to get the snippets from the module fails.</span></span>

<span data-ttu-id="63a84-141">Dieser Parameter ist nur gültig, wenn der **Module** -Parameter im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="63a84-141">This parameter is valid only when the **Module** parameter is used in the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromModule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a84-142">-Modul</span><span class="sxs-lookup"><span data-stu-id="63a84-142">-Module</span></span>

<span data-ttu-id="63a84-143">Importiert Codeausschnitte aus dem angegebenen Modul in die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="63a84-143">Imports snippets from the specified module into the current session.</span></span> <span data-ttu-id="63a84-144">Platzhalterzeichen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63a84-144">Wildcard characters are not supported.</span></span>

<span data-ttu-id="63a84-145">Dieser Parameter importiert Ausschnitte aus Snippet.ps1XML-Dateien im Unterverzeichnis "Snippets" im Modulpfad, z `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets` . b..</span><span class="sxs-lookup"><span data-stu-id="63a84-145">This parameter imports snippets from Snippet.ps1xml files in the Snippets subdirectory in the module path, such as `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets`.</span></span>

<span data-ttu-id="63a84-146">Dieser Parameter ist für die Verwendung durch Modulautoren in einem Startskript gedacht, wie z. B. ein im **ScriptsToProcess** -Schlüssel eines Modulmanifests angegebenes Modul.</span><span class="sxs-lookup"><span data-stu-id="63a84-146">This parameter is designed to be used by module authors in a startup script, such as a script specified in the **ScriptsToProcess** key of a module manifest.</span></span> <span data-ttu-id="63a84-147">Ausschnitte in einem Modul werden nicht automatisch mit dem Modul importiert, Sie können jedoch einen Befehl verwenden, `Import-IseSnippet` um Sie zu importieren.</span><span class="sxs-lookup"><span data-stu-id="63a84-147">Snippets in a module are not automatically imported with the module, but you can use an `Import-IseSnippet` command to import them.</span></span>

```yaml
Type: System.String
Parameter Sets: FromModule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63a84-148">-Path</span><span class="sxs-lookup"><span data-stu-id="63a84-148">-Path</span></span>

<span data-ttu-id="63a84-149">Gibt den Pfad zum Verzeichnis "Snippets" an, in dem das Cmdlet Ausschnitte importiert.</span><span class="sxs-lookup"><span data-stu-id="63a84-149">Specifies the path to the snippets directory in which this cmdlet imports snippets.</span></span>

```yaml
Type: System.String
Parameter Sets: FromFolder
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="63a84-150">-Recurse</span><span class="sxs-lookup"><span data-stu-id="63a84-150">-Recurse</span></span>

<span data-ttu-id="63a84-151">Gibt an, dass dieses Cmdlet Ausschnitte aus allen Unterverzeichnissen des Werts des **path** -Parameters importiert.</span><span class="sxs-lookup"><span data-stu-id="63a84-151">Indicates that this cmdlet imports snippets from all subdirectories of the value of the **Path** parameter.</span></span>

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

### <span data-ttu-id="63a84-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="63a84-152">CommonParameters</span></span>

<span data-ttu-id="63a84-153">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="63a84-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="63a84-154">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="63a84-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="63a84-155">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="63a84-155">INPUTS</span></span>

### <span data-ttu-id="63a84-156">Keine</span><span class="sxs-lookup"><span data-stu-id="63a84-156">None</span></span>

<span data-ttu-id="63a84-157">Dieses Cmdlet nimmt keine Eingabe von der Pipeline an.</span><span class="sxs-lookup"><span data-stu-id="63a84-157">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="63a84-158">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="63a84-158">OUTPUTS</span></span>

### <span data-ttu-id="63a84-159">Keine</span><span class="sxs-lookup"><span data-stu-id="63a84-159">None</span></span>

<span data-ttu-id="63a84-160">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="63a84-160">This cmdlet does not generate output.</span></span>

## <span data-ttu-id="63a84-161">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="63a84-161">NOTES</span></span>

- <span data-ttu-id="63a84-162">Sie können das `Get-IseSnippet` Cmdlet nicht verwenden, um importierte Ausschnitte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="63a84-162">You cannot use the `Get-IseSnippet` cmdlet to get imported snippets.</span></span> <span data-ttu-id="63a84-163">`Get-IseSnippet` Ruft nur Ausschnitte im `$home\Documents\WindowsPowerShell\Snippets` Verzeichnis ab.</span><span class="sxs-lookup"><span data-stu-id="63a84-163">`Get-IseSnippet` gets only snippets in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span>
- <span data-ttu-id="63a84-164">`Import-IseSnippet` verwendet die statische **Lade** Methode von **Microsoft. PowerShell. Host. ISE. isesnippetcollection** -Objekten.</span><span class="sxs-lookup"><span data-stu-id="63a84-164">`Import-IseSnippet` uses the **Load** static method of **Microsoft.PowerShell.Host.ISE.ISESnippetCollection** objects.</span></span> <span data-ttu-id="63a84-165">Sie können auch die **Load** -Methode von Code Ausschnitten im Windows PowerShell ISE-Objektmodell verwenden: `$psISE.CurrentPowerShellTab.Snippets.Load()`</span><span class="sxs-lookup"><span data-stu-id="63a84-165">You can also use the **Load** method of snippets in the Windows PowerShell ISE object model: `$psISE.CurrentPowerShellTab.Snippets.Load()`</span></span>
- <span data-ttu-id="63a84-166">Das- `New-IseSnippet` Cmdlet speichert neue Benutzer erstellte Code Ausschnitte in unsignierten ps1xml-Dateien.</span><span class="sxs-lookup"><span data-stu-id="63a84-166">The `New-IseSnippet` cmdlet stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="63a84-167">Daher kann Windows PowerShell sie nicht in Sitzungen laden, in denen die Ausführungsrichtlinie **AllSigned** oder **Restricted** gilt.</span><span class="sxs-lookup"><span data-stu-id="63a84-167">As such, Windows PowerShell cannot load them into a session in which the execution policy is **AllSigned** or **Restricted** .</span></span> <span data-ttu-id="63a84-168">In einer Sitzung mit der Ausführungsrichtlinie **Restricted** oder **AllSigned** können Sie zwar unsignierte benutzererstellte Codeausschnitte erstellen, abrufen und importieren, aber nicht in der Sitzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="63a84-168">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

  <span data-ttu-id="63a84-169">Um nicht signierte Benutzer erstellte Code Ausschnitte zu verwenden, die vom `Import-IseSnippet` Cmdlet zurückgegeben werden, ändern Sie die Ausführungs Richtlinie, und starten Sie Windows PowerShell ISE neu.</span><span class="sxs-lookup"><span data-stu-id="63a84-169">To use unsigned user-created snippets that the `Import-IseSnippet` cmdlet returns, change the execution policy, and then restart Windows PowerShell ISE.</span></span>

  <span data-ttu-id="63a84-170">Weitere Informationen zu Windows PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="63a84-170">For more information about Windows PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="63a84-171">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="63a84-171">RELATED LINKS</span></span>

[<span data-ttu-id="63a84-172">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="63a84-172">Get-IseSnippet</span></span>](Get-IseSnippet.md)

[<span data-ttu-id="63a84-173">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="63a84-173">New-IseSnippet</span></span>](New-IseSnippet.md)
