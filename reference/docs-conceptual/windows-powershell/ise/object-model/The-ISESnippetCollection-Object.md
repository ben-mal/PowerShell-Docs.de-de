---
ms.date: 12/31/2019
title: Das ISESnippetCollection-Objekt
description: Das ISESnippetCollection-Objekt ist eine Sammlung von ISESnippet-Objekten. Die einem PowerShellTab-Objekt zugeordnete Dateisammlung ist ein Member dieser Klasse.
ms.openlocfilehash: e6170ddf72d5ead840aa3015d4de1dcb21dbfeff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655961"
---
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="5a429-104">Das ISESnippetCollection-Objekt</span><span class="sxs-lookup"><span data-stu-id="5a429-104">The ISESnippetCollection Object</span></span>

<span data-ttu-id="5a429-105">Das **ISESnippetCollection** -Objekt ist eine Sammlung von **ISESnippet** -Objekten.</span><span class="sxs-lookup"><span data-stu-id="5a429-105">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="5a429-106">Die einem **PowerShellTab** -Objekt zugeordnete Dateisammlung ist ein Member dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="5a429-106">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="5a429-107">Ein Beispiel ist die `$psISE.CurrentPowerShellTab.Files`-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="5a429-107">An example is the `$psISE.CurrentPowerShellTab.Files` collection.</span></span>

## <a name="methods"></a><span data-ttu-id="5a429-108">Methoden</span><span class="sxs-lookup"><span data-stu-id="5a429-108">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="5a429-109">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="5a429-109">Load\( FilePathName \)</span></span>

<span data-ttu-id="5a429-110">In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a429-110">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="5a429-111">Lädt eine `.snippets.ps1xml`-Datei mit benutzerdefinierten Codeausschnitten.</span><span class="sxs-lookup"><span data-stu-id="5a429-111">Loads a `.snippets.ps1xml` file that contains user-defined snippets.</span></span> <span data-ttu-id="5a429-112">Die einfachste Möglichkeit zum Erstellen von Codeausschnitten ist das `New-IseSnippet`-Cmdlet, das die Ausschnitte automatisch im Profilordner speichert, sodass sie bei jedem Start der Windows PowerShell ISE geladen werden.</span><span class="sxs-lookup"><span data-stu-id="5a429-112">The easiest way to create snippets is to use the `New-IseSnippet` cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="5a429-113">**FilePathName** – Zeichenfolge – der Pfad und der Dateiname für eine Datei mit der Erweiterung „.snippets.ps1xml“, die Codeausschnittdefinitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="5a429-113">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="5a429-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a429-114">See Also</span></span>

- [<span data-ttu-id="5a429-115">Das ISESnippet-Objekt</span><span class="sxs-lookup"><span data-stu-id="5a429-115">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="5a429-116">Zweck des Windows PowerShell ISE-Skriptobjektmodells</span><span class="sxs-lookup"><span data-stu-id="5a429-116">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="5a429-117">Die ISE-Objektmodellhierarchie</span><span class="sxs-lookup"><span data-stu-id="5a429-117">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
