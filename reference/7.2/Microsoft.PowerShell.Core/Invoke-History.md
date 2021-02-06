---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-History
ms.openlocfilehash: 7fb4341a84706f7d31d463bb527a1a31f387c2ae
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601120"
---
# Invoke-History

## ZUSAMMENFASSUNG
Führt Befehle aus dem Sitzungsverlauf aus.

## SYNTAX

```
Invoke-History [[-Id] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Invoke-History` Cmdlet führt Befehle aus dem Sitzungsverlauf aus. Sie können Objekte, die die Befehle darstellen, von Get-History an übergeben `Invoke-History` , oder Sie können Befehle im aktuellen Verlauf mithilfe Ihrer **ID** -Nummer identifizieren. Verwenden Sie das-Cmdlet, um die ID eines Befehls zu ermitteln `Get-History` .

Der Sitzungsverlauf wird getrennt von dem vom **psread Line** -Modul verwalteten Verlauf verwaltet.
Beide Verläufe sind in Sitzungen verfügbar, in denen **psread Line** geladen wird. Dieses Cmdlet funktioniert nur mit dem Sitzungsverlauf. Weitere Informationen finden Sie unter [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## BEISPIELE

### Beispiel 1: Ausführen des letzten Befehls im Verlauf

In diesem Beispiel wird der letzte oder neueste Befehl im Sitzungsverlauf ausgeführt. Sie können diesen Befehl als `r` , den Alias für, abkürzen `Invoke-History` .

```powershell
Invoke-History
```

### Beispiel 2: führen Sie den Befehl aus, der über eine angegebene ID verfügt.

Dieses Beispiel führt den Befehl im Sitzungsverlauf mit der **ID** 132 aus. Da der Name des **ID** -Parameters optional ist, können Sie diesen Befehl wie folgt abkürzen: `Invoke-History 132` , `ihy 132` oder `r 132` .

```powershell
Invoke-History -Id 132
```

### Beispiel 3: Ausführen des neuesten Befehls mit dem Befehls Text

In diesem Beispiel wird der letzte `Get-Process` Befehl im Sitzungsverlauf ausgeführt. Wenn Sie Zeichen für den **ID** -Parameter eingeben, `Invoke-History` führt den ersten gefundenen Befehl aus, der mit dem Muster übereinstimmt, beginnend mit den neuesten Befehlen.

```powershell
Invoke-History -Id get-pr
```

> [!NOTE]
> Beim Musterabgleich wird die Groß-/Kleinschreibung nicht beachtet, aber das Muster entspricht dem Anfang der Zeile.

### Beispiel 4: Ausführen einer Sequenz von Befehlen aus dem Verlauf

Dieses Beispiel führt die Befehle 16 bis 24 aus. Da Sie nur einen **ID** -Wert auflisten können, verwendet der Befehl das `ForEach-Object` Cmdlet, um den `Invoke-History` Befehl für jeden **ID** -Wert einmal auszuführen.

```powershell
16..24 | ForEach {Invoke-History -Id $_ }
```

### Beispiel 5

Dieses Beispiel führt die sieben Befehle im Verlauf aus, die mit dem Befehl 255 (249 bis 255) enden. Er verwendet das `Get-History` Cmdlet zum Abrufen der Befehle. Da Sie nur einen **ID** -Wert auflisten können, verwendet der Befehl das `ForEach-Object` Cmdlet, um den `Invoke-History` Befehl für jeden **ID** -Wert einmal auszuführen.

```powershell
Get-History -Id 255 -Count 7 | ForEach {Invoke-History -Id $_.Id}
```

## PARAMETERS

### -Id

Gibt die **ID** eines Befehls im Verlauf an. Sie können die **ID** -Nummer des Befehls oder die ersten Zeichen des Befehls eingeben.

Wenn Sie Zeichen eingeben, werden `Invoke-History` zuerst die neuesten Befehle abgeglichen. Wenn Sie diesen Parameter weglassen, `Invoke-History` führt den letzten oder letzten Befehl aus. Verwenden Sie das-Cmdlet, um die **ID** -Nummer eines Befehls zu ermitteln `Get-History` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## EINGABEN

### System.String

Sie können eine Verlaufs- **ID** an dieses Cmdlet weiterreichen.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe, aber die Ausgabe kann durch die Befehle generiert werden, die ausgeführt werden `Invoke-History` .

## HINWEISE

Der Sitzungsverlauf ist eine Liste der Befehle, die während der Sitzung eingegeben wurden. Der Sitzungsverlauf stellt die Reihenfolge der Ausführung, den Status und die Start- und Endzeiten des Befehls dar. Wenn Sie jeden Befehl eingeben, wird er von PowerShell dem Verlauf hinzugefügt, damit Sie ihn wieder verwenden können. Weitere Informationen zum Sitzungsverlauf finden Sie unter [about_History](About/about_History.md).

Weitere Informationen finden Sie auch unter `Invoke-History` den integrierten Aliasen `r` und `ihy` . Weitere Informationen finden Sie unter [about_Aliases](About/about_Aliases.md).

## VERWANDTE LINKS

[Add-History](Add-History.md)

[Clear-History](Clear-History.md)

[Get-History](Get-History.md)

