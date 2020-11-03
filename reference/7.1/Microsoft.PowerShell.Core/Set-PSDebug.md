---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-psdebug?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSDebug
ms.openlocfilehash: a0b5d7e86f9d63b487bc093feb18ecc7a4496999
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217004"
---
# Set-PSDebug

## ZUSAMMENFASSUNG
Aktiviert bzw. deaktiviert Skriptdebuggingfeatures, legt die Ablaufverfolgungsebene fest und schaltet den Strict-Modus um.

## SYNTAX

### on

```
Set-PSDebug [-Trace <Int32>] [-Step] [-Strict] [<CommonParameters>]
```

### aus

```
Set-PSDebug [-Off] [<CommonParameters>]
```

## DESCRIPTION

Das `Set-PSDebug` -Cmdlet aktiviert und deaktiviert skriptdebuggingfeatures, legt die Ablauf Verfolgungs Ebene fest und schaltet den Strict-Modus um. Die PowerShell-Debuggingfunktionen sind standardmäßig deaktiviert.

Wenn der **Trace** -Parameter den Wert aufweist `1` , wird jede Zeile des Skripts während der Ausführung verfolgt. Wenn der-Parameter den Wert aufweist `2` , werden auch Variablen Zuweisungen, Funktionsaufrufe und Skript Aufrufe verfolgt. Wenn der **Step** -Parameter angegeben wird, werden Sie aufgefordert, bevor die einzelnen Zeilen des Skripts ausgeführt werden.

## BEISPIELE

### Beispiel 1: Festlegen der Ablauf Verfolgungs Ebene

Dieses Beispiel legt die Ablauf Verfolgungs Ebene auf fest `2` und führt dann ein Skript aus, das die Zahlen 1, 2 und
3.

```powershell
Set-PSDebug -Trace 2; foreach ($i in 1..3) {$i}
```

```Output
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in  >>>> 1..3) {$i}
DEBUG:     ! SET $foreach = 'IEnumerator'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '1'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
1
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '2'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
2
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '3'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
3
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $foreach = ''.
```

### Beispiel 2: Aktivieren des durch Schrittes

In diesem Beispiel wird die schrittweise Ausführung von ausgeführt, und anschließend wird ein Skript ausgeführt, das die Zahlen 1, 2 und 3 anzeigt.

```powershell
Set-PSDebug -Step; foreach ($i in 1..3) {$i}
```

```Output
Continue with this operation?
   1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
DEBUG:    1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
1
2
3
```

### Beispiel 3: Verwenden des Strict-Modus

In diesem Beispiel wird PowerShell in den Strict-Modus versetzt und versucht, auf eine Variable zuzugreifen, die über keinen zugewiesenen Wert verfügt.

```powershell
Set-PSDebug -Strict; $NewVar
```

```Output
The variable '$NewVar' cannot be retrieved because it has not been set.
At line:1 char:22
+ Set-PSDebug -Strict; $NewVar
```

### Beispiel 4: Deaktivieren der Debuggingfunktionen

In diesem Beispiel werden alle Debuggingfunktionen deaktiviert, und anschließend wird ein Skript ausgeführt, das die Zahlen 1, 2 und 3 anzeigt.

```powershell
Set-PSDebug -Off; foreach ($i in 1..3) {$i}
```

```Output
1
2
3
```

## PARAMETERS

### -Aus

Deaktiviert alle Skriptdebuggingfeatures.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: off
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Schritt

Aktiviert die Schrittausführung für Skripts. Vor der Ausführung der einzelnen Zeilen werden Sie von PowerShell aufgefordert, den Status des Skripts zu überprüfen, fortzusetzen oder eine neue interpreterstufe einzugeben.

Durch die Angabe des **Step** -Parameters wird automatisch die Ablauf Verfolgungs Ebene festgelegt `1`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Strict

Gibt an, dass Variablen ein Wert zugewiesen werden muss, bevor in einem Skript darauf verwiesen wird. Wenn auf eine Variable verwiesen wird, bevor ein Wert zugewiesen wird, gibt PowerShell einen Ausnahme Fehler zurück. Dieser entspricht `Set-StrictMode -Version 1`. Weitere Informationen finden Sie unter [Set-strictmode](Set-StrictMode.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Trace

Gibt die Ablauf Verfolgungs Ebene für jede Zeile in einem Skript an. Jede Zeile wird nachverfolgt, während Sie ausgeführt wird.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- 0: Skript Ablauf Verfolgung deaktivieren.
- 1: Ablauf Verfolgung für Skript Zeilen während der Durchführung.
- 2: Ablauf Verfolgung von Skript Zeilen, Variablen Zuweisungen, Funktionsaufrufen und Skripts.

```yaml
Type: System.Int32
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Sie können keine Eingabe für dieses Cmdlet ausführen.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

## VERWANDTE LINKS

[about_Debuggers](./About/about_Debuggers.md)

[Debug-Process](../Microsoft.PowerShell.Management/Debug-Process.md)

[Set-PSBreakpoint](../Microsoft.PowerShell.Utility/Set-PSBreakpoint.md)

[Set-StrictMode](Set-StrictMode.md)

[Write-Debug](../Microsoft.PowerShell.Utility/Write-Debug.md)

