---
description: Beschreibt die `Prompt` -Funktion und veranschaulicht, wie eine benutzerdefinierte Funktion erstellt wird `Prompt` .
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_prompts?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Prompts
ms.openlocfilehash: 15746fe1ce2c79189dd604b5b6244e337ad389a1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222628"
---
# <a name="about-prompts"></a><span data-ttu-id="88dfe-104">Informationen zu Aufforderungen</span><span class="sxs-lookup"><span data-stu-id="88dfe-104">About Prompts</span></span>

## <a name="short-description"></a><span data-ttu-id="88dfe-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88dfe-105">Short description</span></span>
<span data-ttu-id="88dfe-106">Beschreibt die `Prompt` -Funktion und veranschaulicht, wie eine benutzerdefinierte Funktion erstellt wird `Prompt` .</span><span class="sxs-lookup"><span data-stu-id="88dfe-106">Describes the `Prompt` function and demonstrates how to create a custom `Prompt` function.</span></span>

## <a name="long-description"></a><span data-ttu-id="88dfe-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88dfe-107">Long description</span></span>

<span data-ttu-id="88dfe-108">Die PowerShell-Eingabeaufforderung zeigt an, dass PowerShell zum Ausführen eines Befehls bereit ist:</span><span class="sxs-lookup"><span data-stu-id="88dfe-108">The PowerShell command prompt indicates that PowerShell is ready to run a command:</span></span>

```
PS C:\>
```

<span data-ttu-id="88dfe-109">Die PowerShell-Eingabeaufforderung wird durch die integrierte- `Prompt` Funktion bestimmt.</span><span class="sxs-lookup"><span data-stu-id="88dfe-109">The PowerShell prompt is determined by the built-in `Prompt` function.</span></span> <span data-ttu-id="88dfe-110">Sie können die Eingabeaufforderung anpassen, indem Sie Ihre eigene `Prompt` Funktion erstellen und in Ihrem PowerShell-Profil speichern.</span><span class="sxs-lookup"><span data-stu-id="88dfe-110">You can customize the prompt by creating your own `Prompt` function and saving it in your PowerShell profile.</span></span>

## <a name="about-the-prompt-function"></a><span data-ttu-id="88dfe-111">Informationen zur prompt-Funktion</span><span class="sxs-lookup"><span data-stu-id="88dfe-111">About the Prompt function</span></span>

<span data-ttu-id="88dfe-112">Die `Prompt` Funktion bestimmt das Aussehen der PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="88dfe-112">The `Prompt` function determines the appearance of the PowerShell prompt.</span></span>
<span data-ttu-id="88dfe-113">PowerShell verfügt über eine integrierte `Prompt` Funktion, aber Sie können Sie überschreiben, indem Sie eine eigene `Prompt` Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="88dfe-113">PowerShell comes with a built-in `Prompt` function, but you can override it by defining your own `Prompt` function.</span></span>

<span data-ttu-id="88dfe-114">Die `Prompt` Funktion weist die folgende Syntax auf:</span><span class="sxs-lookup"><span data-stu-id="88dfe-114">The `Prompt` function has the following syntax:</span></span>

```powershell
function Prompt { <function-body> }
```

<span data-ttu-id="88dfe-115">Die `Prompt` Funktion muss ein Objekt zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="88dfe-115">The `Prompt` function must return an object.</span></span> <span data-ttu-id="88dfe-116">Als bewährte Vorgehensweise wird eine Zeichenfolge oder ein Objekt zurückgegeben, das als Zeichenfolge formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="88dfe-116">As a best practice, return a string or an object that is formatted as a string.</span></span> <span data-ttu-id="88dfe-117">Die empfohlene maximale Länge beträgt 80 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="88dfe-117">The maximum recommended length is 80 characters.</span></span>

<span data-ttu-id="88dfe-118">Beispielsweise gibt die folgende `Prompt` Funktion eine Zeichenfolge "Hello, World" gefolgt von einer rechten Spitze Klammer ( `>` ) zurück.</span><span class="sxs-lookup"><span data-stu-id="88dfe-118">For example, the following `Prompt` function returns a "Hello, World" string followed by a  right angle bracket (`>`).</span></span>

```powershell
PS C:\> function prompt {"Hello, World > "}
Hello, World >
```

