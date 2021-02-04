---
description: Erläutert, wie die Ausgabe von PowerShell an Textdateien umgeleitet wird.
Locale: en-US
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_redirection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Redirection
ms.openlocfilehash: 2f2081bbfcc2cfc97eaa5a3c2c527cdd9cd61d2c
ms.sourcegitcommit: b9826dcf402db8a2b6d3eab37edb82c6af113343
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98040879"
---
# <a name="about-redirection"></a><span data-ttu-id="833b7-103">Informationen über die Umleitung</span><span class="sxs-lookup"><span data-stu-id="833b7-103">About Redirection</span></span>

## <a name="short-description"></a><span data-ttu-id="833b7-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="833b7-104">Short description</span></span>
<span data-ttu-id="833b7-105">Erläutert, wie die Ausgabe von PowerShell an Textdateien umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="833b7-105">Explains how to redirect output from PowerShell to text files.</span></span>

## <a name="long-description"></a><span data-ttu-id="833b7-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="833b7-106">Long description</span></span>

<span data-ttu-id="833b7-107">PowerShell sendet die Ausgabe standardmäßig an den PowerShell-Host.</span><span class="sxs-lookup"><span data-stu-id="833b7-107">By default, PowerShell sends output to the PowerShell host.</span></span> <span data-ttu-id="833b7-108">In der Regel handelt es sich hierbei um die Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="833b7-108">Usually this is the console application.</span></span> <span data-ttu-id="833b7-109">Sie können die Ausgabe jedoch an eine Textdatei weiterleiten, und Sie können die Fehlerausgabe an den regulären Ausgabedatenstrom umleiten.</span><span class="sxs-lookup"><span data-stu-id="833b7-109">However, you can direct the output to a text file, and you can redirect error output to the regular output stream.</span></span>

<span data-ttu-id="833b7-110">Zum Umleiten der Ausgabe können Sie die folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="833b7-110">You can use the following methods to redirect output:</span></span>

- <span data-ttu-id="833b7-111">Verwenden Sie das- `Out-File` Cmdlet, das die Befehlsausgabe an eine Textdatei sendet.</span><span class="sxs-lookup"><span data-stu-id="833b7-111">Use the `Out-File` cmdlet, which sends command output to a text file.</span></span>
  <span data-ttu-id="833b7-112">In der Regel verwenden Sie das `Out-File` Cmdlet, wenn Sie die Parameter,, oder verwenden müssen `Encoding` `Force` `Width` `NoClobber` .</span><span class="sxs-lookup"><span data-stu-id="833b7-112">Typically, you use the `Out-File` cmdlet when you need to use its parameters, such as the `Encoding`, `Force`, `Width`, or `NoClobber` parameters.</span></span>

- <span data-ttu-id="833b7-113">Verwenden `Tee-Object` Sie das-Cmdlet, das die Befehlsausgabe an eine Textdatei sendet und Sie dann an die Pipeline sendet.</span><span class="sxs-lookup"><span data-stu-id="833b7-113">Use the `Tee-Object` cmdlet, which sends command output to a text file and then sends it to the pipeline.</span></span>

- <span data-ttu-id="833b7-114">Verwenden Sie die PowerShell-Umleitungs Operatoren.</span><span class="sxs-lookup"><span data-stu-id="833b7-114">Use the PowerShell redirection operators.</span></span> <span data-ttu-id="833b7-115">Die Verwendung des Umleitungs Operators mit einem Dateiziel ist mit der Weiterleitung an `Out-File` ohne zusätzliche Parameter funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="833b7-115">Using the redirection operator with a file target is functionally equivalent to piping to `Out-File` with no extra parameters.</span></span>

<span data-ttu-id="833b7-116">Weitere Informationen zu Streams finden Sie unter [about_Output_Streams](about_Output_Streams.md).</span><span class="sxs-lookup"><span data-stu-id="833b7-116">For more information about streams, see [about_Output_Streams](about_Output_Streams.md).</span></span>

### <a name="redirectable-output-streams"></a><span data-ttu-id="833b7-117">Redirectable-Ausgabestreams</span><span class="sxs-lookup"><span data-stu-id="833b7-117">Redirectable output streams</span></span>

<span data-ttu-id="833b7-118">PowerShell unterstützt die Umleitung der folgenden Ausgabedaten Ströme.</span><span class="sxs-lookup"><span data-stu-id="833b7-118">PowerShell supports redirection of the following output streams.</span></span>

