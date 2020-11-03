---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/join-path?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-Path
ms.openlocfilehash: 4189201cd373d29e8ea8e88441376e0df902742e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211607"
---
# Join-Path

## ZUSAMMENFASSUNG
Kombiniert einen Pfad und einen untergeordneten Pfad zu einem Pfad.

## SYNTAX

```
Join-Path [-Path] <String[]> [-ChildPath] <String> [[-AdditionalChildPath] <String[]>] [-Resolve]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

Das `Join-Path` Cmdlet kombiniert einen Pfad und einen untergeordneten Pfad zu einem einzigen Pfad.
Der Anbieter stellt die Pfadtrennzeichen bereit.

## BEISPIELE

### Beispiel 1: kombinieren eines Pfads mit einem untergeordneten Pfad

```powershell
PS C:\> Join-Path -Path "path" -ChildPath "childpath"
```

```output
path\childpath
```

Dieser Befehl verwendet `Join-Path` , um einen Pfad mit einem childpath zu kombinieren.

Da der Befehl vom Anbieter ausgeführt wird `FileSystem` , stellt er das `\` Trennzeichen zum Verknüpfen der Pfade bereit.

### Beispiel 2: Kombinieren von Pfaden, die bereits Verzeichnis Trennzeichen enthalten

```powershell
PS C:\> Join-Path -Path "path\" -ChildPath "\childpath"
```

```output
path\childpath
```

Vorhandene Verzeichnis Trennzeichen, die `\` so behandelt werden, dass es nur ein Trennzeichen zwischen `Path` und gibt `ChildPath`

### Beispiel 3: Anzeigen von Dateien und Ordnern durch Zusammenfügen eines Pfads mit einem untergeordneten Pfad

```powershell
Join-Path "C:\win*" "System*" -Resolve
```

Mit diesem Befehl werden die Dateien und Ordner angezeigt, auf die verwiesen wird, indem der c:\win \* -Pfad und der untergeordnete Pfad des Systems angeschlossen werden \* .
Es zeigt die gleichen Dateien und Ordner wie `Get-ChildItem` an, zeigt jedoch den voll qualifizierten Pfad zu jedem Element an.
In diesem Befehl werden die `Path` `ChildPath` optionalen Parameternamen und weggelassen.

### Beispiel 4: Verwenden von Join-Path mit dem PowerShell-Registrierungs Anbieter

```powershell
PS HKLM:\> Join-Path -Path System -ChildPath *ControlSet* -Resolve
```

```output
HKLM:\System\ControlSet001
HKLM:\System\CurrentControlSet
```

Dieser Befehl zeigt die Registrierungsschlüssel im `HKLM\System` Registrierungs Unterschlüssel an, die `ControlSet` enthalten.

Der- `Resolve` Parameter versucht, den verbundenen Pfad aufzulösen, einschließlich Platzhalter aus dem aktuellen Anbieter Pfad. `HKLM:\`

### Beispiel 5: Kombinieren mehrerer Pfad Stämme mit einem untergeordneten Pfad

```powershell
Join-Path -Path C:, D:, E:, F: -ChildPath New
```

```output
C:\New
D:\New
E:\New
F:\New
```

Dieser Befehl verwendet `Join-Path` , um mehrere Pfad Stämme mit einem untergeordneten Pfad zu kombinieren.

> [!NOTE]
> Die von angegebenen Laufwerke `Path` müssen vorhanden sein, oder der Join dieses Eintrags schlägt fehl.

### Beispiel 6: Kombinieren der Stämme eines Dateisystem Laufwerks mit einem untergeordneten Pfad

```powershell
Get-PSDrive -PSProvider filesystem | ForEach-Object {$_.root} | Join-Path -ChildPath "Subdir"
```

```output
C:\Subdir
D:\Subdir
```

Dieser Befehl kombiniert die Stämme der einzelnen PowerShell-Dateisystem Laufwerke in der-Konsole mit dem untergeordneten subdir-Pfad.

Der Befehl verwendet das `Get-PSDrive` Cmdlet, um die vom File System-Anbieter unterstützten PowerShell-Laufwerke zu erhalten.
`ForEach-Object`Mit der-Anweisung wird nur die Root-Eigenschaft der `PSDriveInfo` -Objekte ausgewählt und mit dem angegebenen untergeordneten Pfad kombiniert.

Die Ausgabe zeigt, dass die PowerShell-Laufwerke auf dem Computer ein Laufwerk enthalten, das dem Verzeichnis "c:\Program Files" zugeordnet ist.

### Beispiel 7: Kombinieren einer unbestimmten Anzahl von Pfaden

```powershell
Join-Path a b c d e f g
```

```Output
a\b\c\d\e\f\g
```

Der- `AdditionalChildPath` Parameter ermöglicht die zusammen Fügung einer unbegrenzten Anzahl von Pfaden.

In diesem Beispiel werden keine Parameternamen verwendet, daher wird "a" an `Path` , "b" `ChildPath` und "c-g" an gebunden. `AdditionalChildPath`

## PARAMETERS

### -Additionalchildpath

Gibt zusätzliche Elemente an, die an den Wert des *path* -Parameters angefügt werden sollen. Der `ChildPath` -Parameter ist weiterhin obligatorisch und muss ebenfalls angegeben werden.

Dieser Parameter wird mit der- `ValueFromRemainingArguments` Eigenschaft angegeben, die das beitreten zu einer unbestimmten Anzahl von Pfaden ermöglicht.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Childpath

Gibt die Elemente an, die an den Wert des-Parameters angefügt werden sollen `Path` .
Platzhalter sind zulässig.
Der- `ChildPath` Parameter ist erforderlich, obwohl der Parameter Name ("childpath") optional ist.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Credential

> [!NOTE]
> Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.
> Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Gibt die Hauptpfade an, an die der untergeordnete Pfad angefügt wird.
Platzhalter sind zulässig.

Der Wert von `Path` bestimmt, welcher Anbieter die Pfade verbindet, und fügt die Pfad Trennzeichen hinzu.
Der- `Path` Parameter ist erforderlich, obwohl der Parameter Name ("Path") optional ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Auflösen

Gibt an, dass dieses Cmdlet versuchen soll, den verbundenen Pfad vom aktuellen Anbieter aufzulösen.

- Wenn Platzhalter verwendet werden, gibt das Cmdlet alle Pfade zurück, die dem verbundenen Pfad entsprechen.
- Wenn **keine** Platzhalter verwendet werden, tritt beim Cmdlet ein Fehler auf, wenn der Pfad nicht vorhanden ist.

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

### System.String

Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.

## AUSGABEN

### System.String

Dieses Cmdlet gibt eine Zeichenfolge zurück, die den resultierenden Pfad enthält.

## HINWEISE

Die Cmdlets, die das Pfad-Substantiv enthalten (die Path-Cmdlets), bearbeiten Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann. Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll. Die Verwendung entspricht der von %%amp;quot;Dirname%%amp;quot;, %%amp;quot;Normpath%%amp;quot;, %%amp;quot;Realpath%%amp;quot;, %%amp;quot;Join%%amp;quot; und anderer Befehle zum Bearbeiten von Pfaden.

Sie können die Pfad-Cmdlets mit verschiedenen Anbietern verwenden, einschließlich `FileSystem` der `Registry` Anbieter, und `Certificate` .

Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.
Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .
Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Convert-Path](Convert-Path.md)

[Resolve-Path](Resolve-Path.md)

[Split-Path](Split-Path.md)

[Test-Path](Test-Path.md)

[Get-PSProvider](Get-PSProvider.md)

[Get-ChildItem](Get-ChildItem.md)

[Get-PSDrive](Get-PSDrive.md)

