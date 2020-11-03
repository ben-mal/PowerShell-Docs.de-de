---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convert-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-String
ms.openlocfilehash: 29ec9e21277bae02ab94ce5e862787c86a87b439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214148"
---
# Convert-String

## ZUSAMMENFASSUNG
Formatiert eine Zeichenfolge, um Beispiele zu vergleichen.

## SYNTAX

```
Convert-String [-Example <System.Collections.Generic.List`1[System.Management.Automation.PSObject]>]
 -InputObject <String> [<CommonParameters>]
```

## DESCRIPTION

Das **Convert-String-** Cmdlet formatiert eine Zeichenfolge so, dass Sie dem Format von Beispielen entspricht.

## BEISPIELE

### Beispiel 1: Konvertieren des Formats einer Zeichenfolge

```powershell
"Mu Han", "Jim Hance", "David Ahs", "Kim Akers" | Convert-String -Example "Ed Wilson=Wilson, E."
```

```output
Han, M.
Hance, J.
Ahs, D.
Akers, K.
```

Der erste Befehl erstellt ein Array, das vor-und Nachnamen enthält.

Mit dem zweiten Befehl werden die Namen gemäß dem Beispiel formatiert.
Er fügt den Nachnamen zuerst in die Ausgabe ein, gefolgt von einem ursprünglichen.

### Beispiel 2: Vereinfachen der Format Zeichenfolge

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=last, first"
```

```output
Bach, Johann
Mozart, Wolfgang
Chopin, Frederic
Brahms, Johannes
```

Der erste Befehl erstellt ein Array, das vor-, Mittel-und Nachnamen enthält.
Beachten Sie, dass der letzte Eintrag keinen mittleren Namen aufweist.

Mit dem zweiten Befehl werden die Namen gemäß dem Beispiel formatiert.
Der Nachname wird zuerst in die Ausgabe eingefügt, gefolgt vom Vornamen.
Alle mittleren Namen wurden entfernt. der Eintrag ohne den mittleren Namen wird ordnungsgemäß behandelt.

### Beispiel 3: Ausgabe Verwaltung, wenn Zeichen folgen nicht mit Beispiel vergleichen

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=middle, first"
```

```output
Sebastian, Johann
Amadeus, Wolfgang
Francois, Frederic
```

Der erste Befehl erstellt ein Array, das vor-, Mittel-und Nachnamen enthält.
Beachten Sie, dass der letzte Eintrag keinen mittleren Namen aufweist.

Mit dem zweiten Befehl werden die Namen gemäß dem Beispiel formatiert.
**Der zweite Name wird** in die Ausgabe eingefügt, gefolgt vom Vornamen.
Der letzte Eintrag in **$Composers** wird übersprungen, da er nicht mit dem Beispiel Muster identisch ist: er hat keinen mittleren Namen.

### Beispiel 4: Vorsicht bei Beauty Spaces

```powershell
$composers = @("Antonio Vivaldi", "Richard Wagner ", "Franz Schubert", "Johannes Brahms ")
$composers | Convert-String -Example "Patti Fuller = Fuller, P."
```

```output
 Wagner, R.
 Brahms, J.
