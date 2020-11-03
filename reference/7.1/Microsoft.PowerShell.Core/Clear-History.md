---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-history?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-History
ms.openlocfilehash: c159262b21e39965f32db4a0fa736aa70de8e916
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211655"
---
# Clear-History

## ZUSAMMENFASSUNG
Löscht Einträge aus dem PowerShell-Sitzungs Befehlsverlauf.

## SYNTAX

### IDParameter (Standard)

```
Clear-History [[-Id] <int[]>] [[-Count] <int>] [-Newest] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Commandlineparameter

```
Clear-History [[-Count] <int>] [-CommandLine <string[]>] [-Newest] [-WhatIf] [-Confirm]
[<CommonParameters>]
```

## DESCRIPTION

`Clear-History` Löscht den Befehlsverlauf aus einer PowerShell-Sitzung. Jede PowerShell-Sitzung verfügt über einen eigenen Befehlsverlauf. Verwenden Sie das-Cmdlet, um den Befehlsverlauf anzuzeigen `Get-History` .

Standardmäßig wird `Clear-History` der gesamte Befehlsverlauf aus einer PowerShell-Sitzung gelöscht. Sie können Parameter mit verwenden `Clear-History` , um ausgewählte Befehle zu löschen.

`Clear-History` Löscht die Befehls Verlaufs `PSReadLine` Datei nicht. Das `PSReadLine` Modul speichert eine Verlaufs Datei, die jeden PowerShell-Befehl in jeder PowerShell-Sitzung enthält. Verwenden Sie an einer PowerShell-Eingabeaufforderung die Pfeile nach oben und nach unten auf der Tastatur, um durch den Befehlsverlauf zu scrollen. Verwenden Sie, um die `PSReadLine` Konfiguration für den Befehlsverlauf anzuzeigen `Get-PSReadLineOption` .
`PSReadLine` ausgeliefert mit PowerShell 5,0 und höher. Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## BEISPIELE

### Beispiel 1: Löschen des Befehls Verlaufs aus einer PowerShell-Sitzung

Dieser Befehl löscht alle Befehle aus dem Verlauf einer PowerShell-Sitzung.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location .\Test
   2 Update-Help
   3 Set-Location C:\Test\Logs
   4 Get-Location
```

```powershell
Clear-History
Get-History
```

```Output
  Id CommandLine
  -- -----------
   5 Clear-History
```

Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an. `Clear-History` Löscht den gesamten Befehlsverlauf. `Get-History` zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass der vorherige Verlauf gelöscht wurde.

### Beispiel 2: Löschen der neuesten Befehle

Dieser Befehl verwendet die Parameter **count** und **Latest** , um die neuesten Befehle aus dem Verlauf einer PowerShell-Sitzung zu löschen.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Count 5 -Newest
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
  11 Clear-History -Count 5 -Newest
```

Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an. `Clear-History` wird verwendet, um den Befehlsverlauf zu löschen. Der **count** -Parameter gibt die Anzahl der zu löschenden Befehle an, einschließlich der angegebenen **ID** . Der **Latest** -Parameter gibt an, dass die neuesten Befehle aus dem Verlauf gelöscht werden. `Get-History`zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass die fünf neuesten Befehle gelöscht wurden, **ID 6**  -  **ID 10** .

### Beispiel 3: Löschen von Befehlen, die bestimmten Kriterien entsprechen

Dieser Befehl löscht Befehle, die bestimmten Kriterien entsprechen, die vom **CommandLine** -Parameter definiert werden.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
```

```powershell
Clear-History -CommandLine *Help*, *Syntax
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   4 Get-Command Clear-History -ShowCommandInfo
   8 Clear-History -CommandLine *Help*, *Syntax
```

Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an. `Clear-History` Löscht den Befehlsverlauf. Der **CommandLine** -Parameter gibt Befehle an, die **Hilfe** oder Ende mit **Syntax** enthalten. `Get-History` zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass die Befehle **ID 3** , **ID 5** , **ID 6** und **ID 7** gelöscht wurden.

### Beispiel 4: Löschen von Befehlen nach ID-Nummer

Mit diesem Befehl werden bestimmte Verlaufs Elemente mithilfe der **ID** gelöscht. Zum Löschen mehrerer Befehle übermitteln Sie eine durch Trennzeichen getrennte Liste mit **ID** -Nummern.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   3 Get-Help Get-Alias
   4 Get-Command Clear-History
   5 Get-Command Clear-History -Syntax
   6 Get-Command Clear-History -ShowCommandInfo
```

```powershell
Clear-History -Id 3, 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   4 Get-Command Clear-History
   6 Get-Command Clear-History -ShowCommandInfo
   7 Get-History
   8 Clear-History -Id 3, 5
```

Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an. `Clear-History` Löscht den Befehlsverlauf. Der **ID** -Parameter gibt an, welche Befehle gelöscht werden sollen. `Get-History` zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass **ID 3** und **ID 5** gelöscht wurden.

### Beispiel 5: Löschen von Befehlen nach ID-Nummer und-Anzahl

Dieser Befehl verwendet die **ID** -und **count** -Parameter, um den Befehlsverlauf zu löschen. Die Befehle werden aus der angegebenen **ID** in umgekehrter Reihenfolge gelöscht, von der neuesten zum ältesten.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Id 7 -Count 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
  11 Clear-History -Id 7 -Count 5
```

