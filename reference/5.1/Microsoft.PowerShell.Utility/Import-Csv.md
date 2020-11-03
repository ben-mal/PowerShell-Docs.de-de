---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Csv
ms.openlocfilehash: 6d060e0325ba10391f04348178f28b2793fe37fe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213884"
---
# Import-Csv

## ZUSAMMENFASSUNG
Erstellt Tabellen ähnliche benutzerdefinierte Objekte aus den Elementen in einer CSV-Datei (Comma-Separated Value, Komma getrennte Werte).

## SYNTAX

### Trennzeichen (Standard)

```
Import-Csv [[-Path] <string[]>] [[-Delimiter] <char>] [-LiteralPath <string[]>] [-Header <string[]>]
 [-Encoding <string>] [<CommonParameters>]
```

### UseCulture

```
Import-Csv [[-Path] <string[]>] -UseCulture [-LiteralPath <string[]>] [-Header <string[]>]
 [-Encoding <string>] [<CommonParameters>]
```

## DESCRIPTION

`Import-Csv`Mit dem-Cmdlet werden Tabellen ähnliche benutzerdefinierte Objekte aus den Elementen in CSV-Dateien erstellt. Jede Spalte in der CSV-Datei wird zu einer Eigenschaft des benutzerdefinierten Objekts, und die Elemente in den Zeilen werden zu den Eigenschafts Werten. `Import-Csv` funktioniert an allen CSV-Dateien, einschließlich Dateien, die vom `Export-Csv` Cmdlet generiert werden.

Mit den Parametern des `Import-Csv` Cmdlets können Sie die Spalten Kopfzeile und das Element Trennzeichen angeben oder direkt angeben, `Import-Csv` dass das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen verwendet werden soll.

Sie können auch die `ConvertTo-Csv` `ConvertFrom-Csv` Cmdlets und verwenden, um Objekte in CSV-Zeichen folgen (und zurück) zu konvertieren. Diese Cmdlets sind `Export-CSV` mit dem-Cmdlet und dem-Cmdlet identisch, mit dem Unterschied, `Import-Csv` dass Sie keine-Dateien behandeln.

Wenn ein Header Zeileneintrag in einer CSV-Datei einen leeren oder NULL-Wert enthält, fügt PowerShell einen Standard Header-Zeilen Namen ein und zeigt eine Warnmeldung an.

`Import-Csv` verwendet die Byte Reihenfolge-Markierung (BOM), um das Codierungsformat der Datei zu erkennen. Wenn die Datei keine BOM enthält, wird davon ausgegangen, dass die Codierung UTF8 ist.

## BEISPIELE

### Beispiel 1: Importieren von Prozess Objekten

Dieses Beispiel zeigt, wie Sie eine CSV-Datei mit Prozess Objekten exportieren und dann importieren.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv
$P = Import-Csv -Path .\Processes.csv
$P | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name                       MemberType   Definition
----                       ----------   ----------
Equals                     Method       bool Equals(System.Object obj)
GetHashCode                Method       int GetHashCode()
GetType                    Method       type GetType()
ToString                   Method       string ToString()
BasePriority               NoteProperty string BasePriority=8
Company                    NoteProperty string Company=Microsoft Corporation
...
```

```powershell
$P | Format-Table
```

```Output
Name                   SI Handles VM            WS        PM        NPM    Path
----                   -- ------- --            --        --        ---    ----
ApplicationFrameHost   4  407     2199293489152 15884288  15151104  23792  C:\WINDOWS\system32\ApplicationFrameHost.exe
...
wininit                0  157     2199112204288 4591616   1630208   10376
winlogon               4  233     2199125549056 7659520   2826240   10992  C:\WINDOWS\System32\WinLogon.exe
WinStore.App           4  846     873435136     33652736  26607616  55432  C:\Program Files\WindowsApps\Microsoft.WindowsStore_11712.1001.13.0_x64__8weky...
WmiPrvSE               0  201     2199100219392 8830976   3297280   10632  C:\WINDOWS\system32\wbem\wmiprvse.exe
WmiPrvSE               0  407     2199157727232 18509824  12922880  16624  C:\WINDOWS\system32\wbem\wmiprvse.exe
WUDFHost               0  834     2199310204928 51945472  87441408  24984  C:\Windows\System32\WUDFHost.exe
```

Das- `Get-Process` Cmdlet sendet Prozess Objekte über die Pipeline an den `Export-Csv` . Das `Export-Csv` Cmdlet konvertiert die Prozess Objekte in CSV-Zeichen folgen und speichert die Zeichen folgen in der Processes.csv Datei. Mit dem- `Import-Csv` Cmdlet werden die CSV-Zeichen folgen aus der Processes.csv Datei importiert.
Die Zeichen folgen werden in der `$P` Variablen gespeichert. Die `$P` Variable wird über die Pipeline an das `Get-Member` Cmdlet gesendet, das die Eigenschaften der importierten CSV-Zeichen folgen anzeigt. Die `$P` -Variable wird an das Cmdlet über die Pipeline gesendet `Format-Table` und zeigt die-Objekte an.

### Beispiel 2: Angeben des Trenn Zeichens

Dieses Beispiel zeigt die Verwendung des **Delimiter** -Parameters des `Import-Csv` Cmdlets.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter :
$P = Import-Csv -Path .\Processes.csv -Delimiter :
$P | Format-Table
```

