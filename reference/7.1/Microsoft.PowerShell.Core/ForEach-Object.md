---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 7da05aed73fdb52132404bc08f0fd39fafbfc4ca
ms.sourcegitcommit: ca5a89977913bad9efec6bcc23a792d113ec0396
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2021
ms.locfileid: "105631050"
---
# ForEach-Object

## Übersicht
Führt einen Vorgang für jedes Element in einer Auflistung von Eingabeobjekten aus.

## Syntax

### Scriptblockset (Standard)

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Propertyandmethodset

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Parallelparameterset

```
ForEach-Object -Parallel <scriptblock> [-InputObject <PSObject>] [-ThrottleLimit <int>]
[-UseNewRunspace] [-TimeoutSeconds <int>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## BESCHREIBUNG

Das- `ForEach-Object` Cmdlet führt einen Vorgang für jedes Element in einer Auflistung von Eingabe Objekten aus. Die Eingabe Objekte können an das Cmdlet weitergeleitet oder mithilfe des **Inputobject** -Parameters angegeben werden.

Ab Windows PowerShell 3,0 gibt es zwei verschiedene Möglichkeiten, einen Befehl zu erstellen `ForEach-Object` .

- **Skriptblock**. Sie können einen Skriptblock verwenden, um den Vorgang anzugeben. Verwenden Sie innerhalb des Skript Blocks die- `$_` Variable, um das aktuelle-Objekt darzustellen. Der Skriptblock ist der Wert des **Process**-Parameters. Der Skriptblock kann beliebige PowerShell-Skripts enthalten.

  Der folgende Befehl ruft beispielsweise den Wert der **ProcessName**-Eigenschaft der einzelnen Prozesse auf dem Computer ab.

  `Get-Process | ForEach-Object {$_.ProcessName}`

  `ForEach-Object` unterstützt `begin` die `process` Blöcke, und, `end` wie in [about_functions](about/about_functions.md#piping-objects-to-functions)beschrieben.

  > [!NOTE]
  > Die Skriptblöcke werden im Gültigkeitsbereich des Aufrufers ausgeführt. Daher haben die Blöcke Zugriff auf Variablen in diesem Bereich und können neue Variablen erstellen, die in diesem Bereich beibehalten werden, nachdem das Cmdlet abgeschlossen wurde.

- **Operation-Anweisung**. Sie können auch eine Vorgangs Anweisung schreiben, die in natürlicher Sprache sehr viel ähnlicher ist. Sie können die Vorgangsanweisung verwenden, um einen Eigenschaftenwert anzugeben oder eine Methode aufzurufen. Vorgangsanweisungen wurden in Windows PowerShell 3.0 eingeführt.

  Der folgende Befehl ruft beispielsweise ebenfalls den Wert der **ProcessName**-Eigenschaft der einzelnen Prozesse auf dem Computer ab.

  `Get-Process | ForEach-Object ProcessName`

- **Parallel ausgeführten Skriptblock**. Ab PowerShell 7,0 ist ein Dritter Parametersatz verfügbar, der jeden Skriptblock parallel ausführt. Der **throttlelimit** -Parameter schränkt die Anzahl paralleler Skripts ein, die gleichzeitig ausgeführt werden. Verwenden Sie wie zuvor die- `$_` Variable, um das aktuelle Eingabe Objekt im Skriptblock darzustellen. Verwenden Sie das- `$using:` Schlüsselwort, um Variablen Verweise an das laufende Skript zu übergeben.

  In PowerShell 7 wird ein neuer Runspace für jede Schleifen Iteration erstellt, um eine maximale Isolation sicherzustellen.
  Dabei kann es sich um eine große Leistung und einen Ressourcen Treffer handeln, wenn die Arbeit, die Sie ausführen, im Vergleich zum Erstellen neuer Runspaces gering ist, oder wenn viele Iterationen eine bedeutende Arbeit ausführen. Ab PowerShell 7,1 werden Runspaces aus einem Runspace-Pool standardmäßig wieder verwendet. Die Größe des Runspace-Pools wird durch den **throttlelimit** -Parameter angegeben. Die standardmäßige Runspace-Poolgröße ist 5. Mit dem Schalter **usenewrunspace** können Sie immer noch einen neuen Runspace für jede Iterationen erstellen.

  Standardmäßig verwenden die parallelen Scriptblocks das aktuelle Arbeitsverzeichnis des Aufrufers, der die parallelen Aufgaben gestartet hat.

  Fehler ohne Abbruch werden in den Cmdlet-Fehler Datenstrom geschrieben, da Sie in parallel ausgeführten Scriptblocks auftreten. Da die Ausführungsreihenfolge paralleler Scriptblocks nicht bestimmt werden kann, ist die Reihenfolge, in der Fehler im Fehler Datenstrom angezeigt werden, zufällig. Ebenso werden Nachrichten, die in andere Datenströme wie Warnung, ausführlich oder Informationen geschrieben werden, in einer unbestimmten Reihenfolge in diese Datenströme geschrieben.

  Beim Beenden von Fehlern, z. b. Ausnahmen, wird die einzelne parallele Instanz der Scriptblocks beendet, in denen Sie auftreten. Ein Beendigungs Fehler in einem Scriptblocks führt möglicherweise nicht zum Beenden des `Foreach-Object` Cmdlets. Die anderen Skriptblöcke, die parallel ausgeführt werden, werden weiterhin ausgeführt, es sei denn, Sie stoßen auch auf einen Beendigungs Fehler. Der Abbruch Fehler wird in den Fehler Datenstrom als **ErrorRecord** mit der **fullyqualifiederrorid** von geschrieben `PSTaskException` .
  Fehler beim Beenden können mithilfe von PowerShell-try/catch-oder Trap-Blöcken in Fehler ohne Abbruch konvertiert werden.

## Beispiele

### Beispiel 1: Teilen von ganzen Zahlen in einem Array

In diesem Beispiel wird ein Array von drei ganzen Zahlen angenommen, und jedes dieser Elemente wird durch 1024 dividiert.

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### Beispiel 2: erhalten der Länge aller Dateien in einem Verzeichnis

In diesem Beispiel werden die Dateien und Verzeichnisse im PowerShell-Installationsverzeichnis verarbeitet `$PSHOME` .

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

Wenn das Objekt kein Verzeichnis ist, ruft der Skriptblock den Namen der Datei ab, teilt den Wert der **length** -Eigenschaft durch 1024 und fügt ein Leerzeichen ("") hinzu, um es vom nächsten Eintrag zu trennen. Mit dem-Cmdlet wird die **psiscontainer** -Eigenschaft verwendet, um zu bestimmen, ob ein Objekt ein Verzeichnis ist.

### Beispiel 3: Arbeiten mit den neuesten System Ereignissen

In diesem Beispiel werden die 1000 aktuellsten Ereignisse aus dem System Ereignisprotokoll in eine Textdatei geschrieben. Die aktuelle Zeit wird vor und nach der Verarbeitung der Ereignisse angezeigt.

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

`Get-EventLog` Ruft die 1000 aktuellsten Ereignisse aus dem System Ereignisprotokoll ab und speichert Sie in der `$Events` Variablen. `$Events` wird dann an das `ForEach-Object` Cmdlet weitergeleitet. Der **Begin**-Parameter zeigt das aktuelle Datum und die Uhrzeit. Als Nächstes verwendet der **Process** -Parameter das `Out-File` -Cmdlet, um eine Textdatei mit dem Namen events.txt zu erstellen, und speichert die Message-Eigenschaft der einzelnen Ereignisse in dieser Datei. Schließlich wird der **End**-Parameter verwendet, um das Datum und die Uhrzeit anzuzeigen, zu denen die gesamte Verarbeitung abgeschlossen wurde.

### Beispiel 4: Ändern des Werts eines Registrierungsschlüssels

In diesem Beispiel wird der Wert des **remotePath** -Registrierungs Eintrags in allen unter Schlüsseln unter dem `HKCU:\Network` Schlüssel in Großbuchstaben geändert.

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

Sie können dieses Format verwenden,um die Form oder den Inhalt eines Registrierungseintragswerts zu ändern.

Jeder Unterschlüssel im **Netzwerk** Schlüssel stellt ein zugeordnetes Netzwerklaufwerk dar, das bei der Anmeldung erneut eine Verbindung herstellt. Der **RemotePath**-Eintrag enthält den UNC-Pfad des verbundenen Laufwerks. Wenn Sie z. b. das Laufwerk e: zu zuordnen `\\Server\Share` , wird ein **e** -Unterschlüssel in erstellt, `HKCU:\Network` wobei der Registrierungs Wert **remotePath** auf festgelegt ist `\\Server\Share` .

Der Befehl verwendet das `Get-ItemProperty` Cmdlet, um alle untergeordneten Schlüssel des **Netzwerk** Schlüssels zu erhalten, und das `Set-ItemProperty` Cmdlet, um den Wert des **remotePath** -Registrierungs Eintrags in jedem Schlüssel zu ändern.
Im- `Set-ItemProperty` Befehl ist der Pfad der Wert der **pspath** -Eigenschaft des Registrierungsschlüssels. Dies ist eine Eigenschaft des Microsoft .NET Framework-Objekts, das den Registrierungsschlüssel darstellt, nicht einen Registrierungs Eintrag. Der Befehl verwendet die **touppermethode ()** des **remotePath** -Werts, bei der es sich um eine Zeichenfolge (REG_SZ) handelt.

Da `Set-ItemProperty` die-Eigenschaft jedes Schlüssels ändert, ist das `ForEach-Object` Cmdlet für den Zugriff auf die-Eigenschaft erforderlich.

### Beispiel 5: Verwenden der automatischen $NULL Variablen

In diesem Beispiel wird gezeigt, wie die `$Null` Automatische Variable an das `ForEach-Object` Cmdlet weitergeleitet wird.

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

Da PowerShell NULL als expliziten Platzhalter behandelt, `ForEach-Object` generiert das Cmdlet einen Wert für `$Null` , genau wie bei anderen Objekten, die an das Cmdlet weiterreichen.

### Beispiel 6: erhalten von Eigenschafts Werten

In diesem Beispiel wird der Wert der **path** -Eigenschaft aller installierten PowerShell-Module mithilfe des **Mitgliedschafts Namen** -Parameters des `ForEach-Object` Cmdlets abgerufen.

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

Der zweite Befehl entspricht dem ersten. Er verwendet den `Foreach` Alias des `ForEach-Object` Cmdlets und lässt den Namen des **Mitgliedsnamen** -Parameters aus, der optional ist.

Das- `ForEach-Object` Cmdlet ist nützlich zum Abrufen von Eigenschafts Werten, da es den Wert abruft, ohne den Typ zu ändern, im Gegensatz zu den **Format** -Cmdlets oder dem `Select-Object` Cmdlet, die den Eigenschafts Werttyp ändern.

### Beispiel 7: Aufteilen von Modulnamen in Komponentennamen

Dieses Beispiel zeigt drei Möglichkeiten, zwei durch Punkte getrennte Modulnamen in Ihre Komponentennamen aufzuteilen.

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

Die Befehle rufen die **Split** Methode von Zeichenfolgen auf. Die drei Befehle verwenden unterschiedliche Syntax, sind aber äquivalent und austauschbar.

Der erste Befehl verwendet die herkömmliche Syntax, die einen Skriptblock und den aktuellen Objekt Operator enthält `$_` . Es verwendet die Punktsyntax zum Angeben der Methode und die Klammern, um das Trennzeichenargument einzuschließen.

Der zweite Befehl verwendet den **MemberName**-Parameter, um die **Split**-Methode anzugeben,und den **ArgumentName**-Parameter, um den Punkt („.“) als das Teilungstrennzeichen zu identifizieren.

Der dritte Befehl verwendet den **foreach** -Alias des `ForEach-Object` Cmdlets und lässt die Namen der Parameter " **Membership Name** " und "Argument **List** " aus, die optional sind.

### Beispiel 8: Verwenden von ForEach-Object mit zwei Skript Blöcken

In diesem Beispiel übergeben wir zwei Skriptblöcke in der gleichen Weise. Alle Skriptblöcke werden an den **Prozess** Parameter gebunden. Sie werden jedoch so behandelt, als würden Sie an den **Begin** -und den **Process** -Parameter übermittelt.

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### Beispiel 9: Verwenden von ForEach-Object mit mehr als zwei Skript Blöcken

In diesem Beispiel übergeben wir zwei Skriptblöcke in der gleichen Weise. Alle Skriptblöcke werden an den **Prozess** Parameter gebunden. Sie werden jedoch so behandelt, als wären Sie an die **Begin**-, **Process**-und **End** -Parameter übergebenen.

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> Der erste Skriptblock wird immer dem Block zugeordnet `begin` , der letzte Block wird dem `end` Block zugeordnet, und die Blöcke dazwischen werden alle dem `process` Block zugeordnet.

### Beispiel 10: Ausführen mehrerer Skriptblöcke für jedes Pipeline Element

Wie im vorherigen Beispiel gezeigt, werden mehrere Skriptblöcke, die mit dem **Process** -Parameter übergeben wurden, den **Begin** -und **End** -Parametern zugeordnet. Um diese Zuordnung zu vermeiden, müssen Sie explizite Werte für die **Begin** -und **End** -Parameter angeben.

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

### Beispiel 11: Ausführen eines langsamen Skripts in parallelen Batches

In diesem Beispiel wird ein einfacher Skriptblock ausgeführt, der eine Zeichenfolge auswertet und eine Sekunde aufsperrt.

```powershell
$Message = "Output:"

