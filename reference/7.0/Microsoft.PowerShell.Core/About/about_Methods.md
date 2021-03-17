---
description: Beschreibt die Verwendung von Methoden zum Ausführen von Aktionen für Objekte in PowerShell.
Locale: en-US
ms.date: 03/15/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Methods
ms.openlocfilehash: 9c94de53bf320074c5b8aed1d1670fdd53d6b105
ms.sourcegitcommit: 15f759ca68d17acecab46b52250298d4f2037c4d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2021
ms.locfileid: "103575609"
---
# <a name="about-methods"></a><span data-ttu-id="165c3-103">Informationen zu Methoden</span><span class="sxs-lookup"><span data-stu-id="165c3-103">About methods</span></span>

## <a name="short-description"></a><span data-ttu-id="165c3-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="165c3-104">Short description</span></span>
<span data-ttu-id="165c3-105">Beschreibt die Verwendung von Methoden zum Ausführen von Aktionen für Objekte in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="165c3-105">Describes how to use methods to perform actions on objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="165c3-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="165c3-106">Long description</span></span>

<span data-ttu-id="165c3-107">PowerShell verwendet Objekte zur Darstellung der Elemente in Daten speichern oder den Status des Computers.</span><span class="sxs-lookup"><span data-stu-id="165c3-107">PowerShell uses objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="165c3-108">FileInfo-Objekte stellen z. b. die Dateien in Dateisystem Laufwerken dar, und ProcessInfo-Objekte stellen die Prozesse auf dem Computer dar.</span><span class="sxs-lookup"><span data-stu-id="165c3-108">For example, FileInfo objects represent the files in file system drives and ProcessInfo objects represent the processes on the computer.</span></span>

<span data-ttu-id="165c3-109">-Objekte verfügen über Eigenschaften, die Daten über das Objekt speichern, und Methoden, mit denen Sie das Objekt ändern können.</span><span class="sxs-lookup"><span data-stu-id="165c3-109">Objects have properties, which store data about the object, and methods that let you change the object.</span></span>

<span data-ttu-id="165c3-110">Eine "Methode" ist ein Satz von Anweisungen, die eine Aktion angeben, die Sie für das Objekt ausführen können.</span><span class="sxs-lookup"><span data-stu-id="165c3-110">A "method" is a set of instructions that specify an action you can perform on the object.</span></span> <span data-ttu-id="165c3-111">Beispielsweise enthält das- `FileInfo` Objekt die- `CopyTo` Methode, die die Datei kopiert, die das- `FileInfo` Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="165c3-111">For example, the `FileInfo` object includes the `CopyTo` method that copies the file that the `FileInfo` object represents.</span></span>

<span data-ttu-id="165c3-112">Verwenden Sie das-Cmdlet, um die Methoden eines beliebigen Objekts zu erhalten `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="165c3-112">To get the methods of any object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="165c3-113">Verwenden Sie die zugehörige Eigenschaft " **Membership Type** " mit dem Wert "Method".</span><span class="sxs-lookup"><span data-stu-id="165c3-113">Use its **MemberType** property with a value of "Method".</span></span> <span data-ttu-id="165c3-114">Der folgende Befehl ruft die Methoden von Process-Objekten ab.</span><span class="sxs-lookup"><span data-stu-id="165c3-114">The following command gets the methods of process objects.</span></span>

```powershell
Get-Process | Get-Member -MemberType Method
```

```Output
TypeName: System.Diagnostics.Process

