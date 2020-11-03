---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: ff70c7dd5314fd1f123299e8f4ed14c70c7d7c9a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217420"
---
# Out-Null

## ZUSAMMENFASSUNG
Blendet die Ausgabe aus, anstatt Sie über die Pipeline zu senden oder anzuzeigen.

## SYNTAX

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

Das **out-null-** Cmdlet sendet seine Ausgabe an NULL und bewirkt, dass es aus der Pipeline entfernt wird und verhindert, dass die Ausgabe auf dem Bildschirm angezeigt wird.

## BEISPIELE

### Beispiel 1: Löschen der Ausgabe

```powershell
Get-ChildItem | Out-Null
```

Mit diesem Befehl werden Elemente im aktuellen Speicherort/Verzeichnis abgerufen, aber seine Ausgabe wird nicht über die Pipeline oder in der Befehlszeile angezeigt.
Dies ist nützlich, um die Ausgabe zu verbergen, die Sie nicht benötigen.

## PARAMETERS

### -InputObject

Gibt das-Objekt an, das an NULL (aus Pipeline entfernt) gesendet werden soll.
Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Die Cmdlets, die das **out** -Verb (die **out** -Cmdlets) enthalten, haben keine Parameter für Namen oder Dateipfade. Verwenden Sie zum Senden von Daten an ein **out** -Cmdlet einen Pipeline Operator (|), um die Ausgabe eines PowerShell-Befehls an das Cmdlet zu senden. Sie können auch Daten in einer Variablen speichern und den *InputObject* -Parameter verwenden, um die Daten an das Cmdlet zu übergeben. Weitere Informationen finden Sie in den Beispielen.
* **Out-null** gibt keine Ausgabe Objekte zurück. Wenn Sie die Ausgabe von **out-null** an das Get-Member-Cmdlet weiterreichen, meldet **Get-Member** , dass keine Objekte angegeben wurden.

## VERWANDTE LINKS

[Out-Default](Out-Default.md)

[Out-Host](Out-Host.md)

