---
description: Kombinieren von Befehlen in Pipelines in PowerShell
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pipelines?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pipelines
ms.openlocfilehash: ca933e7e130959ef725d760d859ca43b99bdfc76
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222023"
---
# <a name="about-pipelines"></a>Informationen zu Pipelines

## <a name="short-description"></a>Kurze Beschreibung

Kombinieren von Befehlen in Pipelines in PowerShell

## <a name="long-description"></a>Lange Beschreibung

Eine Pipeline ist eine Reihe von Befehlen, die durch Pipeline Operatoren ( `|` ) (ASCII 124) verbunden sind. Jeder Pipeline Operator sendet die Ergebnisse des vorangehenden Befehls an den nächsten Befehl.

Die Ausgabe des ersten Befehls kann als Eingabe für den zweiten Befehl zur Verarbeitung gesendet werden. Und diese Ausgabe kann an einen anderen Befehl gesendet werden. Das Ergebnis ist eine komplexe Befehlskette oder _Pipeline_ , die aus einer Reihe einfacher Befehle besteht.

Ein auf ein Objekt angewendeter

```powershell
Command-1 | Command-2 | Command-3
```

In diesem Beispiel werden die-Objekte, die `Command-1` ausgibt, an gesendet `Command-2` .
`Command-2` verarbeitet die-Objekte und sendet Sie an `Command-3` . `Command-3` verarbeitet die Objekte und sendet Sie über die Pipeline. Da in der Pipeline keine weiteren Befehle vorhanden sind, werden die Ergebnisse in der Konsole angezeigt.

In einer Pipeline werden die Befehle in der Reihenfolge von links nach rechts verarbeitet. Die Verarbeitung wird als einzelner Vorgang behandelt, und die Ausgabe wird angezeigt, wenn Sie generiert wird.

Hier ist ein einfaches Beispiel. Der folgende Befehl ruft den Notepad-Prozess ab und beendet ihn.

Ein auf ein Objekt angewendeter

```powershell
Get-Process notepad | Stop-Process
```

Der erste Befehl verwendet das `Get-Process` Cmdlet, um ein Objekt zu erhalten, das den Notepad-Prozess darstellt. Er verwendet einen Pipeline Operator ( `|` ), um das Process-Objekt an das `Stop-Process` Cmdlet zu senden, das den Notepad-Prozess beendet. Beachten Sie, dass der `Stop-Process` Befehl keinen **namens** -oder **ID** -Parameter besitzt, um den Prozess anzugeben, da der angegebene Prozess über die Pipeline übermittelt wird.

Dieses Pipeline Beispiel ruft die Textdateien im aktuellen Verzeichnis ab, wählt nur die Dateien aus, die mehr als 10.000 Bytes lang sind, sortiert sie nach Länge und zeigt den Namen und die Länge jeder Datei in einer Tabelle an.

```powershell
Get-ChildItem -Path *.txt |
  Where-Object {$_.length -gt 10000} |
    Sort-Object -Property length |
      Format-Table -Property name, length
```

Diese Pipeline besteht aus vier Befehlen in der angegebenen Reihenfolge. Die folgende Abbildung zeigt die Ausgabe der einzelnen Befehle, wenn Sie an den nächsten Befehl in der Pipeline weitergeleitet wird.

```
Get-ChildItem -Path *.txt
| (FileInfo objects for *.txt)
V
Where-Object {$_.length -gt 10000}
| (FileInfo objects for *.txt)
| (      Length > 10000      )
V
Sort-Object -Property Length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
V
Format-Table -Property name, length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
| (   Formatted in a table   )
V

Name                       Length
----                       ------
tmp1.txt                    82920
tmp2.txt                   114000
tmp3.txt                   114000
```

## <a name="using-pipelines"></a>Verwenden von Pipelines

Die meisten PowerShell-Cmdlets sind für die Unterstützung von Pipelines konzipiert. In den meisten Fällen können Sie die Ergebnisse eines **Get** -Cmdlets über die _Pipeline_ an ein anderes Cmdlet desselben Substantivs übergeben.
Beispielsweise können Sie die Ausgabe des- `Get-Service` Cmdlets an das- `Start-Service` Cmdlet oder das- `Stop-Service` Cmdlet weiterreichen.

Diese Beispiel Pipeline startet den WMI-Dienst auf dem Computer:

```powershell
Get-Service wmi | Start-Service
```

