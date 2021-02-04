---
description: Ermöglicht Ihnen, anzugeben, welche Namespaces in der Sitzung verwendet werden.
Locale: en-US
ms.date: 01/19/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: e3bdf9e1285fb8eaa2bdd83a03cce5bd1baa0e8b
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "98620155"
---
# <a name="about-using"></a><span data-ttu-id="d3d24-103">Informationen zur Verwendung von</span><span class="sxs-lookup"><span data-stu-id="d3d24-103">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="d3d24-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d3d24-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="d3d24-105">Ermöglicht Ihnen, anzugeben, welche Namespaces in der Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3d24-105">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="d3d24-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d3d24-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="d3d24-107">Mit der- `using` Anweisung können Sie angeben, welche Namespaces in der Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3d24-107">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="d3d24-108">Das Hinzufügen von Namespaces vereinfacht die Verwendung von .NET-Klassen und-Membern und ermöglicht das Importieren von Klassen aus Skript Modulen und Assemblys.</span><span class="sxs-lookup"><span data-stu-id="d3d24-108">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="d3d24-109">Die- `using` Anweisungen müssen vor allen anderen Anweisungen in einem Skript oder Modul stehen.</span><span class="sxs-lookup"><span data-stu-id="d3d24-109">The `using` statements must come before any other statements in a script or module.</span></span> <span data-ttu-id="d3d24-110">Es kann keine nicht kommentierten Anweisung vorangestellt werden, einschließlich der Parameter.</span><span class="sxs-lookup"><span data-stu-id="d3d24-110">No uncommented statement can precede it, including parameters.</span></span>

<span data-ttu-id="d3d24-111">Die `using` Anweisung darf keine Variablen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d3d24-111">The `using` statement must not contain any variables.</span></span>