1..8 | ForEach-Object -Parallel {
    "$using:Message $_"
    Start-Sleep 1
} -ThrottleLimit 4
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
```

Der Wert des **throttlelimit** -Parameters ist auf 4 festgelegt, sodass die Eingabe in Batches von vier verarbeitet wird.
Das- `$using:` Schlüsselwort wird verwendet, um die `$Message` Variable an jeden parallelen Skriptblock zu übergeben.

### Beispiel 12: paralleles Abrufen von Protokoll Einträgen

In diesem Beispiel werden 50.000-Protokolleinträge aus fünf Systemprotokollen auf einem lokalen Windows-Computer abgerufen.

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count
```

```Output
50000
```

Der Parameter **Parallel** gibt den Skriptblock an, der für jeden Eingabeprotokollnamen parallel ausgeführt wird. Der **throttlelimit** -Parameter stellt sicher, dass alle fünf Skriptblöcke zur gleichen Zeit ausgeführt werden.

### Beispiel 13: parallele Ausführen als Auftrag

In diesem Beispiel wird ein einfacher Skriptblock parallel ausgeführt, wobei jeweils zwei Hintergrund Aufträge erstellt werden.

```powershell
$job = 1..10 | ForEach-Object -Parallel {
    "Output: $_"
    Start-Sleep 1
} -ThrottleLimit 2 -AsJob

$job | Receive-Job -Wait
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
Output: 9
Output: 10
```

