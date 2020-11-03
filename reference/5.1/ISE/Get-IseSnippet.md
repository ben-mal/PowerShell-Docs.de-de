---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/get-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IseSnippet
ms.openlocfilehash: c43dae3f178ae778d78fe3718fa85fd2635eba86
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218103"
---
# <span data-ttu-id="46d25-103">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="46d25-103">Get-IseSnippet</span></span>

## <span data-ttu-id="46d25-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="46d25-104">SYNOPSIS</span></span>
<span data-ttu-id="46d25-105">Ruft vom Benutzer erstellte Codeausschnitte ab.</span><span class="sxs-lookup"><span data-stu-id="46d25-105">Gets snippets that the user created.</span></span>

## <span data-ttu-id="46d25-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="46d25-106">SYNTAX</span></span>

```
Get-IseSnippet [<CommonParameters>]
```

## <span data-ttu-id="46d25-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="46d25-107">DESCRIPTION</span></span>

<span data-ttu-id="46d25-108">Das `Get-IseSnippet` Cmdlet ruft die PS1XML-Dateien ab, die wiederverwendbare Textausschnitte enthalten, die vom Benutzer erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="46d25-108">The `Get-IseSnippet` cmdlet gets the PS1XML files that contain reusable text snippets that the user created.</span></span> <span data-ttu-id="46d25-109">Dies funktioniert nur in Windows PowerShell Integrated Scripting Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="46d25-109">It works only in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="46d25-110">Wenn Sie mit dem `New-IseSnippet` Cmdlet einen Ausschnitt erstellen, wird von `New-IseSnippet` eine `<SnippetTitle>.Snippets.ps1xml` Datei im Verzeichnis erstellt `$home\Documents\WindowsPowerShell\Snippets` .</span><span class="sxs-lookup"><span data-stu-id="46d25-110">When you use the `New-IseSnippet` cmdlet to create a snippet, `New-IseSnippet` creates a `<SnippetTitle>.Snippets.ps1xml` file in the `$home\Documents\WindowsPowerShell\Snippets` directory.</span></span>
<span data-ttu-id="46d25-111">`Get-IseSnippet` Ruft die Ausschnitt Dateien im Verzeichnis "Snippets" ab.</span><span class="sxs-lookup"><span data-stu-id="46d25-111">`Get-IseSnippet` gets the snippet files in the Snippets directory.</span></span>

<span data-ttu-id="46d25-112">Dieses Cmdlet erhält keine integrierten Code Ausschnitte oder Ausschnitte, die aus Modulen über das `Import-IseSnippet` Cmdlet importiert werden.</span><span class="sxs-lookup"><span data-stu-id="46d25-112">This cmdlet does not get built-in snippets or snippets that are imported from modules through the `Import-IseSnippet` cmdlet.</span></span>

<span data-ttu-id="46d25-113">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="46d25-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="46d25-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="46d25-114">EXAMPLES</span></span>

### <span data-ttu-id="46d25-115">Beispiel 1: alle benutzerdefinierten Ausschnitte erhalten</span><span class="sxs-lookup"><span data-stu-id="46d25-115">Example 1: Get all user-defined snippets</span></span>

<span data-ttu-id="46d25-116">In diesem Beispiel werden alle benutzerdefinierten Code Ausschnitte im Verzeichnis "Snippets" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="46d25-116">This example gets all user-define snippets in the Snippets directory.</span></span>

```powershell
Get-IseSnippet
```

### <span data-ttu-id="46d25-117">Beispiel 2: Kopieren aller benutzerdefinierten Code Ausschnitte von Remote Computern in ein frei gegebenes Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="46d25-117">Example 2: Copy all user-defined snippets from remote computers to a shared directory</span></span>

<span data-ttu-id="46d25-118">In diesem Beispiel werden alle vom Benutzer erstellten Code Ausschnitte aus einer Gruppe von Remote Computern in ein frei gegebenes Verzeichnis "Snippets" kopiert.</span><span class="sxs-lookup"><span data-stu-id="46d25-118">This example copies all of the user-created snippets from a group of remote computers to a shared Snippets directory.</span></span>