### <a name="getting-the-prompt-function"></a><span data-ttu-id="88dfe-119">Anfordern der prompt-Funktion</span><span class="sxs-lookup"><span data-stu-id="88dfe-119">Getting the Prompt function</span></span>

<span data-ttu-id="88dfe-120">Um die Funktion zu erhalten `Prompt` , verwenden Sie das `Get-Command` Cmdlet, oder verwenden Sie das `Get-Item` Cmdlet im Funktions Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="88dfe-120">To get the `Prompt` function, use the `Get-Command` cmdlet or use the `Get-Item` cmdlet in the Function drive.</span></span>

<span data-ttu-id="88dfe-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88dfe-121">For example:</span></span>

```powershell
PS C:\> Get-Command Prompt

CommandType     Name      ModuleName
-----------     ----      ----------
Function        prompt
```

<span data-ttu-id="88dfe-122">Um das Skript zu erhalten, mit dem der Wert der Eingabeaufforderung festgelegt wird, verwenden Sie die Punkt-Methode, um die **ScriptBlock** -Eigenschaft der Funktion zu erhalten `Prompt` .</span><span class="sxs-lookup"><span data-stu-id="88dfe-122">To get the script that sets the value of the prompt, use the dot method to get the **ScriptBlock** property of the `Prompt` function.</span></span>

<span data-ttu-id="88dfe-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88dfe-123">For example:</span></span>

```powershell
(Get-Command Prompt).ScriptBlock
```

```Output
"PS $($executionContext.SessionState.Path.CurrentLocation)$('>' * ($nestedPromptLevel + 1)) "
# .Link
# https://go.microsoft.com/fwlink/?LinkID=225750
# .ExternalHelp System.Management.Automation.dll-help.xml
```

<span data-ttu-id="88dfe-124">Wie alle Funktionen wird die `Prompt` Funktion auf dem Laufwerk gespeichert `Function:` .</span><span class="sxs-lookup"><span data-stu-id="88dfe-124">Like all functions, the `Prompt` function is stored in the `Function:` drive.</span></span>
<span data-ttu-id="88dfe-125">Zum Anzeigen des Skripts, das die aktuelle Funktion erstellt, geben Sie Folgendes ein `Prompt` :</span><span class="sxs-lookup"><span data-stu-id="88dfe-125">To display the script that creates the current `Prompt` function, type:</span></span>

```powershell
(Get-Item function:prompt).ScriptBlock
```

### <a name="the-default-prompt"></a><span data-ttu-id="88dfe-126">Die Standardeingabe Aufforderung</span><span class="sxs-lookup"><span data-stu-id="88dfe-126">The default prompt</span></span>

<span data-ttu-id="88dfe-127">Die Standardeingabe Aufforderung wird nur angezeigt, wenn die `Prompt` Funktion einen Fehler generiert oder kein Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="88dfe-127">The default prompt appears only when the `Prompt` function generates an error or does not return an object.</span></span>

<span data-ttu-id="88dfe-128">Die PowerShell-Standardeingabe Aufforderung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="88dfe-128">The default PowerShell prompt is:</span></span>

```
PS>
```

<span data-ttu-id="88dfe-129">Mit dem folgenden Befehl wird beispielsweise die- `Prompt` Funktion auf festgelegt `$null` , was ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="88dfe-129">For example, the following command sets the `Prompt` function to `$null`, which is invalid.</span></span> <span data-ttu-id="88dfe-130">Daher wird die Standardeingabe Aufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88dfe-130">As a result, the default prompt appears.</span></span>

```powershell
PS C:\> function prompt {$null}
PS>
```

<span data-ttu-id="88dfe-131">Da PowerShell über eine integrierte Eingabeaufforderung verfügt, wird die Standardeingabe Aufforderung in der Regel nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88dfe-131">Because PowerShell comes with a built-in prompt, you usually do not see the default prompt.</span></span>

### <a name="built-in-prompt"></a><span data-ttu-id="88dfe-132">Integrierte Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="88dfe-132">Built-in prompt</span></span>

<span data-ttu-id="88dfe-133">PowerShell enthält eine integrierte `Prompt` Funktion.</span><span class="sxs-lookup"><span data-stu-id="88dfe-133">PowerShell includes a built-in `Prompt` function.</span></span>

