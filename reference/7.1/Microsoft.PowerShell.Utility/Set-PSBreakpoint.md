---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-psbreakpoint?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSBreakpoint
ms.openlocfilehash: d4712a945e82a0ba1f2899c679dc0972885de050
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211807"
---
# Set-PSBreakpoint

## ZUSAMMENFASSUNG
Legt einen Haltepunkt in einer Zeile, einem Befehl oder einer Variable fest.

## SYNTAX

### Zeile (Standard)

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Column] <Int32>] [-Line] <Int32[]> [-Script] <String[]>
 [<CommonParameters>]
```

### Get-Help

```
Set-PSBreakpoint [-Action <ScriptBlock>] -Command <String[]> [[-Script] <String[]>] [<CommonParameters>]
```

### Variable

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Script] <String[]>] -Variable <String[]>
 [-Mode <VariableAccessMode>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Set-PSBreakpoint` Cmdlet legt einen Haltepunkt in einem Skript oder in einem beliebigen Befehl fest, der in der aktuellen Sitzung ausgeführt wird. Sie können verwenden, `Set-PSBreakpoint` um einen Haltepunkt festzulegen, bevor Sie ein Skript ausführen oder einen Befehl ausführen oder während des Debuggens an einem anderen Haltepunkt angehalten.

`Set-PSBreakpoint` auf einem Remote Computer kann kein Haltepunkt festgelegt werden. Um ein Skript auf einem Remotecomputer zu debuggen, kopieren Sie das Skript auf den lokalen Computer, und debuggen Sie es dann lokal.

Jeder `Set-PSBreakpoint` Befehl erstellt einen der folgenden drei Haltepunkt Typen:

- Zeilen Haltepunkt: legt Haltepunkte an bestimmten Zeilen-und Spalten Koordinaten fest.
- Command Haltepunkt: legt Haltepunkte für Befehle und Funktionen fest.
- Variable Haltepunkt: legt Haltepunkte für Variablen fest.

Sie können einen Haltepunkt für mehrere Zeilen, Befehle oder Variablen in einem einzelnen Befehl festlegen `Set-PSBreakpoint` , aber jeder `Set-PSBreakpoint` Befehl legt nur einen halte Punkttyp fest.

An einem Haltepunkt beendet PowerShell vorübergehend die Ausführung und übergibt die Steuerung an den Debugger. Die Eingabeaufforderung ändert sich in `DBG\>` , sodass ein Satz von Debugger-Befehlen zur Verwendung verfügbar wird. Sie können jedoch den **Action** -Parameter verwenden, um eine Alternative Antwort anzugeben, z. b. Bedingungen für den Haltepunkt oder Anweisungen, um zusätzliche Aufgaben auszuführen, z. b. Protokollierung oder Diagnose.

Das- `Set-PSBreakpoint` Cmdlet ist eines von mehreren Cmdlets für das Debuggen von PowerShell-Skripts.
Weitere Informationen zum PowerShell-Debugger finden Sie unter [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).

## BEISPIELE

### Beispiel 1: Festlegen eines Breakpoints in einer Zeile

In diesem Beispiel wird ein Haltepunkt in Zeile 5 im Sample.ps1 Skript festgelegt. Wenn das Skript ausgeführt wird, wird die Ausführung unmittelbar vor Ausführung der Zeile 5 angehalten.

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Line 5
```

```output
Column     : 0
Line       : 5
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

Wenn Sie einen neuen Haltepunkt anhand der Zeilennummer festlegen, `Set-PSBreakpoint` generiert das Cmdlet ein Zeilen Haltepunkt Objekt ( **System. Management. Automation. linebreakpoint** ), das die Haltepunkt-ID und Treffer Anzahl enthält.

### Beispiel 2: Festlegen eines Breakpoints für eine Funktion

In diesem Beispiel wird ein Befehls Haltepunkt für die `Increment` Funktion im Cmdlet "Sample.ps1" erstellt. Das Skript wird unmittelbar vor jedem Aufruf der angegebenen Funktion beendet.

```powershell
Set-PSBreakpoint -Command "Increment" -Script "sample.ps1"
```

```Output
Command    : Increment
Action     :
Enabled    : True
HitCount   : 0
Id         : 1
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

Das Ergebnis ist ein Befehlshaltepunktobjekt. Vor dem Ausführen des Skripts ist der Wert der **HitCount** -Eigenschaft 0.

### Beispiel 3: Festlegen eines Breakpoints für eine Variable

In diesem Beispiel wird ein Haltepunkt für die **Server** Variable im Sample.ps1 Skript festgelegt. Er verwendet den **Mode** -Parameter mit dem Wert " **lesewrite** ", um die Ausführung zu beenden, wenn der Wert der Variablen gelesen wird und unmittelbar vor dem Wert geändert wird.

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Variable "Server" -Mode ReadWrite
```

