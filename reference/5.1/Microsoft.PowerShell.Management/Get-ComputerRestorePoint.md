---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerrestorepoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerRestorePoint
ms.openlocfilehash: 73819aafee9ed1911354daf9af23eedff0a3e14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215479"
---
# Get-ComputerRestorePoint

## ZUSAMMENFASSUNG
Ruft die Wiederherstellungspunkte auf dem lokalen Computer ab.

## SYNTAX

### ID (Standard)

```
Get-ComputerRestorePoint [[-RestorePoint] <Int32[]>] [<CommonParameters>]
```

### Last Status

```
Get-ComputerRestorePoint -LastStatus [<CommonParameters>]
```

## DESCRIPTION

Mit dem `Get-ComputerRestorePoint` -Cmdlet werden die System Wiederherstellungspunkte des lokalen Computers abgerufen. Außerdem kann der Status des letzten Versuchs zum Wiederherstellen des Computers angezeigt werden.

Mit den Informationen aus können Sie `Get-ComputerRestorePoint` einen Wiederherstellungspunkt auswählen. Verwenden Sie z. b. eine Sequenznummer, um einen Wiederherstellungspunkt für das `Restore-Computer` Cmdlet zu identifizieren.

System Wiederherstellungspunkte und das `Get-ComputerRestorePoint` Cmdlet werden nur unter Client Betriebssystemen wie Windows 10, Windows 7, Windows Vista und Windows XP unterstützt.

## BEISPIELE

### Beispiel 1: alle System Wiederherstellungspunkte

In diesem Beispiel werden `Get-ComputerRestorePoint` alle System Wiederherstellungspunkte des lokalen Computers abgerufen.

```powershell
Get-ComputerRestorePoint
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
8/7/2019  12:56:45     Installed PowerShell 6-x64     6                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

### Beispiel 2: beziehen bestimmter Sequenznummern

In diesem Beispiel werden System Wiederherstellungspunkte für bestimmte Sequenznummern abgerufen.

```powershell
Get-ComputerRestorePoint -RestorePoint 4, 5
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

`Get-ComputerRestorePoint` verwendet den **RestorePoint** -Parameter, um ein durch Trennzeichen getrenntes Array von Sequenznummern anzugeben.

### Beispiel 3: Anzeigen des Status einer Systemwiederherstellung

In diesem Beispiel wird der Status der letzten Systemwiederherstellung auf dem lokalen Computer angezeigt.

```powershell
Get-ComputerRestorePoint -LastStatus
```

```Output
The last attempt to restore the computer failed.
```

`Get-ComputerRestorePoint` verwendet den **laststatus** -Parameter, um das Ergebnis der letzten Systemwiederherstellung anzuzeigen.

### Beispiel 4: Verwenden eines Ausdrucks zum Konvertieren der "comationtime"

`Get-ComputerRestorePoint` Gibt die **Zeichen** Folge "" als Windows-Verwaltungsinstrumentation (WMI)-Datums-und Uhrzeitangabe aus.

In diesem Beispiel speichert eine Variable einen Ausdruck, der die Zeichenfolge " **comationtime** " in ein **DateTime** -Objekt konvertiert. Verwenden Sie einen Befehl wie, um die vor der Konvertierung verwendeten Zeichen folgen vor dem **konvertieren anzuzeigen** `((Get-ComputerRestorePoint).CreationTime)` . Weitere Informationen zur Datums-und Uhrzeit Zeichenfolge von WMI finden Sie unter [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).

```powershell
$date = @{Label="Date"; Expression={$_.ConvertToDateTime($_.CreationTime)}}
Get-ComputerRestorePoint | Select-Object -Property SequenceNumber, $date, Description
```

```Output
SequenceNumber   Date                 Description
--------------   ----                 -----------
             4   7/30/2019 09:17:24   Windows Update
             5   8/5/2019  08:15:37   Installed PowerShell 7-preview-x64
             6   8/7/2019  12:56:45   Installed PowerShell 6-x64
```

Die `$date` Variable speichert eine Hash Tabelle mit dem Ausdruck, der die **ConvertTo DateTime** -Methode verwendet. Der Ausdruck konvertiert den Wert der Eigenschaft " **kreationtime** " aus einer WMI-Zeichenfolge in ein **DateTime** -Objekt.

`Get-ComputerRestorePoint` sendet die Systemwiederherstellungspunkt Objekte über die Pipeline. `Select-Object` verwendet den **Property** -Parameter, um die anzuzeigenden Eigenschaften anzugeben. Für jedes Objekt in der Pipeline konvertiert der Ausdruck in `$date` die " **deationtime** " und gibt das Ergebnis in der **Date** -Eigenschaft aus.

### Beispiel 5: Verwenden einer Eigenschaft zum erhalten einer Sequenznummer

In diesem Beispiel wird eine Sequenznummer abgerufen, indem die **sequencenumschlag** -Eigenschaft und ein Array Index verwendet werden. Die Ausgabe enthält nur die Sequenznummer.

```powershell
((Get-ComputerRestorePoint).SequenceNumber)[-1]
```

```Output
6
```

`Get-ComputerRestorePoint` verwendet die **sequencenumschlag** -Eigenschaft mit einem Array Index. Der Array Index von ruft `-1` die letzte Sequenznummer im Array ab.

## PARAMETERS

### -Laststatus

Gibt an, dass `Get-ComputerRestorePoint` den Status des letzten System Wiederherstellungs Vorgangs abruft.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LastStatus
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestorePoint

Gibt die Sequenznummern der System Wiederherstellungspunkte an. Sie können entweder eine einzelne Sequenznummer oder ein durch Trennzeichen getrenntes Array von Sequenznummern angeben.

Wenn der **RestorePoint** -Parameter nicht angegeben wird, werden `Get-ComputerRestorePoint` von alle System Wiederherstellungspunkte des lokalen Computers zurückgegeben.

```yaml
Type: System.Int32[]
Parameter Sets: ID
Aliases:

Required: False
Position: 0
Default value: All restore points
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Objekte können nicht über die Pipeline an gesendet werden `Get-ComputerRestorePoint` .

## AUSGABEN

### System. Management. ManagementObject # root\default\systemrestore oder String

`Get-ComputerRestorePoint` Gibt ein **SystemRestore** -Objekt zurück, das eine Instanz der Windows-Verwaltungsinstrumentation (WMI) **SystemRestore** -Klasse ist.

Wenn Sie den **laststatus** -Parameter verwenden, wird `Get-ComputerRestorePoint` eine Zeichenfolge zurückgegeben.

## HINWEISE

Wenn Sie einen `Get-ComputerRestorePoint` Befehl unter Windows Vista und höheren Versionen von Windows ausführen möchten, öffnen Sie PowerShell mit der Option **als Administrator ausführen** .

`Get-ComputerRestorePoint` verwendet die WMI **SystemRestore** -Klasse.

## VERWANDTE LINKS

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[about_Arrays](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[SystemRestore](/windows/win32/sr/systemrestore)
