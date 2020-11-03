---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/start-transcript?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transcript
ms.openlocfilehash: 5f964cec2458309eb736bf2d2930fc65a72b0fe4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211159"
---
# Start-Transcript

## ZUSAMMENFASSUNG
Erstellt einen Datensatz einer gesamten oder eines Teils einer PowerShell-Sitzung in einer Textdatei.

## SYNTAX

### Bypath (Standard)

```
Start-Transcript [[-Path] <String>] [-Append] [-Force] [-NoClobber] [-IncludeInvocationHeader]
 [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### Byliteralpath

```
Start-Transcript [[-LiteralPath] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

### Byoutputdirectory

```
Start-Transcript [[-OutputDirectory] <String>] [-Append] [-Force] [-NoClobber]
 [-IncludeInvocationHeader] [-UseMinimalHeader] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## DESCRIPTION

Das- `Start-Transcript` Cmdlet erstellt einen Datensatz einer gesamten oder eines Teils einer PowerShell-Sitzung in einer Textdatei. Die Aufzeichnung enthält alle Befehle, die der Benutzer eingibt, und alle Ausgaben, die auf der Konsole angezeigt werden.

Ab Windows PowerShell 5,0 `Start-Transcript` schließt den Hostnamen in den generierten Dateinamen aller Transkriptionen ein. Dies ist besonders nützlich, wenn die Protokollierung Ihres Unternehmens zentralisiert ist.
Dateien, die vom `Start-Transcript` Cmdlet erstellt werden, enthalten zufällige Zeichen in Namen, um potenzielle über schreibungen oder Duplizierungen zu vermeiden, wenn zwei oder mehr Transkriptionen gleichzeitig gestartet werden.
Dies verhindert auch eine nicht autorisierte Ermittlung von Transkriptionen, die in einer zentralisierten Dateifreigabe gespeichert sind.

## BEISPIELE

### Beispiel 1: Starten einer Transkriptions Datei mit Standardeinstellungen

```powershell
Start-Transcript
```

Dieser Befehl startet eine Aufzeichnung am Standarddateispeicherort.

### Beispiel 2: Starten einer Transkriptions Datei an einem bestimmten Speicherort

```powershell
Start-Transcript -Path "C:\transcripts\transcript0.txt" -NoClobber
```

Dieser Befehl startet eine Aufzeichnung in der `Transcript0.txt` Datei in `C:\transcripts` . Da der **noClobber** -Parameter verwendet wird, verhindert der Befehl, dass vorhandene Dateien überschrieben werden. Wenn die `Transcript0.txt` Datei bereits vorhanden ist, schlägt der Befehl fehl.

## PARAMETERS

### -Anfügen

Gibt an, dass dieses Cmdlet die neue Aufzeichnung am Ende einer vorhandenen Datei hinzufügt. Verwenden Sie den **path** -Parameter, um die Datei anzugeben.

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

### -Force

Erlaubt dem Cmdlet, die Aufzeichnung an eine vorhandene schreibgeschützte Datei anzuhängen. Bei Anwendung auf eine schreibgeschützte Datei ändert das Cmdlet die Dateiberechtigung in „Lesen/Schreiben“. Das Cmdlet kann Sicherheitseinschränkungen nicht überschreiben, wenn dieser Parameter verwendet wird.

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

### -Includeinvocationheader

Gibt an, dass dieses Cmdlet den Zeitstempel beim Ausführen von Befehlen protokolliert.

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

### -Useminimalheader

Fügen Sie dem Transkripts anstelle des standardmäßig enthaltenen ausführlichen Headers einen kurzen Header vorangestellt. Dieser Parameter wurde in PowerShell 6,2 hinzugefügt.

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

### -Literalpath

Gibt einen Speicherort für die Transkriptions Datei an. Im Gegensatz zum **Path** -Parameter wird der Wert des **LiteralPath** -Parameters genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen informieren PowerShell darüber, dass keine Zeichen als Escapesequenzen interpretiert werden können.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

Gibt an, dass von diesem Cmdlet keine vorhandene Datei überschrieben wird. Wenn eine Transkriptions Datei im angegebenen Pfad vorhanden ist, wird `Start-Transcript` die Datei standardmäßig ohne Warnung überschrieben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputDirectory

Gibt einen bestimmten Pfad und Ordner an, in dem ein Transkript gespeichert werden soll. Der Transkriptions Name wird von PowerShell automatisch zugewiesen.

```yaml
Type: System.String
Parameter Sets: ByOutputDirectory
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt einen Speicherort für die Transkriptions Datei an. Geben Sie einen Pfad zu einer `.txt` Datei ein. Platzhalter sind nicht zulässig.

Wenn Sie keinen Pfad angeben, `Start-Transcript` verwendet den Pfad im Wert der `$Transcript` globalen Variablen. Wenn Sie diese Variable nicht erstellt haben, `Start-Transcript` speichert die Transkriptionen in den `$Home\My Documents directory as \PowerShell_transcript.<time-stamp>.txt` Dateien.

Wenn eines der Verzeichnisse im Pfad nicht vorhanden ist, tritt bei der Ausführung des Befehls ein Fehler auf.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System.String

Dieses Cmdlet gibt eine Zeichenfolge zurück, die eine Bestätigungsmeldung und den Pfad zur Ausgabedatei enthält.

## HINWEISE

Verwenden Sie das-Cmdlet, um eine Aufzeichnung zu verhindern `Stop-Transcript` .

Fügen Sie dem Profil den Befehl hinzu, um eine ganze Sitzung aufzuzeichnen `Start-Transcript` . Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

## VERWANDTE LINKS

[Stop-Transcript](Stop-Transcript.md)
