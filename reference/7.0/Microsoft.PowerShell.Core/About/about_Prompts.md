---
description: Beschreibt die `Prompt` -Funktion und veranschaulicht, wie eine benutzerdefinierte Funktion erstellt wird `Prompt` .
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_prompts?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Prompts
ms.openlocfilehash: 3e1496c84fa528b4673a770b5b2777fc3d31dc34
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220663"
---
# <a name="about-prompts"></a>Informationen zu Aufforderungen

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt die `Prompt` -Funktion und veranschaulicht, wie eine benutzerdefinierte Funktion erstellt wird `Prompt` .

## <a name="long-description"></a>Lange Beschreibung

Die PowerShell-Eingabeaufforderung zeigt an, dass PowerShell zum Ausführen eines Befehls bereit ist:

```
PS C:\>
```

Die PowerShell-Eingabeaufforderung wird durch die integrierte- `Prompt` Funktion bestimmt. Sie können die Eingabeaufforderung anpassen, indem Sie Ihre eigene `Prompt` Funktion erstellen und in Ihrem PowerShell-Profil speichern.

## <a name="about-the-prompt-function"></a>Informationen zur prompt-Funktion

Die `Prompt` Funktion bestimmt das Aussehen der PowerShell-Eingabeaufforderung.
PowerShell verfügt über eine integrierte `Prompt` Funktion, aber Sie können Sie überschreiben, indem Sie eine eigene `Prompt` Funktion definieren.

Die `Prompt` Funktion weist die folgende Syntax auf:

```powershell
function Prompt { <function-body> }
```

Die `Prompt` Funktion muss ein Objekt zurückgeben. Als bewährte Vorgehensweise wird eine Zeichenfolge oder ein Objekt zurückgegeben, das als Zeichenfolge formatiert ist. Die empfohlene maximale Länge beträgt 80 Zeichen.

Beispielsweise gibt die folgende `Prompt` Funktion eine Zeichenfolge "Hello, World" gefolgt von einer rechten Spitze Klammer ( `>` ) zurück.

```powershell
PS C:\> function prompt {"Hello, World > "}
Hello, World >
```

### <a name="getting-the-prompt-function"></a>Anfordern der prompt-Funktion

Um die Funktion zu erhalten `Prompt` , verwenden Sie das `Get-Command` Cmdlet, oder verwenden Sie das `Get-Item` Cmdlet im Funktions Laufwerk.

Beispiel:

```powershell
PS C:\> Get-Command Prompt

CommandType     Name      ModuleName
-----------     ----      ----------
Function        prompt
```

Um das Skript zu erhalten, mit dem der Wert der Eingabeaufforderung festgelegt wird, verwenden Sie die Punkt-Methode, um die **ScriptBlock** -Eigenschaft der Funktion zu erhalten `Prompt` .

Beispiel:

```powershell
(Get-Command Prompt).ScriptBlock
```

```Output
"PS $($executionContext.SessionState.Path.CurrentLocation)$('>' * ($nestedPromptLevel + 1)) "
# .Link
# https://go.microsoft.com/fwlink/?LinkID=225750
# .ExternalHelp System.Management.Automation.dll-help.xml
```

Wie alle Funktionen wird die `Prompt` Funktion auf dem Laufwerk gespeichert `Function:` .
Zum Anzeigen des Skripts, das die aktuelle Funktion erstellt, geben Sie Folgendes ein `Prompt` :

```powershell
(Get-Item function:prompt).ScriptBlock
```

### <a name="the-default-prompt"></a>Die Standardeingabe Aufforderung

Die Standardeingabe Aufforderung wird nur angezeigt, wenn die `Prompt` Funktion einen Fehler generiert oder kein Objekt zurückgibt.

Die PowerShell-Standardeingabe Aufforderung lautet wie folgt:

```
PS>
```

Mit dem folgenden Befehl wird beispielsweise die- `Prompt` Funktion auf festgelegt `$null` , was ungültig ist. Daher wird die Standardeingabe Aufforderung angezeigt.

```powershell
PS C:\> function prompt {$null}
PS>
```

Da PowerShell über eine integrierte Eingabeaufforderung verfügt, wird die Standardeingabe Aufforderung in der Regel nicht angezeigt.

### <a name="built-in-prompt"></a>Integrierte Eingabeaufforderung

PowerShell enthält eine integrierte `Prompt` Funktion.

