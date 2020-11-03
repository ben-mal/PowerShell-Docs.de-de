---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Expression
ms.openlocfilehash: f915a5741ed5c63206da3c35f5322508515bd566
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212959"
---
# Invoke-Expression

## ZUSAMMENFASSUNG
Führt Befehle oder Ausdrücke auf dem lokalen Computer aus.

## SYNTAX

```
Invoke-Expression [-Command] <String> [<CommonParameters>]
```

## DESCRIPTION

Das `Invoke-Expression` -Cmdlet wertet eine angegebene Zeichenfolge aus oder führt Sie als Befehl aus und gibt die Ergebnisse des Ausdrucks oder Befehls zurück. Ohne `Invoke-Expression` wird eine Zeichenfolge, die in der Befehlszeile übermittelt wird, unverändert zurückgegeben (ECHO).

Ausdrücke werden im aktuellen Gültigkeitsbereich ausgewertet und ausgeführt. Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

> [!CAUTION]
> Treffen Sie angemessene Vorsichtsmaßnahmen, wenn Sie das `Invoke-Expression` Cmdlet in Skripts verwenden. Wenn Sie verwenden, `Invoke-Expression` um einen Befehl auszuführen, den der Benutzer eingibt, vergewissern Sie sich, dass der Befehl sicher ausgeführt werden kann, bevor er ausgeführt wird. Im Allgemeinen empfiehlt es sich, Ihr Skript mit vordefinierten Eingabeoptionen zu entwerfen, statt die Freihandformeingabe zuzulassen.

## BEISPIELE

### Beispiel 1: Auswerten eines Ausdrucks

```powershell
$Command = "Get-Process"
$Command
```

```Output
Get-Process
```

```powershell
Invoke-Expression $Command
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
296       4       1572       1956    20       0.53     1348   AdtAgent
270       6       1328       800     34       0.06     2396   alg
67        2       620        484     20       0.22     716    ati2evxx
1060      15      12904      11840   74       11.48    892    CcmExec
1400      33      25280      37544   223      38.44    2564   communicator
...
```

In diesem Beispiel wird die Verwendung von `Invoke-Expression` zum Auswerten eines Ausdrucks veranschaulicht. Ohne `Invoke-Expression` wird der Ausdruck gedruckt, aber nicht ausgewertet.

Der erste Befehl weist `Get-Process` der Variablen den Wert (eine Zeichenfolge) zu `$Command` .

Der zweite Befehl veranschaulicht die Auswirkungen bei der Eingabe des Namens der Variablen in der Befehlszeile. PowerShell gibt die Zeichenfolge zurück.

Der dritte Befehl verwendet `Invoke-Expression` , um die Zeichenfolge zu evaluieren.

### Beispiel 2: Ausführen eines Skripts auf dem lokalen Computer

```powershell
Invoke-Expression -Command "C:\ps-test\testscript.ps1"
"C:\ps-test\testscript.ps1" | Invoke-Expression
```

Diese Befehle verwenden, `Invoke-Expression` um ein Skript, TestScript.ps1, auf dem lokalen Computer auszuführen. Die beiden Befehle sind äquivalent. Der erste verwendet den **Command** -Parameter, um den Befehl anzugeben, der ausgeführt werden soll.
Der zweite verwendet einen Pipeline Operator ( `|` ), um die Befehls Zeichenfolge an zu senden `Invoke-Expression` .

### Beispiel 3: Ausführen eines Befehls in einer Variablen

```powershell
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

In diesem Beispiel wird eine Befehls Zeichenfolge ausgeführt, die in der-Variablen gespeichert ist `$Command` .

Die Befehls Zeichenfolge wird in einfache Anführungszeichen eingeschlossen, da Sie eine Variable enthält, die `$_` das aktuelle Objekt darstellt. Wenn Sie in doppelte Anführungszeichen eingeschlossen `$_` wäre, wird die Variable durch ihren Wert ersetzt, bevor Sie in der Variablen gespeichert wurde `$Command` .

### Beispiel 4: erhalten und Ausführen eines Cmdlet-Hilfe Beispiels

```powershell
$Cmdlet_name = "Get-EventLog"
$Example_number = 1
$Example_code = (Get-Help $Cmdlet_name).examples.example[($Example_number-1)].code
Invoke-Expression $Example_code
```

Dieser Befehl ruft das erste Beispiel im Hilfethema für das Cmdlet ab und führt es aus `Get-EventLog` .

Um ein Beispiel für ein anderes Cmdlet auszuführen, ändern Sie den Wert der `$Cmdlet_name` Variablen in den Namen des Cmdlets. Und ändern Sie die `$Example_number` Variable in die Beispiel Zahl, die Sie ausführen möchten. Der Befehl schlägt fehl, wenn die Beispiel Nummer ungültig ist.

## PARAMETERS

### -Command

Gibt den auszuführenden Befehl oder Ausdruck an. Geben Sie den Befehl oder Ausdruck oder eine Variable ein, die den Befehl oder Ausdruck enthält. Der **Command** -Parameter ist erforderlich.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System. String oder psobject

Sie können ein Objekt, das den Befehl darstellt, an die Pipeline übergeben `Invoke-Expression` .
Verwenden `$Input` Sie die automatische Variable, um die Eingabe Objekte im Befehl darzustellen.

## AUSGABEN

### PSObject

Gibt die Ausgabe zurück, die vom aufgerufenen Befehl (dem Wert des **Befehls** Parameters) generiert wird.

## HINWEISE

In den meisten Fällen rufen Sie Ausdrücke mit dem Aufruf Operator von PowerShell auf und erzielen dieselben Ergebnisse.
Der "calloperator" ist eine sicherere Methode. Weitere Informationen finden Sie unter [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).

## VERWANDTE LINKS

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)