die- `$job` Variable empfängt das Auftrags Objekt, das Ausgabedaten sammelt und den ausgegebene Status überwacht.
Das Auftrags Objekt wird `Receive-Job` mit dem **Wait** -Schalter Parameter an weitergeleitet. Und damit wird die Ausgabe an die Konsole gestreamt, so als ob auch `ForEach-Object -Parallel` ohne **AsJob** ausgeführt würde.

### Beispiel 14: Verwenden von Verweisen auf Thread sichere Variablen

In diesem Beispiel werden Skriptblöcke parallel aufgerufen, um eindeutig benannte Prozess Objekte zu erfassen.

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
Get-Process | ForEach-Object -Parallel {
    $dict = $using:threadSafeDictionary
    $dict.TryAdd($_.ProcessName, $_)
}

$threadSafeDictionary["pwsh"]
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     82    82.87     130.85      15.55    2808   2 pwsh
```

Eine einzelne Instanz eines **ConcurrentDictionary** -Objekts wird an jeden Skriptblock zum Erfassen der Objekte übermittelt. Da das **ConcurrentDictionary** Thread sicher ist, kann es sicher von jedem parallelen Skript geändert werden. Ein nicht Thread sicheres Objekt, wie z. b **. System. Collections. Generic. Dictionary**, kann hier nicht sicher verwendet werden.

> [!NOTE]
> Dieses Beispiel ist eine sehr ineffiziente Verwendung des **parallelen** Parameters. Das Skript fügt das Eingabe Objekt einfach einem gleichzeitigen Wörterbuch Objekt hinzu. Der Aufwand für das Aufrufen der einzelnen Skripts in einem separaten Thread ist trivial. Die normale Ausführung `ForEach-Object` ohne den **parallelen** Switch ist viel effizienter und schneller. Dieses Beispiel soll lediglich veranschaulichen, wie Thread sichere Variablen verwendet werden.

### Beispiel 15: Schreiben von Fehlern mit paralleler Ausführung

In diesem Beispiel wird parallel in den Fehler Datenstrom geschrieben, wobei die Reihenfolge der geschriebenen Fehler zufällig ist.

```powershell
1..3 | ForEach-Object -Parallel {
    Write-Error "Error: $_"
}
```

```Output
Write-Error: Error: 1
Write-Error: Error: 3
Write-Error: Error: 2
```

### Beispiel 16: Beenden von Fehlern bei der parallelen Ausführung

In diesem Beispiel wird ein Beendigungs Fehler in einem parallel ausgeführten ScriptBlock veranschaulicht.

```powershell
1..5 | ForEach-Object -Parallel {
    if ($_ -eq 3)
    {
        throw "Terminating Error: $_"
    }

    Write-Output "Output: $_"
}
```

```Output
Exception: Terminating Error: 3
Output: 1
Output: 4
Output: 2
Output: 5
```

`Output: 3` wird nie geschrieben, da der parallele ScriptBlock für diese Iterationen beendet wurde.

### Beispiel 17: übergeben von Variablen in einem Skript für einen genten parallelen Skript-scriptblockset

Sie können eine Variable außerhalb eines Bereichs bezogenen `Foreach-Object -Parallel` Scriptblocks erstellen und innerhalb von ScriptBlock mit dem `$using` Schlüsselwort verwenden.

```powershell
$test1 = 'TestA'
1..2 | Foreach-Object -Parallel {
    $using:test1
}
```

```Output
TestA
TestA
```

```powershell
# You CANNOT create a variable inside a scoped scriptblock
# to be used in a nested foreach parallel scriptblock.
$test1 = 'TestA'
1..2 | Foreach-Object -Parallel {
    $using:test1
    $test2 = 'TestB'
    1..2 | Foreach-Object -Parallel {
        $using:test2
    }
}
```

```Output
Line |
   2 |  1..2 | Foreach-Object -Parallel {
     |         ~~~~~~~~~~~~~~~~~~~~~~~~~~
     | The value of the using variable '$using:test2' cannot be retrieved because it has not been set in the local session.
```

Der geschsted ScriptBlock kann nicht auf die Variable zugreifen, `$test2` und es wird ein Fehler ausgelöst.

## Parameter

### -Argumentlist

Gibt ein Array von Argumenten für einen Methoden aufzurufenden an. Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BEGIN

Gibt einen Skriptblock an, der ausgeführt wird, bevor dieses Cmdlet Eingabe Objekte verarbeitet. Dieser Skriptblock wird nur einmal für die gesamte Pipeline ausgeführt. Weitere Informationen zum- `begin` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ende

Gibt einen Skriptblock an, der ausgeführt wird, nachdem dieses Cmdlet alle Eingabe Objekte verarbeitet hat. Dieser Skriptblock wird nur einmal für die gesamte Pipeline ausgeführt. Weitere Informationen zum- `end` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die Eingabeobjekte an. `ForEach-Object` führt den Skriptblock oder die Vorgangs Anweisung für jedes Eingabe Objekt aus. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

Wenn Sie den **Inputobject** -Parameter mit verwenden `ForEach-Object` , anstatt Befehls Ergebnisse an zu übergeben `ForEach-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt. Dies gilt auch, wenn der Wert eine Auflistung ist, die das Ergebnis eines Befehls ist, z `-InputObject (Get-Process)` . b..
Da **Inputobject** keine einzelnen Eigenschaften aus einem Array oder einer Auflistung von Objekten zurückgeben kann, empfiehlt es sich, wenn Sie verwenden, `ForEach-Object` um Vorgänge für eine Auflistung von Objekten für Objekte mit spezifischen Werten in definierten Eigenschaften auszuführen, `ForEach-Object` wie in den Beispielen in diesem Thema gezeigt.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Mitgliedsname

Gibt die abzurufende Eigenschaft oder die aufzurufende Methode an.

Platzhalter Zeichen sind zulässig, funktionieren jedoch nur, wenn die resultierende Zeichenfolge in einen eindeutigen Wert aufgelöst wird.
Wenn Sie z. b `Get-Process | ForEach -MemberName *Name` . ausführen, stimmt das Platzhalter Muster mit mehr als einem Member überein, wodurch der Befehl fehlschlägt.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Prozess

Gibt den Vorgang an, der für jedes Eingabeobjekt ausgeführt wird. Dieser Skriptblock wird für jedes Objekt in der Pipeline ausgeführt. Weitere Informationen zum- `process` Block finden Sie unter [about_Functions](about/about_functions.md#piping-objects-to-functions).

Wenn Sie dem **Prozess** Parameter mehrere Skriptblöcke bereitstellen, wird der erste Skriptblock immer dem Block zugeordnet `begin` . Wenn nur zwei Skriptblöcke vorhanden sind, wird der zweite Block dem Block zugeordnet `process` . Wenn es drei oder mehr Skriptblöcke gibt, wird der erste Skriptblock immer dem `begin` Block zugeordnet, der letzte Block wird dem Block zugeordnet `end` , und die Blöcke dazwischen werden alle dem `process` Block zugeordnet.

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Restingscripts

Gibt alle Skriptblöcke an, die nicht vom **Prozess** Parameter übernommen werden.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parallel

Gibt den Skriptblock an, der für die parallele Verarbeitung von Eingabe Objekten verwendet werden soll. Geben Sie einen Skriptblock ein, der den Vorgang beschreibt.

Dieser Parameter wurde in PowerShell 7,0 eingeführt.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ParallelParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Gibt an, wie viele Skriptblöcke parallel ausgeführt werden. Eingabe Objekte werden blockiert, bis die Anzahl der ausgefallenen Skriptblöcke unter den **throttlelimit** fällt. Standardwert: `5`.

Dieser Parameter wurde in PowerShell 7,0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSeconds

Gibt die Anzahl der Sekunden an, die gewartet werden soll, bis alle Eingaben parallel verarbeitet werden. Nach der angegebenen Timeout Zeit werden alle laufenden Skripts angehalten. Und alle verbleibenden zu verarbeitenden Eingabe Objekte werden ignoriert. Der Standardwert `0` deaktiviert den Timeout und `ForEach-Object -Parallel` kann unbegrenzt ausgeführt werden. Wenn <kbd></kbd>Sie + in der Befehlszeile STRG<kbd>C</kbd> eingeben, wird ein laufender `ForEach-Object -Parallel` Befehl beendet. Dieser Parameter kann nicht zusammen mit dem **AsJob** -Parameter verwendet werden.

Dieser Parameter wurde in PowerShell 7,0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usenewrunspace

Bewirkt, dass der parallele Aufruf einen neuen Runspace für jede Schleifen Iteration erstellt, anstatt Runspaces aus dem Runspace-Pool wieder zu verwenden.

Dieser Parameter wurde in PowerShell 7,1 eingeführt.

```yml
Type: SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

Bewirkt, dass der parallele Aufruf als PowerShell-Auftrag ausgeführt wird. Anstelle der Ausgabe der ausgelaufenden Skriptblöcke wird ein einzelnes Auftrags Objekt zurückgegeben. Das Job-Objekt enthält untergeordnete Aufträge für jeden parallelen Skriptblock, der ausführt. Das Auftrags Objekt kann von allen PowerShell-Auftrags-Cmdlets verwendet werden, um den Status der Ausführung und das Abrufen von Daten zu überwachen.

Dieser Parameter wurde in PowerShell 7,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Eingaben

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt über die Pipeline an dieses Cmdlet übergeben.

## Ausgaben

### System. Management. Automation. psobject

Dieses Cmdlet gibt Objekte zurück, die von der Eingabe bestimmt werden.

## Hinweise

- Das- `ForEach-Object` Cmdlet funktioniert ähnlich wie die **foreach** -Anweisung, mit dem Unterschied, dass Sie Eingaben nicht an eine **foreach** -Anweisung übergeben können. Weitere Informationen zur **foreach** -Anweisung finden Sie unter [about_Foreach](./About/about_Foreach.md).

- Ab PowerShell 4,0 `Where` wurden-und-Methoden für die Verwendung mit-Auflistungen `ForEach` hinzugefügt. Weitere Informationen zu diesen neuen Methoden finden Sie hier [about_arrays](./About/about_Arrays.md)

- Der `ForEach-Object -Parallel` Parametersatz verwendet die interne PowerShell-API, um jeden Skriptblock auszuführen. Dies ist deutlich mehr Aufwand als `ForEach-Object` bei der sequenziellen Verarbeitung. Es ist wichtig, **parallel** zu verwenden, wenn der mehr Aufwand für die parallele Ausführung im Vergleich zu den vom Skriptblock ausgeführten Arbeiten gering ist. Beispiel:

  - Rechenintensive Skripts auf mehr Kern Computern
  - Skripts, die Zeit für das warten auf Ergebnisse oder Datei Vorgänge aufwenden

  Die Verwendung des **parallel** -Parameters kann bewirken, dass Skripts wesentlich langsamer ausgeführt werden. Insbesondere, wenn die parallelen Skripts trivial sind. Experimentieren Sie mit **parallel** , um herauszufinden, wo es nützlich sein kann.

- [Pipelinevariable](About/about_CommonParameters.md) allgemeine Parameter Variablen werden  in `Foreach-Object -Parallel` Szenarios auch mit dem- `$using:` Schlüsselwort nicht unterstützt.

  > [!IMPORTANT]
  > Der `ForEach-Object -Parallel` Parametersatz führt Skriptblöcke parallel in separaten Prozessthreads aus. Das- `$using:` Schlüsselwort ermöglicht das Übergeben von Variablen verweisen vom Cmdlet-Aufruf Thread an jeden Skriptblock Thread, der ausgeführt wird. Da die Skriptblöcke in verschiedenen Threads ausgeführt werden, müssen die als Verweis übergebenen Objektvariablen sicher verwendet werden. Im Allgemeinen ist es sicher, aus referenzierten Objekten zu lesen, die sich nicht ändern. Wenn der Objektstatus jedoch geändert wird, müssen Sie Thread sichere Objekte verwenden, wie z. b. .net **System. Collection. Concurrent** -Typen (siehe Beispiel 11).

## Verwandte Links

[Compare-Object](../Microsoft.PowerShell.Utility/Compare-Object.md)

[Where-Object](Where-Object.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Measure-Object](../Microsoft.PowerShell.Utility/Measure-Object.md)

[New-Object](../Microsoft.PowerShell.Utility/New-Object.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Tee-Object](../Microsoft.PowerShell.Utility/Tee-Object.md)