| <span data-ttu-id="833b7-119">Streich #</span><span class="sxs-lookup"><span data-stu-id="833b7-119">Stream #</span></span> |      <span data-ttu-id="833b7-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="833b7-120">Description</span></span>       | <span data-ttu-id="833b7-121">Eingeführt in</span><span class="sxs-lookup"><span data-stu-id="833b7-121">Introduced in</span></span>  |    <span data-ttu-id="833b7-122">Cmdlet schreiben</span><span class="sxs-lookup"><span data-stu-id="833b7-122">Write Cmdlet</span></span>     |
| -------- | ---------------------- | -------------- | ------------------- |
| <span data-ttu-id="833b7-123">1</span><span class="sxs-lookup"><span data-stu-id="833b7-123">1</span></span>        | <span data-ttu-id="833b7-124">**Erfolg** Streich</span><span class="sxs-lookup"><span data-stu-id="833b7-124">**Success** Stream</span></span>     | <span data-ttu-id="833b7-125">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="833b7-125">PowerShell 2.0</span></span> | `Write-Output`      |
| <span data-ttu-id="833b7-126">2</span><span class="sxs-lookup"><span data-stu-id="833b7-126">2</span></span>        | <span data-ttu-id="833b7-127">**Fehler** Streich</span><span class="sxs-lookup"><span data-stu-id="833b7-127">**Error** Stream</span></span>       | <span data-ttu-id="833b7-128">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="833b7-128">PowerShell 2.0</span></span> | `Write-Error`       |
| <span data-ttu-id="833b7-129">3</span><span class="sxs-lookup"><span data-stu-id="833b7-129">3</span></span>        | <span data-ttu-id="833b7-130">**Warnung** Streich</span><span class="sxs-lookup"><span data-stu-id="833b7-130">**Warning** Stream</span></span>     | <span data-ttu-id="833b7-131">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="833b7-131">PowerShell 3.0</span></span> | `Write-Warning`     |
| <span data-ttu-id="833b7-132">4</span><span class="sxs-lookup"><span data-stu-id="833b7-132">4</span></span>        | <span data-ttu-id="833b7-133"> Ausführlich Streich</span><span class="sxs-lookup"><span data-stu-id="833b7-133">**Verbose** Stream</span></span>     | <span data-ttu-id="833b7-134">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="833b7-134">PowerShell 3.0</span></span> | `Write-Verbose`     |
| <span data-ttu-id="833b7-135">5</span><span class="sxs-lookup"><span data-stu-id="833b7-135">5</span></span>        | <span data-ttu-id="833b7-136">**Debuggen** Streich</span><span class="sxs-lookup"><span data-stu-id="833b7-136">**Debug** Stream</span></span>       | <span data-ttu-id="833b7-137">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="833b7-137">PowerShell 3.0</span></span> | `Write-Debug`       |
| <span data-ttu-id="833b7-138">6</span><span class="sxs-lookup"><span data-stu-id="833b7-138">6</span></span>        | <span data-ttu-id="833b7-139">**Informationen** Streich</span><span class="sxs-lookup"><span data-stu-id="833b7-139">**Information** Stream</span></span> | <span data-ttu-id="833b7-140">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="833b7-140">PowerShell 5.0</span></span> | `Write-Information` |
| *        | <span data-ttu-id="833b7-141">Alle Streams</span><span class="sxs-lookup"><span data-stu-id="833b7-141">All Streams</span></span>            | <span data-ttu-id="833b7-142">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="833b7-142">PowerShell 3.0</span></span> |                     |

> [!NOTE]
> <span data-ttu-id="833b7-143">In PowerShell gibt es auch einen **Fortschritts** Datenstrom, der jedoch keine Umleitung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="833b7-143">There is also a **Progress** stream in PowerShell, but it does not support redirection.</span></span>

### <a name="powershell-redirection-operators"></a><span data-ttu-id="833b7-144">PowerShell-Umleitungs Operatoren</span><span class="sxs-lookup"><span data-stu-id="833b7-144">PowerShell redirection operators</span></span>

