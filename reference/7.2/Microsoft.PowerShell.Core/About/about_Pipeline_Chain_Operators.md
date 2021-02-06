---
description: Beschreibt das Verketten von Pipelines mit den `&&` `||` Operatoren und in PowerShell.
Locale: en-US
ms.date: 09/30/2019
schema: 2.0.0
title: about_Pipeline_Chain_Operators
ms.openlocfilehash: ece84ec061126401e53bf58112cd79a07a816e8d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602552"
---
# <a name="about-pipeline-chain-operators"></a><span data-ttu-id="e8b88-103">Informationen zu Pipeline Ketten Operatoren</span><span class="sxs-lookup"><span data-stu-id="e8b88-103">About Pipeline Chain Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="e8b88-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8b88-104">Short description</span></span>

<span data-ttu-id="e8b88-105">Beschreibt das Verketten von Pipelines mit den `&&` `||` Operatoren und in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8b88-105">Describes chaining pipelines with the `&&` and `||` operators in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e8b88-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8b88-106">Long description</span></span>

<span data-ttu-id="e8b88-107">Ab PowerShell 7 implementiert PowerShell die `&&` `||` Operatoren und, um Pipelines bedingt zu verketten.</span><span class="sxs-lookup"><span data-stu-id="e8b88-107">Beginning in PowerShell 7, PowerShell implements the `&&` and `||` operators to conditionally chain pipelines.</span></span> <span data-ttu-id="e8b88-108">Diese Operatoren sind in PowerShell als *Pipeline-Operatoren* bekannt und ähneln den [Listen](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) in POSIX-Shells wie bash, zsh und SH sowie [bedingten Verarbeitungs Symbolen](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) in der Windows-Befehlsshell (cmd.exe).</span><span class="sxs-lookup"><span data-stu-id="e8b88-108">These operators are known in PowerShell as *pipeline chain operators*, and are similar to [AND-OR lists](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) in POSIX shells like bash, zsh and sh, as well as [conditional processing symbols](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) in the Windows Command Shell (cmd.exe).</span></span>

<span data-ttu-id="e8b88-109">Der Operator `&&` führt die rechte Pipeline aus, wenn die linke Pipeline erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="e8b88-109">The `&&` operator executes the right-hand pipeline, if the left-hand pipeline succeeded.</span></span> <span data-ttu-id="e8b88-110">Dagegen führt der Operator `||` die rechte Pipeline aus, wenn die linke Pipeline fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="e8b88-110">Conversely, the `||` operator executes the right-hand pipeline if the left-hand pipeline failed.</span></span>

<span data-ttu-id="e8b88-111">Diese Operatoren verwenden die Variablen `$?` und `$LASTEXITCODE`, um zu bestimmen, ob eine Pipeline fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="e8b88-111">These operators use the `$?` and `$LASTEXITCODE` variables to determine if a pipeline failed.</span></span> <span data-ttu-id="e8b88-112">Dadurch können Sie sie mit nativen Befehlen und nicht bloß mit Cmdlets oder Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8b88-112">This allows you to use them with native commands and not just with cmdlets or functions.</span></span> <span data-ttu-id="e8b88-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8b88-113">For example:</span></span>

```powershell
# Create an SSH key pair - if successful copy the public key to clipboard
ssh-keygen -t rsa -b 2048 && Get-Content -Raw ~\.ssh\id_rsa.pub | clip
```

### <a name="examples"></a><span data-ttu-id="e8b88-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e8b88-114">Examples</span></span>

#### <a name="two-successful-commands"></a><span data-ttu-id="e8b88-115">Zwei erfolgreiche Befehle</span><span class="sxs-lookup"><span data-stu-id="e8b88-115">Two successful commands</span></span>

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

#### <a name="first-command-fails-causing-second-not-to-be-executed"></a><span data-ttu-id="e8b88-116">Der erste Befehl schlägt fehl, wodurch die zweite nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e8b88-116">First command fails, causing second not to be executed</span></span>

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

#### <a name="first-command-succeeds-so-the-second-command-is-not-executed"></a><span data-ttu-id="e8b88-117">Der erste Befehl ist erfolgreich, sodass der zweite Befehl nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e8b88-117">First command succeeds, so the second command is not executed</span></span>

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