Das- `Get-Process` Cmdlet sendet Prozess Objekte über die Pipeline an `Export-Csv` . Das `Export-Csv` Cmdlet konvertiert die Prozess Objekte in CSV-Zeichen folgen und speichert die Zeichen folgen in der Processes.csv Datei.
Der **Delimiter** -Parameter wird verwendet, um ein Doppelpunkt Trennzeichen anzugeben. Mit dem- `Import-Csv` Cmdlet werden die CSV-Zeichen folgen aus der Processes.csv Datei importiert. Die Zeichen folgen werden in der `$P` Variablen gespeichert. An `$P` Variable wird in der Pipeline an das `Format-Table` Cmdlet gesendet.

### Beispiel 3: Angeben der aktuellen Kultur für das Trennzeichen

In diesem Beispiel wird gezeigt, wie das `Import-Csv` Cmdlet mit dem **useculture** -Parameter verwendet wird.

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture
Import-Csv -Path .\Processes.csv -UseCulture
```

Das `Get-Culture` Cmdlet verwendet die netsted-Eigenschaften **TextInfo** und **ListSeparator** , um das Standard Listen Trennzeichen der aktuellen Kultur zu erhalten. Das- `Get-Process` Cmdlet sendet Prozess Objekte über die Pipeline an `Export-Csv` . Das `Export-Csv` Cmdlet konvertiert die Prozess Objekte in CSV-Zeichen folgen und speichert die Zeichen folgen in der Processes.csv Datei. Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur. Mit dem- `Import-Csv` Cmdlet werden die CSV-Zeichen folgen aus der Processes.csv Datei importiert.

### Beispiel 4: Ändern von Eigenschaftsnamen in einem importierten Objekt

In diesem Beispiel wird gezeigt, wie der- **Header** Parameter von verwendet wird `Import-Csv` , um die Namen von Eigenschaften im resultierenden importierten Objekt zu ändern.

```powershell
Start-Job -ScriptBlock { Get-Process } | Export-Csv -Path .\Jobs.csv -NoTypeInformation
$Header = 'State', 'MoreData', 'StatusMessage', 'Location', 'Command', 'StateInfo', 'Finished',
  'InstanceId', 'Id', 'Name', 'ChildJobs', 'BeginTime', 'EndTime', 'JobType', 'Output', 'Error',
  'Progress', 'Verbose', 'Debug', 'Warning', 'Information'
# Delete the default header from file
$A = Get-Content -Path .\Jobs.csv
$A = $A[1..($A.Count - 1)]
$A | Out-File -FilePath .\Jobs.csv
$J = Import-Csv -Path .\Jobs.csv -Header $Header
$J
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

Mit dem- `Start-Job` Cmdlet wird ein Hintergrund Auftrag gestartet, der ausführt `Get-Process` . Ein Auftrags Objekt wird in der Pipeline an das `Export-Csv` Cmdlet gesendet und in eine CSV-Zeichenfolge konvertiert. Der **notypeinformation** -Parameter entfernt den typinformations Header aus der CSV-Ausgabe und ist in PowerShell Core optional.
Die- `$Header` Variable enthält einen benutzerdefinierten Header, der die folgenden Standardwerte ersetzt: **hasmoredata** , **Jobstatus Info** , **psbegintime** , **psendtime** und **psjobtykame** . Die- `$A` Variable verwendet das- `Get-Content` Cmdlet, um die CSV-Zeichenfolge aus der Jobs.csv-Datei zu erhalten. Die- `$A` Variable wird verwendet, um den Standard Header aus der Datei zu entfernen. Das `Out-File` Cmdlet speichert die neue Version der Jobs.csv Datei in der `$A` Variablen. Das `Import-Csv` Cmdlet importiert die Jobs.csv Datei und verwendet den **Header** -Parameter, um die `$Header` Variable anzuwenden. Die `$J` Variable enthält das importierte **pscustomobject** und zeigt das Objekt in der PowerShell-Konsole an.

