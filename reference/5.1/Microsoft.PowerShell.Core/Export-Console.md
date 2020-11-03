---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-console?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Console
ms.openlocfilehash: 7b643b5f9b6868a5da988b19b65dead24f986f67
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212060"
---
# Export-Console

## ZUSAMMENFASSUNG
Exportiert die Namen von Snap-Ins in der aktuellen Sitzung in eine Konsolendatei.

## SYNTAX

```
Export-Console [[-Path] <String>] [-Force] [-NoClobber] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **Export-Console-** Cmdlet exportiert die Namen der Windows PowerShell-Snap-Ins in der aktuellen Sitzung in eine Windows PowerShell-Konsolen Datei (. psc1).
Sie können dieses Cmdlet verwenden, um die Snap-Ins für die Verwendung in zukünftigen Sitzungen zu speichern.

Wenn Sie die Snap-Ins in der Konsolen Datei. psc1 zu einer Sitzung hinzufügen möchten, starten Sie Windows PowerShell (Powershell.exe) in der Befehlszeile, indem Sie Cmd.exe oder eine andere Windows PowerShell-Sitzung verwenden, und verwenden Sie dann den *PsConsoleFile* -Parameter von Powershell.exe, um die Konsolen Datei anzugeben.

Weitere Informationen zu Windows PowerShell-Snap-Ins finden Sie unter „about_PSSnapins“.

## BEISPIELE

### Beispiel 1: Exportieren der Namen von Snap-Ins in der aktuellen Sitzung

```
PS C:\> Export-Console -Path $pshome\Consoles\ConsoleS1.psc1
```

Dieser Befehl exportiert die Namen der Windows PowerShell-Snap-Ins in der aktuellen Sitzung in die Datei "consoles1. psc1 im Ordner Konsolen des Windows PowerShell-Installations Ordners, $PSHome.

### Beispiel 2: Exportieren der Namen von Snap-Ins in die aktuellste Konsolen Datei

```
PS C:\> Export-Console
```

Dieser Befehl exportiert die Namen der Windows PowerShell-Snap-Ins aus der aktuellen Sitzung in die Windows PowerShell-Konsolendatei, die in der aktuellen Sitzung zuletzt verwendet wurde.
Der vorherige Dateiinhalt wird überschrieben.

Wenn Sie in der aktuellen Sitzung keine Konsolendatei exportiert haben, werden Sie vor dem Fortfahren zur Bestätigung und dann zur Eingabe eines Dateinamens aufgefordert.

### Beispiel 3: Hinzufügen eines Snap-Ins und Exportieren der Namen von Snap-Ins

```
PS C:\> Add-PSSnapin NewPSSnapin
PS C:\> Export-Console -path NewPSSnapinConsole.psc1
PS C:\> powershell.exe -PsConsoleFile NewPsSnapinConsole.psc1
```

Diese Befehle fügen das Windows PowerShell-Snap-In „NewPSSnapin“ zur aktuellen Sitzung hinzu, exportieren die Namen der Windows PowerShell-Snap-Ins in der aktuellen Sitzung in eine Konsolendatei und starten dann eine Windows PowerShell-Sitzung mit der Konsolendatei.

Der erste Befehl verwendet das **Add-PSSnapin** -Cmdlet, um das newpssnapin-Snap-in zur aktuellen Sitzung hinzuzufügen.
Sie können nur Windows PowerShell-Snap-Ins hinzufügen, die in Ihrem System registriert sind.

Der zweite Befehl exportiert die Namen der Windows PowerShell-Snap-Ins in die NewPSSnapinConsole.psc1-Datei.

Der dritte Befehl startet Windows PowerShell mit der NewPSSnapinConsole.psc1-Datei.
Da die Konsolendatei den Namen des Windows PowerShell-Snap-Ins enthält, sind die Cmdlets und Anbieter im Snap-In in der aktuellen Sitzung verfügbar.

### Beispiel 4: Exportieren von Namen von Snap-Ins an einen angegebenen Speicherort

```
PS C:\> export-console -path Console01
PS C:\> notepad console01.psc1
<?xml version="1.0" encoding="utf-8"?>
<PSConsoleFile ConsoleSchemaVersion="1.0">
  <PSVersion>2.0</PSVersion>
  <PSSnapIns>
     <PSSnapIn Name="NewPSSnapin" />
  </PSSnapIns>