Ein weiteres Beispiel: Sie können die Ausgabe von `Get-Item` oder `Get-ChildItem` innerhalb des PowerShell-Registrierungs Anbieters an das- `New-ItemProperty` Cmdlet weiterreichen. In diesem Beispiel wird dem Registrierungsschlüssel **MyCompany** ein neuer Registrierungs Eintrag, **noofemployees** , mit dem Wert **8124** hinzugefügt.

```powershell
Get-Item -Path HKLM:\Software\MyCompany |
  New-ItemProperty -Name NoOfEmployees -Value 8124
```

Viele der hilfsprogrammcmdlets, z. b. `Get-Member` , `Where-Object` , `Sort-Object` , `Group-Object` und, `Measure-Object` werden nahezu exklusiv in Pipelines verwendet. Sie können einen beliebigen Objekttyp an diese Cmdlets übergeben. Dieses Beispiel zeigt, wie alle Prozesse auf dem Computer nach der Anzahl der geöffneten Handles in jedem Prozess sortiert werden.

```powershell
Get-Process | Sort-Object -Property handles
```

Sie können Objekte über die Pipeline an die Formatierungs-, Export-und Ausgabe-Cmdlets übergeben, z `Format-List` `Format-Table` . b.,, `Export-Clixml` , `Export-CSV` und `Out-File` .

Dieses Beispiel zeigt, wie das `Format-List` Cmdlet verwendet wird, um eine Liste von Eigenschaften für ein Prozess Objekt anzuzeigen.

```powershell
Get-Process winlogon | Format-List -Property *
```

In der Praxis werden Sie feststellen, dass die Kombination einfacher Befehle in Pipelines Zeit und Eingabe spart und die Skripterstellung effizienter macht.

## <a name="how-pipelines-work"></a>Funktionsweise von Pipelines

In diesem Abschnitt wird erläutert, wie Eingabe Objekte an Cmdlet-Parameter gebunden und während der Pipeline Ausführung verarbeitet werden.

### <a name="accepts-pipeline-input"></a>Akzeptiert Pipeline Eingaben

Um Pipelining zu unterstützen, muss das empfangende Cmdlet über einen Parameter verfügen, der Pipeline Eingaben akzeptiert. Verwenden Sie den- `Get-Help` Befehl mit den Optionen **Full** oder **Parameter** , um zu bestimmen, welche Parameter eines Cmdlets Pipeline Eingaben akzeptieren.

Geben Sie z. b. Folgendes ein, um zu bestimmen, welcher der Parameter des `Start-Service` Cmdlets Pipeline Eingaben akzeptiert:

```powershell
Get-Help Start-Service -Full
```

oder

```powershell
Get-Help Start-Service -Parameter *
```

Die Hilfe für das `Start-Service` Cmdlet zeigt, dass nur der **Inputobject** -Parameter und der **Name** -Parameter Pipeline Eingaben akzeptieren.

```Output
-InputObject <ServiceController[]>
Specifies ServiceController objects representing the services to be started.
Enter a variable that contains the objects, or type a command or expression
that gets the objects.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByValue)
Accept wildcard characters?  false

-Name <String[]>
Specifies the service names for the service to be started.

The parameter name is optional. You can use Name or its alias, ServiceName,
or you can omit the parameter name.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByPropertyName, ByValue)
Accept wildcard characters?  false
```

Wenn Sie Objekte über die Pipeline an senden `Start-Service` , versucht PowerShell, die Objekte den **Inputobject** -und **Name** -Parametern zuzuordnen.

### <a name="methods-of-accepting-pipeline-input"></a>Methoden zum Akzeptieren von Pipeline Eingaben

Cmdlets-Parameter können eine Pipeline Eingabe auf zwei verschiedene Arten akzeptieren:

- **Byvalue** : der Parameter akzeptiert Werte, die dem erwarteten .NET-Typ entsprechen oder in diesen Typ konvertiert werden können.

  Der **Name** -Parameter von akzeptiert beispielsweise `Start-Service` Pipeline Eingaben nach Wert. Sie kann Zeichen folgen Objekte oder-Objekte akzeptieren, die in Zeichen folgen konvertiert werden können.

- **Bypropertyname** : der-Parameter akzeptiert nur Eingaben, wenn das Eingabe Objekt eine Eigenschaft mit dem gleichen Namen wie der-Parameter aufweist.

  Der Name-Parameter von kann z `Start-Service` . b.-Objekte akzeptieren, die über eine **Name** -Eigenschaft verfügen. Um die Eigenschaften eines Objekts aufzulisten, übergeben Sie es an `Get-Member` .