```powershell
function prompt {
    $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
      else { '' }) + 'PS ' + $(Get-Location) +
        $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

Die-Funktion verwendet das- `Test-Path` Cmdlet, um zu bestimmen, ob die `$PSDebugContext` Automatische Variable aufgefüllt wird. Wenn aufgefüllt `$PSDebugContext` wird, befinden Sie sich im Debugmodus und werden `[DBG]:` der Eingabeaufforderung wie folgt hinzugefügt:

```Output
[DBG]: PS C:\ps-test>
```

Wenn `$PSDebugContext` nicht aufgefüllt wird, fügt die Funktion `PS` der Eingabeaufforderung hinzu.
Und die-Funktion verwendet das- `Get-Location` Cmdlet, um den Speicherort des aktuellen Dateisystem Verzeichnisses zu erhalten. Anschließend wird eine schließende spitze Klammer () hinzugefügt `>` .

Beispiel:

```Output
PS C:\ps-test>
```

Wenn Sie sich in einer eingefügten Eingabeaufforderung befinden, fügt die Funktion der Eingabeaufforderung zwei eckige Klammern ( `>>` ) hinzu. (Sie befinden sich in einer eingefügten Eingabeaufforderung, wenn der Wert der `$NestedPromptLevel` automatischen Variablen größer als 1 ist.)

Wenn Sie z. b. in einer eingefügten Aufforderung Debuggen, wird die Eingabeaufforderung ähnlich der folgenden angezeigt:

```Output
[DBG] PS C:\ps-test>>>
```

### <a name="changes-to-the-prompt"></a>Änderungen an der Eingabeaufforderung

Das- `Enter-PSSession` Cmdlet fügt den Namen des Remote Computers der aktuellen `Prompt` Funktion voran. Wenn Sie mit dem `Enter-PSSession` Cmdlet eine Sitzung mit einem Remote Computer starten, wird die Eingabeaufforderung geändert, sodass Sie den Namen des Remote Computers enthält. Beispiel:

```Output
PS Hello, World> Enter-PSSession Server01
[Server01]: PS Hello, World>
```

Andere PowerShell-Host Anwendungen und Alternative Shells verfügen möglicherweise über eigene benutzerdefinierte Eingabe Aufforderungen.

Weitere Informationen zu den `$PSDebugContext` `$NestedPromptLevel` automatischen Variablen und finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).

### <a name="how-to-customize-the-prompt"></a>Vorgehensweise beim Anpassen der Eingabeaufforderung

Zum Anpassen der Eingabeaufforderung schreiben Sie eine neue `Prompt` Funktion. Die Funktion ist nicht geschützt, sodass Sie Sie überschreiben können.

Geben Sie Folgendes ein, um eine Funktion zu schreiben `Prompt` :

```powershell
function prompt { }
```

Geben Sie dann zwischen den geschweiften Klammern die Befehle oder die Zeichenfolge ein, mit der die Eingabeaufforderung erstellt wird.

Beispielsweise enthält die folgende Eingabeaufforderung Ihren Computernamen:

```powershell
function prompt {"PS [$env:COMPUTERNAME]> "}
```

Auf dem Server01-Computer ähnelt die Eingabeaufforderung der folgenden Eingabeaufforderung:

```Output
PS [Server01] >
```

Die folgende `Prompt` Funktion enthält das aktuelle Datum und die Uhrzeit:

```powershell
function prompt {"$(Get-Date)> "}
```

Die Eingabeaufforderung ähnelt der folgenden Eingabeaufforderung:

```Output
03/15/2012 17:49:47>
```

Sie können auch die Standard `Prompt` Funktion ändern:

Beispielsweise fügt die folgende geänderte `Prompt` Funktion `[ADMIN]:` der integrierten PowerShell-Eingabeaufforderung hinzu, wenn PowerShell mit der Option **als Administrator ausführen** geöffnet wird:

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

Wenn Sie PowerShell mit der Option **als Administrator ausführen** starten, wird eine Aufforderung angezeigt, die der folgenden Eingabeaufforderung ähnelt:

```Output
[ADMIN]: PS C:\ps-test>
```

Mit der folgenden Funktion wird die Verlaufs- `Prompt` ID des nächsten Befehls angezeigt. Verwenden Sie das-Cmdlet, um den Befehlsverlauf anzuzeigen `Get-History` .

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

Die folgende Eingabeaufforderung verwendet `Write-Host` die `Get-Random` Cmdlets und, um eine Eingabeaufforderung zu erstellen, die die Farbe nach dem Zufallsprinzip Da `Write-Host` in die aktuelle Host Anwendung geschrieben wird, aber kein-Objekt zurückgegeben wird, enthält diese Funktion eine- `Return` Anweisung. Ohne diesen Befehl verwendet PowerShell die Standardeingabe Aufforderung `PS>` .

```powershell
function prompt {
    $color = Get-Random -Min 1 -Max 16
    Write-Host ("PS " + $(Get-Location) +">") -NoNewLine `
     -ForegroundColor $Color
    return " "
}
```

### <a name="saving-the-prompt-function"></a>Speichern der prompt-Funktion

Wie jede beliebige Funktion ist die `Prompt` Funktion nur in der aktuellen Sitzung vorhanden. Um die `Prompt` Funktion für zukünftige Sitzungen zu speichern, fügen Sie Sie Ihren PowerShell-Profilen hinzu. Weitere Informationen zu Profilen finden Sie unter [about_Profiles](about_Profiles.md).

## <a name="see-also"></a>Weitere Informationen:

[Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Get-History](xref:Microsoft.PowerShell.Core.Get-History)

[Get-Random](xref:Microsoft.PowerShell.Utility.Get-Random)

[Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host)

[about_Profiles](about_Profiles.md)

[about_Functions](about_Functions.md)

[about_Scopes](about_Scopes.md)

[about_Debuggers](about_Debuggers.md)

[about_Automatic_Variables](about_Automatic_Variables.md)
