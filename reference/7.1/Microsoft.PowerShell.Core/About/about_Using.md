---
description: Ermöglicht Ihnen, anzugeben, welche Namespaces in der Sitzung verwendet werden.
Locale: en-US
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: bbea815f93ba503fcce550dec28736630fec5a51
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890762"
---
# <a name="about-using"></a><span data-ttu-id="50b4d-103">Informationen zur Verwendung von</span><span class="sxs-lookup"><span data-stu-id="50b4d-103">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="50b4d-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="50b4d-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="50b4d-105">Ermöglicht Ihnen, anzugeben, welche Namespaces in der Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50b4d-105">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="50b4d-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="50b4d-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="50b4d-107">Mit der- `using` Anweisung können Sie angeben, welche Namespaces in der Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50b4d-107">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="50b4d-108">Das Hinzufügen von Namespaces vereinfacht die Verwendung von .NET-Klassen und-Membern und ermöglicht das Importieren von Klassen aus Skript Modulen und Assemblys.</span><span class="sxs-lookup"><span data-stu-id="50b4d-108">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="50b4d-109">Die- `using` Anweisungen müssen vor allen anderen Anweisungen in einem Skript stehen.</span><span class="sxs-lookup"><span data-stu-id="50b4d-109">The `using` statements must come before any other statements in a script.</span></span>

