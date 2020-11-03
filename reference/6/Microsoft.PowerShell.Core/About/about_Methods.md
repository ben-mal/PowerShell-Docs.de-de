---
description: Beschreibt die Verwendung von Methoden zum Ausführen von Aktionen für Objekte in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Methods
ms.openlocfilehash: 45a57efdf16779cfed0df627976270871068ed1f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221503"
---
# <a name="about-methods"></a><span data-ttu-id="a94ac-104">Informationen zu Methoden</span><span class="sxs-lookup"><span data-stu-id="a94ac-104">About methods</span></span>

## <a name="short-description"></a><span data-ttu-id="a94ac-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a94ac-105">Short description</span></span>
<span data-ttu-id="a94ac-106">Beschreibt die Verwendung von Methoden zum Ausführen von Aktionen für Objekte in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a94ac-106">Describes how to use methods to perform actions on objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a94ac-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a94ac-107">Long description</span></span>

<span data-ttu-id="a94ac-108">PowerShell verwendet Objekte zur Darstellung der Elemente in Daten speichern oder den Status des Computers.</span><span class="sxs-lookup"><span data-stu-id="a94ac-108">PowerShell uses objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="a94ac-109">FileInfo-Objekte stellen z. b. die Dateien in Dateisystem Laufwerken dar, und ProcessInfo-Objekte stellen die Prozesse auf dem Computer dar.</span><span class="sxs-lookup"><span data-stu-id="a94ac-109">For example, FileInfo objects represent the files in file system drives and ProcessInfo objects represent the processes on the computer.</span></span>

<span data-ttu-id="a94ac-110">-Objekte verfügen über Eigenschaften, die Daten über das Objekt speichern, und Methoden, mit denen Sie das Objekt ändern können.</span><span class="sxs-lookup"><span data-stu-id="a94ac-110">Objects have properties, which store data about the object, and methods that let you change the object.</span></span>

<span data-ttu-id="a94ac-111">Eine "Methode" ist ein Satz von Anweisungen, die eine Aktion angeben, die Sie für das Objekt ausführen können.</span><span class="sxs-lookup"><span data-stu-id="a94ac-111">A "method" is a set of instructions that specify an action you can perform on the object.</span></span> <span data-ttu-id="a94ac-112">Beispielsweise enthält das- `FileInfo` Objekt die- `CopyTo` Methode, die die Datei kopiert, die das- `FileInfo` Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="a94ac-112">For example, the `FileInfo` object includes the `CopyTo` method that copies the file that the `FileInfo` object represents.</span></span>

