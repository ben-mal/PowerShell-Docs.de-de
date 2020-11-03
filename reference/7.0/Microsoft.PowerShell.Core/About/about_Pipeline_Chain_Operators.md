---
description: Beschreibt das Verketten von Pipelines mit den `&&` `||` Operatoren und in PowerShell.
ms.date: 09/30/2019
schema: 2.0.0
Locale: en-US
keywords: powershell,cmdlet
title: about_Pipeline_Chain_Operators
ms.openlocfilehash: 107d5eacb7b9629a42d5eef53e0c7c66a522f32e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223095"
---
# <a name="about-pipeline-chain-operators"></a>Informationen zu Pipeline Ketten Operatoren

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt das Verketten von Pipelines mit den `&&` `||` Operatoren und in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

Ab PowerShell 7 implementiert PowerShell die `&&` `||` Operatoren und, um Pipelines bedingt zu verketten. Diese Operatoren sind in PowerShell als *Pipeline-Operatoren* bekannt und ähneln den [Listen](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) in POSIX-Shells wie bash, zsh und SH sowie [bedingten Verarbeitungs Symbolen](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) in der Windows-Befehlsshell (cmd.exe).

Der Operator `&&` führt die rechte Pipeline aus, wenn die linke Pipeline erfolgreich war. Dagegen führt der Operator `||` die rechte Pipeline aus, wenn die linke Pipeline fehlgeschlagen ist.

Diese Operatoren verwenden die Variablen `$?` und `$LASTEXITCODE`, um zu bestimmen, ob eine Pipeline fehlgeschlagen ist. Dadurch können Sie sie mit nativen Befehlen und nicht bloß mit Cmdlets oder Funktionen verwenden. Beispiel:

```powershell
# Create an SSH key pair - if successful copy the public key to clipboard
ssh-keygen -t rsa -b 2048 && Get-Content -Raw ~\.ssh\id_rsa.pub | clip
```

### <a name="examples"></a>Beispiele

#### <a name="two-successful-commands"></a>Zwei erfolgreiche Befehle

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

#### <a name="first-command-fails-causing-second-not-to-be-executed"></a>Der erste Befehl schlägt fehl, wodurch die zweite nicht ausgeführt wird.

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

#### <a name="first-command-succeeds-so-the-second-command-is-not-executed"></a>Der erste Befehl ist erfolgreich, sodass der zweite Befehl nicht ausgeführt wird.

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

#### <a name="first-command-fails-so-the-second-command-is-executed"></a>Der erste Befehl schlägt fehl, daher wird der zweite Befehl ausgeführt.

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error: Bad
Second
```

Pipeline Erfolg wird durch den Wert der Variablen definiert `$?` , die von PowerShell automatisch nach dem Ausführen einer Pipeline basierend auf dem Ausführungs Status festgelegt wird.
Dies bedeutet, dass die Pipeline Ketten Operatoren die folgende Äquivalenz aufweisen:

```powershell
Test-Command '1' && Test-Command '2'
```

funktioniert genauso wie

```powershell
Test-Command '1'; if ($?) { Test-Command '2' }
```

und

```powershell
Test-Command '1' || Test-Command '2'
```

funktioniert genauso wie

```powershell
Test-Command '1'; if (-not $?) { Test-Command '2' }
```

### <a name="assignment-from-pipeline-chains"></a>Zuweisung von Pipeline Ketten

Das Zuweisen einer Variablen aus einer Pipeline Kette übernimmt die Verkettung aller Pipelines in der Kette:

```powershell
$result = Write-Output '1' && Write-Output '2'
$result
```

```Output
1
2
```

Wenn ein Fehler beim Abbrechen eines Skripts während der Zuweisung von einer Pipeline Kette auftritt, ist die Zuweisung nicht erfolgreich:

```powershell
try
{
    $result = Write-Output 'Value' && $(throw 'Bad')
}
catch
{
    # Do nothing, just squash the error
}