```

Der erste Befehl erstellt ein Array von vor-und Nachnamen.
Beachten Sie, dass das zweite und vierte Element nach dem Nachnamen über einen zusätzlichen nachfolgenden Bereich verfügen.

Der zweite Befehl konvertiert alle Zeichen folgen, die mit dem Beispiel Muster übereinstimmen: _Word, Leerzeichen, Word und abschließende nachfolgende leer_ Zeichen, all dies vor dem Gleichheitszeichen.
Beachten Sie auch den führenden Leerraum in der Ausgabe.

### Beispiel 5: Formatieren von Prozessinformationen mit mehreren Mustern

```powershell
$ExamplePatterns = @(
    @{before='"Hello","World"'; after='World: Hello'},
    @{before='"Hello","1"'; after='1: Hello'},
    @{before='"Hello-World","22"'; after='22: Hello-World'},
    @{before='"hello world","333"'; after='333: hello world'}
)
$Processes = Get-Process   | Select-Object -Property ProcessName, Id | ConvertTo-Csv -NoTypeInformation
$Processes | Convert-String -Example $ExamplePatterns
```

```output
Id: ProcessName
4368: AGSService
8896: Amazon Music Helper
4420: AppleMobileDeviceService
...
11140: git-bash
0: Idle
...
56: Secure System
...
13028: WmiPrvSE
2724: WUDFHost
2980: WUDFHost
3348: WUDFHost
```

In **$ExamplePatterns** werden verschiedene erwartete Muster in den Daten anhand von Beispielen definiert.

Das erste Muster, `@{before='"Hello","World"'; after='World: Hello'}` , liest wie folgt: erwartet werden Zeichen folgen, _bei denen ein Wort in doppelte Anführungszeichen eingeschlossen ist, dann ein Komma_ 
 _und dann das zweite und letzte Wort in Anführungszeichen eingeschlossen werden._ 
 _ohne Leerzeichen in der Zeichenfolge. In der Ausgabe: Platzieren Sie das zweite Wort zuerst_ 
 _ohne Anführungszeichen, dann ein einzelnes Leerzeichen und dann das erste Wort ohne Anführungszeichen._

Das zweite Muster, `@{before='"Hello","1"'; after='1: Hello'}` , liest wie folgt: _erwartet werden Zeichen folgen, bei denen ein Wort in doppelte Anführungszeichen eingeschlossen ist, dann ein Komma_ 
 _und eine Zahl in Anführungszeichen eingeschlossen wird._ 
 _ohne Leerzeichen in der Zeichenfolge. In der Ausgabe: Platzieren Sie die Zahl zuerst_ 
 _ohne Anführungszeichen, dann ein einzelnes Leerzeichen und dann das Wort ohne Anführungszeichen._

Das dritte Muster, `@{before='"Hello-World","22"'; after='22: Hello-World'}` , liest wie folgt: erwartet werden Zeichen folgen, _bei denen zwei Wörter mit einem Bindestrich dazwischen in_ 
 _doppelte Anführungszeichen eingeschlossen werden, dann ein Komma und eine Zahl in Anführungszeichen eingeschlossen sind._ 
 _ohne Leerzeichen zwischen dem Komma und dem dritten doppelten Anführungszeichen._ 
 _In der Ausgabe: Platzieren Sie die Zahl zuerst ohne Anführungszeichen und dann ein einzelnes Leerzeichen_ 
 . _und dann die Bindestriche ohne Anführungszeichen._

Das vierte und abschließende Muster, `@{before='"hello world","333"'; after='333: hello world'}` ,, liest wie folgt: erwartet werden Zeichen folgen, _bei denen zwei Wörter mit einem Leerzeichen dazwischen in_ 
 _doppelte Anführungszeichen eingeschlossen werden, dann ein Komma und dann eine Zahl in Anführungszeichen_ eingeschlossen sind. 
 _ohne Leerzeichen zwischen dem Komma und dem dritten doppelten Anführungszeichen._ 
 _In der Ausgabe: Platzieren Sie die Zahl zuerst ohne Anführungszeichen und dann ein einzelnes Leerzeichen_ 
 . _und dann die Wörter mit dem Leerzeichen dazwischen, ohne Anführungszeichen._

Der erste Befehl ruft alle Prozesse mithilfe des Get-Process-Cmdlets ab.
Der Befehl übergibt sie an das Select-Object-Cmdlet, das den Prozessnamen und die Prozess-ID auswählt. Am Ende der Pipeline konvertiert der Befehl die Ausgabe in durch Trennzeichen getrennte Werte ohne Typinformationen mithilfe des-Cmdlets ConvertTo-Csv.
Der Befehl speichert die Ergebnisse in der **$processes** Variable.
**$Processes** jetzt die Prozessnamen und die PID enthält.

Mit dem zweiten Befehl wird eine Beispiel Variable angegeben, die die Reihenfolge der Eingabeelemente ändert.
Der Befehl konvertiert jede Zeichenfolge in **$processes** .

>**Hinweis** Das vierte Muster besagt implizit, dass zwei oder mehr durch Leerzeichen getrennte Wörter übereinstimmen.
>
>Ohne das vierte Muster wird nur das erste Wort der Zeichenfolge abgeglichen, das in doppelte Anführungszeichen eingeschlossen ist.

## PARAMETERS

### -Beispiel

Gibt eine Liste von Beispielen für das Zielformat an.
Geben Sie Paare, die durch das Gleichheitszeichen (=) getrennt sind, mit dem Quell Muster auf der linken Seite und dem Ziel Muster auf der rechten Seite an, wie in den folgenden Beispielen gezeigt:

* `-Example "Hello World=World, Hello"`
* `-Example "Hello World=World: Hello",'"Hello","1"=1: Hello'`

>**Hinweis** Im zweiten Beispiel wird eine Liste mit Mustern verwendet.

Sie können auch eine Liste von Hash Tabellen angeben, die Eigenschaften von " **before** " und " **after** " enthalten.

* `-Example @{before='"Hello","World"'; after='World: Hello'}, @{before='"Hello","1"'; after='1: Hello'}`

>**Vorsicht** Vermeiden Sie die Verwendung von Leerzeichen um das Gleichheitszeichen, da diese als Teil des Musters behandelt werden.

```yaml
Type: System.Collections.Generic.List`1[System.Management.Automation.PSObject]
Parameter Sets: (All)
Aliases: E

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt eine zu formatierende Zeichenfolge an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### String

Sie können Zeichen folgen an dieses Cmdlet übergeben.

## AUSGABEN

### String

Dieses Cmdlet gibt eine Zeichenfolge zurück.

## HINWEISE

## VERWANDTE LINKS

[ConvertFrom-String](ConvertFrom-String.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)

[Out-String](Out-String.md)

[Select-Object](Select-Object.md)
