---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-typedata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TypeData
ms.openlocfilehash: 252915c63539ce4af2ae56a04c4488cc14a13826
ms.sourcegitcommit: bdd0fedaf9ba534645b2f7eb1fe1241481f58715
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "105936494"
---
# Get-TypeData

## Übersicht
Ruft die erweiterten Typdaten in der aktuellen Sitzung ab.

## Syntax

```
Get-TypeData [[-TypeName] <String[]>] [<CommonParameters>]
```

## BESCHREIBUNG

Das- `Get-TypeData` Cmdlet ruft die erweiterten Typdaten in der aktuellen Sitzung ab. Dies schließt Typdaten ein, die der Sitzung durch `Types.ps1xml` Datei-und dynamische Typdaten hinzugefügt wurden, die mithilfe des-Parameters des `Update-TypeData` Cmdlets hinzugefügt wurden.

Sie können die erweiterten Typdaten verwenden, die `Get-TypeData` zurückgibt, um die Typdaten in der Sitzung zu überprüfen und Sie an die `Update-TypeData` -und- `Remove-TypeData` Cmdlets zu senden.

Erweiterte Typdaten fügen Objekten in PowerShell Eigenschaften und Methoden hinzu. Sie können die hinzugefügten Eigenschaften und Methoden auf die gleiche Weise wie die im Objekttyp definierten Eigenschaften und Methoden verwenden. Beachten Sie jedoch beim Schreiben von Skripts, dass die hinzugefügten Eigenschaften und Methoden möglicherweise nicht in jeder PowerShell-Sitzung vorhanden sind.

Weitere Informationen zu `Types.ps1xml` Dateien finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md). Weitere Informationen zu dynamischen Typdaten, die vom `Update-TypeData` Cmdlet hinzugefügt werden, finden Sie unter `Update-TypeData` .

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## Beispiele

### Beispiel 1: alle erweiterten Typdaten

In diesem Beispiel werden alle erweiterten Typdaten in der aktuellen Sitzung abgerufen.

 ```powershell
Get-TypeData
```

### Beispiel 2: Get Type Data by Name

In diesem Beispiel werden alle Typdaten in der aktuellen Sitzung abgerufen, deren Name mit "System.IO" gekennzeichnet ist.

```powershell
Get-TypeData -TypeName System.IO.*
```

```Output
TypeName                Members
--------                -------
System.IO.DirectoryInfo {[Mode, System.Management.Automation.Runspaces.CodePropert…
System.IO.FileInfo      {[Mode, System.Management.Automation.Runspaces.CodePropert…
```

### Beispiel 3: Ruft den Skriptblock ab, der einen Eigenschafts Wert erstellt.

In diesem Beispiel wird der Skriptblock abgerufen, der den Wert der **EventID-** Eigenschaft von **EventLogEntry** -Objekten erstellt.

 ```powershell
(Get-TypeData *EventLogEntry*).Members.EventID
```

```Output
GetScriptBlock                     SetScriptBlock     IsHidden Name
--------------                     --------------     -------- ----
$this.get_EventID() -band 0xFFFF                         False EventID
```

### Beispiel 4: der Skriptblock, der eine Eigenschaft für ein angegebenes Objekt definiert

In diesem Beispiel wird der Skriptblock abgerufen, der die **DateTime** -Eigenschaft der **System. DateTime** -Objekte in PowerShell definiert.

 ```powershell
(Get-TypeData -TypeName System.DateTime).Members["DateTime"].GetScriptBlock
if ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq  "Date") {
    "{0}" -f $this.ToLongDateString()
}
elseif ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq "Time") {
    "{0}" -f  $this.ToLongTimeString()
}
else {
    "{0} {1}" -f $this.ToLongDateString(), $this.ToLongTimeString()
}
```

Der Befehl verwendet das `Get-TypeData` Cmdlet, um die erweiterten Typdaten für den **System. DataTime** -Typ zu erhalten. Mit dem Befehl wird die **Members**-Eigenschaft des **TypeData**-Objekts abgerufen.

Die **Members** -Eigenschaft enthält eine Hash Tabelle mit Eigenschaften und Methoden, die durch erweiterte Typdaten definiert werden. Jeder Schlüssel in der Hashtabelle „Members“ ist ein Eigenschaften- oder Methodenname, und jeder Wert ist die Definition des Eigenschaften- oder Methodenwerts.

Der Befehl ruft den **DateTime** **-Schlüssel** in Membern und dessen **getscriptblock** -Eigenschafts Wert ab.

Die Ausgabe zeigt den Skriptblock, der den Wert der **DateTime** -Eigenschaft jedes **System. DateTime** -Objekts in PowerShell erstellt.

## Parameter

### -Typname

Gibt Typdaten nur für Typen mit den angegebenen Namen als Array an. Standardmäßig ruft `Get-TypeData` alle Typen in der Sitzung ab.

Geben Sie Namen oder ein Namensmuster ein. Vollständige Namen oder Namensmuster mit Platzhalter Zeichen sind erforderlich, auch für Typen im System-Namespace. Platzhalter werden unterstützt, und der Parameter Name **tykenname** ist optional. Sie können Typnamen auch über die Pipeline an senden `Get-TypeData` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Eingaben

### System.String

Sie können Typnamen an übergeben `Get-TypeData` .

## Ausgaben

### System. Management. Automation. Runspaces. typedata

## Hinweise

`Get-TypeData` Ruft nur die erweiterten Typdaten in der aktuellen Sitzung ab. Es ruft keine erweiterten Typdaten ab, die sich auf dem Computer befinden, aber nicht der aktuellen Sitzung hinzugefügt wurden, wie z. B. erweiterte Typen, die in Modulen definiert und nicht in die aktuelle Sitzung importiert wurden.

## Verwandte Links

[about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[Remove-TypeData](Remove-TypeData.md)

[Update-TypeData](Update-TypeData.md)
