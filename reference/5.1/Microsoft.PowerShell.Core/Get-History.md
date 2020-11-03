---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-history?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-History
ms.openlocfilehash: ae9cc8b0daf9a3c25d4385fbca156e8a146334da
ms.sourcegitcommit: 1695df0d241c0390cac71a7401e61198fc6ff756
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "93220156"
---
# Get-History

## ZUSAMMENFASSUNG
Ruft eine Liste der Befehle ab, die während der aktuellen Sitzung eingegeben wurden.

## SYNTAX

```
Get-History [[-Id] <Int64[]>] [[-Count] <Int32>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-History` Cmdlet wird der Sitzungsverlauf abgerufen, d. h. die Liste der Befehle, die während der aktuellen Sitzung eingegeben wurden.

PowerShell verwaltet automatisch einen Verlauf jeder Sitzung. Die Anzahl von Einträgen im Sitzungsverlauf wird durch den Wert der `$MaximumHistoryCount` Preference-Variablen bestimmt. Ab Windows PowerShell 3,0 lautet der Standardwert `4096` . Standardmäßig werden Verlaufsdateien im Basisverzeichnis gespeichert, Sie können die Datei jedoch an einem beliebigen Speicherort speichern. Weitere Informationen zu den Verlaufs Funktionen in PowerShell finden Sie unter [about_History](About/about_History.md).

Der Sitzungsverlauf wird getrennt von dem vom **psread Line** -Modul verwalteten Verlauf verwaltet.
Beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird. Dieses Cmdlet funktioniert nur mit dem Sitzungsverlauf. Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## BEISPIELE

### Beispiel 1: Get the Session History

In diesem Beispiel werden die Einträge im Sitzungsverlauf abgerufen. Die Standard Anzeige zeigt jeden Befehl und seine ID an, der die Reihenfolge angibt, in der Sie ausgeführt wurden.

```powershell
Get-History
```

### Beispiel 2: Get-Einträge, die eine Zeichenfolge enthalten

In diesem Beispiel werden Einträge im Befehlsverlauf abgerufen, die den Zeichen folgen Dienst einschließen. Der erste Befehl ruft alle Einträge im Sitzungsverlauf ab. Der Pipeline Operator ( `|` ) übergibt die Ergebnisse an das `Where-Object` Cmdlet, das nur die Befehle auswählt, die den Dienst einschließen.

```powershell
Get-History | Where-Object {$_.CommandLine -like "*Service*"}
```

### Beispiel 3: Exportieren von Verlaufs Einträgen bis zu einer bestimmten ID

In diesem Beispiel werden die fünf letzten Verlaufs Einträge abgerufen, die mit dem Eintrag 7 enden. Der Pipeline Operator übergibt das Ergebnis an das `Export-Csv` Cmdlet, das den Verlauf als durch Trennzeichen getrennten Text formatiert und in der History.csv-Datei speichert. Die Datei enthält die Daten, die beim Formatieren des Verlaufs als Liste angezeigt werden. Dies schließt den Status und die Start-und Endzeit des Befehls ein.

```powershell
Get-History -ID 7 -Count 5 | Export-Csv History.csv
```

### Beispiel 4: Anzeigen des neuesten Befehls

In diesem Beispiel wird der letzte Befehl im Befehlsverlauf abgerufen. Der letzte Befehl ist der zuletzt eingegebene Befehl. Dieser Befehl verwendet den **count** -Parameter, um nur einen Befehl anzuzeigen. Standardmäßig ruft `Get-History` die neuesten Befehle ab. Dieser Befehl kann mit „h -c 1“ abgekürzt werden und entspricht dem Drücken der NACH-OBEN-TASTE.

```powershell
Get-History -Count 1
```

### Beispiel 5: Anzeigen aller Eigenschaften der Einträge im Verlauf

In diesem Beispiel werden alle Eigenschaften von Einträgen im Sitzungsverlauf angezeigt. Der Pipeline Operator übergibt die Ergebnisse eines `Get-History` Befehls an das `Format-List` Cmdlet, das alle Eigenschaften jedes Verlaufs Eintrags anzeigt. Dies schließt die ID, den Status und die Start-und Endzeiten des Befehls ein.

```powershell
Get-History | Format-List -Property *
```

## PARAMETERS

### -Anzahl

Gibt die Anzahl der letzten Verlaufs Einträge an, die von diesem Cmdlet abgerufen werden. Standardmäßig ruft `Get-History` alle Einträge im Sitzungsverlauf ab. Wenn Sie sowohl den **Count** - als auch den **Id** -Parameter in einem Befehl verwenden, endet die Anzeige mit dem Befehl, der vom **Id** -Parameter angegeben wird.

In Windows PowerShell 2,0 werden standardmäßig `Get-History` die letzten 32 Einträge abgerufen.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Gibt ein Array der IDs von Einträgen im Sitzungsverlauf an. `Get-History` Ruft nur angegebene Einträge ab. Wenn Sie in einem Befehl sowohl den **ID** -als auch den **count** -Parameter verwenden, ruft `Get-History` die letzten Einträge ab, die mit dem durch den **ID** -Parameter angegebenen Eintrag enden.

```yaml
Type: System.Int64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.Int64

Sie können eine Verlaufs-ID an dieses Cmdlet weiterreichen.

## AUSGABEN

### Microsoft. PowerShell. Commands. historyinfo

Dieses Cmdlet gibt ein Verlaufs Objekt für jedes Verlaufs Element zurück, das es abruft.

## HINWEISE

Der Sitzungsverlauf ist eine Liste der Befehle, die während der Sitzung eingegeben wurden. Der Sitzungsverlauf stellt die Reihenfolge, den Status und die Start-und Endzeiten des Befehls dar. Wenn Sie jeden Befehl eingeben, wird er von PowerShell dem Verlauf hinzugefügt, damit Sie ihn wieder verwenden können. Weitere Informationen zum Befehlsverlauf finden Sie unter [about_History](About/about_History.md).

Ab Windows PowerShell 3,0 lautet der Standardwert der Einstellungs `$MaximumHistoryCount` Variablen `4096` . In Windows PowerShell 2,0 ist der Standardwert `64` . Weitere Informationen zur- `$MaximumHistoryCount` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).

## VERWANDTE LINKS

[Add-History](Add-History.md)

[Clear-History](Clear-History.md)

[Invoke-History](Invoke-History.md)

[about_History](About/about_History.md)
