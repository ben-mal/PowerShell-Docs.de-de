---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Process
ms.openlocfilehash: 4efa22e8f2a7339e381d92270c1b127054c219cb
ms.sourcegitcommit: 11abf355ac545531c2b04217a08ebe6be609c0bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "93220004"
---
# Stop-Process

## ZUSAMMENFASSUNG
Beendet ausgeführte Prozesse.

## SYNTAX

### ID (Standard)

```
Stop-Process [-Id] <Int32[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Name

```
Stop-Process -Name <String[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Stop-Process [-InputObject] <Process[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das Cmdlet " **Stopp-Process** " beendet mindestens einen laufenden Prozess.
Sie können einen Prozess anhand des Prozess namens oder der Prozess-ID (PID) angeben oder ein Prozess Objekt an "Process **-Process** " übergeben.
" **Beendet-Process** " funktioniert nur bei Prozessen, die auf dem lokalen Computer ausgeführt werden.

Unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option als Administrator ausführen starten, um einen Prozess zu verhindern, der nicht im Besitz des aktuellen Benutzers ist.
Außerdem werden Sie nicht zur Bestätigung aufgefordert, es sei denn, Sie geben den *Confirm* -Parameter an.

## BEISPIELE

### Beispiel 1: alle Instanzen eines Prozesses werden beendet

```
PS C:\> Stop-Process -Name "notepad"
```

Mit diesem Befehl werden alle Instanzen des Notepad-Prozesses (Editor) auf dem Computer beendet.
Jede Instanz von Editor wird in einem eigenen Prozess ausgeführt.
Er verwendet den *Name* -Parameter, um die Prozesse anzugeben, die alle den gleichen Namen aufweisen.
Wenn Sie den *ID* -Parameter verwenden, um die gleichen Prozesse anzuhalten, müssten Sie die Prozess-IDs jeder Instanz von Notepad auflisten.

### Beispiel 2: beendet eine bestimmte Instanz eines Prozesses.

```
PS C:\> Stop-Process -Id 3952 -Confirm -PassThru
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "notepad (3952)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):y
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
41       2      996       3212    31            3952 notepad
```

Mit diesem Befehl wird eine bestimmte Instanz des Notepad-Prozesses beendet.
Der Prozess wird mit der Prozess-ID 3952 angegeben.
Der *Confirm* -Parameter weist PowerShell an, Sie einzugeben, bevor der Prozess beendet wird.
Da die Eingabeaufforderung neben der ID auch den Prozessnamen enthält, ist dies die bewährte Vorgehensweise.
Der *passthru* -Parameter übergibt das Prozess Objekt zur Anzeige an den Formatierer.
Ohne diesen Parameter wird nach einem Befehl zum **Abbrechen des Vorgangs** keine Anzeige angezeigt.

### Beispiel 3: Beenden eines Prozesses und erkennen, dass er beendet wurde

```
PS C:\> calc
PS C:\> $p = Get-Process -Name "calc"
PS C:\> Stop-Process -InputObject $p
PS C:\> Get-Process | Where-Object {$_.HasExited}
```

Mit dieser Reihe von Befehlen wird der Calc-Prozess gestartet und beendet. Anschließend werden Prozesse erkannt, die beendet wurden.

Mit dem ersten Befehl wird eine Instanz des Rechners gestartet.

Der zweite Befehl verwendet **Get-Process** und ruft ein Objekt ab, das den Calc-Prozess darstellt, und speichert es dann in der $p-Variablen.

Mit dem dritten Befehl wird der Calc-Prozess beendet.
Er verwendet den *Inputobject* -Parameter, um das Objekt an " **Process-Process** " zu übergeben.

Mit dem letzten Befehl werden alle zuvor auf dem Computer ausgeführten Prozesse abgerufen, die nun beendet sind.
Er verwendet **Get-Process** , um alle Prozesse auf dem Computer zu erhalten.
Der Pipeline Operator (|) übergibt die Ergebnisse an das Where-Object-Cmdlet, das diejenigen auswählt, bei denen der Wert der **HasExited** -Eigenschaft $true ist.
**HasExited** ist nur eine Eigenschaft von Process-Objekten.
Um alle Eigenschaften zu suchen, geben Sie ein `Get-Process | Get-Member` .

### Beispiel 4: Beendigung eines Prozesses, der nicht im Besitz des aktuellen Benutzers ist

```
PS C:\> Get-Process -Name "lsass" | Stop-Process

Stop-Process : Cannot stop process 'lsass (596)' because of the following error: Access is denied
At line:1 char:34
+ Get-Process -Name "lsass" | Stop-Process <<<<

[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process

Warning!
Are you sure you want to perform this action?
Performing operation 'Stop-Process' on Target 'lsass(596)'
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process -Force
[ADMIN]: PS C:\>
```

Diese Befehle zeigen die Auswirkung der Verwendung von *Force* zum Abbrechen eines Prozesses, der nicht im Besitz des Benutzers ist.

Der erste Befehl verwendet **Get-Process** , um den LSASS-Prozess zu erhalten.
Ein Pipeline Operator sendet den Prozess an den Prozess **zum Abbrechen, um ihn** zu verhindern.
Wie in der Beispielausgabe gezeigt, schlägt der erste Befehl mit der Meldung "Zugriff verweigert" fehl, da dieser Vorgang nur von einem Mitglied der Administrator Gruppe auf dem Computer beendet werden kann.

Wenn PowerShell mit der Option als Administrator ausführen geöffnet wird und der Befehl wiederholt wird, werden Sie von PowerShell zur Bestätigung aufgefordert.

Der zweite Befehl gibt *Force* an, um die Eingabeaufforderung zu unterdrücken.
Der Prozess wird daher ohne Bestätigung beendet.

## PARAMETERS

### -Force

Beendet die angegebenen Prozesse, ohne zum Bestätigen aufzufordern.
Standardmäßig fordert **Stop-Process** vor dem Beenden eines Prozesses, der nicht im Besitz des aktuellen Benutzers ist, zur Bestätigung auf.

Um den Besitzer eines Prozesses zu suchen, verwenden Sie das `Get-CimInstance` Cmdlet, um ein **Win32_Process** Objekt zu erhalten, das den Prozess darstellt, und verwenden Sie dann die **GetOwner** -Methode des Objekts.

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

### -Id

Gibt die Prozess-IDs der Prozesse an, die beendet werden sollen.
Wenn Sie mehrere IDs angeben, trennen Sie diese durch Kommas.
Um die PID eines Prozesses zu ermitteln, geben Sie ein `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Gibt die Prozess Objekte an, die beendet werden sollen.
Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die Prozessnamen der zu stoppenden Prozesse an.
Sie können mehrere Prozessnamen eingeben, durch Kommas getrennt oder Platzhalter Zeichen verwenden.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

Gibt ein Objekt zurück, das den Prozess darstellt.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### System.Diagnostics.Process

Sie können ein Prozess Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### None, System. Diagnostics. Process

Dieses Cmdlet gibt ein **System. Diagnostics. Process** -Objekt zurück, das den beendeten Prozess darstellt, wenn Sie den *passthru* -Parameter angeben.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* Weitere Informationen finden Sie auch unter **Beenden/verarbeiten** durch die integrierten Aliase, **Kill** und **SPPS**. Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.

  Sie können auch die Eigenschaften und Methoden des Windows-Verwaltungsinstrumentation (WMI) **Win32_Process** -Objekts in Windows PowerShell verwenden.
Weitere Informationen finden Sie unter `Get-CimInstance` und im WMI SDK.

* Wenn Sie Prozesse beenden, beachten Sie, dass durch das Beenden eines Prozesses Prozess und Dienste angehalten werden können, die vom Prozess abhängen.
Im Extremfall kann durch Beenden eines Prozesses sogar Windows beendet werden.

## VERWANDTE LINKS

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
