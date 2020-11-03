---
description: Beschreibt einen Sprachbefehl, mit dem Sie alle Elemente in einer Auflistung von Elementen durchlaufen können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_foreach?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach
ms.openlocfilehash: 42cea9f61330e16adcad0ad543acca21e35d5ca8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223820"
---
# <a name="about-foreach"></a><span data-ttu-id="946b6-104">Informationen zu foreach</span><span class="sxs-lookup"><span data-stu-id="946b6-104">About ForEach</span></span>

## <a name="short-description"></a><span data-ttu-id="946b6-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="946b6-105">Short description</span></span>
<span data-ttu-id="946b6-106">Beschreibt einen Sprachbefehl, mit dem Sie alle Elemente in einer Auflistung von Elementen durchlaufen können.</span><span class="sxs-lookup"><span data-stu-id="946b6-106">Describes a language command you can use to traverse all the items in a collection of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="946b6-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="946b6-107">Long description</span></span>

<span data-ttu-id="946b6-108">Die- `Foreach` Anweisung (auch als- `Foreach` Schleife bezeichnet) ist ein Sprachkonstrukt, mit dem eine Reihe von Werten in einer Auflistung von Elementen durchlaufen (iteriert) werden.</span><span class="sxs-lookup"><span data-stu-id="946b6-108">The `Foreach` statement (also known as a `Foreach` loop) is a language construct for stepping through (iterating) a series of values in a collection of items.</span></span>

<span data-ttu-id="946b6-109">Der einfachste und häufigste Typ der zu traversierungs Auflistung ist ein Array.</span><span class="sxs-lookup"><span data-stu-id="946b6-109">The simplest and most typical type of collection to traverse is an array.</span></span>
<span data-ttu-id="946b6-110">Innerhalb einer- `Foreach` Schleife ist es üblich, einen oder mehrere Befehle für jedes Element in einem Array auszuführen.</span><span class="sxs-lookup"><span data-stu-id="946b6-110">Within a `Foreach` loop, it is common to run one or more commands against each item in an array.</span></span>

## <a name="syntax"></a><span data-ttu-id="946b6-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="946b6-111">Syntax</span></span>

<span data-ttu-id="946b6-112">Im folgenden wird die `ForEach` Syntax veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="946b6-112">The following shows the `ForEach` syntax:</span></span>

```
foreach ($<item> in $<collection>){<statement list>}
```

<span data-ttu-id="946b6-113">Der Teil der `ForEach` in Klammern eingeschlossenen Anweisung stellt eine Variable und eine Auflistung dar, die durchlaufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="946b6-113">The part of the `ForEach` statement enclosed in parenthesis represents a variable and a collection to iterate.</span></span> <span data-ttu-id="946b6-114">PowerShell erstellt die Variable `$<item>` automatisch, wenn die-Schleife ausgeführt wird `Foreach` .</span><span class="sxs-lookup"><span data-stu-id="946b6-114">PowerShell creates the variable `$<item>` automatically when the `Foreach` loop runs.</span></span> <span data-ttu-id="946b6-115">Vor jeder Iterations Schleife durch die-Schleife wird die-Variable auf einen Wert in der-Auflistung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="946b6-115">Prior to each iteration through the loop, the variable is set to a value in the collection.</span></span>
<span data-ttu-id="946b6-116">Der-Block, der auf eine- `Foreach` Anweisung folgt `{<statement list>}` , enthält einen Satz von Befehlen, die für jedes Element in einer Auflistung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="946b6-116">The block following a `Foreach` statement `{<statement list>}` contains a set of commands to execute against each item in a collection.</span></span>

### <a name="examples"></a><span data-ttu-id="946b6-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="946b6-117">Examples</span></span>

<span data-ttu-id="946b6-118">Die- `Foreach` Schleife im folgenden Beispiel zeigt beispielsweise die Werte im- `$letterArray` Array an.</span><span class="sxs-lookup"><span data-stu-id="946b6-118">For example, the `Foreach` loop in the following example displays the values in the `$letterArray` array.</span></span>