```powershell
function prompt {
    $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
      else { '' }) + 'PS ' + $(Get-Location) +
        $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="88dfe-134">Die-Funktion verwendet das- `Test-Path` Cmdlet, um zu bestimmen, ob die `$PSDebugContext` Automatische Variable aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="88dfe-134">The function uses the `Test-Path` cmdlet to determine whether the `$PSDebugContext` automatic variable is populated.</span></span> <span data-ttu-id="88dfe-135">Wenn aufgefüllt `$PSDebugContext` wird, befinden Sie sich im Debugmodus und werden `[DBG]:` der Eingabeaufforderung wie folgt hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="88dfe-135">If `$PSDebugContext` is populated, you are in debugging mode, and `[DBG]:` is added to the prompt, as follows:</span></span>

```Output
[DBG]: PS C:\ps-test>
```

<span data-ttu-id="88dfe-136">Wenn `$PSDebugContext` nicht aufgefüllt wird, fügt die Funktion `PS` der Eingabeaufforderung hinzu.</span><span class="sxs-lookup"><span data-stu-id="88dfe-136">If `$PSDebugContext` is not populated, the function adds `PS` to the prompt.</span></span>
<span data-ttu-id="88dfe-137">Und die-Funktion verwendet das- `Get-Location` Cmdlet, um den Speicherort des aktuellen Dateisystem Verzeichnisses zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="88dfe-137">And, the function uses the `Get-Location` cmdlet to get the current file system directory location.</span></span> <span data-ttu-id="88dfe-138">Anschließend wird eine schließende spitze Klammer () hinzugefügt `>` .</span><span class="sxs-lookup"><span data-stu-id="88dfe-138">Then, it adds a right angle bracket (`>`).</span></span>

<span data-ttu-id="88dfe-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88dfe-139">For example:</span></span>

```Output
PS C:\ps-test>
```

<span data-ttu-id="88dfe-140">Wenn Sie sich in einer eingefügten Eingabeaufforderung befinden, fügt die Funktion der Eingabeaufforderung zwei eckige Klammern ( `>>` ) hinzu.</span><span class="sxs-lookup"><span data-stu-id="88dfe-140">If you are in a nested prompt, the function adds two angle brackets (`>>`) to the prompt.</span></span> <span data-ttu-id="88dfe-141">(Sie befinden sich in einer eingefügten Eingabeaufforderung, wenn der Wert der `$NestedPromptLevel` automatischen Variablen größer als 1 ist.)</span><span class="sxs-lookup"><span data-stu-id="88dfe-141">(You are in a nested prompt if the value of the `$NestedPromptLevel` automatic variable is greater than 1.)</span></span>

<span data-ttu-id="88dfe-142">Wenn Sie z. b. in einer eingefügten Aufforderung Debuggen, wird die Eingabeaufforderung ähnlich der folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="88dfe-142">For example, when you are debugging in a nested prompt, the prompt resembles the following prompt:</span></span>

```Output
[DBG] PS C:\ps-test>>>
```

### <a name="changes-to-the-prompt"></a><span data-ttu-id="88dfe-143">Änderungen an der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="88dfe-143">Changes to the prompt</span></span>

<span data-ttu-id="88dfe-144">Das- `Enter-PSSession` Cmdlet fügt den Namen des Remote Computers der aktuellen `Prompt` Funktion voran.</span><span class="sxs-lookup"><span data-stu-id="88dfe-144">The `Enter-PSSession` cmdlet prepends the name of the remote computer to the current `Prompt` function.</span></span> <span data-ttu-id="88dfe-145">Wenn Sie mit dem `Enter-PSSession` Cmdlet eine Sitzung mit einem Remote Computer starten, wird die Eingabeaufforderung geändert, sodass Sie den Namen des Remote Computers enthält.</span><span class="sxs-lookup"><span data-stu-id="88dfe-145">When you use the `Enter-PSSession` cmdlet to start a session with a remote computer, the command prompt changes to include the name of the remote computer.</span></span> <span data-ttu-id="88dfe-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88dfe-146">For example:</span></span>

```Output
PS Hello, World> Enter-PSSession Server01
[Server01]: PS Hello, World>
```

<span data-ttu-id="88dfe-147">Andere PowerShell-Host Anwendungen und Alternative Shells verfügen möglicherweise über eigene benutzerdefinierte Eingabe Aufforderungen.</span><span class="sxs-lookup"><span data-stu-id="88dfe-147">Other PowerShell host applications and alternate shells might have their own custom command prompts.</span></span>

<span data-ttu-id="88dfe-148">Weitere Informationen zu den `$PSDebugContext` `$NestedPromptLevel` automatischen Variablen und finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="88dfe-148">For more information about the `$PSDebugContext` and `$NestedPromptLevel` automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

### <a name="how-to-customize-the-prompt"></a><span data-ttu-id="88dfe-149">Vorgehensweise beim Anpassen der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="88dfe-149">How to customize the prompt</span></span>

<span data-ttu-id="88dfe-150">Zum Anpassen der Eingabeaufforderung schreiben Sie eine neue `Prompt` Funktion.</span><span class="sxs-lookup"><span data-stu-id="88dfe-150">To customize the prompt, write a new `Prompt` function.</span></span> <span data-ttu-id="88dfe-151">Die Funktion ist nicht geschützt, sodass Sie Sie überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="88dfe-151">The function is not protected, so you can overwrite it.</span></span>

<span data-ttu-id="88dfe-152">Geben Sie Folgendes ein, um eine Funktion zu schreiben `Prompt` :</span><span class="sxs-lookup"><span data-stu-id="88dfe-152">To write a `Prompt` function, type the following:</span></span>

```powershell
function prompt { }
```

<span data-ttu-id="88dfe-153">Geben Sie dann zwischen den geschweiften Klammern die Befehle oder die Zeichenfolge ein, mit der die Eingabeaufforderung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="88dfe-153">Then, between the braces, enter the commands or the string that creates your prompt.</span></span>

<span data-ttu-id="88dfe-154">Beispielsweise enthält die folgende Eingabeaufforderung Ihren Computernamen:</span><span class="sxs-lookup"><span data-stu-id="88dfe-154">For example, the following prompt includes your computer name:</span></span>

```powershell
function prompt {"PS [$env:COMPUTERNAME]> "}
```

<span data-ttu-id="88dfe-155">Auf dem Server01-Computer ähnelt die Eingabeaufforderung der folgenden Eingabeaufforderung:</span><span class="sxs-lookup"><span data-stu-id="88dfe-155">On the Server01 computer, the prompt resembles the following prompt:</span></span>

```Output
PS [Server01] >
```

<span data-ttu-id="88dfe-156">Die folgende `Prompt` Funktion enthält das aktuelle Datum und die Uhrzeit:</span><span class="sxs-lookup"><span data-stu-id="88dfe-156">The following `Prompt` function includes the current date and time:</span></span>

```powershell
function prompt {"$(Get-Date)> "}
```

<span data-ttu-id="88dfe-157">Die Eingabeaufforderung ähnelt der folgenden Eingabeaufforderung:</span><span class="sxs-lookup"><span data-stu-id="88dfe-157">The prompt resembles the following prompt:</span></span>

```Output
03/15/2012 17:49:47>
```

<span data-ttu-id="88dfe-158">Sie können auch die Standard `Prompt` Funktion ändern:</span><span class="sxs-lookup"><span data-stu-id="88dfe-158">You can also change the default `Prompt` function:</span></span>

<span data-ttu-id="88dfe-159">Beispielsweise fügt die folgende geänderte `Prompt` Funktion `[ADMIN]:` der integrierten PowerShell-Eingabeaufforderung hinzu, wenn PowerShell mit der Option **als Administrator ausführen** geöffnet wird:</span><span class="sxs-lookup"><span data-stu-id="88dfe-159">For example, the following modified `Prompt` function adds `[ADMIN]:` to the built-in PowerShell prompt when PowerShell is opened by using the **Run as administrator** option:</span></span>

```powershell
function prompt {
  $identity = [Security.Principal.WindowsIdentity]::GetCurrent()
  $principal = [Security.Principal.WindowsPrincipal] $identity
  $adminRole = [Security.Principal.WindowsBuiltInRole]::Administrator

  $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
    elseif($principal.IsInRole($adminRole)) { "[ADMIN]: " }
    else { '' }
  ) + 'PS ' + $(Get-Location) +
    $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="88dfe-160">Wenn Sie PowerShell mit der Option **als Administrator ausführen** starten, wird eine Aufforderung angezeigt, die der folgenden Eingabeaufforderung ähnelt:</span><span class="sxs-lookup"><span data-stu-id="88dfe-160">When you start PowerShell by using the **Run as administrator** option, a prompt that resembles the following prompt appears:</span></span>

