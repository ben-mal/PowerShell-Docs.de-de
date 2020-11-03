---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/sort-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sort-Object
ms.openlocfilehash: ad546ee4dddac112e76903c28687f2ee974f06a7
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219279"
---
# Sort-Object

## ZUSAMMENFASSUNG
Sortiert Objekte nach Eigenschaftenwerten.

## SYNTAX

### Standard (Standard)

```
Sort-Object [-Stable] [-Descending] [-Unique] [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

### TOP

```
Sort-Object [-Descending] [-Unique] -Top <Int32> [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

### bottom

```
Sort-Object [-Descending] [-Unique] -Bottom <Int32> [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## DESCRIPTION

Das- `Sort-Object` Cmdlet sortiert Objekte in aufsteigender oder absteigender Reihenfolge basierend auf Objekt Eigenschafts Werten. Wenn Sortier Eigenschaften nicht in einem Befehl enthalten sind, verwendet PowerShell die Standard Sortier Eigenschaften des ersten Eingabe Objekts. Wenn der Typ des Eingabe Objekts keine Standard Sortier Eigenschaften aufweist, versucht PowerShell, die Objekte selbst zu vergleichen. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#notes) ".

Objekte können nach einer einzelnen Eigenschaft oder mehreren Eigenschaften sortiert werden. Mehrere Eigenschaften verwenden Hash Tabellen zum Sortieren in aufsteigender Reihenfolge, absteigender Reihenfolge oder in einer Kombination aus Sortier Reihenfolgen. Eigenschaften werden nach Groß-/Kleinschreibung oder Groß-/Kleinschreibung unterschieden. Verwenden Sie den **Unique** -Parameter, um Duplikate aus der Ausgabe zu entfernen.

## BEISPIELE

### Beispiel 1: Sortieren des aktuellen Verzeichnisses nach Name

In diesem Beispiel werden die Dateien und Unterverzeichnisse in einem Verzeichnis sortiert.

```
PS> Get-ChildItem -Path C:\Test | Sort-Object

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
d-----        2/25/2019     18:25                Files
d-----        2/25/2019     18:24                Logs
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
```

`Get-ChildItem`Mit dem-Cmdlet werden die Dateien und Unterverzeichnisse aus dem Verzeichnis abgerufen, das durch den **path** -Parameter **c:\test** angegeben wird. Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.
`Sort-Object` gibt keine Eigenschaft an, sodass die Ausgabe nach der Standard Sortier Eigenschaft " **Name** " sortiert wird.

### Beispiel 2: Sortieren des aktuellen Verzeichnisses nach Dateilänge

Mit diesem Befehl werden die Dateien im aktuellen Verzeichnis nach Länge in aufsteigender Reihenfolge angezeigt.

```
PS> Get-ChildItem -Path C:\Test -File | Sort-Object -Property Length

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
-a----        2/13/2019     08:55             26 anotherfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-a----        2/12/2019     15:40         118014 Command.txt
```

Mit dem- `Get-ChildItem` Cmdlet werden die Dateien aus dem Verzeichnis abgerufen, das durch den **path** -Parameter angegeben wird.
Der **File** -Parameter gibt an, dass `Get-ChildItem` nur Datei Objekte abruft. Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet. `Sort-Object` verwendet den **length** -Parameter, um die Dateien nach Länge in aufsteigender Reihenfolge zu sortieren.

### Beispiel 3: Sortieren von Prozessen nach Speicherauslastung

In diesem Beispiel werden Prozesse mit der höchsten Speicherauslastung basierend auf der Größe Ihres Arbeits Satzes (WS) angezeigt.

```
PS> Get-Process | Sort-Object -Property WS | Select-Object -Last 5

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    136   193.92     217.11     889.16   87492   8 OUTLOOK
    112   347.73     297.02      95.19  106908   8 Teams
    206   266.54     323.71      37.17   60620   8 MicrosoftEdgeCP
     35   552.19     549.94     131.66    6552   8 Code
      0     1.43     595.12       0.00    2780   0 Memory Compression
```

Mit dem- `Get-Process` Cmdlet wird die Liste der Prozesse abgerufen, die auf dem Computer ausgeführt werden. Die Prozess Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet. `Sort-Object` verwendet den **Property** -Parameter, um die Objekte nach **WS** zu sortieren. Die Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.
`Select-Object` verwendet den **letzten** Parameter, um die letzten fünf Objekte anzugeben, die Objekte mit der höchsten **WS** -Verwendung sind.

In PowerShell 6 ist der- `Sort-Object` Parameter **unten** eine Alternative zu `Select-Object` . Beispiel: `Get-Process | Sort-Object -Property WS -Bottom 5`.

### Beispiel 4: Sortieren von historyinfo-Objekten nach ID

Mit diesem Befehl werden die **historyinfo** -Objekte der PowerShell-Sitzung mithilfe der **ID** -Eigenschaft sortiert. Jede PowerShell-Sitzung verfügt über einen eigenen Befehlsverlauf.

```
PS> Get-History | Sort-Object -Property Id -Descending

  Id CommandLine
  -- -----------
  10 Get-Command Sort-Object -Syntax
   9 $PSVersionTable
   8 Get-Command Sort-Object -Syntax
   7 Get-Command Sort-Object -ShowCommandInfo
   6 Get-ChildItem -Path C:\Test | Sort-Object -Property Length
   5 Get-Help Clear-History -online
   4 Get-Help Clear-History -full
   3 Get-ChildItem | Get-Member
   2 Get-Command Sort-Object -Syntax
   1 Set-Location C:\Test\
```

Mit dem- `Get-History` Cmdlet werden die Verlaufs Objekte aus der aktuellen PowerShell-Sitzung abgerufen. Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet. `Sort-Object` verwendet den **Property** -Parameter, um die Objekte nach **ID** zu sortieren. Der **Absteig** Ende Parameter sortiert den Befehlsverlauf vom neuesten zum ältesten.

### Beispiel 5: Verwenden einer Hash Tabelle zum Sortieren von Eigenschaften in aufsteigender und absteigender Reihenfolge

In diesem Beispiel werden zwei Eigenschaften verwendet, um die Objekte " **Status** " und " **Display Name** " zu sortieren. Der **Status** wird in absteigender Reihenfolge sortiert, und **Display Name** wird in aufsteigender Reihenfolge sortiert.

Eine Hash Tabelle wird verwendet, um den Wert des **Eigenschafts** Parameters anzugeben. Die Hash Tabelle verwendet einen Ausdruck, um die Eigenschaften Namen und die Sortierreihenfolge anzugeben. Weitere Informationen zu Hashtabellen finden Sie unter [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md) (Informationen zu Hashtabellen).

Die in der Hash Tabelle verwendete **Status** Eigenschaft ist eine enumerierte Eigenschaft.
Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

```
PS C:\> Get-Service | Sort-Object -Property @{Expression = "Status"; Descending = $True}, @{Expression = "DisplayName"; Descending = $False}

Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  BthAvctpSvc        AVCTP service
Running  BrokerInfrastru... Background Tasks Infrastructure Ser...
Running  BDESVC             BitLocker Drive Encryption Service
Running  CoreMessagingRe... CoreMessaging
Running  VaultSvc           Credential Manager
Running  DsSvc              Data Sharing Service
Running  Dhcp               DHCP Client
...
Stopped  ALG                Application Layer Gateway Service
Stopped  AppMgmt            Application Management
Stopped  BITS               Background Intelligent Transfer Ser...
Stopped  wbengine           Block Level Backup Engine Service
Stopped  BluetoothUserSe... Bluetooth User Support Service_14fb...
Stopped  COMSysApp          COM+ System Application
Stopped  smstsmgr           ConfigMgr Task Sequence Agent
Stopped  DeviceInstall      Device Install Service
Stopped  MSDTC              Distributed Transaction Coordinator
```

Mit dem- `Get-Service` Cmdlet wird die Liste der Dienste auf dem Computer abgerufen. Die Dienst Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet. `Sort-Object` verwendet den **Property** -Parameter mit einer Hash Tabelle, um die Eigenschaften Namen und die Sortierreihenfolge anzugeben. Der **Property** -Parameter wird nach zwei Eigenschaften sortiert: **Status** in absteigender Reihenfolge und **Display Name** in aufsteigender Reihenfolge.

Der **Status** ist eine aufgezählte Eigenschaft. " **Beendet** " hat den Wert " **1** " und "wird **ausgeführt** " den Wert **4**. Der **Absteig** Ende Parameter ist auf festgelegt `$True` , sodass ausgestellte **Stopped** Prozesse vor beendeten Prozessen angezeigt werden. **Running** **Display Name** legt den **Absteig** enden Parameter auf fest `$False` , um die anzeigen Amen in alphabetischer Reihenfolge zu sortieren.

### Beispiel 6: Sortieren von Textdateien nach Zeitspanne

Dieser Befehl sortiert Textdateien in absteigender Reihenfolge nach der Zeitspanne zwischen " **comationtime** " und " **lastschreitetime** ".

```
PS> Get-ChildItem -Path C:\Test\*.txt | Sort-Object -Property @{Expression = {$_.CreationTime - $_.LastWriteTime}; Descending = $False} | Format-Table CreationTime, LastWriteTime, FullName

CreationTime          LastWriteTime        FullName
------------          -------------        --------
11/21/2018 12:39:01   2/26/2019 08:59:36   C:\Test\test2.txt
12/4/2018 08:29:41    2/26/2019 08:57:05   C:\Test\powershell_list.txt
2/20/2019 08:15:59    2/26/2019 12:09:43   C:\Test\CreateTestFile.txt
2/20/2019 08:15:59    2/26/2019 12:07:41   C:\Test\Command.txt
2/20/2019 08:15:59    2/26/2019 08:57:52   C:\Test\ReadOnlyFile.txt
11/29/2018 15:16:50   12/4/2018 16:16:24   C:\Test\LogData.txt
2/25/2019 18:25:11    2/26/2019 12:08:47   C:\Test\Zsystemlog.txt
2/25/2019 18:25:11    2/26/2019 08:55:33   C:\Test\Bfile.txt
2/26/2019 08:46:59    2/26/2019 12:12:19   C:\Test\LogFile3.txt
```

Das `Get-ChildItem` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis **c:\test** und alle `*.txt` Dateien anzugeben. Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.
`Sort-Object` verwendet den **Property** -Parameter mit einer Hash Tabelle, um die Zeitspanne zwischen " **comationtime** " und " **LastWrite-Time** " zu bestimmen. Der **Absteig** Ende Parameter ist auf festgelegt, um `$False` in der Reihenfolge der längsten bis zum kürzesten Zeitspanne zu sortieren.

### Beispiel 7: Sortieren von Namen in einer Textdatei

In diesem Beispiel wird gezeigt, wie eine Liste aus einer Textdatei sortiert wird. Die ursprüngliche Datei wird als unsortierte Liste angezeigt. `Sort-Object` sortiert den Inhalt und sortiert dann den Inhalt mit dem **eindeutigen** Parameter, der Duplikate entfernt.

```
PS> Get-Content -Path C:\Test\ServerNames.txt
localhost
server01
server25
LOCALHOST
Server19
server3
localhost

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object
localhost
LOCALHOST
localhost
server01
Server19
server25
server3

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object -Unique
localhost
server01
Server19
server25
server3
```

Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis und den Dateinamen anzugeben. Die Datei **ServerNames.txt** enthält eine unsortierte Liste mit Computernamen.

Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis und den Dateinamen anzugeben. Die Datei **ServerNames.txt** enthält eine unsortierte Liste mit Computernamen. Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet. `Sort-Object` sortiert die Liste in der Standard Reihenfolge aufsteigend.

Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um das Verzeichnis und den Dateinamen anzugeben. Die Datei **ServerNames.txt** enthält eine unsortierte Liste mit Computernamen. Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet. `Sort-Object` verwendet den **Unique** -Parameter, um doppelte Computernamen zu entfernen. Die Liste wird in der Standard Reihenfolge aufsteigend sortiert.

### Beispiel 8: Sortieren einer Zeichenfolge als ganze Zahl

In diesem Beispiel wird gezeigt, wie eine Textdatei, die Zeichen folgen Objekte enthält, als ganze Zahlen sortiert wird. Sie können jeden Befehl über die Pipeline an senden `Get-Member` und überprüfen, ob es sich bei den Objekten um Zeichen folgen anstelle von ganzen Zahlen handelt. In diesen Beispielen enthält die `ProductId.txt` Datei eine unsortierte Liste mit Produktnummern.

Im ersten Beispiel `Get-Content` wird der Inhalt der Datei abgerufen und Zeilen an das `Sort-Object` Cmdlet weitergeleitet. `Sort-Object` sortiert die Zeichen folgen Objekte in aufsteigender Reihenfolge.

```
PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object
0
1
12345
1500
2
2800
3500
4100
500
6200
77
88
99999

PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object {[int]$_}
0
1
2
77
88
500
1500
2800
3500
4100
6200
12345
99999
```

Im zweiten Beispiel `Get-Content` wird der Inhalt der Datei abgerufen und Zeilen an das `Sort-Object` Cmdlet weitergeleitet. `Sort-Object` verwendet einen Skriptblock, um die Zeichen folgen in ganze Zahlen zu konvertieren. Im Beispielcode `[int]` konvertiert die Zeichenfolge in eine ganze Zahl und `$_` stellt jede Zeichenfolge dar, wenn Sie in der Pipeline angezeigt wird. Die ganzzahligen Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet.
`Sort-Object` sortiert die ganzzahligen Objekte in numerischer Reihenfolge.

### Beispiel 9: verwenden stabiler Sortierungen

Wenn Sie die Parameter **Top** , **Bottom** oder **stable** verwenden, werden die sortierten Objekte in der Reihenfolge zugestellt, in der Sie empfangen wurden, `Sort-Object` Wenn die Sortierkriterien gleich sind. In diesem Beispiel sortieren wir die Zahlen 1 bis 20 durch den Wert "Modulo 3". Der Modulo-Wert liegt zwischen 0 und 2.

```powershell
PS> 1..20 |Sort-Object {$_ % 3}
18
3
15
6
12
9
1
16
13
10
7
4
19
11
8
14
5
17
2
20

PS> 1..20 |Sort-Object {$_ % 3} -Stable
3
6
9
12
15
18
1
4
7
10
13
16
19
2
5
8
11
14
17
20
```

Die Ausgabe der ersten Sortierung ist ordnungsgemäß nach dem Modulo-Wert gruppiert, aber die einzelnen Elemente werden nicht innerhalb des Modulo Bereichs sortiert. Die zweite Sortierung verwendet die Option **stable** , um eine stabile Sortierung zurückzugeben.

## PARAMETERS

### -Unten

Gibt die Anzahl der Objekte an, die vom Ende eines sortierten Objekt Arrays abgeleitet werden sollen. Dies führt zu einer stabilen Sortierung.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: Bottom
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CaseSensitive

Gibt an, dass die Sortierung die Groß-/Kleinschreibung beachtet. Standardmäßig wird bei Sortierungen die Groß-/Kleinschreibung nicht beachtet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Case-insensitive
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kultur

Gibt die Kultur Konfiguration an, die für Sortiervorgänge verwendet werden soll. Verwenden `Get-Culture` Sie, um die Kultur Konfiguration des Systems anzuzeigen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Absteigend

Gibt an, dass `Sort-Object` die Objekte in absteigender Reihenfolge sortiert. Standardmäßig wird in aufsteigender Reihenfolge sortiert.

Wenn Sie mehrere Eigenschaften mit unterschiedlichen Sortier Reihenfolgen sortieren möchten, verwenden Sie eine Hash Tabelle. Beispielsweise können Sie mit einer Hash Tabelle eine Eigenschaft in aufsteigender Reihenfolge und eine andere Eigenschaft in absteigender Reihenfolge sortieren.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Ascending
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Um Objekte zu sortieren, senden Sie Sie über die Pipeline an `Sort-Object` . Wenn Sie den **Inputobject** -Parameter verwenden, um eine Auflistung von Elementen zu senden, `Sort-Object` empfängt ein Objekt, das die Auflistung darstellt. Da ein Objekt nicht sortiert werden kann, `Sort-Object` gibt die gesamte Auflistung unverändert zurück.

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

### -Eigenschaft

Gibt die Eigenschaftsnamen `Sort-Object` an, die von zum Sortieren der Objekte verwendet werden. Platzhalter sind zulässig.
Objekte werden basierend auf den Eigenschafts Werten sortiert. Wenn Sie keine Eigenschaft angeben, sortiert nach `Sort-Object` den Standardeigenschaften für den Objekttyp oder die Objekte.

Mehrere Eigenschaften können in aufsteigender Reihenfolge, absteigender Reihenfolge oder in einer Kombination aus Sortier Reihenfolgen sortiert werden. Wenn Sie mehrere Eigenschaften angeben, werden die Objekte nach der ersten Eigenschaft sortiert. Wenn mehrere Objekte denselben Wert für die erste Eigenschaft aufweisen, werden diese Objekte nach der zweiten Eigenschaft sortiert. Dieser Prozess wird fortgesetzt, bis keine weiteren angegebenen Eigenschaften oder keine Gruppen von Objekten mehr vorhanden sind.

Der Wert des **Property** -Parameters kann eine berechnete Eigenschaft sein. Zum Erstellen einer berechneten Eigenschaft verwenden Sie eine Hashtabelle.

Gültige Schlüssel für eine Hash Tabelle sind:

- `expression` - `<string>` oder `<script block>`
- `ascending` noch `descending` - `<boolean>`

Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: Default properties
Accept pipeline input: False
Accept wildcard characters: True
```

### -Top

Gibt die Anzahl der Objekte an, die vom Anfang eines sortierten Objekt Arrays abzurufenden werden. Dies führt zu einer stabilen Sortierung.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: Top
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Eindeutig

Gibt an, dass `Sort-Object` Duplikate entfernt und nur die eindeutigen Member der Auflistung zurückgibt. Die erste Instanz eines eindeutigen Werts ist in der sortierten Ausgabe enthalten.

Bei **Unique** wird Groß-/Kleinschreibung nicht beachtet Zeichen folgen, die sich nur durch Zeichen Fälle unterscheiden, werden als identisch betrachtet.
Beispielsweise Zeichen und Zeichen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stabil

Die sortierten Objekte werden in der Reihenfolge zugestellt, in der Sie empfangen wurden, wenn die Sortierkriterien gleich sind.

Dieser Parameter wurde in PowerShell v 6.2.0 hinzugefügt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
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

### System. Management. Automation. psobject

Sie können die zu sortierenden Objekte über die Pipeline übergeben `Sort-Object` .

## AUSGABEN

### System. Management. Automation. psobject

`Sort-Object` Gibt die sortierten Objekte zurück.

## HINWEISE

Das- `Sort-Object` Cmdlet sortiert Objekte auf der Grundlage der im-Befehl angegebenen Eigenschaften oder der Standard Sortierungs Eigenschaften für den Objekttyp. Standard Sortier Eigenschaften werden mit dem `PropertySet` benannten `DefaultKeyPropertySet` in einer `types.ps1xml` Datei definiert. Weitere Informationen finden Sie unter [about_Types.ps1XML](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).

Wenn ein Objekt keine der angegebenen Eigenschaften aufweist, wird der Eigenschafts Wert für dieses Objekt von `Sort-Object` als **null** interpretiert und am Ende der Sortierreihenfolge platziert.

Wenn keine Sortier Eigenschaften verfügbar sind, versucht PowerShell, die Objekte selbst zu vergleichen.
`Sort-Object` verwendet die **Compare** -Methode für jede Eigenschaft. Wenn eine Eigenschaft **ivergleichbare** nicht implementiert, konvertiert das Cmdlet den Eigenschafts Wert in eine Zeichenfolge und verwendet die **Compare** -Methode für **System. String**. Weitere Informationen finden Sie unter [psobject. CompareTo (Object)-Methode](/dotnet/api/system.management.automation.psobject.compareto).

Wenn Sie nach einer enumerierten Eigenschaft wie dem **Status** sortieren, `Sort-Object` sortiert nach den Enumerationswerten. Für Windows-Dienste hat " **beendet** " den Wert **1** und "wird **ausgeführt** " den Wert **4**.
" **Beendet** " wird vor dem **Ausführen** aufgrund der aufgelisteten Werte sortiert. Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

Die Leistung des Sortieralgorithmus ist langsamer, wenn ein stabiler Sortiervorgang durchgeführt wird.

## VERWANDTE LINKS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Tee-Object](Tee-Object.md)