```powershell
$letterArray = "a","b","c","d"
foreach ($letter in $letterArray)
{
  Write-Host $letter
}
```

<span data-ttu-id="946b6-119">In diesem Beispiel wird das `$letterArray` Array mit den Zeichen folgen Werten,, und erstellt und initialisiert `"a"` `"b"` `"c"` `"d"` .</span><span class="sxs-lookup"><span data-stu-id="946b6-119">In this example, the `$letterArray` array is created and initialized with the string values `"a"`, `"b"`, `"c"`, and `"d"`.</span></span> <span data-ttu-id="946b6-120">Wenn die-Anweisung zum ersten Mal ausgeführt `Foreach` wird, wird die- `$letter` Variable auf das erste Element in `$letterArray` () festgelegt `"a"` .</span><span class="sxs-lookup"><span data-stu-id="946b6-120">The first time the `Foreach` statement runs, it sets the `$letter` variable equal to the first item in `$letterArray` (`"a"`).</span></span> <span data-ttu-id="946b6-121">Dann wird das `Write-Host` Cmdlet verwendet, um den Buchstaben a anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="946b6-121">Then, it uses the `Write-Host` cmdlet to display the letter a.</span></span> <span data-ttu-id="946b6-122">Wenn die Schleife das nächste Mal durchlaufen wird, `$letter` wird auf festgelegt `"b"` , usw.</span><span class="sxs-lookup"><span data-stu-id="946b6-122">The next time through the loop, `$letter` is set to `"b"`, and so on.</span></span> <span data-ttu-id="946b6-123">Nachdem die `Foreach` Schleife den Buchstaben d angezeigt hat, beendet PowerShell die Schleife.</span><span class="sxs-lookup"><span data-stu-id="946b6-123">After the `Foreach` loop displays the letter d, PowerShell exits the loop.</span></span>

<span data-ttu-id="946b6-124">Die gesamte- `Foreach` Anweisung muss in einer einzelnen Zeile angezeigt werden, um Sie an der PowerShell-Eingabeaufforderung als Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="946b6-124">The entire `Foreach` statement must appear on a single line to run it as a command at the PowerShell command prompt.</span></span> <span data-ttu-id="946b6-125">Die gesamte- `Foreach` Anweisung muss nicht in einer einzelnen Zeile angezeigt werden, wenn Sie stattdessen den Befehl in einer PS1-Skriptdatei platzieren.</span><span class="sxs-lookup"><span data-stu-id="946b6-125">The entire `Foreach` statement does not have to appear on a single line if you place the command in a .ps1 script file instead.</span></span>

<span data-ttu-id="946b6-126">`Foreach` -Anweisungen können auch in Verbindung mit Cmdlets verwendet werden, die eine Auflistung von Elementen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="946b6-126">`Foreach` statements can also be used together with cmdlets that return a collection of items.</span></span> <span data-ttu-id="946b6-127">Im folgenden Beispiel durchläuft die foreach-Anweisung die Liste der Elemente, die vom `Get-ChildItem` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="946b6-127">In the following example, the Foreach statement steps through the list of items that is returned by the `Get-ChildItem` cmdlet.</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  Write-Host $file
}
```

<span data-ttu-id="946b6-128">Sie können das Beispiel verfeinern, indem Sie eine- `If` Anweisung verwenden, um die zurückgegebenen Ergebnisse einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="946b6-128">You can refine the example by using an `If` statement to limit the results that are returned.</span></span> <span data-ttu-id="946b6-129">Im folgenden Beispiel führt die- `Foreach` Anweisung den gleichen Schleifen Vorgang wie im vorherigen Beispiel aus. es wird jedoch eine-Anweisung hinzugefügt, `If` um die Ergebnisse auf Dateien zu beschränken, die größer als 100 Kilobyte (KB) sind:</span><span class="sxs-lookup"><span data-stu-id="946b6-129">In the following example, the `Foreach` statement performs the same looping operation as the previous example, but it adds an `If` statement to limit the results to files that are greater than 100 kilobytes (KB):</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
  }
}
```

