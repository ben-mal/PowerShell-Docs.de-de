---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/21/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-csv?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Csv
ms.openlocfilehash: b2ef2f069c6b5527e2425e3d8adc96d707c65553
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217292"
---
# ConvertFrom-Csv

## ZUSAMMENFASSUNG
Konvertiert Objekteigenschaften im durch Trennzeichen getrennten (CSV-)Format in CSV-Versionen der ursprünglichen Objekte.

## SYNTAX

### Trennzeichen (Standard)

```
ConvertFrom-Csv [[-Delimiter] <Char>] [-InputObject] <PSObject[]> [-Header <String[]>]
 [<CommonParameters>]
```

### UseCulture

```
ConvertFrom-Csv -UseCulture [-InputObject] <PSObject[]> [-Header <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das- `ConvertFrom-Csv` Cmdlet erstellt Objekte aus CSV-Zeichen folgen variabler Länge, die vom `ConvertTo-Csv` Cmdlet generiert werden.

Sie können die Parameter dieses Cmdlets verwenden, um die Spalten Kopfzeile anzugeben, die die Eigenschaftsnamen der resultierenden Objekte bestimmt, um das Element Trennzeichen anzugeben, oder um dieses Cmdlet anzuweisen, das Listen Trennzeichen für die aktuelle Kultur als Trennzeichen zu verwenden.

Die Objekte, die `ConvertFrom-Csv` von erstellt werden, sind CSV-Versionen der ursprünglichen Objekte. Die Eigenschaftswerte der CSV-Objekte sind Zeichenfolgenversionen der Eigenschaftswerte der ursprünglichen Objekte. Die CSV-Versionen der Objekte haben keine Methoden.

Sie können auch die `Export-Csv` `Import-Csv` Cmdlets und verwenden, um Objekte in CSV-Zeichen folgen in einer Datei (und zurück) zu konvertieren. Diese Cmdlets sind identisch `ConvertTo-Csv` mit den-und- `ConvertFrom-Csv` Cmdlets, mit dem Unterschied, dass Sie die CSV-Zeichen folgen in einer Datei speichern.

## BEISPIELE

### Beispiel 1: Konvertieren von Prozessen auf dem lokalen Computer in das CSV-Format

In diesem Beispiel wird gezeigt, wie die Prozesse auf dem lokalen Computer in das CSV-Format konvertiert und anschließend im Objekt Formular wieder hergestellt werden.

```powershell
$P = Get-Process | ConvertTo-Csv
$P | ConvertFrom-Csv
```

Das- `Get-Process` Cmdlet sendet die Prozesse nach unten in der Pipeline an `ConvertTo-Csv` . Mit dem- `ConvertTo-Csv` Cmdlet werden die Prozess Objekte in eine Reihe von CSV-Zeichen folgen konvertiert. Mit dem- `ConvertFrom-Csv` Cmdlet werden die CSV-Zeichen folgen in CSV-Versionen der ursprünglichen Prozess Objekte konvertiert. Die CSV-Zeichen folgen werden in der `$P` Variablen gespeichert.

### Beispiel 2: Konvertieren eines Datenobjekts in das CSV-Format und dann in das CSV-Objekt Format

Dieses Beispiel zeigt, wie Sie ein Datenobjekt in das CSV-Format und dann in das CSV-Objekt Format konvertieren.

```powershell
$Date = Get-Date | ConvertTo-Csv -Delimiter ';'
ConvertFrom-Csv -InputObject $Date -Delimiter ';'
```

Der erste Befehl verwendet `Get-Date` , um das aktuelle Datum und die aktuelle Zeit an die Pipeline zu senden `ConvertTo-Csv` . Mit dem- `ConvertTo-Csv` Cmdlet wird das Date-Objekt in eine Reihe von CSV-Zeichen folgen konvertiert.
Der **Delimiter** -Parameter wird verwendet, um ein Semikolon-Trennzeichen anzugeben. Die Zeichen folgen werden in der `$Date` Variablen gespeichert.

### Beispiel 3: Verwenden Sie den Header-Parameter, um die Namen von Eigenschaften zu ändern.

In diesem Beispiel wird gezeigt, wie der- **Header** Parameter von verwendet wird `ConvertFrom-Csv` , um die Namen von Eigenschaften im resultierenden importierten Objekt zu ändern.

```powershell
$J = Start-Job -ScriptBlock { Get-Process } | ConvertTo-Csv  -NoTypeInformation
$Header = 'State', 'MoreData', 'StatusMessage', 'Location', 'Command', 'StateInfo', 'Finished', 'InstanceId', 'Id', 'Name', 'ChildJobs', 'BeginTime', 'EndTime', 'JobType', 'Output', 'Error', 'Progress', 'Verbose', 'Debug', 'Warning', 'Information'
# Delete the default header from $J
$J = $J[1..($J.count - 1)]
$J | ConvertFrom-Csv -Header $Header
```

```Output
State         : Running
MoreData      : True
StatusMessage :
Location      : localhost
Command       : Get-Process
StateInfo     : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : a259eb63-6824-4b97-a033-305108ae1c2e
Id            : 1
Name          : Job1
ChildJobs     : System.Collections.Generic.List`1[System.Management.Automation.Job]
BeginTime     : 12/20/2018 18:59:57
EndTime       :
JobType       : BackgroundJob
Output        : System.Management.Automation.PSDataCollection`1[System.Management.Automation.PSObject]
Error         : System.Management.Automation.PSDataCollection`1[System.Management.Automation.ErrorRecord]
Progress      : System.Management.Automation.PSDataCollection`1[System.Management.Automation.ProgressRecord]
Verbose       : System.Management.Automation.PSDataCollection`1[System.Management.Automation.VerboseRecord]
Debug         : System.Management.Automation.PSDataCollection`1[System.Management.Automation.DebugRecord]
Warning       : System.Management.Automation.PSDataCollection`1[System.Management.Automation.WarningRecord]
Information   : System.Management.Automation.PSDataCollection`1[System.Management.Automation.InformationRecord]
```

Mit dem- `Start-Job` Cmdlet wird ein Hintergrund Auftrag gestartet, der ausführt `Get-Process` . Ein Auftrags Objekt wird an die Pipeline gesendet `ConvertTo-Csv` und in eine CSV-Zeichenfolge konvertiert. Der **notypeinformation** -Parameter entfernt den typinformations Header aus der CSV-Ausgabe und ist in PowerShell Core optional. Die- `$Header` Variable enthält einen benutzerdefinierten Header, der die folgenden Standardwerte ersetzt: **hasmoredata** , **Jobstatus Info** , **psbegintime** , **psendtime** und **psjobtykame**. Die `$J` -Variable enthält die CSV-Zeichenfolge und wird verwendet, um den Standard Header zu entfernen. Das `ConvertFrom-Csv` -Cmdlet konvertiert die CSV-Zeichenfolge in ein **pscustomobject-Objekt** und verwendet den **Header** -Parameter zum Anwenden der `$Header` Variablen.

### Beispiel 4: Konvertieren von CSV-Zeichen folgen von Dienst Objekten

In diesem Beispiel wird gezeigt, wie das `ConvertFrom-Csv` Cmdlet mit dem **useculture** -Parameter verwendet wird.

```powershell
(Get-Culture).TextInfo.ListSeparator
$Services = (Get-Service | ConvertTo-Csv)
ConvertFrom-Csv -InputObject $Services -UseCulture
```

Das `Get-Culture` Cmdlet verwendet die netsted-Eigenschaften **TextInfo** und **ListSeparator** , um das Standard Listen Trennzeichen der aktuellen Kultur zu erhalten. Das- `Get-Service` Cmdlet sendet Dienst Objekte über die Pipeline an `ConvertTo-Csv` . `ConvertTo-Csv`Konvertiert die Dienst Objekte in eine Reihe von CSV-Zeichen folgen. Die CSV-Zeichen folgen werden in der `$Services` Variablen gespeichert. Das `ConvertFrom-Csv` Cmdlet verwendet den **Inputobject** -Parameter und konvertiert die CSV-Zeichen folgen aus der `$Services` Variablen. Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur.

Wenn der **useculture** -Parameter verwendet wird, stellen Sie sicher, dass das Standard Listen Trennzeichen der aktuellen Kultur mit dem in den CSV-Zeichen folgen verwendeten Trennzeichen übereinstimmt. Andernfalls `ConvertFrom-Csv` können keine Objekte aus den CSV-Zeichen folgen generiert werden.

## PARAMETERS

### -Delimiter

Gibt das Trennzeichen an, das die Eigenschaftswerte in den CSV-Zeichenfolgen trennt.
Der Standardwert ist ein Komma (,).

Geben Sie ein Zeichen ein, z. B. einen Doppelpunkt (:).
So geben Sie ein Semikolon an (;) Schließen Sie Sie in einfache Anführungszeichen ein.

Wenn Sie ein anderes Zeichen als das tatsächliche Zeichen folgen Trennzeichen in der Datei angeben, `ConvertFrom-Csv` kann die Objekte nicht aus den CSV-Zeichen folgen erstellen und die CSV-Zeichen folgen zurückgeben.

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header

Gibt eine alternative Spaltenkopfzeile für die importierte Zeichenfolge an. Der Spaltenheader bestimmt die Eigenschaftsnamen der Objekte, die von erstellt werden `ConvertFrom-Csv` .

Geben Sie Spaltenüberschriften als durch Trennzeichen getrennte Liste ein. Die Kopfzeichenfolge darf nicht in Anführungszeichen eingeschlossen werden. Schließen Sie jeden Spaltenheader in einfache Anführungszeichen ein.

Wenn Sie weniger Spaltenüberschriften eingeben, als Datenspalten vorhanden sind, werden die restlichen Datenspalten verworfen. Wenn Sie mehr Spaltenüberschriften eingeben, als Datenspalten vorhanden sind, werden die zusätzlichen Spaltenüberschriften mit leeren Datenspalten erstellt.

Wenn Sie den **Header** -Parameter verwenden, lassen Sie die Spaltenheader Zeichenfolge aus den CSV-Zeichen folgen aus. Andernfalls erstellt dieses Cmdlet ein zusätzliches Objekt aus den Elementen in der Kopfzeile.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die CSV-Zeichenfolgen an, die in Objekte konvertiert werden sollen. Geben Sie eine Variable ein, die die CSV-Zeichenfolgen enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die CSV-Zeichenfolgen abgerufen werden. Sie können die CSV-Zeichen folgen auch über die Pipeline an senden `ConvertFrom-Csv` .

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Useculture

Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen. Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können CSV-Zeichen folgen an dieses Cmdlet übergeben.

## AUSGABEN

### System. Management. Automation. psobject

Dieses Cmdlet gibt die Objekte zurück, die von den Eigenschaften in den CSV-Zeichen folgen beschrieben werden.

## HINWEISE

Da die importierten Objekte CSV-Versionen des Objekt Typs sind, werden Sie von den PowerShell-typformatierungs Einträgen, die die nicht-CSV-Versionen des Objekt Typs formatieren, nicht erkannt und formatiert.

Im CSV-Format wird jedes Objekt durch eine durch Trennzeichen getrennte Liste der Eigenschaftswerte des Objekts dargestellt. Die Eigenschaftswerte werden in Zeichen folgen konvertiert (mithilfe der Methode "- **Zeichenfolge ()** " des-Objekts), sodass Sie durch den Namen des Eigenschafts Werts dargestellt werden. Dieses Cmdlet exportiert nicht die Methoden des Objekts.

## VERWANDTE LINKS

[ConvertTo-Csv](ConvertTo-Csv.md)

[Export-Csv](Export-Csv.md)

[Import-Csv](Import-Csv.md)