### Beispiel 5: Erstellen eines benutzerdefinierten Objekts mithilfe einer CSV-Datei

Dieses Beispiel zeigt, wie ein benutzerdefiniertes Objekt in PowerShell mithilfe einer CSV-Datei erstellt wird.

```powershell
Get-Content -Path .\Links.csv
```

```Output
113207,about_Aliases
113208,about_Arithmetic_Operators
113209,about_Arrays
113210,about_Assignment_Operators
113212,about_Automatic_Variables
113213,about_Break
113214,about_Command_Precedence
113215,about_Command_Syntax
144309,about_Comment_Based_Help
113216,about_CommonParameters
113217,about_Comparison_Operators
113218,about_Continue
113219,about_Core_Commands
113220,about_Data_Section
```

```powershell
$A = Import-Csv -Path .\Links.csv -Header 'LinkID', 'TopicTitle'
$A | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
LinkID      NoteProperty string LinkID=113207
TopicTitle  NoteProperty string TopicTitle=about_Aliases
```

```powershell
$A | Where-Object -Property TopicTitle -Like '*alias*'
```

```Output
LinkID TopicTitle
------ ----------
113207 about_Aliases
```

Verwenden Sie die Werte, die in der Ausgabe angezeigt werden, um die Links.csv-Datei zu erstellen `Get-Content` .

Das- `Get-Content` Cmdlet zeigt die Links.csv Datei an. Mit dem- `Import-Csv` Cmdlet wird die Links.csv Datei importiert. Der **Header** Parameter gibt die Eigenschaftsnamen " **linkid** " und " **topictitle** " an. Die-Objekte werden in der- `$A` Variable gespeichert. Mit dem- `Get-Member` Cmdlet werden die Eigenschaften Namen aus dem **Header** Parameter angezeigt. Das `Where-Object` Cmdlet wählt Objekte mit der **topictitle** -Eigenschaft aus, die den **Alias** enthält.

### Beispiel 6: Importieren eines CSV, dem ein Wert fehlt

Dieses Beispiel zeigt, wie das `Import-Csv` Cmdlet in PowerShell antwortet, wenn die Kopfzeile in einer CSV-Datei einen NULL-Wert oder einen leeren Wert enthält. `Import-Csv` ersetzt einen Standardnamen für die fehlende Kopfzeile, die zum Eigenschaftsnamen des Objekts wird, das `Import-Csv` zurückgibt.

```powershell
Get-Content -Path .\Projects.csv
```

```Output
ProjectID,ProjectName,,Completed
13,Inventory,Redmond,True
440,,FarEast,True
469,Marketing,Europe,False
```

```powershell
Import-Csv -Path .\Projects.csv
```

```Output
WARNING: One or more headers were not specified. Default names starting with "H" have been used in place of any missing headers.

ProjectID ProjectName H1      Completed
--------- ----------- --      ---------
13        Inventory   Redmond True
440                   FarEast True
469       Marketing   Europe  False
```

```powershell
(Import-Csv -Path .\Projects.csv).H1
```

```Output
WARNING: One or more headers were not specified. Default names starting with "H" have been used in place of any missing headers.
Redmond
FarEast
Europe
```

Verwenden Sie die Werte, die in der Ausgabe des Beispiels angezeigt werden, um die Projects.csv-Datei zu erstellen `Get-Content` .

Das- `Get-Content` Cmdlet zeigt die Projects.csv Datei an. In der Kopfzeile fehlt ein Wert zwischen " **ProjectName** " und " **abgeschlossen** ". Das `Import-Csv` Cmdlet importiert die Projects.csv Datei und zeigt eine Warnmeldung an, da **H1** ein Standard Header Name ist. Der `(Import-Csv -Path
.\Projects.csv).H1` Befehl ruft die **H1** -Eigenschaftswerte ab und zeigt eine Warnung an.

## PARAMETERS

### -Delimiter

Gibt das Trennzeichen für die Eigenschaftswerte in der CSV-Datei an.
Der Standardwert ist ein Komma (,).