"Result: $result"
```

```Output
Result:
```

### <a name="operator-syntax-and-precedence"></a>Operator Syntax und Rangfolge

Anders als bei anderen Operatoren, `&&` und `||` arbeiten Sie auf Pipelines, nicht auf Ausdrücken wie `+` oder `-and` , z. b..

`&&` und `||` haben eine niedrigere Rangfolge als "Piping ()" oder "Redirect `|` ( `>` )", aber eine höhere Rangfolge als Auftrags Operatoren ( `&` ), Zuweisung ( `=` ) oder Semikolons ( `;` ). Dies bedeutet, dass Pipelines innerhalb einer Pipeline Kette einzeln umgeleitet werden können, und dass die gesamten Pipeline Ketten mit einem Hintergrund versehen, Variablen zugewiesen oder als Anweisungen getrennt werden können.

Um die Syntax mit niedrigerer Rangfolge in einer Pipeline Kette zu verwenden, sollten Sie die Verwendung von Klammern in Erwägung gezogen `(...)` .
Ebenso kann ein Teil Ausdruck verwendet werden, um eine Anweisung in eine Pipeline Kette einzubetten `$(...)` .
Dies kann nützlich sein, um native Befehle mit Ablauf Steuerung zu kombinieren:

```powershell
foreach ($file in 'file1','file2','file3')
{
    # When find succeeds, the loop breaks
    find $file && Write-Output "Found $file" && $(break)
}
```

```Output
find: file1: No such file or directory
file2
Found file2
```

Ab PowerShell 7 wurde das Verhalten dieser Syntaxen so geändert, dass `$?` es wie erwartet festgelegt wird, wenn ein Befehl in Klammern oder einem Teil Ausdruck erfolgreich ausgeführt wird oder fehlschlägt.

Wie die meisten anderen Operatoren in PowerShell `&&` `||` sind und auch *links assoziativ* , d. h., Sie Gruppieren von Links. Beispiel:

```powershell
Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist" && Get-Content -Raw ./file.txt
```

Gruppieren als:

```
[Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist"] && Get-Content -Raw ./file.txt
```

Äquivalent zu:

```powershell
Get-ChildItem -Path ./file.txt

if (-not $?) { Write-Error "file.txt does not exist" }

if ($?) { Get-Content -Raw ./file.txt }
```

### <a name="error-interaction"></a>Fehler Interaktion

Pipeline Ketten Operatoren können keine Fehler auffangen. Wenn eine Anweisung in einer Pipeline Kette einen Fehler mit Skript Abbruch auslöst, wird die Pipeline Kette beendet.

Beispiel:

```powershell
$(throw 'Bad') || Write-Output '2'
```

```Output
Exception: Bad
```

Auch wenn der Fehler abgefangen wird, wird die Pipeline Kette weiterhin beendet:

```powershell
try
{
    $(throw 'Bad') || Write-Output '2'
}
catch
{
    Write-Output "Caught: $_"
}
Write-Output 'Done'
```

```Output
Caught: Bad
Done
```

Wenn ein Fehler nicht abgebrochen wird oder nur eine Pipeline beendet, wird die Pipeline Kette fortgesetzt, wobei der Wert von berücksichtigt wird `$?` :

```powershell
function Test-NonTerminatingError
{
    [CmdletBinding()]
    param()

    $exception = [System.Exception]::new('BAD')
    $errorId = 'BAD'
    $errorCategory = 'NotSpecified'

    $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

    $PSCmdlet.WriteError($errorRecord)
}

Test-NonTerminatingError || Write-Output 'Second'
```

```Output
Test-NonTerminatingError: BAD
Second
```

### <a name="chaining-pipelines-rather-than-commands"></a>Verketten von Pipelines anstelle von Befehlen

Pipeline Ketten Operatoren können nach Ihrem Namen zum Verketten von Pipelines anstelle von Befehlen verwendet werden. Dies entspricht dem Verhalten anderer Shells, kann jedoch die Bestimmung des *Erfolgs* erschweren:

```powershell
function Test-NotTwo
{
    [CmdletBinding()]
    param(
      [Parameter(ValueFromPipeline)]
      $Input
    )

    process
    {
        if ($Input -ne 2)
        {
            return $Input
        }

        $exception = [System.Exception]::new('Input is 2')
        $errorId = 'InputTwo'
        $errorCategory = 'InvalidData'

        $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

        $PSCmdlet.WriteError($errorRecord)
    }
}

1,2,3 | Test-NotTwo && Write-Output 'All done!'
```

```Output
1
Test-NotTwo : Input is 2
3
```

Beachten Sie, dass `Write-Output 'All done!'` nicht ausgeführt wird, da `Test-NotTwo` als fehlgeschlagen eingestuft wird, nachdem der Fehler ohne Abbruch erzeugt wurde.

## <a name="see-also"></a>Weitere Informationen:

- [about_Operators](about_Operators.md)
- [about_Automatic_Variables](about_Automatic_Variables.md)
- [about_pipelines](about_pipelines.md)