<span data-ttu-id="946b6-130">In diesem Beispiel verwendet die- `Foreach` Schleife eine-Eigenschaft der- `$file` Variable, um einen Vergleichs Vorgang ( `$file.length -gt 100KB` ) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="946b6-130">In this example, the `Foreach` loop uses a property of the `$file` variable to perform a comparison operation (`$file.length -gt 100KB`).</span></span> <span data-ttu-id="946b6-131">Die- `$file` Variable enthält alle Eigenschaften des-Objekts, das vom `Get-ChildItem` Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="946b6-131">The `$file` variable contains all the properties in the object that is returned by the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="946b6-132">Daher können Sie mehr als nur einen Dateinamen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="946b6-132">Therefore, you can return more than just a file name.</span></span>
<span data-ttu-id="946b6-133">Im nächsten Beispiel gibt PowerShell die Länge und die Uhrzeit des letzten Zugriffs in der Anweisungs Liste zurück:</span><span class="sxs-lookup"><span data-stu-id="946b6-133">In the next example, PowerShell returns the length and the last access time inside the statement list:</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
    Write-Host $file.length
    Write-Host $file.lastaccesstime
  }
}
```

<span data-ttu-id="946b6-134">In diesem Beispiel sind Sie nicht auf die Ausführung eines einzelnen Befehls in einer Anweisungs Liste beschränkt.</span><span class="sxs-lookup"><span data-stu-id="946b6-134">In this example, you are not limited to running a single command in a statement list.</span></span>

<span data-ttu-id="946b6-135">Sie können auch eine Variable außerhalb einer `Foreach` Schleife verwenden und die Variable innerhalb der Schleife erhöhen.</span><span class="sxs-lookup"><span data-stu-id="946b6-135">You can also use a variable outside a `Foreach` loop and increment the variable inside the loop.</span></span> <span data-ttu-id="946b6-136">Im folgenden Beispiel werden Dateien mit einer Größe von mehr als 100 KB gezählt:</span><span class="sxs-lookup"><span data-stu-id="946b6-136">The following example counts files over 100 KB in size:</span></span>

```powershell
$i = 0
foreach ($file in Get-ChildItem) {
  if ($file.length -gt 100KB) {
    Write-Host $file "file size:" ($file.length / 1024).ToString("F0") KB
    $i = $i + 1
  }
}