<span data-ttu-id="833b7-145">Die PowerShell-Umleitungs Operatoren lauten wie folgt, wobei `n` die streamnummer darstellt.</span><span class="sxs-lookup"><span data-stu-id="833b7-145">The PowerShell redirection operators are as follows, where `n` represents the stream number.</span></span> <span data-ttu-id="833b7-146">Der **Success** Stream ( `1` ) ist der Standardwert, wenn kein Stream angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="833b7-146">The **Success** stream ( `1` ) is the default if no stream is specified.</span></span>

| <span data-ttu-id="833b7-147">Operator</span><span class="sxs-lookup"><span data-stu-id="833b7-147">Operator</span></span> |                         <span data-ttu-id="833b7-148">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="833b7-148">Description</span></span>                         | <span data-ttu-id="833b7-149">Syntax</span><span class="sxs-lookup"><span data-stu-id="833b7-149">Syntax</span></span> |
| -------- | ----------------------------------------------------------- | ------ |
| `>`      | <span data-ttu-id="833b7-150">Sendet den angegebenen Stream an eine Datei.</span><span class="sxs-lookup"><span data-stu-id="833b7-150">Send specified stream to a file.</span></span>                            | `n>`   |
| `>>`     | <span data-ttu-id="833b7-151">**Anfügen** des angegebenen Streams an eine Datei.</span><span class="sxs-lookup"><span data-stu-id="833b7-151">**Append** specified stream to a file.</span></span>                      | `n>>`  |
| `>&1`    | <span data-ttu-id="833b7-152">_Leitet_ den angegebenen Stream an den **Erfolgs** Datenstrom um.</span><span class="sxs-lookup"><span data-stu-id="833b7-152">_Redirects_ the specified stream to the **Success** stream.</span></span> | `n>&1` |

> [!NOTE]
> <span data-ttu-id="833b7-153">Im Gegensatz zu einigen Unix-Shells können Sie nur andere Streams an den **Erfolgs** Datenstrom umleiten.</span><span class="sxs-lookup"><span data-stu-id="833b7-153">Unlike some Unix shells, you can only redirect other streams to the **Success** stream.</span></span>

## <a name="examples"></a><span data-ttu-id="833b7-154">Beispiele</span><span class="sxs-lookup"><span data-stu-id="833b7-154">Examples</span></span>

### <a name="example-1-redirect-errors-and-output-to-a-file"></a><span data-ttu-id="833b7-155">Beispiel 1: Umleiten von Fehlern und Ausgaben in eine Datei</span><span class="sxs-lookup"><span data-stu-id="833b7-155">Example 1: Redirect errors and output to a file</span></span>

<span data-ttu-id="833b7-156">Dieses Beispiel wird `dir` für ein Element ausgeführt, das erfolgreich ausgeführt werden kann, und eines, das einen Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="833b7-156">This example runs `dir` on one item that will succeed, and one that will error.</span></span>

```powershell
dir 'C:\', 'fakepath' 2>&1 > .\dir.log
```

<span data-ttu-id="833b7-157">Es verwendet, `2>&1` um den **Fehler** Datenstrom an den **Success** -Stream umzuleiten und `>` den resultierenden **Erfolgs** Datenstrom an eine Datei mit dem Namen `dir.log`</span><span class="sxs-lookup"><span data-stu-id="833b7-157">It uses `2>&1` to redirect the **Error** stream to the **Success** stream, and `>` to send the resultant **Success** stream to a file called `dir.log`</span></span>

### <a name="example-2-send-all-success-stream-data-to-a-file"></a><span data-ttu-id="833b7-158">Beispiel 2: Senden aller Erfolgs Datenstrom Daten an eine Datei</span><span class="sxs-lookup"><span data-stu-id="833b7-158">Example 2: Send all Success stream data to a file</span></span>

<span data-ttu-id="833b7-159">In diesem Beispiel werden alle **Erfolgs** Datenstrom Daten an eine Datei mit dem Namen gesendet `script.log` .</span><span class="sxs-lookup"><span data-stu-id="833b7-159">This example sends all **Success** stream data to a file called `script.log`.</span></span>

```powershell
.\script.ps1 > script.log
```

### <a name="example-3-send-success-warning-and-error-streams-to-a-file"></a><span data-ttu-id="833b7-160">Beispiel 3: Senden von Erfolgs-, Warnungs-und Fehler Datenströmen an eine Datei</span><span class="sxs-lookup"><span data-stu-id="833b7-160">Example 3: Send Success, Warning, and Error streams to a file</span></span>