Geben Sie ein Zeichen ein, z. B. einen Doppelpunkt (:).
So geben Sie ein Semikolon an (;) Schließen Sie Sie in einfache Anführungszeichen ein.

Wenn Sie ein anderes Zeichen als das tatsächliche Zeichen folgen Trennzeichen in der Datei angeben, `Import-Csv` kann die Objekte nicht aus den CSV-Zeichen folgen erstellen und die CSV-Zeichen folgen zurückgeben.

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

### -Codierung

Gibt den Typ der Codierung für die Zieldatei an. Der Standardwert ist `Default`.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- `ASCII` Verwendet den ASCII-Zeichensatz (7-Bit).
- `BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.
- `Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).
- `OEM` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.
- `Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.
- `UTF7` Verwendet UTF-7.
- `UTF8` Verwendet UTF-8.
- `UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header

Gibt eine alternative Spaltenkopfzeile für die importierte Datei an. Der Spaltenheader bestimmt die Eigenschaftsnamen der Objekte, die von erstellt werden `Import-Csv` .

Geben Sie Spaltenüberschriften als durch Trennzeichen getrennte Liste ein. Die Kopfzeichenfolge darf nicht in Anführungszeichen eingeschlossen werden. Schließen Sie jeden Spaltenheader in einfache Anführungszeichen ein.

Wenn Sie weniger Spaltenüberschriften eingeben, als Datenspalten vorhanden sind, werden die restlichen Datenspalten verworfen. Wenn Sie mehr Spaltenüberschriften eingeben, als Datenspalten vorhanden sind, werden die zusätzlichen Spaltenüberschriften mit leeren Datenspalten erstellt.

Wenn Sie den **Header** -Parameter verwenden, löschen Sie die ursprüngliche Kopfzeile aus der CSV-Datei. Andernfalls `Import-Csv` erstellt ein zusätzliches Objekt aus den Elementen in der Kopfzeile.

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

### -Literalpath

Gibt den Pfad zu der zu importierenden CSV-Datei an. Im Gegensatz zu **Path** wird der Wert des **LiteralPath** -Parameters genauso verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zu der zu importierenden CSV-Datei an.
Sie können einen Pfad auch über die Pipeline an übergeben `Import-Csv` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

Sie können eine Zeichenfolge über die Pipeline übergeben, die einen Pfad zu enthält `Import-Csv` .

## AUSGABEN

### Object

Dieses Cmdlet gibt die Objekte zurück, die durch den Inhalt in der CSV-Datei beschrieben werden.

## HINWEISE

Da die importierten Objekte CSV-Versionen des Objekt Typs sind, werden Sie von den PowerShell-typformatierungs Einträgen, die die nicht-CSV-Versionen des Objekt Typs formatieren, nicht erkannt und formatiert.

Das Ergebnis eines `Import-Csv` Befehls ist eine Auflistung von Zeichen folgen, die ein Tabellen ähnliches benutzerdefiniertes Objekt bilden. Jede Zeile ist eine separate Zeichenfolge, sodass Sie die **count** -Eigenschaft des Objekts verwenden können, um die Tabellenzeilen zu zählen. Die Spalten sind die Eigenschaften des Objekts, und die Elemente in den Zeilen sind die Eigenschaftswerte.

Die Spaltenkopfzeile bestimmt die Anzahl der Spalten und die Spaltennamen. Die Spaltennamen dienen auch als Namen der Objekteigenschaften . Die erste Zeile wird als Spalten Kopfzeile interpretiert, es sei denn, Sie verwenden den **Header** -Parameter, um Spaltenüberschriften anzugeben. Weist eine beliebige Zeile mehr Werte als die Kopfzeile auf, werden die zusätzlichen Werte ignoriert.

Wenn in der Spalten Kopfzeile ein Wert fehlt oder ein NULL-Wert oder ein leerer Wert enthalten ist, `Import-Csv` verwendet **H** , gefolgt von einer Zahl für den fehlenden Spaltenheader und den Eigenschaftsnamen.

In der CSV-Datei wird jedes Objekt durch eine durch Trennzeichen getrennte Liste der Eigenschaftswerte des Objekts dargestellt. Die Eigenschaftswerte werden mithilfe der Methode "- **Zeichenfolge ()** " des-Objekts in Zeichen folgen konvertiert, sodass Sie durch den Namen des Eigenschafts Werts dargestellt werden. `Export-Csv` exportiert nicht die Methoden des-Objekts.

## VERWANDTE LINKS

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[Export-Csv](Export-Csv.md)

[Get-Culture](Get-Culture.md)