Einige Parameter können Objekte sowohl nach Wert als auch nach Eigenschaftsname akzeptieren, sodass Sie die Eingabe von der Pipeline vereinfachen.

### <a name="parameter-binding"></a>Parameterbindung

Wenn Sie Objekte von einem Befehl an einen anderen Befehl übergeben, versucht PowerShell, die weitergeleiteten Objekte einem Parameter des empfangenden Cmdlets zuzuordnen.

Die Parameter bindungskomponente von PowerShell ordnet die Eingabe Objekte den Cmdlet-Parametern gemäß den folgenden Kriterien zu:

- Der-Parameter muss Eingaben aus einer Pipeline akzeptieren.
- Der-Parameter muss den Typ des gesendeten Objekts oder einen Typ akzeptieren, der in den erwarteten Typ konvertiert werden kann.
- Der-Parameter wurde im Befehl nicht verwendet.

Beispielsweise hat das `Start-Service` Cmdlet viele Parameter, aber nur zwei von Ihnen, **Name** und **Inputobject** akzeptieren Pipeline Eingaben. Der **Name** -Parameter nimmt Zeichen folgen an, und der **Inputobject** -Parameter übernimmt Dienst Objekte. Daher können Sie Zeichen folgen, Dienst Objekte und Objekte mit Eigenschaften übergeben, die in Zeichen folgen-oder Dienst Objekte konvertiert werden können.

PowerShell verwaltet die Parameter Bindung so effizient wie möglich. Sie können nicht vorschlagen oder erzwingen, dass PowerShell an einen bestimmten Parameter gebunden wird. Der Befehl schlägt fehl, wenn die weitergeleiteten Objekte von PowerShell nicht gebunden werden können.