<span data-ttu-id="833b7-161">Dieses Beispiel zeigt, wie Sie Umleitungs Operatoren kombinieren können, um ein gewünschtes Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="833b7-161">This example shows how you can combine redirection operators to achieve a desired result.</span></span>

```powershell
&{
   Write-Warning "hello"
   Write-Error "hello"
   Write-Output "hi"
} 3>&1 2>&1 > C:\Temp\redirection.log
```

- <span data-ttu-id="833b7-162">`3>&1` leitet den **Warnungs** Datenstrom an den **Erfolgs** Datenstrom um.</span><span class="sxs-lookup"><span data-stu-id="833b7-162">`3>&1` redirects the **Warning** stream to the **Success** stream.</span></span>
- <span data-ttu-id="833b7-163">`2>&1` leitet den **Fehler** Datenstrom an den **Success** -Stream um (der jetzt auch alle **Warnungs** Datenstrom Daten enthält)</span><span class="sxs-lookup"><span data-stu-id="833b7-163">`2>&1` redirects the **Error** stream to the **Success** stream (which also now includes all **Warning** stream data)</span></span>
- <span data-ttu-id="833b7-164">`>` leitet den **Erfolgs** Datenstrom (der nun sowohl **Warnungs** -als auch **Fehler** Datenströme enthält) in eine Datei mit `C:\temp\redirection.log` dem Namen um.</span><span class="sxs-lookup"><span data-stu-id="833b7-164">`>` redirects the **Success** stream (which now contains both **Warning** and **Error** streams) to a file called `C:\temp\redirection.log`)</span></span>

### <a name="example-4-redirect-all-streams-to-a-file"></a><span data-ttu-id="833b7-165">Beispiel 4: Umleiten aller Streams an eine Datei</span><span class="sxs-lookup"><span data-stu-id="833b7-165">Example 4: Redirect all streams to a file</span></span>

<span data-ttu-id="833b7-166">In diesem Beispiel werden alle Streams-Ausgaben von einem Skript namens `script.ps1` an eine Datei mit dem Namen gesendet. `script.log`</span><span class="sxs-lookup"><span data-stu-id="833b7-166">This example sends all streams output from a script called `script.ps1` to a file called `script.log`</span></span>

```powershell
.\script.ps1 *> script.log
```

### <a name="example-5-suppress-all-write-host-and-information-stream-data"></a><span data-ttu-id="833b7-167">Beispiel 5: unterdrücken aller Write-Host-und Informationsdaten Strom Daten</span><span class="sxs-lookup"><span data-stu-id="833b7-167">Example 5: Suppress all Write-Host and Information stream data</span></span>

<span data-ttu-id="833b7-168">In diesem Beispiel werden alle Datenstrom Daten unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="833b7-168">This example suppresses all information stream data.</span></span> <span data-ttu-id="833b7-169">Weitere Informationen zu Cmdlets für den **Informations** Strom finden Sie unter [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) und [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) .</span><span class="sxs-lookup"><span data-stu-id="833b7-169">To read more about **Information** stream cmdlets, see [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) and [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)</span></span>

```powershell
&{
   Write-Host "Hello"
   Write-Information "Hello" -InformationAction Continue
} 6> $null
```

### <a name="example-6-show-the-effect-of-action-preferences"></a><span data-ttu-id="833b7-170">Beispiel 6: Anzeigen der Auswirkung von Aktions Einstellungen</span><span class="sxs-lookup"><span data-stu-id="833b7-170">Example 6: Show the effect of Action Preferences</span></span>

<span data-ttu-id="833b7-171">Aktions Einstellungs Variablen und Parameter können ändern, was in einen bestimmten Stream geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="833b7-171">Action Preference variables and parameters can change what gets written to a particular stream.</span></span> <span data-ttu-id="833b7-172">Das Skript in diesem Beispiel zeigt, wie sich der Wert von auf den Wert `$ErrorActionPreference` auswirkt, der in den **Fehler** Datenstrom geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="833b7-172">The script in this example shows how the value of `$ErrorActionPreference` affects what gets written to the **Error** stream.</span></span>

