---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-output?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Output
ms.openlocfilehash: ccc72ac961adbcba542a7b8be55ad49df68a5ef6
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224295"
---
# Write-Output

## ZUSAMMENFASSUNG
Sendet die angegebenen Objekte an den nächsten Befehl in der Pipeline. Wenn der Befehl der letzte Befehl in der Pipeline ist, werden die Objekte in der Konsole angezeigt.

## SYNTAX

```
Write-Output [-InputObject] <PSObject[]> [-NoEnumerate] [<CommonParameters>]
```

## DESCRIPTION

Das- `Write-Output` Cmdlet sendet das angegebene Objekt über die Pipeline an den nächsten Befehl.
Wenn der Befehl der letzte Befehl in der Pipeline ist, wird das Objekt in der Konsole angezeigt.

`Write-Output` sendet Objekte über die primäre Pipeline, auch bekannt als "Ausgabestream" oder "Erfolgs Pipeline". Verwenden Sie zum Senden von Fehlerobjekten über die Fehlerpipeline das Cmdlet „Write-Error“.

Dieses Cmdlet wird in der Regel in Skripts verwendet, um Zeichenfolgen und andere Objekte in der Konsole anzuzeigen. Eine der integrierten Aliase für `Write-Output` ist `echo` und ähnlich wie andere Shells `echo` , die verwenden. das Standardverhalten besteht darin, die Ausgabe am Ende einer Pipeline anzuzeigen. In PowerShell ist es im Allgemeinen nicht erforderlich, das Cmdlet in Instanzen zu verwenden, in denen die Ausgabe standardmäßig angezeigt wird. `Get-Process | Write-Output` entspricht beispielsweise `Get-Process`. Oder `echo "Home directory: $HOME"` können geschrieben werden `"Home directory: $HOME"` .

Standardmäßig werden `Write-Output` für das Cmdlet bereitgestellte Auflistungen aufgelistet. Kann jedoch `Write-Output` auch verwendet werden, um Auflistungen in der Pipeline als einzelnes Objekt mit dem **noenumerate** -Parameter zu übergeben.

## BEISPIELE

### Beispiel 1: Objekte erhalten und in die Konsole schreiben

```powershell
$P = Get-Process
Write-Output $P
```

Der erste Befehl ruft die Prozesse ab, die auf dem Computer ausgeführt werden, und speichert Sie in der `$P` Variablen.

Mit dem zweiten und dritten Befehl werden die Prozess Objekte in `$P` auf der Konsole angezeigt.

### Beispiel 2: übergeben der Ausgabe an ein anderes Cmdlet

```powershell
Write-Output "test output" | Get-Member
```

Mit diesem Befehl wird die Zeichenfolge "Test Output" über die Pipeline an das `Get-Member` Cmdlet übergeben, das die Member der **System. String** -Klasse anzeigt und zeigt, dass die Zeichenfolge an der Pipeline übergeben wurde.

### Beispiel 3: Unterdrücken der Enumeration in der Ausgabe

```powershell
Write-Output 1,2,3 | Measure-Object
```

```Output
Count    : 3
...
```

```powershell
Write-Output 1,2,3 -NoEnumerate | Measure-Object
```

```Output
Count    : 1
...
```

Dieser Befehl fügt den **noenumerate** -Parameter hinzu, um eine Auflistung oder ein Array als ein einzelnes Objekt über die Pipeline zu behandeln.

## PARAMETERS

### -InputObject

Gibt die Objekte an, die über die Pipeline gesendet werden sollen. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Noenumerate

Standardmäßig zählt das `Write-Output` Cmdlet seine Ausgabe immer auf. Der **noenumerate** -Parameter unterdrückt das Standardverhalten und verhindert die `Write-Output` Enumeration der Ausgabe. Der **noenumerate** -Parameter hat keine Auswirkung, wenn der Befehl in Klammern eingeschlossen wird, da die Klammern eine Enumeration erzwingen. `(Write-Output 1,2,3)`Listet z. b. immer noch das Array auf.

> [!IMPORTANT]
> Es liegt ein Problem mit diesem Switch in Windows PowerShell vor, der in PowerShell 6,2 und höher behoben ist. Bei Verwendung von **noenumerate** und expliziter Verwendung des **Inputobject** -Parameters wird der Befehl trotzdem aufgelistet. Um dieses Problem zu umgehen, übergeben Sie das **Inputobject** -Argument (n) Positional.

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

Sie können Objekte über die Pipeline an übergeben `Write-Output` .

## AUSGABEN

### System. Management. Automation. psobject

`Write-Output` Gibt die Objekte zurück, die als Eingabe übermittelt werden.

## HINWEISE

## VERWANDTE LINKS

[about_Output_Streams](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[Tee-Object](Tee-Object.md)

[Write-Debug](Write-Debug.md)

[Schreibfehler](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Information](Write-Information.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