#### <a name="first-command-fails-so-the-second-command-is-executed"></a><span data-ttu-id="e8b88-118">Der erste Befehl schlägt fehl, daher wird der zweite Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8b88-118">First command fails, so the second command is executed</span></span>

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error: Bad
Second
```

<span data-ttu-id="e8b88-119">Pipeline Erfolg wird durch den Wert der Variablen definiert `$?` , die von PowerShell automatisch nach dem Ausführen einer Pipeline basierend auf dem Ausführungs Status festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e8b88-119">Pipeline success is defined by the value of the `$?` variable, which PowerShell automatically sets after executing a pipeline based on its execution status.</span></span>
<span data-ttu-id="e8b88-120">Dies bedeutet, dass die Pipeline Ketten Operatoren die folgende Äquivalenz aufweisen:</span><span class="sxs-lookup"><span data-stu-id="e8b88-120">This means that pipeline chain operators have the following equivalence:</span></span>

```powershell
Test-Command '1' && Test-Command '2'
```

<span data-ttu-id="e8b88-121">funktioniert genauso wie</span><span class="sxs-lookup"><span data-stu-id="e8b88-121">works the same as</span></span>

```powershell
Test-Command '1'; if ($?) { Test-Command '2' }
```

<span data-ttu-id="e8b88-122">und</span><span class="sxs-lookup"><span data-stu-id="e8b88-122">and</span></span>

```powershell
Test-Command '1' || Test-Command '2'
```

<span data-ttu-id="e8b88-123">funktioniert genauso wie</span><span class="sxs-lookup"><span data-stu-id="e8b88-123">works the same as</span></span>

```powershell
Test-Command '1'; if (-not $?) { Test-Command '2' }
```

### <a name="assignment-from-pipeline-chains"></a><span data-ttu-id="e8b88-124">Zuweisung von Pipeline Ketten</span><span class="sxs-lookup"><span data-stu-id="e8b88-124">Assignment from pipeline chains</span></span>

<span data-ttu-id="e8b88-125">Das Zuweisen einer Variablen aus einer Pipeline Kette übernimmt die Verkettung aller Pipelines in der Kette:</span><span class="sxs-lookup"><span data-stu-id="e8b88-125">Assigning a variable from a pipeline chain takes the concatenation of all the pipelines in the chain:</span></span>

```powershell
$result = Write-Output '1' && Write-Output '2'
$result
```

```Output
1
2
```

<span data-ttu-id="e8b88-126">Wenn ein Fehler beim Abbrechen eines Skripts während der Zuweisung von einer Pipeline Kette auftritt, ist die Zuweisung nicht erfolgreich:</span><span class="sxs-lookup"><span data-stu-id="e8b88-126">If a script-terminating error occurs during assignment from a pipeline chain, the assignment does not succeed:</span></span>

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

### <a name="operator-syntax-and-precedence"></a><span data-ttu-id="e8b88-127">Operator Syntax und Rangfolge</span><span class="sxs-lookup"><span data-stu-id="e8b88-127">Operator syntax and precedence</span></span>

<span data-ttu-id="e8b88-128">Anders als bei anderen Operatoren, `&&` und `||` arbeiten Sie auf Pipelines, nicht auf Ausdrücken wie `+` oder `-and` , z. b..</span><span class="sxs-lookup"><span data-stu-id="e8b88-128">Unlike other operators, `&&` and `||` operate on pipelines, rather than on expressions like `+` or `-and`, for example.</span></span>

<span data-ttu-id="e8b88-129">`&&` und `||` haben eine niedrigere Rangfolge als "Piping ()" oder "Redirect `|` ( `>` )", aber eine höhere Rangfolge als Auftrags Operatoren ( `&` ), Zuweisung ( `=` ) oder Semikolons ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="e8b88-129">`&&` and `||` have a lower precedence than piping (`|`) or redirection (`>`), but a higher precedence than job operators (`&`), assignment (`=`) or semicolons (`;`).</span></span> <span data-ttu-id="e8b88-130">Dies bedeutet, dass Pipelines innerhalb einer Pipeline Kette einzeln umgeleitet werden können, und dass die gesamten Pipeline Ketten mit einem Hintergrund versehen, Variablen zugewiesen oder als Anweisungen getrennt werden können.</span><span class="sxs-lookup"><span data-stu-id="e8b88-130">This means that pipelines within a pipeline chain can be individually redirected, and that entire pipeline chains can be backgrounded, assigned to variables, or separated as statements.</span></span>

<span data-ttu-id="e8b88-131">Um die Syntax mit niedrigerer Rangfolge in einer Pipeline Kette zu verwenden, sollten Sie die Verwendung von Klammern in Erwägung gezogen `(...)` .</span><span class="sxs-lookup"><span data-stu-id="e8b88-131">To use lower precedence syntax within a pipeline chain, consider the use of parentheses `(...)`.</span></span>
<span data-ttu-id="e8b88-132">Ebenso kann ein Teil Ausdruck verwendet werden, um eine Anweisung in eine Pipeline Kette einzubetten `$(...)` .</span><span class="sxs-lookup"><span data-stu-id="e8b88-132">Similarly, to embed a statement within a pipeline chain, a subexpression `$(...)` can be used.</span></span>
<span data-ttu-id="e8b88-133">Dies kann nützlich sein, um native Befehle mit Ablauf Steuerung zu kombinieren:</span><span class="sxs-lookup"><span data-stu-id="e8b88-133">This can be useful for combining native commands with control flow:</span></span>

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

<span data-ttu-id="e8b88-134">Ab PowerShell 7 wurde das Verhalten dieser Syntaxen so geändert, dass `$?` es wie erwartet festgelegt wird, wenn ein Befehl in Klammern oder einem Teil Ausdruck erfolgreich ausgeführt wird oder fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="e8b88-134">As of PowerShell 7, the behaviour of these syntaxes has been changed so that `$?` is set as expected when a command succeeds or fails within parentheses or a subexpression.</span></span>

<span data-ttu-id="e8b88-135">Wie die meisten anderen Operatoren in PowerShell `&&` `||` sind und auch *links assoziativ*, d. h., Sie Gruppieren von Links.</span><span class="sxs-lookup"><span data-stu-id="e8b88-135">Like most other operators in PowerShell, `&&` and `||` are also *left-associative*, meaning they group from the left.</span></span> <span data-ttu-id="e8b88-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8b88-136">For example:</span></span>

```powershell
Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist" && Get-Content -Raw ./file.txt
```

<span data-ttu-id="e8b88-137">Gruppieren als:</span><span class="sxs-lookup"><span data-stu-id="e8b88-137">will group as:</span></span>

```
[Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist"] && Get-Content -Raw ./file.txt
```

<span data-ttu-id="e8b88-138">Äquivalent zu:</span><span class="sxs-lookup"><span data-stu-id="e8b88-138">being equivalent to:</span></span>

```powershell
Get-ChildItem -Path ./file.txt

if (-not $?) { Write-Error "file.txt does not exist" }

if ($?) { Get-Content -Raw ./file.txt }
```

### <a name="error-interaction"></a><span data-ttu-id="e8b88-139">Fehler Interaktion</span><span class="sxs-lookup"><span data-stu-id="e8b88-139">Error interaction</span></span>

<span data-ttu-id="e8b88-140">Pipeline Ketten Operatoren können keine Fehler auffangen.</span><span class="sxs-lookup"><span data-stu-id="e8b88-140">Pipeline chain operators do not absorb errors.</span></span> <span data-ttu-id="e8b88-141">Wenn eine Anweisung in einer Pipeline Kette einen Fehler mit Skript Abbruch auslöst, wird die Pipeline Kette beendet.</span><span class="sxs-lookup"><span data-stu-id="e8b88-141">When a statement in a pipeline chain throws a script-terminating error, the pipeline chain is terminated.</span></span>

<span data-ttu-id="e8b88-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8b88-142">For example:</span></span>

```powershell
$(throw 'Bad') || Write-Output '2'
```

```Output
Exception: Bad
```

<span data-ttu-id="e8b88-143">Auch wenn der Fehler abgefangen wird, wird die Pipeline Kette weiterhin beendet:</span><span class="sxs-lookup"><span data-stu-id="e8b88-143">Even when the error is caught, the pipeline chain is still terminated:</span></span>

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

<span data-ttu-id="e8b88-144">Wenn ein Fehler nicht abgebrochen wird oder nur eine Pipeline beendet, wird die Pipeline Kette fortgesetzt, wobei der Wert von berücksichtigt wird `$?` :</span><span class="sxs-lookup"><span data-stu-id="e8b88-144">If an error is non-terminating, or only terminates a pipeline, the pipeline chain continues, respecting the value of `$?`:</span></span>

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

### <a name="chaining-pipelines-rather-than-commands"></a><span data-ttu-id="e8b88-145">Verketten von Pipelines anstelle von Befehlen</span><span class="sxs-lookup"><span data-stu-id="e8b88-145">Chaining pipelines rather than commands</span></span>

<span data-ttu-id="e8b88-146">Pipeline Ketten Operatoren können nach Ihrem Namen zum Verketten von Pipelines anstelle von Befehlen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8b88-146">Pipeline chain operators, by their name, can be used to chain pipelines, rather than just commands.</span></span> <span data-ttu-id="e8b88-147">Dies entspricht dem Verhalten anderer Shells, kann jedoch die Bestimmung des *Erfolgs* erschweren:</span><span class="sxs-lookup"><span data-stu-id="e8b88-147">This matches the behavior of other shells, but can make *success* harder to determine:</span></span>

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

<span data-ttu-id="e8b88-148">Beachten Sie, dass `Write-Output 'All done!'` nicht ausgeführt wird, da `Test-NotTwo` als fehlgeschlagen eingestuft wird, nachdem der Fehler ohne Abbruch erzeugt wurde.</span><span class="sxs-lookup"><span data-stu-id="e8b88-148">Note that `Write-Output 'All done!'` is not executed, since `Test-NotTwo` is deemed to have failed after generating the non-terminating error.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8b88-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8b88-149">See also</span></span>

- [<span data-ttu-id="e8b88-150">about_Operators</span><span class="sxs-lookup"><span data-stu-id="e8b88-150">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="e8b88-151">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="e8b88-151">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="e8b88-152">about_pipelines</span><span class="sxs-lookup"><span data-stu-id="e8b88-152">about_pipelines</span></span>](about_pipelines.md)