<span data-ttu-id="d3d24-112">Die- `using` Anweisung sollte nicht mit dem bereichsmodifizierer `using:` für Variablen verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="d3d24-112">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="d3d24-113">Weitere Informationen finden Sie unter [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d3d24-113">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="namespace-syntax"></a><span data-ttu-id="d3d24-114">Namespace Syntax</span><span class="sxs-lookup"><span data-stu-id="d3d24-114">Namespace syntax</span></span>

<span data-ttu-id="d3d24-115">So geben Sie .NET-Namespaces an, aus denen Typen aufgelöst werden sollen:</span><span class="sxs-lookup"><span data-stu-id="d3d24-115">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="d3d24-116">Durch die Angabe eines Namespace wird es einfacher, auf Typen anhand ihrer Kurznamen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d3d24-116">Specifying a namespace makes it easier to reference types by their short names.</span></span>

## <a name="module-syntax"></a><span data-ttu-id="d3d24-117">Modul Syntax</span><span class="sxs-lookup"><span data-stu-id="d3d24-117">Module syntax</span></span>

<span data-ttu-id="d3d24-118">So laden Sie Klassen aus einem PowerShell-Modul:</span><span class="sxs-lookup"><span data-stu-id="d3d24-118">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="d3d24-119">Der Wert von `<module-name>` kann ein Modulname, eine vollständige Modul Spezifikation oder ein Pfad zu einer Modul Datei sein.</span><span class="sxs-lookup"><span data-stu-id="d3d24-119">The value of `<module-name>` can be a module name, a full module specification, or a path to a module file.</span></span>

<span data-ttu-id="d3d24-120">Wenn `<module-name>` ein Pfad ist, kann der Pfad voll qualifiziert oder relativ sein.</span><span class="sxs-lookup"><span data-stu-id="d3d24-120">When `<module-name>` is a path, the path can be fully qualified or relative.</span></span> <span data-ttu-id="d3d24-121">Ein relativer Pfad wird relativ zum Skript aufgelöst, das die using-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="d3d24-121">A relative path is resolved relative to the script that contains the using statement.</span></span>

<span data-ttu-id="d3d24-122">Wenn `<module-name>` eine Name-oder Modul Spezifikation ist, durchsucht PowerShell den **psmodulepath** nach dem angegebenen Modul.</span><span class="sxs-lookup"><span data-stu-id="d3d24-122">When `<module-name>` is a name or module specification, PowerShell searches the **PSModulePath** for the specified module.</span></span>

<span data-ttu-id="d3d24-123">Eine Modul Spezifikation ist eine Hash Tabelle mit den folgenden Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d3d24-123">A module specification is a hash table that has the following keys.</span></span>

- <span data-ttu-id="d3d24-124">`ModuleName` - **Erforderlich** Gibt den Namen des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="d3d24-124">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="d3d24-125">`GUID` - **Optional** Gibt die GUID des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="d3d24-125">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="d3d24-126">Es ist auch **erforderlich** , einen der drei folgenden Schlüssel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d3d24-126">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="d3d24-127">Diese Schlüssel können nicht gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3d24-127">These keys can't be used together.</span></span>
  - <span data-ttu-id="d3d24-128">`ModuleVersion` : Gibt eine zulässige Mindestversion des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="d3d24-128">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="d3d24-129">`RequiredVersion` : Gibt eine exakte, erforderliche Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="d3d24-129">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="d3d24-130">`MaximumVersion` : Gibt die maximal zulässige Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="d3d24-130">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

<span data-ttu-id="d3d24-131">Die- `using module` Anweisung importiert Klassen aus dem Stamm Modul ( `ModuleToProcess` ) eines Skript Moduls oder eines binären Moduls.</span><span class="sxs-lookup"><span data-stu-id="d3d24-131">The `using module` statement imports classes from the root module (`ModuleToProcess`) of a script module or binary module.</span></span> <span data-ttu-id="d3d24-132">Klassen, die in geschposteten Modulen oder Klassen definiert sind, die in Skripts definiert sind, die in das Modul eingefügt werden, werden nicht konsistent importiert.</span><span class="sxs-lookup"><span data-stu-id="d3d24-132">It does not consistently import classes defined in nested modules or classes defined in scripts that are dot-sourced into the module.</span></span> <span data-ttu-id="d3d24-133">Klassen, die für Benutzer außerhalb des Moduls verfügbar sein sollen, sollten im Stamm Modul definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d3d24-133">Classes that you want to be available to users outside of the module should be defined in the root module.</span></span>

<span data-ttu-id="d3d24-134">Während der Entwicklung eines Skript Moduls ist es üblich, Änderungen am Code vorzunehmen und dann die neue Version des Moduls `Import-Module` mit dem **Force** -Parameter zu laden.</span><span class="sxs-lookup"><span data-stu-id="d3d24-134">During development of a script module, it is common to make changes to the code then load the new version of the module using `Import-Module` with the **Force** parameter.</span></span> <span data-ttu-id="d3d24-135">Dies funktioniert nur bei Änderungen an Funktionen im Stamm Modul.</span><span class="sxs-lookup"><span data-stu-id="d3d24-135">This works for changes to functions in the root module only.</span></span> <span data-ttu-id="d3d24-136">`Import-Module` führt keine erneuten Laden von Netz Modulen aus.</span><span class="sxs-lookup"><span data-stu-id="d3d24-136">`Import-Module` does not reload any nested modules.</span></span> <span data-ttu-id="d3d24-137">Außerdem gibt es keine Möglichkeit, aktualisierte Klassen zu laden.</span><span class="sxs-lookup"><span data-stu-id="d3d24-137">Also, there is no way to load any updated classes.</span></span>

<span data-ttu-id="d3d24-138">Um sicherzustellen, dass Sie die neueste Version ausführen, müssen Sie das Modul mit dem `Remove-Module` Cmdlet entladen.</span><span class="sxs-lookup"><span data-stu-id="d3d24-138">To ensure that you are running the latest version, you must unload the module using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="d3d24-139">`Remove-Module` entfernt das Stamm Modul, alle in den Modulen definierten Klassen und Klassen.</span><span class="sxs-lookup"><span data-stu-id="d3d24-139">`Remove-Module` removes the root module, all nested modules, and any classes defined in the modules.</span></span> <span data-ttu-id="d3d24-140">Anschließend können Sie das Modul und die Klassen mithilfe von `Import-Module` und der-Anweisung erneut laden `using module` .</span><span class="sxs-lookup"><span data-stu-id="d3d24-140">Then you can reload the module and the classes using `Import-Module` and the `using module` statement.</span></span>

## <a name="assembly-syntax"></a><span data-ttu-id="d3d24-141">Assemblysyntax</span><span class="sxs-lookup"><span data-stu-id="d3d24-141">Assembly syntax</span></span>

<span data-ttu-id="d3d24-142">So laden Sie Typen aus einer .NET-Assembly vorab:</span><span class="sxs-lookup"><span data-stu-id="d3d24-142">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
```

<span data-ttu-id="d3d24-143">Durch das Laden einer Assembly werden .NET-Typen aus dieser Assembly zur Analysezeit vorab in ein Skript geladen.</span><span class="sxs-lookup"><span data-stu-id="d3d24-143">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="d3d24-144">Dies ermöglicht es Ihnen, neue PowerShell-Klassen zu erstellen, die Typen aus der vorgeladenen Assembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3d24-144">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="d3d24-145">Wenn Sie keine neuen PowerShell-Klassen erstellen, verwenden Sie `Add-Type` stattdessen das-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d3d24-145">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="d3d24-146">Weitere Informationen finden Sie unter [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span><span class="sxs-lookup"><span data-stu-id="d3d24-146">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="d3d24-147">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d3d24-147">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="d3d24-148">Beispiel 1: Hinzufügen von Namespaces für die Typname-Auflösung</span><span class="sxs-lookup"><span data-stu-id="d3d24-148">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="d3d24-149">Mit dem folgenden Skript wird der kryptografiehash für die Zeichenfolge "Hallo Welt" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d3d24-149">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="d3d24-150">Beachten Sie `using namespace System.Text` , wie und `using namespace System.IO` die Verweise auf `[UnicodeEncoding]` in `System.Text` und `[Stream]` und auf `[MemoryStream]` in vereinfachen `System.IO` .</span><span class="sxs-lookup"><span data-stu-id="d3d24-150">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

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

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="d3d24-151">Beispiel 2: Laden von Klassen aus einem Skript Modul</span><span class="sxs-lookup"><span data-stu-id="d3d24-151">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="d3d24-152">In diesem Beispiel verfügen wir über ein PowerShell-Skript Modul namens **Cardgames** , das die folgenden Klassen definiert:</span><span class="sxs-lookup"><span data-stu-id="d3d24-152">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="d3d24-153">**Cardgames. Karten**</span><span class="sxs-lookup"><span data-stu-id="d3d24-153">**CardGames.Deck**</span></span>
- <span data-ttu-id="d3d24-154">**Cardgames. Card**</span><span class="sxs-lookup"><span data-stu-id="d3d24-154">**CardGames.Card**</span></span>

<span data-ttu-id="d3d24-155">`Import-Module` und die- `#requires` Anweisung importiert nur die Modulfunktionen, Aliase und Variablen, wie vom Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="d3d24-155">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="d3d24-156">Klassen werden nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="d3d24-156">Classes are not imported.</span></span> <span data-ttu-id="d3d24-157">Der `using module` Befehl importiert das Modul und lädt auch die Klassendefinitionen.</span><span class="sxs-lookup"><span data-stu-id="d3d24-157">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="d3d24-158">Beispiel 3: Laden von Klassen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="d3d24-158">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="d3d24-159">In diesem Beispiel wird eine Assembly geladen, damit Ihre Klassen zum Erstellen neuer PowerShell-Klassen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d3d24-159">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="d3d24-160">Mit dem folgenden Skript wird eine neue PowerShell-Klasse erstellt, die von der **DirectoryContext** -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="d3d24-160">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

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