<span data-ttu-id="a94ac-113">Verwenden Sie das-Cmdlet, um die Methoden eines beliebigen Objekts zu erhalten `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="a94ac-113">To get the methods of any object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="a94ac-114">Verwenden Sie die zugehörige Eigenschaft " **Membership Type** " mit dem Wert "Method".</span><span class="sxs-lookup"><span data-stu-id="a94ac-114">Use its **MemberType** property with a value of "Method".</span></span> <span data-ttu-id="a94ac-115">Der folgende Befehl ruft die Methoden von Process-Objekten ab.</span><span class="sxs-lookup"><span data-stu-id="a94ac-115">The following command gets the methods of process objects.</span></span>

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

<span data-ttu-id="a94ac-116">Geben Sie einen Punkt (.), den Methodennamen und eine Reihe von Klammern "()" ein, um eine Methode eines Objekts auszuführen oder zu "aufrufen".</span><span class="sxs-lookup"><span data-stu-id="a94ac-116">To perform or "invoke" a method of an object, type a dot (.), the method name, and a set of parentheses "()".</span></span> <span data-ttu-id="a94ac-117">Wenn die Methode über Argumente verfügt, platzieren Sie die Argument Werte in den Klammern.</span><span class="sxs-lookup"><span data-stu-id="a94ac-117">If the method has arguments, place the argument values inside the parentheses.</span></span> <span data-ttu-id="a94ac-118">Die Klammern sind für jeden Methoden aufrufbedarf erforderlich, auch wenn keine Argumente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a94ac-118">The parentheses are required for every method call, even when there are no arguments.</span></span> <span data-ttu-id="a94ac-119">Wenn die Methode mehrere Argumente annimmt, sollten Sie durch Kommas getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="a94ac-119">If the method takes multiple arguments, they should be separated by commas.</span></span>

<span data-ttu-id="a94ac-120">Beispielsweise ruft der folgende Befehl die Kill-Methode von Prozessen auf, um den Notepad-Prozess auf dem Computer zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a94ac-120">For example, the following command invokes the Kill method of processes to end the Notepad process on the computer.</span></span>

```powershell
$notepad = Get-Process notepad
$notepad.Kill()
```

<span data-ttu-id="a94ac-121">Dieses Beispiel kann durch Kombinieren der obigen-Anweisungen verkürzt werden.</span><span class="sxs-lookup"><span data-stu-id="a94ac-121">This example can be shortened by combining the above statements.</span></span>

```powershell
(Get-Process Notepad).Kill()
```

<span data-ttu-id="a94ac-122">Der `Get-Process` Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er ausgeführt wird, bevor die Kill-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a94ac-122">The `Get-Process` command is enclosed in parentheses to ensure that it runs before the Kill method is invoked.</span></span> <span data-ttu-id="a94ac-123">Die- `Kill` Methode wird dann für das zurückgegebene- `Process` Objekt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a94ac-123">The `Kill` method is then invoked on the returned `Process` object.</span></span>

<span data-ttu-id="a94ac-124">Eine weitere sehr nützliche Methode ist die- `Replace` Methode von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="a94ac-124">Another very useful method is the `Replace` method of strings.</span></span> <span data-ttu-id="a94ac-125">Die- `Replace` Methode ersetzt Text in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a94ac-125">The `Replace` method, replaces text within a string.</span></span> <span data-ttu-id="a94ac-126">Im folgenden Beispiel kann der Punkt (.) direkt nach dem endanführungs Zeichen der Zeichenfolge platziert werden.</span><span class="sxs-lookup"><span data-stu-id="a94ac-126">In the example below, the dot (.) can be placed immediately after the end quote of the string.</span></span>

```powershell
'this is rocket science'.Replace('rocket', 'rock')
```

```Output
this is rock science
```

<span data-ttu-id="a94ac-127">Wie in den vorherigen Beispielen gezeigt, können Sie eine Methode für ein Objekt aufrufen, das Sie mit einem Befehl, einem Objekt in einer Variablen oder etwas, das zu einem Objekt führt (z. b. eine Zeichenfolge in Anführungszeichen).</span><span class="sxs-lookup"><span data-stu-id="a94ac-127">As shown in the previous examples, you can invoke a method on an object that you get by using a command, an object in a variable, or anything that results in an object (like a string in quotes).</span></span>

<span data-ttu-id="a94ac-128">Ab PowerShell 4,0 wird der Methodenaufruf mithilfe dynamischer Methodennamen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a94ac-128">Starting in PowerShell 4.0, method invocation by using dynamic method names is supported.</span></span>

### <a name="learning-about-methods"></a><span data-ttu-id="a94ac-129">Erlernen von Methoden</span><span class="sxs-lookup"><span data-stu-id="a94ac-129">Learning about methods</span></span>

<span data-ttu-id="a94ac-130">Um Definitionen der Methoden eines Objekts zu finden, wechseln Sie zum Hilfethema für den Objekttyp in MSDN, und suchen Sie nach den zugehörigen Methoden.</span><span class="sxs-lookup"><span data-stu-id="a94ac-130">To find definitions of the methods of an object, go to help topic for the object type in MSDN and look for its methods page.</span></span> <span data-ttu-id="a94ac-131">Auf der folgenden Seite werden z. b. die Methoden von Process Objects [System. Diagnostics. Process](/dotnet/api/system.diagnostics.process#methods)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a94ac-131">For example, the following page describes the methods of process objects [System.Diagnostics.Process](/dotnet/api/system.diagnostics.process#methods).</span></span>

<span data-ttu-id="a94ac-132">Überprüfen Sie die Methoden Definition, die dem Syntax Diagramm eines PowerShell-Cmdlets ähnelt, um die Argumente einer Methode zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a94ac-132">To determine the arguments of a method, review the method definition, which is like the syntax diagram of a PowerShell cmdlet.</span></span>

<span data-ttu-id="a94ac-133">Eine Methoden Definition kann mindestens eine Methoden Signatur aufweisen, die den Parametersätzen von PowerShell-Cmdlets ähnelt.</span><span class="sxs-lookup"><span data-stu-id="a94ac-133">A method definition might have one or more method signatures, which are like the parameter sets of PowerShell cmdlets.</span></span> <span data-ttu-id="a94ac-134">Die Signaturen zeigen alle gültigen Formate von Befehlen zum Aufrufen der Methode an.</span><span class="sxs-lookup"><span data-stu-id="a94ac-134">The signatures show all of the valid formats of commands to invoke the method.</span></span>

<span data-ttu-id="a94ac-135">Beispielsweise enthält die- `CopyTo` Methode der- `FileInfo` Klasse die folgenden beiden Methoden Signaturen:</span><span class="sxs-lookup"><span data-stu-id="a94ac-135">For example, the `CopyTo` method of the `FileInfo` class contains the following two method signatures:</span></span>

```
    CopyTo(String destFileName)
    CopyTo(String destFileName, Boolean overwrite)
