---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-Item
ms.openlocfilehash: b331398480243bbc23059acfa9a2c0cbb344c0cc
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209983"
---
# Move-Item

## ZUSAMMENFASSUNG
Verschiebt ein Element von einem Speicherort an einen anderen Speicherort.

## SYNTAX

### Pfad (Standard)

```
Move-Item [-Path] <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Move-Item -LiteralPath <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Move-Item`Mit dem-Cmdlet wird ein Element einschließlich seiner Eigenschaften, Inhalte und untergeordneten Elemente von einem Speicherort an einen anderen Speicherort verschoben. Die Speicherorte müssen vom selben Anbieter unterstützt werden.
Beispielsweise kann eine Datei oder ein Unterverzeichnis von einem Verzeichnis in ein anderes oder ein Registrierungsunterschlüssel von einem Schlüssel in einen anderen verschoben werden.
Beim Verschieben eines Elements wird dieses am neuen Speicherort hinzugefügt und an seinem ursprünglichen Speicherort gelöscht.

## BEISPIELE

### Beispiel 1: Verschieben einer Datei in ein anderes Verzeichnis und Umbenennen

Dieser Befehl verschiebt die `Test.txt` Datei vom `C:` Laufwerk in das `E:\Temp` Verzeichnis und benennt Sie von `test.txt` in um `tst.txt` .

```powershell
Move-Item -Path C:\test.txt -Destination E:\Temp\tst.txt
```

### Beispiel 2: Verschieben eines Verzeichnisses und seiner Inhalte in ein anderes Verzeichnis

Dieser Befehl verschiebt das `C:\Temp` Verzeichnis und seinen Inhalt in das `C:\Logs` Verzeichnis.
Das Verzeichnis "Temp" und alle zugehörigen Unterverzeichnisse und Dateien werden dann im Verzeichnis "Logs" angezeigt.

```powershell
Move-Item -Path C:\Temp -Destination C:\Logs
```

### Beispiel 3: Verschieben aller Dateien einer angegebenen Erweiterung aus dem aktuellen Verzeichnis in ein anderes Verzeichnis

Mit diesem Befehl werden alle Textdateien ( `*.txt` ) im aktuellen Verzeichnis (dargestellt durch einen Punkt ( `.` )) in das Verzeichnis verschoben `C:\Logs` .

```powershell
Move-Item -Path .\*.txt -Destination C:\Logs
```

### Beispiel 4: rekursiver Verschieben aller Dateien einer angegebenen Erweiterung aus dem aktuellen Verzeichnis in ein anderes Verzeichnis

Mit diesem Befehl werden alle Textdateien aus dem aktuellen Verzeichnis und allen Unterverzeichnissen rekursiv in das Verzeichnis "c:\textfiles" verschoben.

```powershell
Get-ChildItem -Path ".\*.txt" -Recurse | Move-Item -Destination "C:\TextFiles"
```

Der Befehl verwendet das `Get-ChildItem` Cmdlet, um alle untergeordneten Elemente im aktuellen Verzeichnis (dargestellt durch den Punkt \[ \] ) und seine Unterverzeichnisse mit der *Dateinamenerweiterung ". txt" abzurufen. Er verwendet den **recurse** -Parameter, um den Abruf rekursiv zu machen, und den Include-Parameter, um den Abruf auf "*. txt"-Dateien zu beschränken.

Der Pipeline Operator ( `|` ) sendet die Ergebnisse dieses Befehls an `Move-Item` , wodurch die Textdateien in das Verzeichnis "Textfiles" verschoben werden.

Wenn Dateien, die in "c:\textfiles" verschoben werden sollen, denselben Namen aufweisen, wird von `Move-Item` ein Fehler angezeigt und der Vorgang fortgesetzt, es wird jedoch nur eine Datei mit jedem Namen in "c:\textfiles" verschoben.
Die anderen Dateien verbleiben in ihren ursprünglichen Verzeichnissen.

Wenn das Verzeichnis "Textfiles" (oder ein beliebiges anderes Element des Zielpfads) nicht vorhanden ist, schlägt der Befehl fehl.
Das fehlende Verzeichnis wird nicht für Sie erstellt, auch wenn Sie den **Force** -Parameter verwenden.
`Move-Item` Verschiebt das erste Element in eine Datei mit dem Namen "Textfiles" und zeigt dann einen Fehler an, in dem erläutert wird, dass die Datei bereits vorhanden ist.