if ($i -ne 0) {
  Write-Host
  Write-Host $i " file(s) over 100 KB in the current directory."
}
else {
  Write-Host "No files greater than 100 KB in the current directory."
}
```

<span data-ttu-id="946b6-137">Im vorherigen Beispiel `$i` wird die-Variable auf `0` außerhalb der-Schleife festgelegt, und die-Variable wird in der-Schleife für jede gefundene Datei erhöht, die größer als 100 KB ist.</span><span class="sxs-lookup"><span data-stu-id="946b6-137">In the preceding example, the `$i` variable is set to `0` outside the loop, and the variable is incremented inside the loop for each file that is found that is larger than 100 KB.</span></span> <span data-ttu-id="946b6-138">Wenn die Schleife beendet wird, `If` wertet eine-Anweisung den Wert von aus `$i` , um die Anzahl aller Dateien über 100 KB anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="946b6-138">When the loop exits, an `If` statement evaluates the value of `$i` to display a count of all the files over 100 KB.</span></span> <span data-ttu-id="946b6-139">Oder es wird eine Meldung angezeigt, die besagt, dass keine Dateien über 100 KB gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="946b6-139">Or, it displays a message stating that no files over 100 KB were found.</span></span>

<span data-ttu-id="946b6-140">Im vorherigen Beispiel wird auch veranschaulicht, wie die Ergebnisse der Dateilänge formatiert werden:</span><span class="sxs-lookup"><span data-stu-id="946b6-140">The previous example also demonstrates how to format the file length results:</span></span>

```powershell
($file.length / 1024).ToString("F0")
```

<span data-ttu-id="946b6-141">Der Wert wird durch 1.024 dividiert, um die Ergebnisse in Kilobyte anstelle von Bytes anzuzeigen, und der resultierende Wert wird dann mithilfe des Festkomma-Format bezeichnerformats formatiert, um alle Dezimalwerte aus dem Ergebnis zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="946b6-141">The value is divided by 1,024 to show the results in kilobytes rather than bytes, and the resulting value is then formatted using the fixed-point format specifier to remove any decimal values from the result.</span></span> <span data-ttu-id="946b6-142">Der Wert 0 gibt an, dass der Formatspezifizierer keine Dezimalstellen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="946b6-142">The 0 makes the format specifier show no decimal places.</span></span>

<span data-ttu-id="946b6-143">Im folgenden Beispiel analysiert die definierte Funktion PowerShell-Skripts und Skript Module und gibt den Speicherort der Funktionen zurück, die in enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="946b6-143">In the following example, the function defined parses PowerShell scripts and script modules and returns the location of functions contained within.</span></span> <span data-ttu-id="946b6-144">Im Beispiel wird veranschaulicht, wie die `MoveNext` -Methode (die ähnlich wie `skip X` bei einer- `For` Schleife funktioniert) und die- `Current` Eigenschaft der- `$foreach` Variablen in einem Foreach-Skriptblock verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="946b6-144">The example demonstrates how to use the `MoveNext` method (which works similarly to `skip X` on a `For` loop) and the `Current` property of the `$foreach` variable inside of a foreach script block.</span></span> <span data-ttu-id="946b6-145">Die Beispiel Funktion kann Funktionen in einem Skript suchen, auch wenn die Funktionsdefinitionen ungewöhnlich oder nicht konsistent sind, die sich über mehrere Zeilen erstrecken.</span><span class="sxs-lookup"><span data-stu-id="946b6-145">The example function can find functions in a script even if there are unusually- or inconsistently-spaced function definitions that span multiple lines.</span></span>

<span data-ttu-id="946b6-146">Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](about_Automatic_Variables.md#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="946b6-146">For more information, see [Using Enumerators](about_Automatic_Variables.md#using-enumerators).</span></span>

```powershell
function Get-FunctionPosition {
  [CmdletBinding()]
  [OutputType('FunctionPosition')]
  param(
    [Parameter(Position = 0, Mandatory,
      ValueFromPipeline, ValueFromPipelineByPropertyName)]
    [ValidateNotNullOrEmpty()]
    [Alias('PSPath')]
    [System.String[]]
    $Path
  )

  process {
    try {
      $filesToProcess = if ($_ -is [System.IO.FileSystemInfo]) {
        $_
      } else {
        $filesToProcess = Get-Item -Path $Path
      }
      $parser = [System.Management.Automation.Language.Parser]
      foreach ($item in $filesToProcess) {
        if ($item.PSIsContainer -or
            $item.Extension -notin @('.ps1', '.psm1')) {
          continue
        }
        $tokens = $errors = $null
        $ast = $parser::ParseFile($item.FullName, ([REF]$tokens),
          ([REF]$errors))
        if ($errors) {
          $msg = "File '{0}' has {1} parser errors." -f $item.FullName,
            $errors.Count
          Write-Warning $msg
        }
        :tokenLoop foreach ($token in $tokens) {
          if ($token.Kind -ne 'Function') {
            continue
          }
          $position = $token.Extent.StartLineNumber
          do {
            if (-not $foreach.MoveNext()) {
              break tokenLoop
            }
            $token = $foreach.Current
          } until ($token.Kind -in @('Generic', 'Identifier'))
          $functionPosition = [pscustomobject]@{
            Name       = $token.Text
            LineNumber = $position
            Path       = $item.FullName
          }
          Add-Member -InputObject $functionPosition `
            -TypeName FunctionPosition -PassThru
        }
      }
    }
    catch {
      throw
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="946b6-147">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="946b6-147">SEE ALSO</span></span>

[<span data-ttu-id="946b6-148">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="946b6-148">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="946b6-149">about_If</span><span class="sxs-lookup"><span data-stu-id="946b6-149">about_If</span></span>](about_If.md)

[<span data-ttu-id="946b6-150">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="946b6-150">ForEach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
