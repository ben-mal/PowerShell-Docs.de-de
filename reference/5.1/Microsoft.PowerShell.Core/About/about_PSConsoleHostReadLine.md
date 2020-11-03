---
description: Erläutert, wie Sie eine Anpassung an die Eingabeaufforderung von PowerShell an der Konsole erstellen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_psconsolehostreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSConsoleHostReadLine
ms.openlocfilehash: 3c5f629471ce2a4315e3e90f2baec86dfda1506b
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224948"
---
# <a name="about_psconsolehostreadline"></a>about_PSConsoleHostReadLine

## <a name="short-description"></a>KURZE BESCHREIBUNG

Erläutert, wie Sie eine Anpassung an die Eingabeaufforderung von PowerShell an der Konsole erstellen.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Ab Windows PowerShell V3 können Sie eine Funktion mit dem Namen psconsolehostread Line schreiben, mit der die Standardmethode für die Verarbeitung der Konsolen Eingabe überschrieben wird.

### <a name="examples"></a>BEISPIELE

Im folgenden Beispiel wird Notepad gestartet und Eingaben aus einer vom Benutzer erstellten Textdatei abgerufen:

```powershell
function PSConsoleHostReadLine
{
  $inputFile = Join-Path $env:TEMP PSConsoleHostReadLine
  Set-Content $inputFile "PS > "

  # Notepad opens. Enter your command in it, save the file, and then exit.
  notepad $inputFile | Out-Null
  $userInput = Get-Content $inputFile
  $resultingCommand = $userInput.Replace("PS >", "")
  $resultingCommand
}
```

### <a name="remarks"></a>ANMERKUNGEN

PowerShell liest Eingaben standardmäßig in der-Konsole, was als "gekochte Modus" bezeichnet wird. dabei verarbeitet das Windows-Konsolen Subsystem alle Tastatur drücken, F7-Menüs und andere Eingaben. Wenn Sie die EINGABETASTE oder die Tab-Taste drücken, ruft Windows PowerShell den Text ab, den Sie bis zu diesem Punkt eingegeben haben. Es gibt keine Möglichkeit, zu wissen, dass Sie STRG + R, STRG + A, STRG + E oder andere Tasten gedrückt haben, bevor Sie die EINGABETASTE oder TAB drücken. In Windows PowerShell, Version 3, löst die psconsolehostread Line-Funktion dieses Problem. Wenn Sie im Windows PowerShell-Konsolen Host eine Funktion mit dem Namen psconsolehostread Line definieren, wird diese Funktion von Windows PowerShell anstelle des Eingabe Mechanismus "gekochte Modus" aufgerufen.

### <a name="see-also"></a>SIEHE AUCH

[about_Prompts](about_Prompts.md)
