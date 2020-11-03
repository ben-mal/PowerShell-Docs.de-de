---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 3217a3c67c262f8061963fd1302c6782620e270d
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224436"
---
# Write-Debug

## ZUSAMMENFASSUNG
Schreibt eine Debugmeldung in die Konsole.

## SYNTAX

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## DESCRIPTION

Das `Write-Debug` Cmdlet schreibt Debugmeldungen aus einem Skript oder Befehl in den Host.

Standardmäßig werden Debugmeldungen nicht in der-Konsole angezeigt, Sie können Sie jedoch mit dem **Debug** -Parameter oder der- `$DebugPreference` Variablen anzeigen.

## BEISPIELE

### Beispiel 1: verstehen $DebugPreference

In diesem Beispiel wird eine Debugmeldung geschrieben.

```powershell
Write-Debug "Cannot open file."
```

Der Standardwert von `$DebugPreference` ist **SilentlyContinue**. Daher wird die Meldung nicht in der Konsole angezeigt.

### Beispiel 2: Ändern des Werts von $DebugPreference

Dieses Beispiel zeigt die Auswirkung der Änderung des Werts der `$DebugPreference` Variablen. Zuerst wird der aktuelle Wert von angezeigt, `$DebugPreference` und es wird versucht, eine Debugmeldung zu schreiben. Anschließend ändern wir den Wert von `$DebugPreference` , um **fortzufahren**. Dadurch können Debugmeldungen angezeigt werden.

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

Weitere Informationen zu `$DebugPreference` finden Sie unter [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).

### Beispiel 3: Verwenden des Debug-Parameters zum Überschreiben von $DebugPreference

Die `Test-Debug` -Funktion schreibt den Wert der `$DebugPreference` Variablen in den PowerShell-Host und den debugdatenstrom. In diesem Beispiel verwenden wir den **Debug** -Parameter, um den Wert zu überschreiben `$DebugPreference` .

```powershell
function Test-Debug {
    [CmdletBinding()]
    param()
    Write-Debug ('$DebugPreference is ' + $DebugPreference)
    Write-Host ('$DebugPreference is ' + $DebugPreference)
}
```

```
PS> Test-Debug
$DebugPreference is SilentlyContinue

PS> Test-Debug -Debug
DEBUG: $DebugPreference is Continue
$DebugPreference is Continue
PS> $DebugPreference
SilentlyContinue
```

Beachten Sie, dass sich der Wert von `$DebugPreference` ändert, wenn Sie den **Debug** -Parameter verwenden. Diese Änderung wirkt sich nur auf den Gültigkeitsbereich der Funktion aus. Der Wert ist außerhalb der Funktion nicht betroffen.

Weitere Informationen zum allgemeinen **Debug** -Parameter finden Sie unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## PARAMETERS

### -Meldung

Gibt die Debugmeldung an, die an die Konsole gesendet werden soll.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge, die eine Debugmeldung enthält, an die Pipeline übergeben `Write-Debug` .

## AUSGABEN

### Keine

`Write-Debug` schreibt nur in den debugdatenstrom. Es werden keine Objekte in die Pipeline geschrieben.

## HINWEISE

## VERWANDTE LINKS

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Schreibfehler](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