<span data-ttu-id="50b4d-110">Die- `using` Anweisung sollte nicht mit dem bereichsmodifizierer `using:` für Variablen verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="50b4d-110">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="50b4d-111">Weitere Informationen finden Sie unter [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="50b4d-111">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="namespace-syntax"></a><span data-ttu-id="50b4d-112">Namespace Syntax</span><span class="sxs-lookup"><span data-stu-id="50b4d-112">Namespace syntax</span></span>

<span data-ttu-id="50b4d-113">So geben Sie .NET-Namespaces an, aus denen Typen aufgelöst werden sollen:</span><span class="sxs-lookup"><span data-stu-id="50b4d-113">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="50b4d-114">Durch die Angabe eines Namespace wird es einfacher, auf Typen anhand ihrer Kurznamen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="50b4d-114">Specifying a namespace makes it easier to reference types by their short names.</span></span>

## <a name="module-syntax"></a><span data-ttu-id="50b4d-115">Modul Syntax</span><span class="sxs-lookup"><span data-stu-id="50b4d-115">Module syntax</span></span>

<span data-ttu-id="50b4d-116">So laden Sie Klassen aus einem PowerShell-Modul:</span><span class="sxs-lookup"><span data-stu-id="50b4d-116">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="50b4d-117">Der Wert von `<module-name>` kann ein Modulname, eine vollständige Modul Spezifikation oder ein Pfad zu einer Modul Datei sein.</span><span class="sxs-lookup"><span data-stu-id="50b4d-117">The value of `<module-name>` can be a module name, a full module specification, or a path to a module file.</span></span>

<span data-ttu-id="50b4d-118">Wenn `<module-name>` ein Pfad ist, kann der Pfad voll qualifiziert oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="50b4d-118">When `<module-name>` is a path, the path can be fully qualified or relative.</span></span> <span data-ttu-id="50b4d-119">Ein relativer Pfad wird relativ zum Skript aufgelöst, das die using-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="50b4d-119">A relative path is resolved relative to the script that contains the using statement.</span></span>

<span data-ttu-id="50b4d-120">Wenn `<module-name>` eine Name-oder Modul Spezifikation ist, durchsucht PowerShell den **psmodulepath** nach dem angegebenen Modul.</span><span class="sxs-lookup"><span data-stu-id="50b4d-120">When `<module-name>` is a name or module specification, PowerShell searches the **PSModulePath** for the specified module.</span></span>

<span data-ttu-id="50b4d-121">Eine Modul Spezifikation ist eine Hash Tabelle mit den folgenden Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="50b4d-121">A module specification is a hash table that has the following keys.</span></span>

- <span data-ttu-id="50b4d-122">`ModuleName` - **Erforderlich** Gibt den Namen des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="50b4d-122">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="50b4d-123">`GUID` - **Optional** Gibt die GUID des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="50b4d-123">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="50b4d-124">Es ist auch **erforderlich** , einen der drei folgenden Schlüssel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="50b4d-124">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="50b4d-125">Diese Schlüssel können nicht gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50b4d-125">These keys can't be used together.</span></span>
  - <span data-ttu-id="50b4d-126">`ModuleVersion` : Gibt eine zulässige Mindestversion des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="50b4d-126">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="50b4d-127">`RequiredVersion` : Gibt eine exakte, erforderliche Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="50b4d-127">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="50b4d-128">`MaximumVersion` : Gibt die maximal zulässige Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="50b4d-128">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

## <a name="assembly-syntax"></a><span data-ttu-id="50b4d-129">Assemblysyntax</span><span class="sxs-lookup"><span data-stu-id="50b4d-129">Assembly syntax</span></span>

<span data-ttu-id="50b4d-130">So laden Sie Typen aus einer .NET-Assembly vorab:</span><span class="sxs-lookup"><span data-stu-id="50b4d-130">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
```

<span data-ttu-id="50b4d-131">Durch das Laden einer Assembly werden .NET-Typen aus dieser Assembly zur Analysezeit vorab in ein Skript geladen.</span><span class="sxs-lookup"><span data-stu-id="50b4d-131">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="50b4d-132">Dies ermöglicht es Ihnen, neue PowerShell-Klassen zu erstellen, die Typen aus der vorgeladenen Assembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="50b4d-132">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="50b4d-133">Wenn Sie keine neuen PowerShell-Klassen erstellen, verwenden Sie `Add-Type` stattdessen das-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="50b4d-133">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="50b4d-134">Weitere Informationen finden Sie unter [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span><span class="sxs-lookup"><span data-stu-id="50b4d-134">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="50b4d-135">Beispiele</span><span class="sxs-lookup"><span data-stu-id="50b4d-135">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="50b4d-136">Beispiel 1: Hinzufügen von Namespaces für die Typname-Auflösung</span><span class="sxs-lookup"><span data-stu-id="50b4d-136">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="50b4d-137">Mit dem folgenden Skript wird der kryptografiehash für die Zeichenfolge "Hallo Welt" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="50b4d-137">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="50b4d-138">Beachten Sie `using namespace System.Text` , wie und `using namespace System.IO` die Verweise auf `[UnicodeEncoding]` in `System.Text` und `[Stream]` und auf `[MemoryStream]` in vereinfachen `System.IO` .</span><span class="sxs-lookup"><span data-stu-id="50b4d-138">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

```powershell
using namespace System.Text
using namespace System.IO

[string]$string = "Hello World"
## Valid values are "SHA1", "SHA256", "SHA384", "SHA512", "MD5"
[string]$algorithm = "SHA256"

[byte[]]$stringbytes = [UnicodeEncoding]::Unicode.GetBytes($string)

[Stream]$memorystream = [MemoryStream]::new($stringbytes)
$hashfromstream = Get-FileHash -InputStream $memorystream `
  -Algorithm $algorithm
$hashfromstream.Hash.ToString()
```

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="50b4d-139">Beispiel 2: Laden von Klassen aus einem Skript Modul</span><span class="sxs-lookup"><span data-stu-id="50b4d-139">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="50b4d-140">In diesem Beispiel verfügen wir über ein PowerShell-Skript Modul namens **Cardgames** , das die folgenden Klassen definiert:</span><span class="sxs-lookup"><span data-stu-id="50b4d-140">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="50b4d-141">**Cardgames. Karten**</span><span class="sxs-lookup"><span data-stu-id="50b4d-141">**CardGames.Deck**</span></span>
- <span data-ttu-id="50b4d-142">**Cardgames. Card**</span><span class="sxs-lookup"><span data-stu-id="50b4d-142">**CardGames.Card**</span></span>

<span data-ttu-id="50b4d-143">`Import-Module` und die- `#requires` Anweisung importiert nur die Modulfunktionen, Aliase und Variablen, wie vom Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="50b4d-143">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="50b4d-144">Klassen werden nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="50b4d-144">Classes are not imported.</span></span> <span data-ttu-id="50b4d-145">Der `using module` Befehl importiert das Modul und lädt auch die Klassendefinitionen.</span><span class="sxs-lookup"><span data-stu-id="50b4d-145">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="50b4d-146">Beispiel 3: Laden von Klassen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="50b4d-146">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="50b4d-147">In diesem Beispiel wird eine Assembly geladen, damit Ihre Klassen zum Erstellen neuer PowerShell-Klassen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="50b4d-147">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="50b4d-148">Mit dem folgenden Skript wird eine neue PowerShell-Klasse erstellt, die von der **DirectoryContext** -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="50b4d-148">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

```powershell
using assembly 'C:\Program Files\PowerShell\7\System.DirectoryServices.dll'
using namespace System.DirectoryServices.ActiveDirectory

class myDirectoryClass : System.DirectoryServices.ActiveDirectory.DirectoryContext
{

  [DirectoryContext]$domain

  myDirectoryClass([DirectoryContextType]$ctx) : base($ctx)
  {
    $this.domain = [DirectoryContext]::new([DirectoryContextType]$ctx)
  }

}

$myDomain = [myDirectoryClass]::new([DirectoryContextType]::Domain)
$myDomain
```

```Output
domain                                                    Name UserName ContextType
------                                                    ---- -------- -----------
System.DirectoryServices.ActiveDirectory.DirectoryContext                    Domain
```