Das `Get-History` -Cmdlet zeigt den Verlauf der PowerShell-Sitzung an. `Clear-History` Löscht den Befehlsverlauf. Der **ID** -Parameter gibt an, dass mit **ID 7** begonnen werden soll. Der **count** -Parameter gibt an, dass fünf Befehle einschließlich der angegebenen **ID** gelöscht werden sollen. `Get-History`zeigt den aktualisierten Befehlsverlauf an und bestätigt, dass fünf Befehle gelöscht wurden, **ID 3**  -  **ID 7** .

## PARAMETERS

### -CommandLine

Löscht den Befehlsverlauf aus einer PowerShell-Sitzung. Die Zeichenfolge muss eine exakte Entsprechung sein oder Platzhalter verwenden, um Befehle in dem von angezeigten PowerShell-Sitzungsverlauf abzugleichen `Get-History` . Wenn Sie mehr als eine Zeichenfolge eingeben, `Clear-History` Löscht die Befehle, die mit einer der Zeichen folgen zu vergleichen sind. Der **CommandLine** -Parameter kann mit **count** verwendet werden.

Verwenden Sie für Zeichen folgen mit einem Leerzeichen einfache Anführungszeichen. Weitere Informationen finden Sie unter [about_Quoting_Rules](About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: CommandLineParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Anzahl

Gibt die Anzahl von Verlaufs Einträgen an, die von `Clear-History` gelöscht werden. Befehle werden in der Reihenfolge gelöscht, beginnend mit dem ältesten Eintrag im Verlauf.

Die Parameter **count** und **ID** können gleichzeitig verwendet werden. Der **count** -Parameter gibt die Anzahl der zu löschenden Befehle an, einschließlich der angegebenen **ID** . Beginnend bei der angegebenen **ID** werden die Befehle in umgekehrter sequenzieller Reihenfolge gelöscht. Wenn die **ID** z. b. 30 und die **Anzahl** 10 beträgt, `Clear-History` Löscht die Elemente 21 bis 30.

Die Parameter **count** und **CommandLine** können gleichzeitig verwendet werden. **Count** gibt die Anzahl der zu löschenden Befehle an, die dem **CommandLine** -Parameterwert entsprechen. Die Befehle werden in sequenzieller Reihenfolge gelöscht.

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

Gibt die Befehlsverlauf- **ID** an, die von `Clear-History` gelöscht wird Verwenden Sie das-Cmdlet, um die **ID** -Nummern anzuzeigen `Get-History` . Die **ID** -Nummern sind sequenziell, und die Befehle behalten ihre **ID** -Nummer in einer PowerShell-Sitzung bei. Der **ID** -Parameter kann mit **count** und **Latest** verwendet werden.

```yaml
Type: System.Int32[]
Parameter Sets: IDParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Latest

Wenn der **neueste** Parameter verwendet wird, `Clear-History` Löscht die neuesten Einträge im Verlauf. Standardmäßig `Clear-History` Löscht die ältesten Einträge im Verlauf.

Der **neueste** Parameter kann mit der **ID** und der **Anzahl** verwendet werden. Der **count** -Parameter gibt die Anzahl der zu löschenden Befehle an, einschließlich der angegebenen **ID** . Beginnend bei der angegebenen **ID** werden die Befehle in sequenzieller Reihenfolge gelöscht. Wenn die **ID** z. b. 30 und die **Anzahl** 10 beträgt, `Clear-History` Löscht die Elemente 30 bis 39.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Sie werden zur Bestätigung aufgefordert, bevor Sie das `Clear-History` Cmdlet ausführen.

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

Zeigt, was geschieht, wenn das `Clear-History` Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### Keine

Objekte können nicht an übergeben werden `Clear-History` .

## AUSGABEN

### Keine

`Clear-History` generiert keine Ausgabe.

## HINWEISE

Der PowerShell-Sitzungsverlauf ist eine Liste der Befehle, die während einer PowerShell-Sitzung eingegeben wurden. Sie können den Verlauf anzeigen, Befehle hinzufügen und löschen und Befehle aus dem Verlauf ausführen. Weitere Informationen finden Sie unter [about_History](About/about_History.md).

Der Sitzungsverlauf wird getrennt von dem vom **psread Line** -Modul verwalteten Verlauf verwaltet.
Beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird. Dieses Cmdlet funktioniert nur mit dem Sitzungsverlauf. Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## VERWANDTE LINKS

[about_History](About/about_History.md)

[about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)

[about_Quoting_Rules](About/about_Quoting_Rules.md)

[Add-History](Add-History.md)

[Get-History](Get-History.md)

[Invoke-History](Invoke-History.md)

[Get-psread lineoption](/powershell/module/psreadline/get-psreadlineoption)

[Set-psread lineoption](/powershell/module/psreadline/set-psreadlineoption)