```powershell
$ErrorActionPreference = 'Continue'
$ErrorActionPreference > log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'SilentlyContinue'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Stop'
$ErrorActionPreference >> log.txt
Try {
    get-item /not-here 2>&1 >> log.txt
}
catch {
    "`tError caught!" >> log.txt
}
$ErrorActionPreference = 'Ignore'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Inquire'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Continue'
```

<span data-ttu-id="833b7-173">Wenn Sie dieses Skript ausführen, werden Sie aufgefordert `$ErrorActionPreference` , wenn auf festgelegt ist `Inquire` .</span><span class="sxs-lookup"><span data-stu-id="833b7-173">When we run this script we get prompted when `$ErrorActionPreference` is set to `Inquire`.</span></span>

```powershell
PS C:\temp> .\test.ps1

Confirm
Cannot find path 'C:\not-here' because it does not exist.
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): H
Get-Item: C:\temp\test.ps1:23
Line |
  23 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | The running command stopped because the user selected the Stop option.
```

<span data-ttu-id="833b7-174">Wenn wir die Protokolldatei untersuchen, wird Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="833b7-174">When we examine the log file we see the following:</span></span>

```
PS C:\temp> Get-Content .\log.txt
Continue

Get-Item: C:\temp\test.ps1:3
Line |
   3 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | Cannot find path 'C:\not-here' because it does not exist.

SilentlyContinue
Stop
    Error caught!
Ignore
Inquire
```

## <a name="notes"></a><span data-ttu-id="833b7-175">Hinweise</span><span class="sxs-lookup"><span data-stu-id="833b7-175">Notes</span></span>

<span data-ttu-id="833b7-176">Die Umleitungs Operatoren, die keine Daten anfügen ( `>` und `n>` ), überschreiben den aktuellen Inhalt der angegebenen Datei ohne Warnung.</span><span class="sxs-lookup"><span data-stu-id="833b7-176">The redirection operators that do not append data (`>` and `n>`) overwrite the current contents of the specified file without warning.</span></span>

<span data-ttu-id="833b7-177">Wenn die Datei jedoch eine schreibgeschützte, verborgene oder Systemdatei ist, tritt ein Fehler bei der **Umleitung auf**.</span><span class="sxs-lookup"><span data-stu-id="833b7-177">However, if the file is a read-only, hidden, or system file, the redirection **fails**.</span></span> <span data-ttu-id="833b7-178">Die Anfüge Weiterleitungs Operatoren ( `>>` und `n>>` ) schreiben nicht in eine schreibgeschützte Datei, fügen aber Inhalte an ein System oder eine ausgeblendete Datei an.</span><span class="sxs-lookup"><span data-stu-id="833b7-178">The append redirection operators (`>>` and `n>>`) do not write to a read-only file, but they append content to a system or hidden file.</span></span>

<span data-ttu-id="833b7-179">Verwenden Sie das Cmdlet mit dem-Parameter, um die Umleitung von Inhalt in eine schreibgeschützte, verborgene oder Systemdatei zu erzwingen `Out-File` `Force` .</span><span class="sxs-lookup"><span data-stu-id="833b7-179">To force the redirection of content to a read-only, hidden, or system file, use the `Out-File` cmdlet with its `Force` parameter.</span></span>

<span data-ttu-id="833b7-180">Beim Schreiben in Dateien verwenden die Umleitungs Operatoren die `UTF8NoBOM` Codierung.</span><span class="sxs-lookup"><span data-stu-id="833b7-180">When you are writing to files, the redirection operators use `UTF8NoBOM` encoding.</span></span> <span data-ttu-id="833b7-181">Wenn die Datei eine andere Codierung hat, ist die Ausgabe möglicherweise nicht ordnungsgemäß formatiert.</span><span class="sxs-lookup"><span data-stu-id="833b7-181">If the file has a different encoding, the output might not be formatted correctly.</span></span> <span data-ttu-id="833b7-182">Um in Dateien mit einer anderen Codierung zu schreiben, verwenden Sie das- `Out-File` Cmdlet mit dem- `Encoding` Parameter.</span><span class="sxs-lookup"><span data-stu-id="833b7-182">To write to files with a different encoding, use the `Out-File` cmdlet with its `Encoding` parameter.</span></span>

### <a name="potential-confusion-with-comparison-operators"></a><span data-ttu-id="833b7-183">Mögliche Verwirrung mit Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="833b7-183">Potential confusion with comparison operators</span></span>

<span data-ttu-id="833b7-184">Der `>` Operator muss nicht mit dem Operator " [größer als](about_Comparison_Operators.md#-gt--ge--lt-and--le) Vergleichs Operator" verwechselt werden (oftmals als `>` in anderen Programmiersprachen bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="833b7-184">The `>` operator is not to be confused with the [Greater-than](about_Comparison_Operators.md#-gt--ge--lt-and--le) comparison operator (often denoted as `>` in other programming languages).</span></span>

<span data-ttu-id="833b7-185">Abhängig von den verglichenen Objekten kann die Ausgabe mit `>` korrekt erscheinen (da 36 nicht größer als 42 ist).</span><span class="sxs-lookup"><span data-stu-id="833b7-185">Depending on the objects being compared, the output using `>` can appear to be correct (because 36 is not greater than 42).</span></span>

```powershell
PS> if (36 > 42) { "true" } else { "false" }
false
```

<span data-ttu-id="833b7-186">Eine Überprüfung des lokalen Dateisystems kann jedoch sehen, dass eine Datei `42` mit dem Namen mit dem Inhalt geschrieben wurde `36` .</span><span class="sxs-lookup"><span data-stu-id="833b7-186">However, a check of the local filesystem can see that a file called `42` was written, with the contents `36`.</span></span>

```powershell
PS> dir

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
------          1/02/20  10:10 am              3 42

