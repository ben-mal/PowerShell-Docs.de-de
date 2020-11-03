---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: 34e8d6edd7199921254a3835a9f13b6331c2d26e
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224383"
---
# Write-Verbose

## ZUSAMMENFASSUNG
Schreibt Text in den Stream für ausführliche Meldungen.

## SYNTAX

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## DESCRIPTION

Das `Write-Verbose` Cmdlet schreibt Text in den Stream für ausführliche Meldungen in PowerShell. In der Regel wird der Stream für ausführliche Meldungen verwendet, um ausführlichere Informationen zur Befehls Verarbeitung bereitzustellen.

Standardmäßig wird der Stream für ausführliche Meldungen nicht angezeigt. Sie können ihn jedoch anzeigen, indem Sie den Wert der `$VerbosePreference` Variablen ändern oder den allgemeinen **ausführliche** -Parameter in einem beliebigen Befehl verwenden.

## BEISPIELE

### Beispiel 1: Schreiben einer Statusmeldung

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

Diese Befehle verwenden das `Write-Verbose` Cmdlet, um eine Statusmeldung anzuzeigen. Standardmäßig wird die Meldung nicht angezeigt.

Der zweite Befehl verwendet den allgemeinen **ausführliche** -Parameter, der alle ausführlichen Meldungen anzeigt, unabhängig vom Wert der `$VerbosePreference` Variablen.

### Beispiel 2: Festlegen $VerbosePreference und Schreiben einer Statusmeldung

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

Diese Befehle verwenden das `Write-Verbose` Cmdlet, um eine Statusmeldung anzuzeigen. Standardmäßig wird die Meldung nicht angezeigt.

Der erste Befehl weist der Preference-Variablen den Wert Continue zu `$VerbosePreference` . Der Standardwert, `SilentlyContinue` , unterdrückt ausführliche Meldungen. Der zweite Befehl schreibt eine ausführliche Meldung.

## PARAMETERS

### -Meldung

Gibt die anzuzeigende Meldung an. Dieser Parameter ist erforderlich. Sie können eine Meldungs Zeichenfolge auch an übergeben `Write-Verbose` .

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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge, die die Meldung enthält, an die Pipeline übergeben `Write-Verbose` .

## AUSGABEN

### Keine

`Write-Verbose` schreibt nur in den Stream für ausführliche Meldungen.

## HINWEISE

- Ausführliche Meldungen werden nur zurückgegeben, wenn der Befehl den allgemeinen **Verbose** -Parameter verwendet. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).
- In Windows PowerShell-Hintergrund Aufträgen und Remote Befehlen `$VerbosePreference` bestimmen die Variablen in der Auftrags Sitzung und in der Remote Sitzung, ob die ausführliche Meldung standardmäßig angezeigt wird.
  Weitere Informationen zur- `$VerbosePreference` Variablen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

## VERWANDTE LINKS

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Write-Debug](Write-Debug.md)

[Schreibfehler](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Warning](Write-Warning.md)
