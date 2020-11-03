---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: e6acb18799646a2e238237d3879198e3a78e7f9a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216228"
---
# Set-TraceSource

## ZUSAMMENFASSUNG
Konfiguriert, startet und beendet eine Ablauf Verfolgung von PowerShell-Komponenten.

## SYNTAX

### optionsset (Standard)

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### removealllistenersset

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### removefilelistenersset

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das Cmdlet " **Set-TraceSource** " konfiguriert, startet und beendet eine Ablauf Verfolgung einer PowerShell-Komponente.
Sie können mit ihm angeben, welche Komponenten verfolgt werden sollen und an welches Element die Ausgabe der Ablaufverfolgung gesendet werden soll.

## BEISPIELE

### Beispiel 1: Ablauf Verfolgung der ParameterBinding-Komponente

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

Dieser Befehl startet die Ablauf Verfolgung für die ParameterBinding-Komponente von PowerShell.
Er verwendet den *Name* -Parameter, um die Ablauf Verfolgungs Quelle anzugeben, den *Option* -Parameter zur Auswahl der executionflow-Ablauf Verfolgungs Ereignisse und den *pshost* -Parameter, um den PowerShell-hostlistener auszuwählen, der die Ausgabe an die Konsole sendet.
Der *listeneroption* -Parameter fügt die ProcessID-und timestamp-Werte zum Präfix der Ablauf Verfolgungs Meldung hinzu.

### Beispiel 2: Abbrechen einer Ablauf Verfolgung

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

Dieser Befehl beendet die Ablauf Verfolgung der ParameterBinding-Komponente von PowerShell.
Er verwendet den *Name* -Parameter, um die Komponente zu identifizieren, die verfolgt wurde, und den *RemoveListener* -Parameter, um den Ablaufverfolgungslistener

## PARAMETERS

### -Debugger

Gibt an, dass das Cmdlet die Ablauf Verfolgungs Ausgabe an den Debugger sendet.
Sie können die Ausgabe in jedem Benutzer- oder Kernelmodusdebugger oder in Microsoft Visual Studio anzeigen.
Dieser Parameter wählt auch den Standard-Ablaufverfolgungslistener aus.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Gibt eine Datei an, an die dieses Cmdlet die Ablauf Verfolgungs Ausgabe sendet.
Dieser Parameter wählt auch den Ablaufverfolgungslistener der Datei aus.
Wenn Sie diesen Parameter verwenden, um die Ablauf Verfolgung zu starten, verwenden Sie den *removefilelistener* -Parameter, um die Ablauf Verfolgung zu verhindern.

```yaml
Type: System.String
Parameter Sets: optionsSet
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Gibt an, dass das Cmdlet eine schreibgeschützte Datei überschreibt.
Verwenden Sie mit dem *FilePath* -Parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Listeneroption

Gibt optionale Daten für das Präfix der einzelnen Ablauf Verfolgungs Meldungen in der Ausgabe an.
Zulässige Werte für diesen Parameter:

- Keine
- LogicalOperationStack
- Datetime
- Timestamp
- ProcessId
- ThreadID
- Aufruf Liste

"None" ist die Standardeinstellung.

Um mehrere Optionen anzugeben, trennen Sie diese durch Kommas, aber ohne Leerzeichen, und schließen Sie sie in Anführungszeichen ein, z. B. "ProcessID,ThreadID".

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt an, welche Komponenten verfolgt werden.
Geben Sie den Namen der Ablaufverfolgungsquelle jeder Komponente ein.
Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Option

Gibt den Typ der Ereignisse an, die nachverfolgt werden.
Zulässige Werte für diesen Parameter:

- Keine
- Konstruktor
- Dispose
- Finalizer
- Methode
- Eigenschaft
- Delegaten
- Ereignisse
- Ausnahme
- Sperre
- Fehler
- Errors
- Warnung
- Ausführlich
- WriteLine
- Daten
- `Scope`
- ExecutionFlow
- Assert
- Alle

„All“ ist die Standardeinstellung.

Die folgenden Werte sind Kombinationen von anderen Werten:

- Executionflow: (Konstruktor, verwerfen, Finalizer, Methode, Delegaten, Ereignisse und Bereich)
- Daten: (Konstruktor, verwerfen, Finalizer, Property, verbose und Write teline)
- Fehler: (Fehler und Ausnahme).

Um mehrere Optionen anzugeben, trennen Sie diese durch Kommas, aber ohne Leerzeichen, und schließen Sie sie in Anführungszeichen ein, z. B. "Constructor,Dispose".

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pshost

Gibt an, dass dieses Cmdlet die Ablauf Verfolgungs Ausgabe an den PowerShell-Host sendet.
Dieser Parameter wählt auch den PSHost-Ablaufverfolgungslistener aus.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Removefilelistener

Beendet die Ablaufverfolgung durch Entfernen des Datei-Ablaufverfolgungslisteners, der der angegebenen Datei zugeordnet ist.
Geben Sie den Pfad und den Dateinamen der Ablaufverfolgungsausgabe-Datei an.

```yaml
Type: System.String[]
Parameter Sets: removeFileListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveListener

