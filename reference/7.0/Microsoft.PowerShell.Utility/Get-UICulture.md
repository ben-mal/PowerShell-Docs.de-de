---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: cd5bbcae124b1c24438d2821c4da9d71a22d38a2
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200922"
---
# Get-UICulture

## ZUSAMMENFASSUNG
Ruft die aktuellen Einstellungen der Benutzeroberflächen Kultur im Betriebssystem ab.

## SYNTAX

```
Get-UICulture [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-UICulture` Cmdlet ruft Informationen über die aktuellen Kultur Einstellungen der Benutzeroberfläche (UI) für Windows ab.
Die Benutzeroberflächenkultur bestimmt, welche Textzeichenfolgen für die Benutzeroberflächenelemente, z. B. Menüs und Meldungen, verwendet werden.

Sie können auch das- `Get-Culture` Cmdlet verwenden, das die aktuelle Kultur auf dem System abruft.
Die Kultur bestimmt das Anzeigeformat für Elemente, z. B. Zahlen, Währung und Datumsangaben.

## BEISPIELE

### Beispiel 1: Holen Sie sich die Benutzeroberflächen Kultur

```powershell
Get-UICulture
```

Dieser Befehl ruft die aktuellen Benutzeroberflächenkulturinformationen ab.

### Beispiel 2: erhalten der Benutzeroberflächen Kultur und Formatieren der Ergebnisse

```powershell
Get-UICulture | Format-List *
```

Dieser Befehl zeigt die Werte aller Eigenschaften der aktuellen Benutzeroberflächenkultur in einer Liste an.

### Beispiel 3: erhalten Sie den Wert der Calendar-Eigenschaft.

```powershell
(Get-UICulture).Calendar
```

Dieser Befehl zeigt die aktuellen Werte für die **Calendar** -Eigenschaft der aktuellen Benutzeroberflächen Kultur an.
„Calendar“ ist nur eine der Eigenschaften der Benutzeroberflächenkultur.
Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-UICulture | Get-Member` .

### Beispiel 4: Holen Sie sich das kurze Datums Muster

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

Dieser Befehl zeigt das kurze Datumsmuster für die aktuelle Benutzeroberflächenkultur an.
Wenn Sie alle untergeordneten Eigenschaften der **DateTimeFormat** -Eigenschaft der Benutzeroberflächen Kultur anzeigen möchten, geben Sie ein `(Get-UICulture).DateTimeFormat | gm` .

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Globalization. CultureInfo, Microsoft. PowerShell. vistacultureinfo

`Get-UICulture` Gibt ein-Objekt zurück, das die aktuelle Benutzeroberflächen Kultur darstellt.
In Windows PowerShell 3,0 wird ein **CultureInfo** -Objekt zurückgegeben.
In Windows PowerShell 2,0 wird ein **vistacultureinfo** -Objekt zurückgegeben.

## HINWEISE

- Sie können auch die `$PsCulture` Variablen und verwenden `$PsUICulture` . Die `$PsCulture` Variable speichert den Namen der aktuellen Kultur, und die `$PsUICulture` Variable speichert den Namen der aktuellen Benutzeroberflächen Kultur.

## VERWANDTE LINKS
