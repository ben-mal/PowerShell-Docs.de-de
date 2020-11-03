---
description: Beschreibt einen Sprachbefehl, mit dem Sie alle Elemente in einer Auflistung von Elementen durchlaufen können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_foreach?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach
ms.openlocfilehash: 87d4b78df35c8944bdd95a478be4ea0b8d6fbe49
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220911"
---
# <a name="about-foreach"></a>Informationen zu foreach

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt einen Sprachbefehl, mit dem Sie alle Elemente in einer Auflistung von Elementen durchlaufen können.

## <a name="long-description"></a>Lange Beschreibung

Die- `Foreach` Anweisung (auch als- `Foreach` Schleife bezeichnet) ist ein Sprachkonstrukt, mit dem eine Reihe von Werten in einer Auflistung von Elementen durchlaufen (iteriert) werden.

Der einfachste und häufigste Typ der zu traversierungs Auflistung ist ein Array.
Innerhalb einer- `Foreach` Schleife ist es üblich, einen oder mehrere Befehle für jedes Element in einem Array auszuführen.

## <a name="syntax"></a>Syntax

Im folgenden wird die `ForEach` Syntax veranschaulicht:

```
foreach ($<item> in $<collection>){<statement list>}
```

Der Teil der `ForEach` in Klammern eingeschlossenen Anweisung stellt eine Variable und eine Auflistung dar, die durchlaufen werden soll. PowerShell erstellt die Variable `$<item>` automatisch, wenn die-Schleife ausgeführt wird `Foreach` . Vor jeder Iterations Schleife durch die-Schleife wird die-Variable auf einen Wert in der-Auflistung festgelegt.
Der-Block, der auf eine- `Foreach` Anweisung folgt `{<statement list>}` , enthält einen Satz von Befehlen, die für jedes Element in einer Auflistung ausgeführt werden.

### <a name="examples"></a>Beispiele

Die- `Foreach` Schleife im folgenden Beispiel zeigt beispielsweise die Werte im- `$letterArray` Array an.

```powershell
$letterArray = "a","b","c","d"
foreach ($letter in $letterArray)
{
  Write-Host $letter
}
```

In diesem Beispiel wird das `$letterArray` Array mit den Zeichen folgen Werten,, und erstellt und initialisiert `"a"` `"b"` `"c"` `"d"` . Wenn die-Anweisung zum ersten Mal ausgeführt `Foreach` wird, wird die- `$letter` Variable auf das erste Element in `$letterArray` () festgelegt `"a"` . Dann wird das `Write-Host` Cmdlet verwendet, um den Buchstaben a anzuzeigen. Wenn die Schleife das nächste Mal durchlaufen wird, `$letter` wird auf festgelegt `"b"` , usw. Nachdem die `Foreach` Schleife den Buchstaben d angezeigt hat, beendet PowerShell die Schleife.

Die gesamte- `Foreach` Anweisung muss in einer einzelnen Zeile angezeigt werden, um Sie an der PowerShell-Eingabeaufforderung als Befehl auszuführen. Die gesamte- `Foreach` Anweisung muss nicht in einer einzelnen Zeile angezeigt werden, wenn Sie stattdessen den Befehl in einer PS1-Skriptdatei platzieren.

`Foreach` -Anweisungen können auch in Verbindung mit Cmdlets verwendet werden, die eine Auflistung von Elementen zurückgeben. Im folgenden Beispiel durchläuft die foreach-Anweisung die Liste der Elemente, die vom `Get-ChildItem` Cmdlet zurückgegeben werden.

```powershell
foreach ($file in Get-ChildItem)
{
  Write-Host $file
}
```

Sie können das Beispiel verfeinern, indem Sie eine- `If` Anweisung verwenden, um die zurückgegebenen Ergebnisse einzuschränken. Im folgenden Beispiel führt die- `Foreach` Anweisung den gleichen Schleifen Vorgang wie im vorherigen Beispiel aus. es wird jedoch eine-Anweisung hinzugefügt, `If` um die Ergebnisse auf Dateien zu beschränken, die größer als 100 Kilobyte (KB) sind:

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
  }
}
```

In diesem Beispiel verwendet die- `Foreach` Schleife eine-Eigenschaft der- `$file` Variable, um einen Vergleichs Vorgang ( `$file.length -gt 100KB` ) auszuführen. Die- `$file` Variable enthält alle Eigenschaften des-Objekts, das vom `Get-ChildItem` Cmdlet zurückgegeben wird. Daher können Sie mehr als nur einen Dateinamen zurückgeben.
Im nächsten Beispiel gibt PowerShell die Länge und die Uhrzeit des letzten Zugriffs in der Anweisungs Liste zurück:

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

In diesem Beispiel sind Sie nicht auf die Ausführung eines einzelnen Befehls in einer Anweisungs Liste beschränkt.

Sie können auch eine Variable außerhalb einer `Foreach` Schleife verwenden und die Variable innerhalb der Schleife erhöhen. Im folgenden Beispiel werden Dateien mit einer Größe von mehr als 100 KB gezählt:

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

Im vorherigen Beispiel `$i` wird die-Variable auf `0` außerhalb der-Schleife festgelegt, und die-Variable wird in der-Schleife für jede gefundene Datei erhöht, die größer als 100 KB ist. Wenn die Schleife beendet wird, `If` wertet eine-Anweisung den Wert von aus `$i` , um die Anzahl aller Dateien über 100 KB anzuzeigen. Oder es wird eine Meldung angezeigt, die besagt, dass keine Dateien über 100 KB gefunden wurden.

Im vorherigen Beispiel wird auch veranschaulicht, wie die Ergebnisse der Dateilänge formatiert werden:

```powershell
($file.length / 1024).ToString("F0")
```

Der Wert wird durch 1.024 dividiert, um die Ergebnisse in Kilobyte anstelle von Bytes anzuzeigen, und der resultierende Wert wird dann mithilfe des Festkomma-Format bezeichnerformats formatiert, um alle Dezimalwerte aus dem Ergebnis zu entfernen. Der Wert 0 gibt an, dass der Formatspezifizierer keine Dezimalstellen anzeigt.

Im folgenden Beispiel analysiert die definierte Funktion PowerShell-Skripts und Skript Module und gibt den Speicherort der Funktionen zurück, die in enthalten sind. Im Beispiel wird veranschaulicht, wie die `MoveNext` -Methode (die ähnlich wie `skip X` bei einer- `For` Schleife funktioniert) und die- `Current` Eigenschaft der- `$foreach` Variablen in einem Foreach-Skriptblock verwendet werden. Die Beispiel Funktion kann Funktionen in einem Skript suchen, auch wenn die Funktionsdefinitionen ungewöhnlich oder nicht konsistent sind, die sich über mehrere Zeilen erstrecken.

Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](about_Automatic_Variables.md#using-enumerators).

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

## <a name="see-also"></a>SIEHE AUCH

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_If](about_If.md)

[ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)