Weitere Informationen zur Problembehandlung bei Bindungs Fehlern finden Sie unter unter [Suchen von Pipeline Fehlern](#investigating-pipeline-errors) weiter unten in diesem Artikel.

### <a name="one-at-a-time-processing"></a>Uni-at-a-Time-Verarbeitung

Das Weiterleiten von Objekten an einen Befehl ähnelt dem Verwenden eines Parameters des Befehls, um die Objekte zu übermitteln. Sehen wir uns ein Beispiel für eine Pipeline an. In diesem Beispiel verwenden wir eine Pipeline, um eine Tabelle mit Dienst Objekten anzuzeigen.

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

Funktionell ist dies die Verwendung des **Inputobject** -Parameters von `Format-Table` zum übermitteln der Objekt Auflistung.

Beispielsweise können wir die Auflistung der Dienste in einer Variablen speichern, die mithilfe des **Inputobject** -Parameters übergeben wird.

```powershell
$services = Get-Service
Format-Table -InputObject $services -Property Name, DependentServices
```

Oder Sie können den Befehl in den **Inputobject-Parameter einbetten** .

```powershell
Format-Table -InputObject (Get-Service) -Property Name, DependentServices
```

Es gibt jedoch einen wichtigen Unterschied. Wenn Sie mehrere Objekte an einen Befehl übergeben, sendet PowerShell die Objekte nacheinander an den Befehl. Wenn Sie einen Command-Parameter verwenden, werden die-Objekte als einzelnes Array Objekt gesendet. Dieser geringfügige Unterschied hat bedeutende Konsequenzen.

Beim Ausführen einer Pipeline listet PowerShell automatisch jeden Typ auf, der die- `IEnumerable` Schnittstelle implementiert, und sendet die Elemente nacheinander über die Pipeline. Die Ausnahme ist `[hashtable]` , was einen aufzurufenden- `GetEnumerator()` Methode erfordert.

In den folgenden Beispielen werden ein Array und eine Hash Tabelle an das `Measure-Object` Cmdlet weitergeleitet, um die Anzahl der Objekte zu zählen, die von der Pipeline empfangen werden. Das Array verfügt über mehrere Member, und die Hash Tabelle verfügt über mehrere Schlüssel-Wert-Paare. Nur das Array wird nacheinander aufgelistet.

```powershell
@(1,2,3) | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

```powershell
@{"One"=1;"Two"=2} | Measure-Object
```

```Output
Count    : 1
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

Wenn Sie mehrere Prozess Objekte aus dem `Get-Process` Cmdlet an das `Get-Member` Cmdlet weiterreichen, sendet PowerShell jedes Prozess Objekt einzeln an `Get-Member` . `Get-Member` zeigt die .NET-Klasse (Typ) der Prozess Objekte und ihre Eigenschaften und Methoden an.

```powershell
Get-Process | Get-Member
```

```Output
TypeName: System.Diagnostics.Process

Name      MemberType     Definition
----      ----------     ----------
Handles   AliasProperty  Handles = Handlecount
Name      AliasProperty  Name = ProcessName
NPM       AliasProperty  NPM = NonpagedSystemMemorySize
...
```

> [!NOTE]
> `Get-Member` entfernt Duplikate, sodass nur ein Objekttyp angezeigt wird, wenn die Objekte alle denselben Typ haben.

Wenn Sie jedoch den **Inputobject** -Parameter von verwenden `Get-Member` , `Get-Member` empfängt ein Array von **System. Diagnostics. Process** -Objekten als einzelne Einheit. Es zeigt die Eigenschaften eines Arrays von-Objekten an. (Beachten Sie das Array Symbol ( `[]` ) nach dem **System. Object** -Typnamen.)

Ein auf ein Objekt angewendeter

```powershell
Get-Member -InputObject (Get-Process)
```

```Output
TypeName: System.Object[]

Name               MemberType    Definition
----               ----------    ----------
Count              AliasProperty Count = Length
Address            Method        System.Object& Address(Int32 )
Clone              Method        System.Object Clone()
...
```

Das Ergebnis ist möglicherweise nicht das, was Sie beabsichtigt haben. Aber nachdem Sie es verstanden haben, können Sie es verwenden. Beispielsweise verfügen alle Array Objekte über eine **count** -Eigenschaft. Damit können Sie die Anzahl der Prozesse zählen, die auf dem Computer ausgeführt werden.

Ein auf ein Objekt angewendeter

```powershell
(Get-Process).count
```

Beachten Sie, dass Objekte, die über die Pipeline gesendet werden, nacheinander zugestellt werden.

## <a name="investigating-pipeline-errors"></a>Untersuchen von Pipeline Fehlern

Wenn PowerShell die weitergeleiteten Objekte keinem Parameter des empfangenden Cmdlets zuordnen kann, schlägt der Befehl fehl.

Im folgenden Beispiel wird versucht, einen Registrierungs Eintrag aus einem Registrierungsschlüssel in einen anderen zu verschieben. Mit dem- `Get-Item` Cmdlet wird der Zielpfad abgerufen, der dann an das `Move-ItemProperty` Cmdlet weitergeleitet wird. Der `Move-ItemProperty` Befehl gibt den aktuellen Pfad und Namen des Registrierungs Eintrags an, der verschoben werden soll.

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales |
Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
```

Der Befehl schlägt fehl, und PowerShell zeigt die folgende Fehlermeldung an:

```Output
Move-ItemProperty : The input object can't be bound to any parameters for
the command either because the command doesn't take pipeline input or the
input and its properties do not match any of the parameters that take
pipeline input.
At line:1 char:23
+ $a | Move-ItemProperty <<<<  -Path HKLM:\Software\MyCompany\design -Name p
```

Um dies zu untersuchen, verwenden Sie das- `Trace-Command` Cmdlet, um die Parameter bindungskomponente von PowerShell zu verfolgen. Im folgenden Beispiel wird die Parameter Bindung nachverfolgt, während die Pipeline ausgeführt wird. Der **pshost** -Parameter zeigt die Ablauf Verfolgungs Ergebnisse in der-Konsole an, und der **FilePath** -Parameter sendet die Ablauf Verfolgungs Ergebnisse zur `debug.txt` späteren Referenz an die Datei.

```powershell
Trace-Command -Name ParameterBinding -PSHost -FilePath debug.txt -Expression {
  Get-Item -Path HKLM:\Software\MyCompany\sales |
    Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
}
```

Die Ergebnisse der Ablauf Verfolgung sind langwierig, aber Sie zeigen die Werte an, die an das `Get-Item` Cmdlet gebunden werden, und dann die benannten Werte, die an das `Move-ItemProperty` Cmdlet gebunden werden.

```Output
...
BIND NAMED cmd line args [`Move-ItemProperty`]
BIND arg [HKLM:\Software\MyCompany\design] to parameter [Path]
...
BIND arg [product] to parameter [Name]
...
BIND POSITIONAL cmd line args [`Move-ItemProperty`]
...
```

Schließlich wird angezeigt, dass der Versuch, den Pfad an den **Ziel** Parameter von zu binden, `Move-ItemProperty` fehlgeschlagen ist.

```Output
...
BIND PIPELINE object to parameters: [`Move-ItemProperty`]
PIPELINE object TYPE = [Microsoft.Win32.RegistryKey]
RESTORING pipeline parameter's original values
Parameter [Destination] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
Parameter [Credential] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
...
```

Verwenden Sie das- `Get-Help` Cmdlet, um die Attribute des **Destination** -Parameters anzuzeigen.

```Output
Get-Help Move-ItemProperty -Parameter Destination

-Destination <String>
    Specifies the path to the destination location.

    Required?                    true
    Position?                    1
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  false
```

Die Ergebnisse zeigen an, dass das **Ziel** nur Pipeline Eingaben "by Property Name" annimmt. Daher muss das weitergeleitete Objekt über eine Eigenschaft mit dem Namen " **Destination** " verfügen.

Verwenden `Get-Member` Sie, um die Eigenschaften des Objekts anzuzeigen, das aus stammt `Get-Item` .

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales | Get-Member
```

Die Ausgabe zeigt, dass es sich bei dem Element um ein **Microsoft. Win32. RegistryKey** -Objekt handelt, das nicht über eine **Ziel** Eigenschaft verfügt. Dies erläutert, warum der Befehl fehlgeschlagen ist.

Der **path** -Parameter akzeptiert Pipeline Eingaben nach Namen oder Wert.

```Output
Get-Help Move-ItemProperty -Parameter Path

-Path <String[]>
    Specifies the path to the current location of the property. Wildcard
    characters are permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  true
```

Zum Beheben des Befehls müssen wir das Ziel im `Move-ItemProperty` Cmdlet angeben und verwenden `Get-Item` , um den **Pfad** des Elements zu erhalten, das verschoben werden soll.

Ein auf ein Objekt angewendeter

```powershell
Get-Item -Path HKLM:\Software\MyCompany\design |
Move-ItemProperty -Destination HKLM:\Software\MyCompany\sales -Name product
```

## <a name="intrinsic-line-continuation"></a>Intrinsische Zeilen Fortsetzung

Wie bereits erwähnt, besteht eine Pipeline aus einer Reihe von Befehlen, die durch Pipeline Operatoren ( `|` ) verbunden sind, die in der Regel in einer einzelnen Zeile geschrieben werden. Zur besseren Lesbarkeit ermöglicht Ihnen PowerShell jedoch, die Pipeline über mehrere Zeilen hinweg aufzuteilen.
Wenn ein Pipeoperator das letzte Token in der Zeile ist, fügt der PowerShell-Parser den Befehl nächste Zeile zum aktuellen Befehl ein, um die Erstellung der Pipeline fortzusetzen.

Beispielsweise die folgende einzeilige Pipeline:

```powershell
Command-1 | Command-2 | Command-3
```

kann wie folgt geschrieben werden:

```powershell
Command-1 |
  Command-2 |
    Command-3
```

Die führenden Leerzeichen in den nachfolgenden Zeilen sind nicht von Bedeutung. Der Einzug verbessert die Lesbarkeit.

PowerShell 7 fügt Unterstützung für die Fortsetzung von Pipelines mit dem Pipeline Zeichen am Anfang einer Zeile hinzu. In den folgenden Beispielen wird gezeigt, wie Sie diese neue Funktion verwenden können.

```powershell
# Wrapping with a pipe at the beginning of a line (no backtick required)
Get-Process | Where-Object CPU | Where-Object Path
    | Get-Item | Where-Object FullName -match "AppData"
    | Sort-Object FullName -Unique

# Wrapping with a pipe on a line by itself
Get-Process | Where-Object CPU | Where-Object Path
    |
    Get-Item | Where-Object FullName -match "AppData"
    |
    Sort-Object FullName -Unique
```

> [!IMPORTANT]
> Wenn Sie in der Shell interaktiv arbeiten, fügen Sie Code nur am Anfang einer Zeile mit Pipelines ein, wenn <kbd>Ctrl</kbd>Sie + zum Einfügen Strg<kbd>V</kbd> verwenden.
> Klicken Sie mit der rechten Maustaste auf Einfügevorgänge, um die Zeilen einzeln einzufügen. Da die Zeile nicht mit einem Pipeline Zeichen endet, betrachtet PowerShell die Eingabe als abgeschlossen und führt diese Zeile wie eingegeben aus.

## <a name="see-also"></a>Weitere Informationen

[about_PSReadLine](../../PSReadLine/About/about_PSReadLine.md)

[about_Objects](about_objects.md)

[about_Parameters](about_parameters.md)

[about_Command_Syntax](about_command_syntax.md)

[about_ForEach](about_foreach.md)