</PSConsoleFile>
```

Dieser Befehl exportiert die Namen der Windows PowerShell-Snap-Ins in der aktuellen Sitzung in die Datei „Console01.psc1“ im aktuellen Verzeichnis.

Der zweite Befehl zeigt den Inhalt der Console01.psc1-Datei im Editor an.

### Beispiel 5: Bestimmen der zu Aktualisier-Konsolen Datei

```
PS C:\> powershell.exe -PSConsoleFile Console01.psc1
PS C:\> Add-PSSnapin MySnapin
PS C:\> Export-Console NewConsole.psc1
PS C:\> $ConsoleFileName
PS C:\> Add-PSSnapin SnapIn03
PS C:\> Export-Console
```

In diesem Beispiel wird gezeigt, wie die automatische $ConsoleFileName Variable verwendet wird, um die Konsolen Datei zu bestimmen, die aktualisiert wird, wenn Sie **Export-Console** ohne einen *path* -Parameterwert verwenden.

Der erste Befehl verwendet den *PsConsoleFile* -Parameter von PowerShell.exe, um Windows PowerShell mit der Datei Console01. psc1 zu öffnen.

Der zweite Befehl verwendet das **Add-PSSnapin** -Cmdlet, um das Windows PowerShell-Snap-in "mysnapin" zur aktuellen Sitzung hinzuzufügen.

Der dritte Befehl verwendet das **Export-Console-** Cmdlet, um die Namen aller Windows PowerShell-Snap-Ins in der Sitzung in die newconsole. psc1-Datei zu exportieren.

Der vierte Befehl zeigt die $ConsoleFileName Variable an.
Sie enthält die zuletzt verwendete Konsolen Datei.
Die Beispielausgabe zeigt, dass NewConsole.ps1 die zuletzt verwendete Datei ist.

Der fünfte Befehl fügt „SnapIn03“ zur aktuellen Konsole hinzu.

Der sechste Befehl verwendet das **Export-Console-** Cmdlet ohne *path* -Parameter.
Mit diesem Befehl werden die Namen aller Windows PowerShell-Snap-Ins in der aktuellen Sitzung in die zuletzt verwendete Datei (NewConsole.psc1) exportiert.

## PARAMETERS

### -Force
Gibt an, dass dieses Cmdlet die Daten in einer Konsolen Datei ohne Warnung überschreibt, auch wenn die Datei das schreibgeschützte Attribut aufweist.
Das Read-only-Attribut wird geändert und wird nicht zurückgesetzt, wenn der Befehl abgeschlossen ist.

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

### -NoClobber
Gibt an, dass dieses Cmdlet eine vorhandene Konsolen Datei nicht überschreibt.
Wenn eine Datei im angegebenen Pfad vorkommt, überschreibt **Export-Console** die Datei standardmäßig ohne Warnung.

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

### -Path
Gibt einen Pfad und Dateinamen für die Konsolendatei (*.psc1) an.
Geben Sie einen optionalen Pfad und einen Namen ein.
Platzhalterzeichen sind nicht zulässig.

Wenn Sie nur einen Dateinamen angeben, erstellt **Export-Console** im aktuellen Verzeichnis eine Datei mit diesem Namen und der Dateinamenerweiterung ". psc1".

Dieser Parameter ist erforderlich, es sei denn, Sie haben Windows PowerShell mit dem *PsConsoleFile* -Parameter geöffnet oder während der aktuellen Sitzung eine Konsolen Datei exportiert.
Dies ist auch erforderlich, wenn Sie den *noClobber* -Parameter verwenden, um zu verhindern, dass die aktuelle Konsolen Datei überschrieben wird.

Wenn Sie diesen Parameter weglassen, überschreibt **Export-Console** die Konsolen Datei, die in dieser Sitzung zuletzt verwendet wurde.
Der Pfad der zuletzt verwendeten Konsolen Datei wird im Wert der automatischen $ConsoleFileName Variablen gespeichert.
Weitere Informationen finden Sie unter %%amp;quot;about_Automatic_Variables%%amp;quot;.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System.String
Sie können eine Pfad Zeichenfolge über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### System. IO. fileingefo
Mit diesem Cmdlet wird eine Datei erstellt, die die exportierten Aliase enthält.

## HINWEISE

* Wenn eine Konsolendatei (.psc1) zum Starten der Sitzung verwendet wird, wird der Name der Konsolendatei automatisch in der automatischen $ConsoleFileName-Variablen gespeichert. Der Wert $ConsoleFileName wird aktualisiert, wenn Sie den *path* -Parameter von **Export-Console** verwenden, um eine neue Konsolen Datei anzugeben. Wenn keine Konsolen Datei verwendet wird, hat $ConsoleFileName keinen Wert ($null).

  Um eine Windows PowerShell-Konsolendatei in einer neuen Sitzung zu verwenden, starten Sie Windows PowerShell mit der folgenden Syntax:

  `powershell.exe -PsConsoleFile \<ConsoleFile\>.psc1`

  Sie können Windows PowerShell-Snap-Ins auch für zukünftige Sitzungen speichern, indem Sie einen Add-PSSnapin-Befehl zu Ihrem Windows PowerShell-Profil hinzufügen.
Weitere Informationen finden Sie unter „about_Profiles“.


## VERWANDTE LINKS

[Add-PSSnapin](Add-PSSnapin.md)

[Get-PSSnapin](Get-PSSnapin.md)

[Remove-PSSnapin](Remove-PSSnapin.md)