Außerdem werden von standardmäßig keine ausgeblendeten `Get-ChildItem` Dateien verschoben.
Um verborgene Dateien zu verschieben, verwenden Sie den **Force** -Parameter mit `Get-ChildItem` .

> [!NOTE]
> In Windows PowerShell 2,0 muss bei Verwendung des **recurse** -Parameters des `Get-ChildItem` Cmdlets der Wert des **path** -Parameters ein Container sein.
> Geben Sie den Filter für die Dateinamenerweiterung %%amp;quot;.txt%%amp;quot; mithilfe des **Include** -Parameters an (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`).

### Beispiel 5: Verschieben von Registrierungs Schlüsseln und-Werten in einen anderen Schlüssel

Mit diesem Befehl werden die Registrierungsschlüssel und-Werte innerhalb des Registrierungsschlüssels "MyCompany" in in `HKLM\Software` den Schlüssel "mynewcompany" verschoben.
Das Platzhalter Zeichen ( `*` ) gibt an, dass der Inhalt des Schlüssels "MyCompany" und nicht der Schlüssel selbst verschoben werden soll.
In diesem Befehl werden die optionalen **Pfad** -und **Ziel** Parameternamen ausgelassen.

```powershell
Move-Item "HKLM:\software\mycompany\*" "HKLM:\software\mynewcompany"
```

### Beispiel 6: Verschieben eines Verzeichnisses und seiner Inhalte in ein Unterverzeichnis des angegebenen Verzeichnisses

Mit diesem Befehl wird das Verzeichnis "Logs \[ \` \] . 06" (und dessen Inhalt) in das Verzeichnis "Logs \[ 2006 \] " verschoben.

```powershell
Move-Item -LiteralPath 'Logs[Sept`06]' -Destination 'Logs[2006]'
```

Der **literalpath** -Parameter wird anstelle von **path** verwendet, da der ursprüngliche Verzeichnisname linke eckige Klammer und rechte eckige Klammern (" \[ " und " \] ") enthält.
Der Pfad wird auch in einfache Anführungszeichen (' ') eingeschlossen, sodass das Graviszeichen-Symbol ( \` ) nicht falsch interpretiert wird.

Der **Destination** -Parameter erfordert keinen literalen Pfad, da die Zielvariable auch in einfache Anführungszeichen eingeschlossen werden muss, da Sie eckige Klammern enthält, die falsch interpretiert werden können.

## PARAMETERS

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
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Destination

Gibt den Pfad zum Speicherort an, an den die Elemente verschoben werden.
Der Standardwert ist das aktuelle Verzeichnis.
Platzhalter sind zulässig, das Ergebnis muss jedoch ein einziger Speicherort sein.

Um das Element umzubenennen, das verschoben wird, geben Sie im Wert des **Destination** -Parameters einen neuen Namen an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Ausschließen

Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b.. Platzhalterzeichen sind zulässig. Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Filter

Gibt einen Filter zum Qualifizieren des **path** -Parameters an. Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt. Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.
Die Implementierung unterscheidet sich bei den einzelnen Anbietern.
Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include

Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt. Der Wert dieses Parameters qualifiziert den **Path** -Parameter. Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b.. Platzhalterzeichen sind zulässig. Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Literalpath

Gibt einen Pfad zu einem oder mehreren Speicherorten an. Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zum aktuellen Speicherort der Elemente an.
Der Standardwert ist das aktuelle Verzeichnis.
Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

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

Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` . Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.

## AUSGABEN

### None oder ein Objekt, das das verschoderte Element darstellt.

Wenn Sie den *passthru* -Parameter verwenden, generiert dieses Cmdlet ein Objekt, das das verschoderte Element darstellt.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

- Mit diesem Cmdlet werden Dateien Zwischenlauf Werken verschoben, die vom gleichen Anbieter unterstützt werden. die Verzeichnisse werden jedoch nur auf demselben Laufwerk verschoben.
- Da `Move-Item` mit einem Befehl die Eigenschaften, Inhalte und untergeordneten Elemente eines Elements verschoben werden, sind alle Verschiebungen standardmäßig rekursiv.
- Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.
  Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .
  Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## VERWANDTE LINKS

[Clear-Item](Clear-Item.md)

[Copy-Item](Copy-Item.md)

[Get-Item](Get-Item.md)

[Invoke-Item](Invoke-Item.md)

[New-Item](New-Item.md)

[Remove-Item](Remove-Item.md)

[Rename-Item](Rename-Item.md)

[Set-Item](Set-Item.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)
