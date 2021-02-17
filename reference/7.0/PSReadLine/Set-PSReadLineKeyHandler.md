---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 02/16/2021
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: 22ad8a33f80ad5f4d75fe23c0c8f6c845a40d748
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563242"
---
# Set-PSReadLineKeyHandler

## ZUSAMMENFASSUNG
Bindet Schlüssel an benutzerdefinierte oder psread Line-schlüsselhandlerfunktionen.

## SYNTAX

### ScriptBlock

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### Funktion

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Set-PSReadLineKeyHandler` Cmdlet passt das Ergebnis an, wenn ein Schlüssel oder eine Sequenz von Schlüsseln gedrückt wird. Mit benutzerdefinierten Tastenkombinationen können Sie nahezu alles ausführen, was in einem PowerShell-Skript möglich ist.

## BEISPIELE

### Beispiel 1: Binden der Pfeiltaste an eine Funktion

Mit diesem Befehl wird die nach-oben-Taste an die **historysearchrückwärts** -Funktion gebunden. Diese Funktion durchsucht den Befehlsverlauf nach Befehlszeilen, die mit dem aktuellen Inhalt der Befehlszeile beginnen.

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### Beispiel 2: Binden eines Schlüssels an einen Skriptblock

Dieses Beispiel zeigt, wie ein einzelner Schlüssel zum Ausführen eines Befehls verwendet werden kann. Mit dem Befehl wird der Schlüssel `Ctrl+B` an einen Skriptblock gebunden, der die Zeile löscht, das Wort "Build" einfügt und dann die Zeile annimmt.

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## PARAMETERS

### -Briefdescription

Eine kurze Beschreibung der schlüsselbindung. Diese Beschreibung wird vom `Get-PSReadLineKeyHandler` Cmdlet angezeigt.

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Akkord

Der Schlüssel oder die Sequenz von Schlüsseln, die an eine Funktion oder einen Skriptblock gebunden werden sollen. Verwenden Sie eine einzelne Zeichenfolge, um eine einzelne Bindung anzugeben. Wenn die Bindung eine Sequenz von Schlüsseln ist, trennen Sie die Schlüssel durch ein Komma, wie im folgenden Beispiel gezeigt:

`Ctrl+X,Ctrl+L`

> [!NOTE]
> Ab psread Line 2.0.0 **wird die** **Groß-/Kleinschreibung** berücksichtigt. Dies bedeutet, dass `Ctrl+X` `Ctrl+x` unterschiedliche Bindungen erstellt werden.

Dieser Parameter akzeptiert ein Array von Zeichen folgen. Jede Zeichenfolge ist eine separate Bindung und keine Sequenz von Schlüsseln für eine einzelne Bindung.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Gibt eine ausführlichere Beschreibung der schlüsselbindung an, die in der Ausgabe des `Get-PSReadLineKeyHandler` Cmdlets sichtbar ist.

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases: LongDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Funktion

Gibt den Namen eines vorhandenen Schlüssel Handlers an, der von psread Line bereitgestellt wird. Dieser Parameter ermöglicht das erneute Binden vorhandener Schlüsselbindungen oder das Binden eines Handlers, der zurzeit nicht gebunden ist.

```yaml
Type: System.String
Parameter Sets: Function
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Gibt einen Skriptblock Wert an, der beim Eintreten des Akkords ausgeführt werden soll. Psread Line übergibt einen oder zwei Parameter an diesen Skriptblock. Der erste Parameter ist ein **ConsoleKeyInfo** -Objekt, das den gedrückten Schlüssel darstellt. Das zweite Argument kann je nach Kontext ein beliebiges Objekt sein.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vimode

Geben Sie den VI-Modus an, für den die Bindung gilt.

Gültige Werte sind:

- Insert
- Get-Help

```yaml
Type: Microsoft.PowerShell.ViMode
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

### Keine

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

## VERWANDTE LINKS

[Get-psread linekeyhandler](Get-PSReadLineKeyHandler.md)

[Remove-psread linekeyhandler](Remove-PSReadLineKeyHandler.md)

[Get-psread lineoption](Get-PSReadLineOption.md)

[Set-psread lineoption](Set-PSReadLineOption.md)