```

<span data-ttu-id="a94ac-136">Die erste Methoden Signatur nimmt den Namen der Ziel Datei (und einen Pfad).</span><span class="sxs-lookup"><span data-stu-id="a94ac-136">The first method signature takes the destination file name (and a path).</span></span> <span data-ttu-id="a94ac-137">Im folgenden Beispiel wird die erste `CopyTo` Methode verwendet, um die `Final.txt` Datei in das Verzeichnis zu kopieren `C:\Bin` .</span><span class="sxs-lookup"><span data-stu-id="a94ac-137">The following example uses the first `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt")
```

> [!NOTE]
> <span data-ttu-id="a94ac-138">Im Gegensatz zum- _Argument_ Modus von PowerShell werden Objektmethoden im _Ausdrucks_ Modus ausgeführt. Hierbei handelt es sich um eine Pass-Through-Version von .NET Framework, auf der PowerShell basiert.</span><span class="sxs-lookup"><span data-stu-id="a94ac-138">Unlike PowerShell's _argument_ mode, object methods execute in _expression_ mode, which is a pass-through to the .NET framework that PowerShell is built on.</span></span> <span data-ttu-id="a94ac-139">Im _Ausdrucks_ Modus sind **bareword** -Argumente (Zeichen folgen ohne Anführungszeichen) nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a94ac-139">In _expression_ mode **bareword** arguments (unquoted strings) are not allowed.</span></span> <span data-ttu-id="a94ac-140">Dieser Unterschied wird angezeigt, wenn Sie einen Pfad als Parameter und den Pfad als Argument verwenden.</span><span class="sxs-lookup"><span data-stu-id="a94ac-140">You can see this difference when using a the path as a parameter, versus the path as an argument.</span></span> <span data-ttu-id="a94ac-141">Weitere Informationen finden Sie unter [about_Parsing](about_Parsing.md)</span><span class="sxs-lookup"><span data-stu-id="a94ac-141">You can read more about parsing modes in [about_Parsing](about_Parsing.md)</span></span>

<span data-ttu-id="a94ac-142">Die zweite Methoden Signatur nimmt einen Ziel Dateinamen und einen booleschen Wert an, der bestimmt, ob die Zieldatei überschrieben werden soll, falls Sie bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a94ac-142">The second method signature takes a destination file name and a Boolean value that determines whether the destination file should be overwritten, if it already exists.</span></span>

<span data-ttu-id="a94ac-143">Im folgenden Beispiel wird die zweite Methode verwendet, um `CopyTo` die `Final.txt` Datei in das Verzeichnis zu kopieren `C:\Bin` und vorhandene Dateien zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="a94ac-143">The following example uses the second `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory, and to overwrite existing files.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt", $true)
```

### <a name="methods-of-scalar-objects-and-collections"></a><span data-ttu-id="a94ac-144">Methoden von skalaren Objekten und Auflistungen</span><span class="sxs-lookup"><span data-stu-id="a94ac-144">Methods of Scalar objects and Collections</span></span>

<span data-ttu-id="a94ac-145">Die Methoden eines Objekts ("Skalar") eines bestimmten Typs unterscheiden sich häufig von den Methoden einer Auflistung von Objekten desselben Typs.</span><span class="sxs-lookup"><span data-stu-id="a94ac-145">The methods of one ("scalar") object of a particular type are often different from the methods of a collection of objects of the same type.</span></span>

<span data-ttu-id="a94ac-146">Beispielsweise verfügt jeder Prozess über eine- `Kill` Methode, aber eine Auflistung von Prozessen weist keine Kill-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="a94ac-146">For example, every process has a `Kill` method, but a collection of processes does not have a Kill method.</span></span>

<span data-ttu-id="a94ac-147">Ab PowerShell 3,0 versucht PowerShell, Skript Fehler zu verhindern, die sich aus den unterschiedlichen Methoden von skalaren Objekten und Auflistungen ergeben.</span><span class="sxs-lookup"><span data-stu-id="a94ac-147">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing methods of scalar objects and collections.</span></span>

<span data-ttu-id="a94ac-148">Wenn Sie eine Sammlung übermitteln, aber eine Methode anfordern, die nur in einzelnen (skalaren) Objekten vorhanden ist, ruft PowerShell die-Methode für jedes Objekt in der Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="a94ac-148">If you submit a collection, but request a method that exists only on single ("scalar") objects, PowerShell invokes the method on every object in the collection.</span></span>

<span data-ttu-id="a94ac-149">Wenn die-Methode für die einzelnen Objekte und für die Auflistung vorhanden ist, wird nur die-Methode der-Auflistung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a94ac-149">If the method exists on the individual objects and on the collection, only the collection's method is invoked.</span></span>

<span data-ttu-id="a94ac-150">Diese Funktion funktioniert auch mit Eigenschaften von skalaren Objekten und Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="a94ac-150">This feature also works on properties of scalar objects and collections.</span></span> <span data-ttu-id="a94ac-151">Weitere Informationen finden Sie unter [about_Properties](about_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="a94ac-151">For more information, see [about_Properties](about_Properties.md).</span></span>

### <a name="examples"></a><span data-ttu-id="a94ac-152">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a94ac-152">Examples</span></span>

<span data-ttu-id="a94ac-153">Im folgenden Beispiel wird die **Kill** -Methode einzelner Prozess Objekte in einer Auflistung von-Objekten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a94ac-153">The following example runs the **Kill** method of individual process objects in a collection of objects.</span></span>

<span data-ttu-id="a94ac-154">Der erste Befehl startet drei Instanzen des Notepad-Prozesses.</span><span class="sxs-lookup"><span data-stu-id="a94ac-154">The first command starts three instances of the Notepad process.</span></span> <span data-ttu-id="a94ac-155">`Get-Process` Ruft alle drei Instanzen des Notepad-Prozesses ab und speichert Sie in der `$p` Variablen.</span><span class="sxs-lookup"><span data-stu-id="a94ac-155">`Get-Process` gets all three instance of the Notepad process and saves them in the `$p` variable.</span></span>

```powershell
Notepad; Notepad; Notepad
$p = Get-Process Notepad
$p.Count
```

```Output
3
```

<span data-ttu-id="a94ac-156">Der nächste Befehl führt die **Kill** -Methode für alle drei Prozesse in der `$p` Variablen aus.</span><span class="sxs-lookup"><span data-stu-id="a94ac-156">The next command runs the **Kill** method on all three processes in the `$p` variable.</span></span> <span data-ttu-id="a94ac-157">Dieser Befehl funktioniert, obwohl eine Auflistung von Prozessen keine-Methode besitzt `Kill` .</span><span class="sxs-lookup"><span data-stu-id="a94ac-157">This command works even though a collection of processes does not have a `Kill` method.</span></span>

```powershell
$p.Kill()
Get-Process Notepad
```

<span data-ttu-id="a94ac-158">Der- `Get-Process` Befehl bestätigt, dass die- `Kill` Methode funktioniert hat.</span><span class="sxs-lookup"><span data-stu-id="a94ac-158">The `Get-Process` command confirms that the `Kill` method worked.</span></span>

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

<span data-ttu-id="a94ac-159">Dieses Beispiel ist funktional äquivalent zur Verwendung des- `Foreach-Object` Cmdlets, um die-Methode für jedes Objekt in der Auflistung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a94ac-159">This example is functionally equivalent to using the `Foreach-Object` cmdlet to run the method on each object in the collection.</span></span>

```powershell
$p | ForEach-Object {$_.Kill()}
```

### <a name="foreach-and-where-methods"></a><span data-ttu-id="a94ac-160">Foreach-Methode und Where-Methode</span><span class="sxs-lookup"><span data-stu-id="a94ac-160">ForEach and Where methods</span></span>

<span data-ttu-id="a94ac-161">Ab PowerShell 4,0 wird das Filtern von Sammlungen mithilfe einer Methoden Syntax unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a94ac-161">Beginning in PowerShell 4.0, collection filtering by using a method syntax is supported.</span></span> <span data-ttu-id="a94ac-162">Dies ermöglicht die Verwendung von zwei neuen Methoden beim Umgang mit Sammlungen `ForEach` und `Where` .</span><span class="sxs-lookup"><span data-stu-id="a94ac-162">This allows use of two new methods when dealing with collections `ForEach` and `Where`.</span></span>

<span data-ttu-id="a94ac-163">Weitere Informationen zu diesen Methoden finden Sie unter [about_arrays](about_arrays.md).</span><span class="sxs-lookup"><span data-stu-id="a94ac-163">You can read more about these methods in [about_arrays](about_arrays.md)</span></span>

### <a name="calling-a-specific-method-when-multiple-overloads-exist"></a><span data-ttu-id="a94ac-164">Aufrufen einer bestimmten Methode, wenn mehrere über Ladungen vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="a94ac-164">Calling a specific method when multiple overloads exist</span></span>

<span data-ttu-id="a94ac-165">Beachten Sie das folgende Szenario, wenn Sie .NET-Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a94ac-165">Consider the following scenario when calling .NET methods.</span></span> <span data-ttu-id="a94ac-166">Wenn eine Methode ein-Objekt akzeptiert, aber über eine-Schnittstelle verfügt, die einen spezifischeren Typ annimmt, wählt PowerShell die Methode aus, die das Objekt akzeptiert, es sei denn, Sie haben es explizit in diese Schnittstelle umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="a94ac-166">If a method takes an object but has an overload via an interface taking a more specific type, PowerShell chooses the method that accepts the object unless you explicitly cast it to that interface.</span></span>

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

<span data-ttu-id="a94ac-167">In diesem Beispiel wurde die weniger spezifische Überladung der `object` **Bar** -Methode ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="a94ac-167">In this example the less specific `object` overload of the **Bar** method was chosen.</span></span>

```powershell
[Foo]::new().Bar(1)
```

```Output
object: 1
```

<span data-ttu-id="a94ac-168">In diesem Beispiel konvertieren wir die-Methode in die-Schnittstelle **IFoo** , um die spezifischere Überlastung der **Bar** -Methode auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a94ac-168">In this example we cast the method to the interface **IFoo** to select the more specific overload of the **Bar** method.</span></span>

```powershell
([IFoo] [Foo]::new()).Bar(1)
```

```Output
int: 1
```

## <a name="see-also"></a><span data-ttu-id="a94ac-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a94ac-169">See Also</span></span>

[<span data-ttu-id="a94ac-170">about_Objects</span><span class="sxs-lookup"><span data-stu-id="a94ac-170">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="a94ac-171">about_Properties</span><span class="sxs-lookup"><span data-stu-id="a94ac-171">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="a94ac-172">Get-Member</span><span class="sxs-lookup"><span data-stu-id="a94ac-172">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