```Output
[ADMIN]: PS C:\ps-test>
```

<span data-ttu-id="88dfe-161">Mit der folgenden Funktion wird die Verlaufs- `Prompt` ID des nächsten Befehls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88dfe-161">The following `Prompt` function displays the history ID of the next command.</span></span> <span data-ttu-id="88dfe-162">Verwenden Sie das-Cmdlet, um den Befehlsverlauf anzuzeigen `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="88dfe-162">To view the command history, use the `Get-History` cmdlet.</span></span>

```powershell
function prompt {
   # The at sign creates an array in case only one history item exists.
   $history = @(Get-History)
   if($history.Count -gt 0)
   {
      $lastItem = $history[$history.Count - 1]
      $lastId = $lastItem.Id
   }

   $nextCommand = $lastId + 1
   $currentDirectory = Get-Location
   "PS: $nextCommand $currentDirectory >"
}
```

<span data-ttu-id="88dfe-163">Die folgende Eingabeaufforderung verwendet `Write-Host` die `Get-Random` Cmdlets und, um eine Eingabeaufforderung zu erstellen, die die Farbe nach dem Zufallsprinzip</span><span class="sxs-lookup"><span data-stu-id="88dfe-163">The following prompt uses the `Write-Host` and `Get-Random` cmdlets to create a prompt that changes color randomly.</span></span> <span data-ttu-id="88dfe-164">Da `Write-Host` in die aktuelle Host Anwendung geschrieben wird, aber kein-Objekt zurückgegeben wird, enthält diese Funktion eine- `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="88dfe-164">Because `Write-Host` writes to the current host application but does not return an object, this function includes a `Return` statement.</span></span> <span data-ttu-id="88dfe-165">Ohne diesen Befehl verwendet PowerShell die Standardeingabe Aufforderung `PS>` .</span><span class="sxs-lookup"><span data-stu-id="88dfe-165">Without it, PowerShell uses the default prompt, `PS>`.</span></span>

```powershell
function prompt {
    $color = Get-Random -Min 1 -Max 16
    Write-Host ("PS " + $(Get-Location) +">") -NoNewLine `
     -ForegroundColor $Color
    return " "
}
```

### <a name="saving-the-prompt-function"></a><span data-ttu-id="88dfe-166">Speichern der prompt-Funktion</span><span class="sxs-lookup"><span data-stu-id="88dfe-166">Saving the Prompt function</span></span>

<span data-ttu-id="88dfe-167">Wie jede beliebige Funktion ist die `Prompt` Funktion nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="88dfe-167">Like any function, the `Prompt` function exists only in the current session.</span></span> <span data-ttu-id="88dfe-168">Um die `Prompt` Funktion für zukünftige Sitzungen zu speichern, fügen Sie Sie Ihren PowerShell-Profilen hinzu.</span><span class="sxs-lookup"><span data-stu-id="88dfe-168">To save the `Prompt` function for future sessions, add it to your PowerShell profiles.</span></span> <span data-ttu-id="88dfe-169">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="88dfe-169">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="88dfe-170">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="88dfe-170">See also</span></span>

[<span data-ttu-id="88dfe-171">Get-Location</span><span class="sxs-lookup"><span data-stu-id="88dfe-171">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)

[<span data-ttu-id="88dfe-172">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="88dfe-172">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="88dfe-173">Get-History</span><span class="sxs-lookup"><span data-stu-id="88dfe-173">Get-History</span></span>](xref:Microsoft.PowerShell.Core.Get-History)

[<span data-ttu-id="88dfe-174">Get-Random</span><span class="sxs-lookup"><span data-stu-id="88dfe-174">Get-Random</span></span>](xref:Microsoft.PowerShell.Utility.Get-Random)

[<span data-ttu-id="88dfe-175">Write-Host</span><span class="sxs-lookup"><span data-stu-id="88dfe-175">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)

[<span data-ttu-id="88dfe-176">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="88dfe-176">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="88dfe-177">about_Functions</span><span class="sxs-lookup"><span data-stu-id="88dfe-177">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="88dfe-178">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="88dfe-178">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="88dfe-179">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="88dfe-179">about_Debuggers</span></span>](about_Debuggers.md)

[<span data-ttu-id="88dfe-180">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="88dfe-180">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
