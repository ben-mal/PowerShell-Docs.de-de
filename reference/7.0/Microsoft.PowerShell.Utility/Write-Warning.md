---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-warning?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Warning
ms.openlocfilehash: dde8e497159e3e9a7bf63010bc12566d68d8de0f
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224431"
---
# Write-Warning

## ZUSAMMENFASSUNG
Schreibt eine Warnmeldung.

## SYNTAX

```
Write-Warning [-Message] <String> [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Write-Warning` Cmdlet wird eine Warnmeldung in den PowerShell-Host geschrieben. Die Antwort auf die Warnung hängt vom Wert der Variablen des Benutzers `$WarningPreference` und der Verwendung des allgemeinen **WarningAction** -Parameters ab.

## BEISPIELE

### Beispiel 1: Schreiben einer Warnmeldung

Mit diesem Befehl wird die Meldung "Warnung: Dies ist nur eine Test Warnung" angezeigt.

```powershell
Write-Warning "This is only a test warning."
```

### Beispiel 2: übergeben einer Zeichenfolge an Write-Warning

Dieser Befehl zeigt, dass Sie einen Pipeline Operator () verwenden können, um `|` eine Zeichenfolge an zu senden `Write-Warning` .
Sie können die Zeichenfolge in einer Variablen speichern, wie in diesem Befehl gezeigt, oder die Zeichenfolge direkt an die Pipeline übergeben `Write-Warning` .

```powershell
$w = "This is only a test warning."
$w | Write-Warning
```

### Beispiel 3: Festlegen der $WarningPreference Variable und Schreiben einer Warnung

Dieses Beispiel zeigt die Auswirkung des Werts der `$WarningPreference` Variablen in einem `Write-Warning` Befehl.

```powershell
PS> $WarningPreference
Continue
PS> Write-Warning "This is only a test warning."
This is only a test warning.
PS> $WarningPreference = "SilentlyContinue"
PS> Write-Warning "This is only a test warning."
PS> $WarningPreference = "Stop"
PS> Write-Warning "This is only a test warning."
WARNING: This is only a test message.
Write-Warning : Command execution stopped because the shell variable "WarningPreference" is set to Stop.
At line:1 char:14
     + Write-Warning <<<<  "This is only a test message."
```

Der erste Befehl zeigt den Standardwert der `$WarningPreference` Variablen an, die ist `Continue` . Beim Schreiben einer Warnung wird daher die Warnmeldung angezeigt, und die Ausführung wird fortgesetzt.

Wenn Sie den Wert der Variablen ändern `$WarningPreference` , ändert sich die Auswirkung des `Write-Warning` Befehls erneut. `SilentlyContinue`Der Wert unterdrückt die Warnung. `Stop`Der Wert zeigt die Warnung an und beendet dann die Ausführung des Befehls.

Weitere Informationen zur- `$WarningPreference` Variablen finden Sie unter [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).

### Beispiel 4: Festlegen des WarningAction-Parameters und Schreiben einer Warnung

Dieses Beispiel zeigt die Auswirkung des allgemeinen **WarningAction** -Parameters auf einen `Write-Warning` Befehl. Sie können den allgemeinen **WarningAction** -Parameter mit jedem Cmdlet verwenden, um zu bestimmen, wie PowerShell auf Warnungen reagiert, die durch diesen Befehl entstehen. Der allgemeine **WarningAction** -Parameter überschreibt den Wert von `$WarningPreference` nur für diesen speziellen Befehl.

```powershell
PS> Write-Warning "This is only a test warning." -WarningAction Inquire
WARNING: This is only a test warning.
Confirm
Continue with this operation?
 [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

Dieser Befehl verwendet das `Write-Warning` Cmdlet, um eine Warnung anzuzeigen. Der allgemeine **WarningAction** -Parameter mit dem Wert "Anfrage" weist das System an, den Benutzer zur Eingabe aufzufordern, wenn der Befehl eine Warnung anzeigt.

Weitere Informationen zu den allgemeinen **WarningAction** -Parametern finden Sie unter [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).

## PARAMETERS

### -Meldung
Gibt die Warnmeldung an.

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

Sie können eine Zeichenfolge, die die Warnung enthält, an die Pipeline übergeben `Write-Warning` .

## AUSGABEN

### Keine

`Write-Warning` schreibt nur in den Warnungs Datenstrom. Es generiert keine andere Ausgabe.

## HINWEISE

Der Standardwert für die `$WarningPreference` Variable ist `Continue` , wodurch die Warnung angezeigt und die Ausführung des Befehls fortgesetzt wird. Um gültige Werte für eine Einstellungs Variable wie zu ermitteln `$WarningPreference` , legen Sie Sie auf eine Zeichenfolge zufälliger Zeichen fest, z. b. "ABC". Die resultierende Fehlermeldung listet die gültigen Werte auf.

## VERWANDTE LINKS

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Schreibfehler](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)