PS> cat 42
36
```

<span data-ttu-id="833b7-187">Wenn Sie versuchen, den umgekehrten Vergleich `<` (kleiner als) zu verwenden, ergibt sich ein Systemfehler:</span><span class="sxs-lookup"><span data-stu-id="833b7-187">Attempting to use the reverse comparison `<` (less than), yields a system error:</span></span>

```powershell
PS> if (36 < 42) { "true" } else { "false" }
At line:1 char:8
+ if (36 < 42) { "true" } else { "false" }
+        ~
The '<' operator is reserved for future use.
    + CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
    + FullyQualifiedErrorId : RedirectionNotSupported
```

<span data-ttu-id="833b7-188">Wenn der numerische Vergleich der erforderliche Vorgang ist `-lt` , `-gt` sollte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="833b7-188">If numeric comparison is the required operation, `-lt` and `-gt` should be used.</span></span> <span data-ttu-id="833b7-189">Weitere Informationen finden Sie unter dem- `-gt` Operator in [about_Comparison_Operators](about_Comparison_Operators.md#-gt--ge--lt-and--le).</span><span class="sxs-lookup"><span data-stu-id="833b7-189">For more information, see the `-gt` operator in [about_Comparison_Operators](about_Comparison_Operators.md#-gt--ge--lt-and--le).</span></span>

## <a name="see-also"></a><span data-ttu-id="833b7-190">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="833b7-190">See also</span></span>

- [<span data-ttu-id="833b7-191">Out-File</span><span class="sxs-lookup"><span data-stu-id="833b7-191">Out-File</span></span>](xref:Microsoft.PowerShell.Utility.Out-File)
- [<span data-ttu-id="833b7-192">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="833b7-192">Tee-Object</span></span>](xref:Microsoft.PowerShell.Utility.Tee-Object)
- [<span data-ttu-id="833b7-193">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="833b7-193">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="833b7-194">Write-Error</span><span class="sxs-lookup"><span data-stu-id="833b7-194">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)
- [<span data-ttu-id="833b7-195">Write-Host</span><span class="sxs-lookup"><span data-stu-id="833b7-195">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)
- [<span data-ttu-id="833b7-196">Write-Information</span><span class="sxs-lookup"><span data-stu-id="833b7-196">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)
- [<span data-ttu-id="833b7-197">Write-Output</span><span class="sxs-lookup"><span data-stu-id="833b7-197">Write-Output</span></span>](xref:Microsoft.PowerShell.Utility.Write-Output)
- [<span data-ttu-id="833b7-198">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="833b7-198">Write-Progress</span></span>](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [<span data-ttu-id="833b7-199">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="833b7-199">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [<span data-ttu-id="833b7-200">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="833b7-200">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [<span data-ttu-id="833b7-201">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="833b7-201">about_Output_Streams</span></span>](about_Output_Streams.md)
- [<span data-ttu-id="833b7-202">about_Operators</span><span class="sxs-lookup"><span data-stu-id="833b7-202">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="833b7-203">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="833b7-203">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="833b7-204">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="833b7-204">about_Path_Syntax</span></span>](about_Path_Syntax.md)
