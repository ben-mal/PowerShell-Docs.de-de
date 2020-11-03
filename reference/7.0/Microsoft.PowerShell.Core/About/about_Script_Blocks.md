---
description: Definiert, was ein Skriptblock ist, und erläutert, wie Skriptblöcke in der PowerShell-Programmiersprache verwendet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_blocks?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Blocks
ms.openlocfilehash: 1793deded63669399246d18132bbc5b6d6c4810b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220612"
---
# <a name="about-script-blocks"></a>Informationen zu Skript Blöcken

## <a name="short-description"></a>Kurze Beschreibung

Definiert, was ein Skriptblock ist, und erläutert, wie Skriptblöcke in der PowerShell-Programmiersprache verwendet werden.

## <a name="long-description"></a>Lange Beschreibung

In der PowerShell-Programmiersprache ist ein Skriptblock eine Auflistung von Anweisungen oder Ausdrücken, die als einzelne Einheit verwendet werden kann.
Ein Skriptblock kann Argumente und Rückgabewerte akzeptieren.

Syntaktisch ist ein Skriptblock eine Anweisungs Liste in geschweiften Klammern, wie in der folgenden Syntax gezeigt:

```
{<statement list>}
```

Ein Skriptblock gibt die Ausgabe aller Befehle im Skriptblock zurück, entweder als einzelnes Objekt oder als Array.

Sie können auch einen Rückgabewert mit dem- `return` Schlüsselwort angeben. Das- `return` Schlüsselwort wirkt sich nicht auf andere Ausgaben aus, die vom Skriptblock zurückgegeben werden. Das `return` Schlüsselwort beendet jedoch den Skriptblock in dieser Zeile. Weitere Informationen finden Sie unter [about_Return](about_Return.md).

Wie Functions kann ein Skriptblock Parameter enthalten. Verwenden Sie das Schlüsselwort param, um benannte Parameter zuzuweisen, wie in der folgenden Syntax gezeigt:

```
{
Param([type]$Parameter1 [,[type]$Parameter2])
<statement list>
}
```

> [!NOTE]
> In einem Skriptblock können im Gegensatz zu einer Funktion keine Parameter außerhalb der geschweiften Klammern angegeben werden.

Ebenso wie Functions können Skriptblöcke die `DynamicParam` `Begin` `Process` Schlüsselwörter,, und enthalten `End` . Weitere Informationen finden Sie unter [about_Functions](about_Functions.md) und [about_Functions_Advanced](about_Functions_Advanced.md).

## <a name="using-script-blocks"></a>Verwenden von Skript Blöcken

Ein Skriptblock ist eine Instanz eines Microsoft .NET Framework-Typs `System.Management.Automation.ScriptBlock` . Befehle können Skriptblock-Parameterwerte aufweisen. Beispielsweise verfügt das `Invoke-Command` Cmdlet über einen `ScriptBlock` Parameter, der einen Skriptblock Wert annimmt, wie im folgenden Beispiel gezeigt:

```powershell
Invoke-Command -ScriptBlock { Get-Process }
```

```Output
Handles  NPM(K)    PM(K)     WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----     ----- -----   ------     -- -----------
999          28    39100     45020   262    15.88   1844 communicator
721          28    32696     36536   222    20.84   4028 explorer
...
```

`Invoke-Command` kann auch Skriptblöcke ausführen, die über Parameter Blöcke verfügen.
Parameter werden mithilfe des Argument **List** -Parameters über die Position zugewiesen.

```powershell
Invoke-Command -ScriptBlock { param($p1, $p2)
"p1: $p1"
"p2: $p2"
} -ArgumentList "First", "Second"
```

```Output
p1: First
p2: Second
```

Der Skriptblock im vorangehenden Beispiel verwendet das `param` -Schlüsselwort, um die Parameter und zu erstellen `$p1` `$p2` . Die Zeichenfolge "First" ist an den ersten Parameter ( `$p1` ) und "Second" an () gebunden `$p2` .

Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about_Splatting.md#splatting-with-arrays).

Sie können Variablen verwenden, um Skriptblöcke zu speichern und auszuführen. Im folgenden Beispiel wird ein Skriptblock in einer Variablen gespeichert und an weitergeleitet `Invoke-Command` .

```powershell
$a = { Get-Service BITS }
Invoke-Command -ScriptBlock $a
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  BITS               Background Intelligent Transfer Ser...
```

Der "calloperator" ist eine andere Möglichkeit, Skriptblöcke auszuführen, die in einer Variablen gespeichert sind.
Wie `Invoke-Command` führt der callenoperator den Skriptblock in einem untergeordneten Bereich aus. Der Operator "Operator" kann es Ihnen erleichtern, Parameter mit ihren Skript Blöcken zu verwenden.

```powershell
$a ={ param($p1, $p2)
"p1: $p1"
"p2: $p2"
}
&$a -p2 "First" -p1 "Second"
```

```Output
p1: Second
p2: First
```

Sie können die Ausgabe aus ihren Skript Blöcken in einer Variablen speichern, indem Sie die Zuweisung verwenden.

```
PS>  $a = { 1 + 1}
PS>  $b = &$a
PS>  $b
2
```

```
PS>  $a = { 1 + 1}
PS>  $b = Invoke-Command $a
PS>  $b
2
```

Weitere Informationen zum-Operator finden Sie unter [about_Operators](about_Operators.md).

## <a name="using-delay-bind-script-blocks-with-parameters"></a>Verwenden von verzögerten Bindungs Skript Blöcken mit Parametern

Ein typisierter Parameter, der Pipeline Eingaben ( `by Value` ) oder () akzeptiert, `by PropertyName` ermöglicht die Verwendung von **verzögerten Bindungs** Skript Blöcken für den Parameter.
Im **verzögerten Bindungs** Skriptblock können Sie mithilfe der Pipeline Variable auf das weitergeleitete in-Objekt verweisen `$_` .

```powershell
# Renames config.log to old_config.log
dir config.log | Rename-Item -NewName {"old_" + $_.Name}
```

In komplexeren Cmdlets ermöglichen verzögertes Binden von Skript Blöcken die Wiederverwendung eines weitergeleiteten Objekts im Objekt, um andere Parameter aufzufüllen.

Hinweise zu **verzögerten Bindungs** Skript Blöcken als Parameter:

- Sie müssen explizit alle Parameternamen angeben, die Sie mit **verzögerten Bindungs** Skript Blöcken verwenden.
- Der-Parameter darf nicht als nicht typisiert sein, und der-Parametertyp darf nicht `[scriptblock]` oder sein `[object]` .
- Sie erhalten eine Fehlermeldung, wenn Sie einen Skriptblock mit **verzögerter Bindung** verwenden, ohne Pipeline Eingaben bereitzustellen.

  ```powershell
  Rename-Item -NewName {$_.Name + ".old"}
  ```

  ```Output
  Rename-Item : Cannot evaluate parameter 'NewName' because its argument is
  specified as a script block and there is no input. A script block cannot
  be evaluated without input.
  At line:1 char:23
  +  Rename-Item -NewName {$_.Name + ".old"}
  +                       ~~~~~~~~~~~~~~~~~~
      + CategoryInfo          : MetadataError: (:) [Rename-Item],
        ParameterBindingException
      + FullyQualifiedErrorId : ScriptBlockArgumentNoInput,
        Microsoft.PowerShell.Commands.RenameItemCommand
  ```

## <a name="see-also"></a>Weitere Informationen

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Operators](about_Operators.md)