```powershell
Invoke-Command -Computer (Get-Content Servers.txt) {Get-IseSnippet | Copy-Item -Destination \\Server01\Share01\Snippets}
```

<span data-ttu-id="46d25-119">`Invoke-Command` wird `Get-IseSnippet` auf den Computern in der `Servers.txt` Datei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="46d25-119">`Invoke-Command` runs `Get-IseSnippet` on the computers in the `Servers.txt` file.</span></span> <span data-ttu-id="46d25-120">Ein Pipeline Operator ( `|` ) sendet die Ausschnitt Dateien an das `Copy-Item` Cmdlet, das Sie in das durch den **Ziel** Parameter angegebene Verzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="46d25-120">A pipeline operator (`|`) sends the snippet files to the `Copy-Item` cmdlet, which copies them to the directory that is specified by the **Destination** parameter.</span></span>

### <span data-ttu-id="46d25-121">Beispiel 3: Anzeigen des Titels und Texts jedes Ausschnitts auf einem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="46d25-121">Example 3: Display the title and text of each snippet on a local computer</span></span>

<span data-ttu-id="46d25-122">In diesem Beispiel werden die `Get-IseSnippet` -und- `Select-Xml` Cmdlets verwendet, um den Titel und den Text jedes Ausschnitts auf dem lokalen Computer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46d25-122">This example uses the `Get-IseSnippet` and `Select-Xml` cmdlets to display the title and text of each snippet on the local computer.</span></span>

```powershell
#Parse-Snippet Function
function Parse-Snippet {
  $SnippetFiles = Get-IseSnippet
  $SnippetNamespace = @{x="http://schemas.microsoft.com/PowerShell/Snippets"}
  foreach ($SnippetFile in $SnippetFiles) {
     Write-Host ""
     $Title = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Title" |
       ForEach-Object {$_.Node.InnerXML}
     $Text = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Script" |
       ForEach-Object {$_.Node.InnerText}
     Write-Host "Title: $Title"
     Write-Host "Text: $Text"
   }
}
```

```Output
Title: Mandatory
Text:
Param
(
  [parameter(Mandatory=True)]
  [String[]]
  $<ParameterName>
)

Title: Copyright
Text:  (c) Fabrikam, Inc. 2012
```

### <span data-ttu-id="46d25-123">Beispiel 4: Anzeigen des Titels und der Beschreibung aller Ausschnitte in der Sitzung</span><span class="sxs-lookup"><span data-stu-id="46d25-123">Example 4: Display the title and description of all snippets in the session</span></span>

<span data-ttu-id="46d25-124">In diesem Beispiel werden der Titel und die Beschreibung aller Code Ausschnitte in der Sitzung angezeigt, einschließlich integrierter Code Ausschnitte, benutzerdefinierter Code Ausschnitte und importierter Code Ausschnitte.</span><span class="sxs-lookup"><span data-stu-id="46d25-124">This example displays the title and description of all snippets in the session, including built-in snippets, user-defined snippets, and imported snippets.</span></span>

```powershell
$PSISE.CurrentPowerShellTab.Snippets | Format-Table DisplayTitle, Description
```

<span data-ttu-id="46d25-125">Die- `$PSISE` Variable stellt das Windows PowerShell ISE Host Programm dar.</span><span class="sxs-lookup"><span data-stu-id="46d25-125">The `$PSISE` variable represents the Windows PowerShell ISE host program.</span></span> <span data-ttu-id="46d25-126">Die **currentpowershelltab** -Eigenschaft der `$PSISE` Variablen stellt die aktuelle Sitzung dar.</span><span class="sxs-lookup"><span data-stu-id="46d25-126">The **CurrentPowerShellTab** property of the `$PSISE` variable represent the current session.</span></span> <span data-ttu-id="46d25-127">Die **Snippets** -Eigenschaft stellt Codeausschnitte in der aktuellen Sitzung dar.</span><span class="sxs-lookup"><span data-stu-id="46d25-127">The **Snippets** property represents snippets in the current session.</span></span>