Beendet die Ablaufverfolgung durch Entfernen des Ablaufverfolgungslisteners.

Verwenden Sie für *RemoveListener* die folgenden Werte:

- Um pshost (Console) zu entfernen, geben Sie ein `Host` .
- Um den Debugger zu entfernen, geben Sie ein `Debug` .
- Um alle Ablaufverfolgungslistener zu entfernen, `*`

Zum Entfernen des dateiablaufverfolgungslistener verwenden Sie den *removefilelistener* -Parameter.

```yaml
Type: System.String[]
Parameter Sets: removeAllListenersSet
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

Sie können eine Zeichenfolge, die einen Namen enthält, über die Pipeline an **Set-TraceSource** übergeben.

## AUSGABEN

### None oder System. Management. Automation. pstracesource

Wenn Sie den *passthru* -Parameter verwenden, generiert **Set-TraceSource** ein **System. Management. Automation. pstracesource** -Objekt, das die Ablauf Verfolgungs Sitzung darstellt.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* Die Ablaufverfolgung ist eine Methode, die Entwickler zum Debuggen und Optimieren von Programmen verwenden. Bei der Ablaufverfolgung erzeugt das Programm ausführliche Meldungen zu den einzelnen Schritten in der internen Verarbeitung.

  Die PowerShell-Ablaufverfolgungs-Cmdlets sind für die Unterstützung von PowerShell-Entwicklern konzipiert, aber Sie stehen allen Benutzern zur Verfügung.
Mit Ihnen können Sie fast jeden Aspekt der Funktionalität von PowerShell überwachen.

  Eine Ablauf Verfolgungs Quelle ist der Teil jeder PowerShell-Komponente, die die Ablauf Verfolgung verwaltet und Ablauf Verfolgungs Meldungen für die Komponente generiert.
Um eine Komponente zu verfolgen, identifizieren Sie die Ablaufverfolgungsquelle.

  Ein Ablaufverfolgungslistener empfängt die Ausgabe der Ablauf Verfolgung und zeigt Sie dem Benutzer an.
Sie können festlegen, dass die Ablauf Verfolgungs Daten an einen Benutzermodus-oder Kernel Modus-Debugger, an die Konsole, an eine Datei oder an einen benutzerdefinierten Listener gesendet werden, der von der **System. Diagnostics. TraceListener** -Klasse abgeleitet wird.

* Um eine Ablauf Verfolgung zu starten, verwenden Sie den *Name* -Parameter, um eine Ablauf Verfolgungs Quelle und die Parameter *FilePath* , *Debugger* oder *pshost* anzugeben, um einen Listener anzugeben (ein Ziel für die Ausgabe). Verwenden Sie den *options* -Parameter, um die Typen der Ablauf Verfolgungs Ereignisse zu bestimmen, und den *listeneroption* -Parameter, um die Ablauf Verfolgungs Ausgabe zu konfigurieren.
* Um die Konfiguration einer Ablauf Verfolgung zu ändern, geben Sie einen **Set-TraceSource-** Befehl ein, wie Sie eine Ablauf Verfolgung starten würden. PowerShell erkennt, dass die Ablauf Verfolgungs Quelle bereits verfolgt wird. Es beendet die Ablaufverfolgung, fügt die neue Konfiguration hinzu und startet die Ablaufverfolgung erneut.
* Um eine Ablauf Verfolgung zu verhindern, verwenden Sie den *RemoveListener* -Parameter. Um eine Ablauf Verfolgung zu verhindern, die den dateilistener verwendet (eine Ablauf Verfolgung, die mit dem *FilePath* -Parameter gestartet wurde), verwenden Sie den *removefilelistener* -Parameter. Wenn Sie den Listener entfernen, wird die Ablaufverfolgung beendet.
* Um zu bestimmen, welche Komponenten verfolgt werden können, verwenden Sie Get-TraceSource. Die Ablauf Verfolgungs Quellen für jedes Modul werden automatisch geladen, wenn die Komponente verwendet wird, und Sie werden in der Ausgabe von " **Get-TraceSource** " angezeigt.

## VERWANDTE LINKS

[Get-TraceSource](Get-TraceSource.md)

[Trace-Command](Trace-Command.md)