Name                      MemberType Definition
----                      ---------- ----------
BeginErrorReadLine        Method     System.Void BeginErrorReadLine()
BeginOutputReadLine       Method     System.Void BeginOutputReadLine()
...
Kill                      Method     System.Void Kill()
Refresh                   Method     System.Void Refresh()
Start                     Method     bool Start()
ToString                  Method     string ToString()
WaitForExit               Method     bool WaitForExit(int milliseconds), ...
WaitForInputIdle          Method     bool WaitForInputIdle(int millisecon...
```

<span data-ttu-id="165c3-115">Geben Sie einen Punkt (.), den Methodennamen und eine Reihe von Klammern "()" ein, um eine Methode eines Objekts auszuführen oder zu "aufrufen".</span><span class="sxs-lookup"><span data-stu-id="165c3-115">To perform or "invoke" a method of an object, type a dot (.), the method name, and a set of parentheses "()".</span></span> <span data-ttu-id="165c3-116">Wenn die Methode über Argumente verfügt, platzieren Sie die Argument Werte in den Klammern.</span><span class="sxs-lookup"><span data-stu-id="165c3-116">If the method has arguments, place the argument values inside the parentheses.</span></span> <span data-ttu-id="165c3-117">Die Klammern sind für jeden Methoden aufrufbedarf erforderlich, auch wenn keine Argumente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="165c3-117">The parentheses are required for every method call, even when there are no arguments.</span></span> <span data-ttu-id="165c3-118">Wenn die Methode mehrere Argumente annimmt, sollten Sie durch Kommas getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="165c3-118">If the method takes multiple arguments, they should be separated by commas.</span></span>

<span data-ttu-id="165c3-119">Beispielsweise ruft der folgende Befehl die Kill-Methode von Prozessen auf, um den Notepad-Prozess auf dem Computer zu beenden.</span><span class="sxs-lookup"><span data-stu-id="165c3-119">For example, the following command invokes the Kill method of processes to end the Notepad process on the computer.</span></span>

```powershell
$notepad = Get-Process notepad
$notepad.Kill()
```

<span data-ttu-id="165c3-120">Dieses Beispiel kann durch Kombinieren der obigen-Anweisungen verkürzt werden.</span><span class="sxs-lookup"><span data-stu-id="165c3-120">This example can be shortened by combining the above statements.</span></span>

```powershell
(Get-Process Notepad).Kill()
```

<span data-ttu-id="165c3-121">Der `Get-Process` Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er ausgeführt wird, bevor die Kill-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="165c3-121">The `Get-Process` command is enclosed in parentheses to ensure that it runs before the Kill method is invoked.</span></span> <span data-ttu-id="165c3-122">Die- `Kill` Methode wird dann für das zurückgegebene- `Process` Objekt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="165c3-122">The `Kill` method is then invoked on the returned `Process` object.</span></span>

<span data-ttu-id="165c3-123">Eine weitere sehr nützliche Methode ist die- `Replace` Methode von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="165c3-123">Another very useful method is the `Replace` method of strings.</span></span> <span data-ttu-id="165c3-124">Die- `Replace` Methode ersetzt Text in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="165c3-124">The `Replace` method, replaces text within a string.</span></span> <span data-ttu-id="165c3-125">Im folgenden Beispiel kann der Punkt (.) direkt nach dem endanführungs Zeichen der Zeichenfolge platziert werden.</span><span class="sxs-lookup"><span data-stu-id="165c3-125">In the example below, the dot (.) can be placed immediately after the end quote of the string.</span></span>

```powershell
'this is rocket science'.Replace('rocket', 'rock')
```

```Output
this is rock science
```

<span data-ttu-id="165c3-126">Wie in den vorherigen Beispielen gezeigt, können Sie eine Methode für ein Objekt aufrufen, das Sie mit einem Befehl, einem Objekt in einer Variablen oder etwas, das zu einem Objekt führt (z. b. eine Zeichenfolge in Anführungszeichen).</span><span class="sxs-lookup"><span data-stu-id="165c3-126">As shown in the previous examples, you can invoke a method on an object that you get by using a command, an object in a variable, or anything that results in an object (like a string in quotes).</span></span>

<span data-ttu-id="165c3-127">Ab PowerShell 4,0 wird der Methodenaufruf mithilfe dynamischer Methodennamen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="165c3-127">Starting in PowerShell 4.0, method invocation by using dynamic method names is supported.</span></span>

## <a name="learning-about-methods"></a><span data-ttu-id="165c3-128">Erlernen von Methoden</span><span class="sxs-lookup"><span data-stu-id="165c3-128">Learning about methods</span></span>

<span data-ttu-id="165c3-129">Um Definitionen der Methoden eines Objekts zu suchen, navigieren Sie zu Hilfe Themen für den Objekttyp, und suchen Sie nach der entsprechenden Methoden Seite.</span><span class="sxs-lookup"><span data-stu-id="165c3-129">To find definitions of the methods of an object, go to help topic for the object type and look for its methods page.</span></span> <span data-ttu-id="165c3-130">Auf der folgenden Seite werden z. b. die Methoden von Process Objects [System. Diagnostics. Process](/dotnet/api/system.diagnostics.process#methods)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="165c3-130">For example, the following page describes the methods of process objects [System.Diagnostics.Process](/dotnet/api/system.diagnostics.process#methods).</span></span>

<span data-ttu-id="165c3-131">Überprüfen Sie die Methoden Definition, die dem Syntax Diagramm eines PowerShell-Cmdlets ähnelt, um die Argumente einer Methode zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="165c3-131">To determine the arguments of a method, review the method definition, which is like the syntax diagram of a PowerShell cmdlet.</span></span>

<span data-ttu-id="165c3-132">Eine Methoden Definition kann mindestens eine Methoden Signatur aufweisen, die den Parametersätzen von PowerShell-Cmdlets ähnelt.</span><span class="sxs-lookup"><span data-stu-id="165c3-132">A method definition might have one or more method signatures, which are like the parameter sets of PowerShell cmdlets.</span></span> <span data-ttu-id="165c3-133">Die Signaturen zeigen alle gültigen Formate von Befehlen zum Aufrufen der Methode an.</span><span class="sxs-lookup"><span data-stu-id="165c3-133">The signatures show all of the valid formats of commands to invoke the method.</span></span>

<span data-ttu-id="165c3-134">Beispielsweise enthält die- `CopyTo` Methode der- `FileInfo` Klasse die folgenden beiden Methoden Signaturen:</span><span class="sxs-lookup"><span data-stu-id="165c3-134">For example, the `CopyTo` method of the `FileInfo` class contains the following two method signatures:</span></span>

```
    CopyTo(String destFileName)
    CopyTo(String destFileName, Boolean overwrite)
```

<span data-ttu-id="165c3-135">Die erste Methoden Signatur nimmt den Namen der Ziel Datei (und einen Pfad).</span><span class="sxs-lookup"><span data-stu-id="165c3-135">The first method signature takes the destination file name (and a path).</span></span> <span data-ttu-id="165c3-136">Im folgenden Beispiel wird die erste `CopyTo` Methode verwendet, um die `Final.txt` Datei in das Verzeichnis zu kopieren `C:\Bin` .</span><span class="sxs-lookup"><span data-stu-id="165c3-136">The following example uses the first `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt")
```

> [!NOTE]
> <span data-ttu-id="165c3-137">Im Gegensatz zum- _Argument_ Modus von PowerShell werden Objektmethoden im _Ausdrucks_ Modus ausgeführt. Hierbei handelt es sich um eine Pass-Through-Version von .NET Framework, auf der PowerShell basiert.</span><span class="sxs-lookup"><span data-stu-id="165c3-137">Unlike PowerShell's _argument_ mode, object methods execute in _expression_ mode, which is a pass-through to the .NET framework that PowerShell is built on.</span></span> <span data-ttu-id="165c3-138">Im _Ausdrucks_ Modus sind **bareword** -Argumente (Zeichen folgen ohne Anführungszeichen) nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="165c3-138">In _expression_ mode **bareword** arguments (unquoted strings) are not allowed.</span></span> <span data-ttu-id="165c3-139">Dieser Unterschied wird angezeigt, wenn Sie einen Pfad als Parameter und den Pfad als Argument verwenden.</span><span class="sxs-lookup"><span data-stu-id="165c3-139">You can see this difference when using a the path as a parameter, versus the path as an argument.</span></span> <span data-ttu-id="165c3-140">Weitere Informationen finden Sie unter [about_Parsing](about_Parsing.md)</span><span class="sxs-lookup"><span data-stu-id="165c3-140">You can read more about parsing modes in [about_Parsing](about_Parsing.md)</span></span>

<span data-ttu-id="165c3-141">Die zweite Methoden Signatur nimmt einen Ziel Dateinamen und einen booleschen Wert an, der bestimmt, ob die Zieldatei überschrieben werden soll, falls Sie bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="165c3-141">The second method signature takes a destination file name and a Boolean value that determines whether the destination file should be overwritten, if it already exists.</span></span>

<span data-ttu-id="165c3-142">Im folgenden Beispiel wird die zweite Methode verwendet, um `CopyTo` die `Final.txt` Datei in das Verzeichnis zu kopieren `C:\Bin` und vorhandene Dateien zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="165c3-142">The following example uses the second `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory, and to overwrite existing files.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt", $true)
```

## <a name="methods-of-scalar-objects-and-collections"></a><span data-ttu-id="165c3-143">Methoden von skalaren Objekten und Auflistungen</span><span class="sxs-lookup"><span data-stu-id="165c3-143">Methods of Scalar objects and Collections</span></span>

<span data-ttu-id="165c3-144">Die Methoden eines Objekts ("Skalar") eines bestimmten Typs unterscheiden sich häufig von den Methoden einer Auflistung von Objekten desselben Typs.</span><span class="sxs-lookup"><span data-stu-id="165c3-144">The methods of one ("scalar") object of a particular type are often different from the methods of a collection of objects of the same type.</span></span>

<span data-ttu-id="165c3-145">Beispielsweise verfügt jeder Prozess über eine- `Kill` Methode, aber eine Auflistung von Prozessen weist keine Kill-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="165c3-145">For example, every process has a `Kill` method, but a collection of processes does not have a Kill method.</span></span>

<span data-ttu-id="165c3-146">Ab PowerShell 3,0 versucht PowerShell, Skript Fehler zu verhindern, die sich aus den unterschiedlichen Methoden von skalaren Objekten und Auflistungen ergeben.</span><span class="sxs-lookup"><span data-stu-id="165c3-146">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing methods of scalar objects and collections.</span></span>

<span data-ttu-id="165c3-147">Wenn Sie eine Sammlung übermitteln, aber eine Methode anfordern, die nur in einzelnen (skalaren) Objekten vorhanden ist, ruft PowerShell die-Methode für jedes Objekt in der Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="165c3-147">If you submit a collection, but request a method that exists only on single ("scalar") objects, PowerShell invokes the method on every object in the collection.</span></span>

<span data-ttu-id="165c3-148">Wenn die-Methode für die einzelnen Objekte und für die Auflistung vorhanden ist, wird nur die-Methode der-Auflistung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="165c3-148">If the method exists on the individual objects and on the collection, only the collection's method is invoked.</span></span>

<span data-ttu-id="165c3-149">Diese Funktion funktioniert auch mit Eigenschaften von skalaren Objekten und Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="165c3-149">This feature also works on properties of scalar objects and collections.</span></span> <span data-ttu-id="165c3-150">Weitere Informationen finden Sie unter [about_Properties](about_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="165c3-150">For more information, see [about_Properties](about_Properties.md).</span></span>

### <a name="examples"></a><span data-ttu-id="165c3-151">Beispiele</span><span class="sxs-lookup"><span data-stu-id="165c3-151">Examples</span></span>

<span data-ttu-id="165c3-152">Im folgenden Beispiel wird die **Kill** -Methode einzelner Prozess Objekte in einer Auflistung von-Objekten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="165c3-152">The following example runs the **Kill** method of individual process objects in a collection of objects.</span></span>

<span data-ttu-id="165c3-153">Der erste Befehl startet drei Instanzen des Notepad-Prozesses.</span><span class="sxs-lookup"><span data-stu-id="165c3-153">The first command starts three instances of the Notepad process.</span></span> <span data-ttu-id="165c3-154">`Get-Process` Ruft alle drei Instanzen des Notepad-Prozesses ab und speichert Sie in der `$p` Variablen.</span><span class="sxs-lookup"><span data-stu-id="165c3-154">`Get-Process` gets all three instance of the Notepad process and saves them in the `$p` variable.</span></span>

```powershell
Notepad; Notepad; Notepad
$p = Get-Process Notepad
$p.Count
```

```Output
3
```

<span data-ttu-id="165c3-155">Der nächste Befehl führt die **Kill** -Methode für alle drei Prozesse in der `$p` Variablen aus.</span><span class="sxs-lookup"><span data-stu-id="165c3-155">The next command runs the **Kill** method on all three processes in the `$p` variable.</span></span> <span data-ttu-id="165c3-156">Dieser Befehl funktioniert, obwohl eine Auflistung von Prozessen keine-Methode besitzt `Kill` .</span><span class="sxs-lookup"><span data-stu-id="165c3-156">This command works even though a collection of processes does not have a `Kill` method.</span></span>

```powershell
$p.Kill()
Get-Process Notepad
```

<span data-ttu-id="165c3-157">Der- `Get-Process` Befehl bestätigt, dass die- `Kill` Methode funktioniert hat.</span><span class="sxs-lookup"><span data-stu-id="165c3-157">The `Get-Process` command confirms that the `Kill` method worked.</span></span>

```Output
Get-Process : Cannot find a process with the name "notepad". Verify the proc
ess name and call the cmdlet again.
At line:1 char:12
+ Get-Process <<<<  notepad
    + CategoryInfo          : ObjectNotFound: (notepad:String) [Get-Process]
, ProcessCommandException
    + FullyQualifiedErrorId : NoProcessFoundForGivenName,Microsoft.PowerShel
l.Commands.GetProcessCommand
```

<span data-ttu-id="165c3-158">Dieses Beispiel ist funktional äquivalent zur Verwendung des- `Foreach-Object` Cmdlets, um die-Methode für jedes Objekt in der Auflistung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="165c3-158">This example is functionally equivalent to using the `Foreach-Object` cmdlet to run the method on each object in the collection.</span></span>

```powershell
$p | ForEach-Object {$_.Kill()}
```

### <a name="foreach-and-where-methods"></a><span data-ttu-id="165c3-159">Foreach-Methode und Where-Methode</span><span class="sxs-lookup"><span data-stu-id="165c3-159">ForEach and Where methods</span></span>

<span data-ttu-id="165c3-160">Ab PowerShell 4,0 wird das Filtern von Sammlungen mithilfe einer Methoden Syntax unterstützt.</span><span class="sxs-lookup"><span data-stu-id="165c3-160">Beginning in PowerShell 4.0, collection filtering using a method syntax is supported.</span></span> <span data-ttu-id="165c3-161">Dies ermöglicht die Verwendung von zwei neuen Methoden beim Umgang mit Sammlungen `ForEach` und `Where` .</span><span class="sxs-lookup"><span data-stu-id="165c3-161">This allows use of two new methods when dealing with collections `ForEach` and `Where`.</span></span>

<span data-ttu-id="165c3-162">Weitere Informationen zu diesen Methoden finden Sie unter [about_arrays](about_arrays.md).</span><span class="sxs-lookup"><span data-stu-id="165c3-162">You can read more about these methods in [about_arrays](about_arrays.md)</span></span>

## <a name="calling-a-specific-method-when-multiple-overloads-exist"></a><span data-ttu-id="165c3-163">Aufrufen einer bestimmten Methode, wenn mehrere über Ladungen vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="165c3-163">Calling a specific method when multiple overloads exist</span></span>

<span data-ttu-id="165c3-164">Beachten Sie das folgende Szenario, wenn Sie .NET-Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="165c3-164">Consider the following scenario when calling .NET methods.</span></span> <span data-ttu-id="165c3-165">Wenn eine Methode ein-Objekt akzeptiert, aber über eine-Schnittstelle verfügt, die einen spezifischeren Typ annimmt, wählt PowerShell die Methode aus, die das Objekt akzeptiert, es sei denn, Sie haben es explizit in diese Schnittstelle umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="165c3-165">If a method takes an object but has an overload via an interface taking a more specific type, PowerShell chooses the method that accepts the object unless you explicitly cast it to that interface.</span></span>

```powershell
Add-Type -TypeDefinition @'

   // Interface
   public interface IFoo {
     string Bar(int p);
   }

   // Type that implements the interface
   public class Foo : IFoo {

   // Direct member method named 'Bar'
   public string Bar(object p) { return $"object: {p}"; }

   // *Explicit* implementation of IFoo's 'Bar' method().
   string IFoo.Bar(int p) {
       return $"int: {p}";
   }

}
'@
```

<span data-ttu-id="165c3-166">In diesem Beispiel wurde die weniger spezifische Überladung der `object` **Bar** -Methode ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="165c3-166">In this example the less specific `object` overload of the **Bar** method was chosen.</span></span>

```powershell
[Foo]::new().Bar(1)
```

```Output
object: 1
```

<span data-ttu-id="165c3-167">In diesem Beispiel konvertieren wir die-Methode in die-Schnittstelle **IFoo** , um die spezifischere Überlastung der **Bar** -Methode auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="165c3-167">In this example we cast the method to the interface **IFoo** to select the more specific overload of the **Bar** method.</span></span>

```powershell
([IFoo] [Foo]::new()).Bar(1)
```

```Output
int: 1
```

## <a name="using-net-methods-that-take-filesystem-paths"></a><span data-ttu-id="165c3-168">Verwenden von .NET-Methoden, die Dateisystem Pfade übernehmen</span><span class="sxs-lookup"><span data-stu-id="165c3-168">Using .NET methods that take filesystem paths</span></span>

<span data-ttu-id="165c3-169">PowerShell unterstützt mehrere Runspaces pro Prozess.</span><span class="sxs-lookup"><span data-stu-id="165c3-169">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="165c3-170">Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.</span><span class="sxs-lookup"><span data-stu-id="165c3-170">Each runspace has its own _current directory_.</span></span> <span data-ttu-id="165c3-171">Dies entspricht nicht dem Arbeitsverzeichnis des aktuellen Prozesses: `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="165c3-171">This is not the same as the working directory of the current process: `[System.Environment]::CurrentDirectory`.</span></span>

<span data-ttu-id="165c3-172">.NET-Methoden verwenden das Arbeitsverzeichnis für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="165c3-172">.NET methods use the process working directory.</span></span> <span data-ttu-id="165c3-173">PowerShell-Cmdlets verwenden den Runspace-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="165c3-173">PowerShell cmdlets use the Runspace location.</span></span> <span data-ttu-id="165c3-174">Außerdem funktionieren .NET-Methoden nur mit nativen Dateisystem Pfaden, nicht mit PowerShell-Pfad Objekten.</span><span class="sxs-lookup"><span data-stu-id="165c3-174">Also, .NET methods only work with native filesystem paths, not PowerShell Path objects.</span></span> <span data-ttu-id="165c3-175">Um PowerShell-Pfade mit .NET-Methoden zu verwenden, müssen Sie den Pfad zu einem Dateisystem eigenen Pfad auflösen, bevor Sie ihn an die .NET-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="165c3-175">To use PowerShell paths with .NET methods, you must resolve the path to a filesystem-native path before passing it to the .NET method.</span></span>

## <a name="see-also"></a><span data-ttu-id="165c3-176">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="165c3-176">See Also</span></span>

[<span data-ttu-id="165c3-177">about_Objects</span><span class="sxs-lookup"><span data-stu-id="165c3-177">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="165c3-178">about_Properties</span><span class="sxs-lookup"><span data-stu-id="165c3-178">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="165c3-179">Get-Member</span><span class="sxs-lookup"><span data-stu-id="165c3-179">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
