---
description: Ermöglicht Ihnen, anzugeben, welche Namespaces in der Sitzung verwendet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: ff6b43c3af1deddb5cb1b4c2e2c86a2cc2cac5d4
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224943"
---
# <a name="about-using"></a><span data-ttu-id="3bf82-104">Informationen zur Verwendung von</span><span class="sxs-lookup"><span data-stu-id="3bf82-104">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="3bf82-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3bf82-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="3bf82-106">Ermöglicht Ihnen, anzugeben, welche Namespaces in der Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3bf82-106">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="3bf82-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3bf82-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="3bf82-108">Mit der- `using` Anweisung können Sie angeben, welche Namespaces in der Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3bf82-108">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="3bf82-109">Das Hinzufügen von Namespaces vereinfacht die Verwendung von .NET-Klassen und-Membern und ermöglicht das Importieren von Klassen aus Skript Modulen und Assemblys.</span><span class="sxs-lookup"><span data-stu-id="3bf82-109">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="3bf82-110">Die- `using` Anweisungen müssen vor allen anderen Anweisungen in einem Skript stehen.</span><span class="sxs-lookup"><span data-stu-id="3bf82-110">The `using` statements must come before any other statements in a script.</span></span>

<span data-ttu-id="3bf82-111">Die- `using` Anweisung sollte nicht mit dem bereichsmodifizierer `using:` für Variablen verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="3bf82-111">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="3bf82-112">Weitere Informationen finden Sie unter [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="3bf82-112">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="3bf82-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bf82-113">Syntax</span></span>

<span data-ttu-id="3bf82-114">So geben Sie .NET-Namespaces an, aus denen Typen aufgelöst werden sollen:</span><span class="sxs-lookup"><span data-stu-id="3bf82-114">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="3bf82-115">So laden Sie Klassen aus einem PowerShell-Modul:</span><span class="sxs-lookup"><span data-stu-id="3bf82-115">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="3bf82-116">So laden Sie Typen aus einer .NET-Assembly vorab:</span><span class="sxs-lookup"><span data-stu-id="3bf82-116">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
using assembly <.NET-namespace>
```

<span data-ttu-id="3bf82-117">Durch die Angabe eines Namespace wird es einfacher, auf Typen anhand ihrer Kurznamen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="3bf82-117">Specifying a namespace makes it easier to reference types by their short names.</span></span>

<span data-ttu-id="3bf82-118">Durch das Laden einer Assembly werden .NET-Typen aus dieser Assembly zur Analysezeit vorab in ein Skript geladen.</span><span class="sxs-lookup"><span data-stu-id="3bf82-118">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="3bf82-119">Dies ermöglicht es Ihnen, neue PowerShell-Klassen zu erstellen, die Typen aus der vorgeladenen Assembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="3bf82-119">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="3bf82-120">In Windows PowerShell 5,1 können Sie die Assembly nach Pfadname oder Name laden.</span><span class="sxs-lookup"><span data-stu-id="3bf82-120">In Windows PowerShell 5.1 you can load the assembly by path name or by name.</span></span> <span data-ttu-id="3bf82-121">Wenn Sie den Namen verwenden, durchsucht PowerShell den globalen Assemblycache (Global Assembly Cache, GAC) der zugeordneten Assembly.</span><span class="sxs-lookup"><span data-stu-id="3bf82-121">When you use the name, PowerShell searches the .NET Global Assembly Cache (GAC) for the associated assembly.</span></span>

<span data-ttu-id="3bf82-122">Wenn Sie keine neuen PowerShell-Klassen erstellen, verwenden Sie `Add-Type` stattdessen das-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3bf82-122">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="3bf82-123">Weitere Informationen finden Sie unter [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span><span class="sxs-lookup"><span data-stu-id="3bf82-123">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="3bf82-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3bf82-124">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="3bf82-125">Beispiel 1: Hinzufügen von Namespaces für die Typname-Auflösung</span><span class="sxs-lookup"><span data-stu-id="3bf82-125">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="3bf82-126">Mit dem folgenden Skript wird der kryptografiehash für die Zeichenfolge "Hallo Welt" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3bf82-126">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="3bf82-127">Beachten Sie `using namespace System.Text` , wie und `using namespace System.IO` die Verweise auf `[UnicodeEncoding]` in `System.Text` und `[Stream]` und auf `[MemoryStream]` in vereinfachen `System.IO` .</span><span class="sxs-lookup"><span data-stu-id="3bf82-127">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

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

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="3bf82-128">Beispiel 2: Laden von Klassen aus einem Skript Modul</span><span class="sxs-lookup"><span data-stu-id="3bf82-128">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="3bf82-129">In diesem Beispiel verfügen wir über ein PowerShell-Skript Modul namens **Cardgames** , das die folgenden Klassen definiert:</span><span class="sxs-lookup"><span data-stu-id="3bf82-129">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="3bf82-130">**Cardgames. Karten**</span><span class="sxs-lookup"><span data-stu-id="3bf82-130">**CardGames.Deck**</span></span>
- <span data-ttu-id="3bf82-131">**Cardgames. Card**</span><span class="sxs-lookup"><span data-stu-id="3bf82-131">**CardGames.Card**</span></span>

<span data-ttu-id="3bf82-132">`Import-Module` und die- `#requires` Anweisung importiert nur die Modulfunktionen, Aliase und Variablen, wie vom Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="3bf82-132">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="3bf82-133">Klassen werden nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="3bf82-133">Classes are not imported.</span></span> <span data-ttu-id="3bf82-134">Der `using module` Befehl importiert das Modul und lädt auch die Klassendefinitionen.</span><span class="sxs-lookup"><span data-stu-id="3bf82-134">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="3bf82-135">Beispiel 3: Laden von Klassen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="3bf82-135">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="3bf82-136">In diesem Beispiel wird eine Assembly geladen, damit Ihre Klassen zum Erstellen neuer PowerShell-Klassen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3bf82-136">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="3bf82-137">Mit dem folgenden Skript wird eine neue PowerShell-Klasse erstellt, die von der **DirectoryContext** -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="3bf82-137">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

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
