---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-host?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Host
ms.openlocfilehash: d40dc5d85fc1a6999eccac54e72f2f0870afd9b4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212847"
---
# Out-Host

## ZUSAMMENFASSUNG
Sendet eine Ausgabe an die Befehlszeile.

## SYNTAX

### Alle

```
Out-Host [-Paging] [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

Das `Out-Host` Cmdlet sendet die Ausgabe zur Anzeige an den PowerShell-Host. Der Host zeigt die Ausgabe in der Befehlszeile an. Da `Out-Host` der Standardwert ist, müssen Sie ihn nicht angeben, es sei denn, Sie möchten seine Parameter verwenden.

`Out-Host` wird automatisch an jeden Befehl angehängt, der ausgeführt wird. Sie übergibt die Ausgabe der Pipeline an den Host, der den Befehl ausführt. `Out-Host` ignoriert ANSI-Escapesequenzen. Die Escapesequenzen werden vom Host behandelt. `Out-Host` übergibt ANSI-Escapesequenzen an den Host, ohne zu versuchen, Sie zu interpretieren oder zu ändern.

## BEISPIELE

### Beispiel 1: Anzeigen der Ausgabeseiten Weise

In diesem Beispiel werden die System Prozesse jeweils auf einer Seite angezeigt.

```powershell
Get-Process | Out-Host -Paging
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     30    24.12      36.95      15.86   21004  14 ApplicationFrameHost
     55    24.33      60.48      10.80   12904  14 BCompare
<SPACE> next page; <CR> next line; Q quit
      9     4.71       8.94       0.00   16864  14 explorer
<SPACE> next page; <CR> next line; Q quit
```

`Get-Process` Ruft die System Prozesse ab und sendet die Objekte in der Pipeline. `Out-Host` verwendet den **Paging** -Parameter, um jeweils eine Seite mit Daten anzuzeigen.

### Beispiel 2: Verwenden einer Variablen als Eingabe

In diesem Beispiel werden-Objekte, die in einer Variablen gespeichert sind, als Eingabe für verwendet `Out-Host` .

```powershell
$io = Get-History
Out-Host -InputObject $io
```

`Get-History` Ruft den Verlauf der PowerShell-Sitzung ab und speichert die Objekte in der `$io` Variablen.
`Out-Host` verwendet den **Inputobject** -Parameter, um die Variable anzugeben, `$io` und zeigt den Verlauf an.

## PARAMETERS

### -InputObject

Gibt die Objekte an, die in die Konsole geschrieben werden. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

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

### -Paging

Gibt an, dass `Out-Host` eine Seite der Ausgabe gleichzeitig anzeigt und auf die Benutzereingabe wartet, bevor die verbleibenden Seiten angezeigt werden. Standardmäßig wird die gesamte Ausgabe auf einer einzelnen Seite angezeigt. Die Seitengröße wird durch die Eigenschaften des Hosts bestimmt.

Drücken Sie die <kbd>LEERTASTE</kbd> , um die nächste Seite der Ausgabe anzuzeigen, oder drücken <kbd>Sie die Eingabe</kbd> Taste, um die nächste Zeile der Ausgabe anzuzeigen. Drücken Sie <kbd>Q</kbd> zum Beenden.

**Paging** ähnelt dem **more** -Befehl.

> [!NOTE]
> Der **Paging** -Parameter wird vom PowerShell ISE-Host nicht unterstützt.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können Objekte über die Pipeline an senden `Out-Host` .

## AUSGABEN

### Keine

`Out-Host` generiert keine Ausgabe. Objekte werden zur Anzeige an den Host gesendet.

## HINWEISE

Der **Paging** -Parameter wird nicht von allen PowerShell-Hosts unterstützt. Wenn Sie z. b. den **Paging** -Parameter in der PowerShell ISE verwenden, wird der folgende Fehler angezeigt: `out-lineoutput : The method or operation is not implemented.`

Mit den Cmdlets, die das **out** -Verb enthalten, `Out-` werden keine Objekte formatiert. Sie Rendering-Objekte und senden Sie an das angegebene Anzeige Ziel. Wenn Sie ein unformatiertes Objekt an ein `Out-` Cmdlet senden, sendet das Cmdlet es vor dem Rendern an ein Formatierungs-Cmdlet.

Die `Out-` Cmdlets enthalten keine Parameter für Namen oder Dateipfade. Verwenden Sie zum Senden von Daten an ein `Out-` Cmdlet die Pipeline, um die Ausgabe eines PowerShell-Befehls an das Cmdlet zu senden. Oder Sie können Daten in einer Variablen speichern und den **Inputobject** -Parameter verwenden, um die Daten an das Cmdlet zu übergeben.

`Out-Host` sendet Daten, aber es werden keine Ausgabe Objekte erzeugt. Wenn Sie die Ausgabe von `Out-Host` an das `Get-Member` Cmdlet weitergeben, `Get-Member` meldet, dass keine Objekte angegeben wurden.

## VERWANDTE LINKS

[Clear-Host](Clear-Host.md)

[Out-Default](Out-Default.md)

[Out-File](../Microsoft.PowerShell.Utility/Out-File.md)

[Out-Null](Out-Null.md)

[Out-Printer](../Microsoft.PowerShell.Utility/Out-Printer.md)

[Out-String](../Microsoft.PowerShell.Utility/Out-String.md)

[Write-Host](../Microsoft.PowerShell.Utility/Write-Host.md)