<span data-ttu-id="46d25-128">Der `$PSISE.CurrentPowerShellTab.Snippets` Befehl gibt ein **Microsoft. PowerShell. Host. ISE. isesnippet** -Objekt zurück, das einen Ausschnitt darstellt, im Gegensatz zum `Get-IseSnippet` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="46d25-128">The `$PSISE.CurrentPowerShellTab.Snippets` command returns a **Microsoft.PowerShell.Host.ISE.ISESnippet** object that represents a snippet, unlike the `Get-IseSnippet` cmdlet.</span></span> <span data-ttu-id="46d25-129">`Get-IseSnippet` Gibt ein Datei Objekt (System. IO. FileInfo) zurück, das eine codeausschnittsdatei darstellt.</span><span class="sxs-lookup"><span data-stu-id="46d25-129">`Get-IseSnippet` returns a file object (System.Io.FileInfo) that represents a snippet file.</span></span>

<span data-ttu-id="46d25-130">`Format-Table`Mit dem-Cmdlet werden die Eigenschaften **Display Title** und **Description** der Code Ausschnitte in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46d25-130">The `Format-Table` cmdlet displays the **DisplayTitle** and **Description** properties of the snippets in a table.</span></span>

## <span data-ttu-id="46d25-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="46d25-131">PARAMETERS</span></span>

### <span data-ttu-id="46d25-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="46d25-132">CommonParameters</span></span>

<span data-ttu-id="46d25-133">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="46d25-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="46d25-134">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="46d25-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="46d25-135">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="46d25-135">INPUTS</span></span>

## <span data-ttu-id="46d25-136">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="46d25-136">OUTPUTS</span></span>

### <span data-ttu-id="46d25-137">System. IO. fileingefo</span><span class="sxs-lookup"><span data-stu-id="46d25-137">System.IO.FileInfo</span></span>

<span data-ttu-id="46d25-138">Dieses Cmdlet gibt ein Datei Objekt zurück, das die codeausschnittsdatei darstellt.</span><span class="sxs-lookup"><span data-stu-id="46d25-138">This cmdlet returns a file object that represents the snippet file.</span></span>

## <span data-ttu-id="46d25-139">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="46d25-139">NOTES</span></span>

* <span data-ttu-id="46d25-140">Das- `New-IseSnippet` Cmdlet speichert neue Benutzer erstellte Code Ausschnitte in unsignierten ps1xml-Dateien.</span><span class="sxs-lookup"><span data-stu-id="46d25-140">The `New-IseSnippet` cmdlet stores new user-created snippets in unsigned .ps1xml files.</span></span> <span data-ttu-id="46d25-141">Daher kann Windows PowerShell sie nicht zu Sitzungen hinzufügen, in denen die Ausführungsrichtlinie **AllSigned** oder **Restricted** gilt.</span><span class="sxs-lookup"><span data-stu-id="46d25-141">As such, Windows PowerShell cannot add them to a session in which the execution policy is **AllSigned** or **Restricted**.</span></span> <span data-ttu-id="46d25-142">In einer Sitzung mit der Ausführungsrichtlinie **Restricted** oder **AllSigned** können Sie zwar unsignierte benutzererstellte Codeausschnitte erstellen, abrufen und importieren, aber nicht in der Sitzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="46d25-142">In a **Restricted** or **AllSigned** session, you can create, get, and import unsigned user-created snippets, but you cannot use them in the session.</span></span>

  <span data-ttu-id="46d25-143">Um nicht signierte Benutzer erstellte Code Ausschnitte zu verwenden, die vom `Get-IseSnippet` Cmdlet zurückgegeben werden, ändern Sie die Ausführungs Richtlinie, und starten Sie Windows PowerShell ISE neu.</span><span class="sxs-lookup"><span data-stu-id="46d25-143">To use unsigned user-created snippets that the `Get-IseSnippet` cmdlet returns, change the execution policy, and then restart Windows PowerShell ISE.</span></span>

  <span data-ttu-id="46d25-144">Weitere Informationen zu Windows PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="46d25-144">For more information about Windows PowerShell execution policies, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="46d25-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="46d25-145">RELATED LINKS</span></span>

[<span data-ttu-id="46d25-146">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="46d25-146">New-IseSnippet</span></span>](New-IseSnippet.md)

[<span data-ttu-id="46d25-147">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="46d25-147">Import-IseSnippet</span></span>](Import-IseSnippet.md)