### Beispiel 4: Festlegen eines Breakpoints für jeden Befehl, der mit dem angegebenen Text beginnt

In diesem Beispiel wird ein Haltepunkt für jeden Befehl im Sample.ps1 Skript festgelegt, das mit "Write" beginnt, z `Write-Host` . b..

```powershell
Set-PSBreakpoint -Script Sample.ps1 -Command "write*"
```

### Beispiel 5: Festlegen eines Breakpoints in Abhängigkeit vom Wert einer Variablen

In diesem Beispiel wird die Ausführung an der- `DiskTest` Funktion im Test.ps1 Skript nur beendet, wenn der Wert der- `$Disk` Variablen größer als 2 ist.

```powershell
Set-PSBreakpoint -Script "test.ps1" -Command "DiskTest" -Action { if ($Disk -gt 2) { break } }
```

Der Wert der **Aktion** ist ein Skriptblock, der den Wert der `$Disk` Variablen in der Funktion testet.

Die Aktion verwendet das- `break` Schlüsselwort, um die Ausführung zu verhindern, wenn die Bedingung erfüllt ist. Die Alternative (und die Standardeinstellung) lautet " **Continue** ".

### Beispiel 6: Festlegen eines Breakpoints für eine Funktion

In diesem Beispiel wird ein Breakpoint für die-Funktion festgelegt `CheckLog` . Da der Befehl kein Skript angibt, wird der Haltepunkt für alles festgelegt, was in der aktuellen Sitzung ausgeführt wird. Der Debugger wird unterbrochen, sobald die Funktion aufgerufen wird, nicht wenn sie deklariert wird.

```
PS> Set-PSBreakpoint -Command "checklog"
Id       : 0
Command  : checklog
Enabled  : True
HitCount : 0
Action   :

function CheckLog {
>> get-eventlog -log Application |
>> where {($_.source -like "TestApp") -and ($_.Message -like "*failed*")}
>>}
>>
PS> Checklog
DEBUG: Hit breakpoint(s)
DEBUG:  Function breakpoint on 'prompt:Checklog'
```

### Beispiel 7: Festlegen von Breakpoints in mehreren Zeilen

In diesem Beispiel werden drei Zeilen-Haltepunkte im Sample.ps1 Skript festgelegt. Es wird ein Haltepunkt in Spalte 2 für jede im Skript angegebene Zeile festgelegt. Die im **Action** -Parameter angegebene Aktion gilt für alle Breakpoints.

```powershell
PS C:\> Set-PSBreakpoint -Script "sample.ps1" -Line 1, 14, 19 -Column 2 -Action {&(log.ps1)}
```

```Output
Column     : 2
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 6
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 14
Action     :
Enabled    : True
HitCount   : 0
Id         : 7
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 19
Action     :
Enabled    : True
HitCount   : 0
Id         : 8
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

## PARAMETERS

### -Action

Gibt die Befehle an, die an jedem Haltepunkt ausgeführt werden, anstatt unterbrochen zu werden. Geben Sie einen Skriptblock ein, der die Befehle enthält. Sie können diesen Parameter verwenden, um bedingte Haltepunkte festzulegen oder um andere Aufgaben auszuführen, z. B. Tests oder Protokollierung.

Wenn dieser Parameter nicht festgelegt ist oder keine Aktion angegeben ist, wird die Ausführung am Haltepunkt beendet, und der Debugger startet.

Wenn der **Action** -Parameter verwendet wird, wird der Action-Skriptblock an jedem Haltepunkt ausgeführt. Die Ausführung wird nicht beendet, es sei denn, der Skriptblock enthält das Schlüsselwort „Break“. Wenn Sie im Skriptblock das Schlüsselwort „Continue“ verwenden, wird die Ausführung bis zum nächsten Haltepunkt fortgesetzt.

Weitere Informationen finden Sie unter [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md)und [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Spalte

Gibt die Spaltennummer der Spalte in der Skriptdatei an, bei der die Ausführung angehalten wird. Geben Sie nur eine Spaltennummer an. Der Standardwert ist „Spalte 1“.

Der Spaltenwert wird zusammen mit dem Wert des **Line** -Parameters verwendet, um den Breakpoint anzugeben. Wenn der **Line** -Parameter mehrere Zeilen angibt, legt der **Column** -Parameter einen Haltepunkt in der angegebenen Spalte in jeder der angegebenen Zeilen fest. PowerShell beendet die Ausführung vor der Anweisung oder dem Ausdruck, die das Zeichen an der angegebenen Zeilen-und Spaltenposition enthält.

Spalten werden vom oberen linken Rand aus beginnend mit Spaltennummer 1 (nicht 0) gezählt. Wenn Sie eine Spalte angeben, die sich nicht im Skript befindet, wird kein Fehler ausgegeben, doch der Haltepunkt wird nie ausgeführt.

```yaml
Type: System.Int32
Parameter Sets: Line
Aliases:

Required: False
Position: 2
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

Legt einen Befehlshaltepunkt fest. Geben Sie Cmdlet-Namen ein, z `Get-Process` . b. oder Funktionsnamen. Platzhalter sind zulässig.

Die Ausführung wird sofort angehalten, bevor jede Instanz des jeweiligen Befehls ausgeführt wird. Wenn der Befehl eine Funktion ist, wird die Ausführung jedes Mal angehalten, wenn die Funktion aufgerufen wird, sowie bei jedem BEGIN-, PROCESS- und END-Abschnitt.

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases: C

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Zeile

Legt einen Zeilenhaltepunkt in einem Skript fest. Geben Sie mindestens eine durch Kommas getrennte Zeilennummer ein. PowerShell wird unmittelbar vor der Ausführung der Anweisung angehalten, die in jeder der angegebenen Zeilen beginnt.

Zeilen werden vom oberen linken Rand der Skriptdatei aus beginnend mit Zeilennummer 1 (nicht 0) gezählt.
Wenn Sie eine leere Zeile angeben, endet die Ausführung vor der nächsten nicht leeren Zeile. Wenn die Zeile außerhalb des Bereichs liegt, wird der Haltepunkt niemals erreicht.

```yaml
Type: System.Int32[]
Parameter Sets: Line
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode

Gibt den Zugriffsmodus an, durch den Variablen Breakpoints ausgelöst werden. Der Standardwert ist " **Write** ".

Dieser Parameter ist nur gültig, wenn der **Variable** -Parameter im Befehl verwendet wird. Der Modus gilt für alle im Befehl festgelegten Haltepunkte. Zulässige Werte für diesen Parameter:

- **Write** -stoppt die Ausführung unmittelbar bevor ein neuer Wert in die Variable geschrieben wird.
- **Lese** Vorgänge werden ausgeführt, wenn die Variable gelesen wird, d. h. wenn auf den Wert zugegriffen wird, um zugewiesen, angezeigt oder verwendet zu werden. Im Lesemodus wird die Ausführung nicht beendet, wenn sich der Wert der Variablen ändert.
- Lesende **Vorgang: beendet** die Ausführung, wenn die Variable gelesen oder geschrieben wird.

```yaml
Type: System.Management.Automation.VariableAccessMode
Parameter Sets: Variable
Aliases:
Accepted values: Read, Write, ReadWrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skript

Gibt ein Array von Skriptdateien an, in denen dieses Cmdlet einen Haltepunkt festlegt. Geben Sie die Pfade und Dateinamen von mindestens einer Datei ein. Wenn die Dateien sich im aktuellen Verzeichnis befinden, können Sie den Pfad weglassen.
Platzhalter sind zulässig.

Standardmäßig werden Variablenhaltepunkte und Befehlshaltepunkte für einen beliebigen Befehl festgelegt, der in der aktuellen Sitzung ausgeführt wird. Dieser Parameter ist nur erforderlich, wenn Sie einen Zeilenhaltepunkt festlegen.

```yaml
Type: System.String[]
Parameter Sets: Line, Command, Variable
Aliases:

Required: True (Line), False (Command, Variable)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Variable

Gibt ein Array von Variablen an, auf die dieses Cmdlet Breakpoints festlegt. Geben Sie eine durch Trennzeichen getrennte Liste der Variablen ohne Dollarzeichen ( `$` ) ein.

Verwenden Sie den **Mode** -Parameter, um den Zugriffsmodus zu bestimmen, der die Breakpoints auslöst. Der Standardmodus „Write“ beendet die Ausführung, kurz bevor ein neuer Wert in die Variable geschrieben wird.

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases: V

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Eingaben können nicht an übergeben werden `Set-PSBreakpoint` .

## AUSGABEN

### Breakpoint-Objekt (System. Management. Automation. linebreakpoint, System. Management. Automation. variablebreakpoint, System. Management. Automation. commandbreakpoint)

`Set-PSBreakpoint` Gibt ein-Objekt zurück, das jeden von ihm festgelegt Haltepunkt darstellt.

## HINWEISE

- `Set-PSBreakpoint` auf einem Remote Computer kann kein Haltepunkt festgelegt werden. Um ein Skript auf einem Remotecomputer zu debuggen, kopieren Sie das Skript auf den lokalen Computer, und debuggen Sie es dann lokal.
- Wenn Sie einen Haltepunkt für mehr als eine Zeile, einen Befehl oder eine Variable festlegen, `Set-PSBreakpoint` generiert ein Haltepunkt Objekt für jeden Eintrag.
- Beim Festlegen eines Haltepunkts für eine Funktion oder Variable an der Eingabeaufforderung können Sie den Haltepunkt festlegen, bevor oder nachdem Sie die Funktion oder Variable erstellen.

## VERWANDTE LINKS

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

