---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/01/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: 5880ded4ea7b6c901f9d242dfe19db2a2a4f6c7d
ms.sourcegitcommit: 5b48fe7b2593581b7d4f7dd7c22206d8a45bb8af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "106184357"
---
# Trace-Command

## Übersicht
Konfiguriert und startet eine Ablaufverfolgung des angegebenen Ausdrucks oder Befehls.

## Syntax

### expressionset (Standard)

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### commandSet

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## BESCHREIBUNG

Das `Trace-Command` -Cmdlet konfiguriert und startet eine Ablauf Verfolgung des angegebenen Ausdrucks oder Befehls.
Es funktioniert wie Set-TraceSource, mit dem Unterschied, dass es nur für den angegebenen Befehl gilt.

## Beispiele

### Beispiel 1: Verarbeitung von Ablauf Verfolgungs Metadaten, Parameter Bindung und ein Ausdruck

In diesem Beispiel wird eine Ablauf Verfolgung der Metadatenverarbeitung, der Parameter Bindung und der Cmdlet-Erstellung und-Zerstörung des `Get-Process Notepad` Ausdrucks gestartet.

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

Er verwendet den **Name** -Parameter zum Angeben der Ablauf Verfolgungs Quellen, den **Expression** -Parameter zur Angabe des Befehls und den **pshost** -Parameter, um die Ausgabe an die Konsole zu senden. Da keine Ablauf Verfolgungs Optionen oder Listeneroptionen angegeben werden, verwendet der Befehl die Standardwerte:

- Alle für die Ablauf Verfolgungs Optionen
- Keine für die Listeneroptionen

### Beispiel 2: Verfolgen der Aktionen von ParameterBinding-Vorgängen

In diesem Beispiel werden die Aktionen der **ParameterBinding** -Vorgänge von PowerShell nachverfolgt, während ein-Ausdruck verarbeitet wird `Get-Alias` , der Eingaben aus der Pipeline annimmt.

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

In `Trace-Command` übergibt der **Inputobject** -Parameter ein Objekt an den Ausdruck, der während der Ablauf Verfolgung verarbeitet wird.

Der erste Befehl speichert die Zeichenfolge `i*` in der `$A` Variablen. Der zweite Befehl verwendet das `Trace-Command` Cmdlet mit der ParameterBinding-Ablauf Verfolgungs Quelle. Der **pshost** -Parameter sendet die Ausgabe an die Konsole.

Der Ausdruck, der verarbeitet wird `Get-Alias $Input` , ist, wobei die `$Input` Variable dem **Inputobject** -Parameter zugeordnet ist. Der **Inputobject** -Parameter übergibt die Variable `$A` an den Ausdruck. Tatsächlich ist der Befehl, der während der Ablauf Verfolgung verarbeitet wird, `Get-Alias -InputObject $A" or "$A | Get-Alias` .

## Parameter

### -Argumentlist

Gibt die Parameter und Parameterwerte für den verfolgten Befehl an. Der Alias für **ArgumentList** ist **Args**. Diese Funktion ist besonders nützlich für das Debuggen dynamischer Parameter.

Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: commandSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

Gibt einen Befehl an, der während der Ablaufverfolgung verarbeitet wird.

```yaml
Type: System.String
Parameter Sets: commandSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Debugger

Gibt an, dass das Cmdlet die Ablauf Verfolgungs Ausgabe an den Debugger sendet. Sie können die Ausgabe in jeden Benutzermodus- oder Kernelmodus-Debugger oder in Visual Studio anzeigen. Dieser Parameter wählt auch den Standard-Ablaufverfolgungslistener aus.

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

### -Ausdruck

Gibt den Ausdruck an, der während der Ablaufverfolgung verarbeitet wird. Schließen Sie den Ausdruck in geschweifte Klammern ( `{}` ) ein.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: expressionSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Gibt eine Datei an, an die das Cmdlet die Ablauf Verfolgungs Ausgabe sendet. Dieser Parameter wählt auch den Ablaufverfolgungslistener der Datei aus.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer. Wird mit dem **FilePath** -Parameter verwendet. Selbst bei Verwendung des **Force** -Parameters kann das Cmdlet keine Sicherheitseinschränkungen außer Kraft setzen.

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

### -InputObject

Gibt die Eingabe für den Ausdruck an, der während der Ablauf Verfolgung verarbeitet wird. Sie können eine Variable eingeben, die die Eingabe darstellt und die vom Ausdruck akzeptiert wird, oder Sie können ein Objekt über die Pipeline übergeben.

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

### -Listeneroption

Gibt optionale Daten für das Präfix der einzelnen Ablauf Verfolgungs Meldungen in der Ausgabe an. Zulässige Werte für diesen Parameter:

- `None`
- `LogicalOperationStack`
- `DateTime`
- `Timestamp`
- `ProcessId`
- `ThreadId`
- `Callstack`

`None` ist die Standardeinstellung.

Diese Werte werden als Flag-basierte Enumeration definiert. Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen. Die Werte können als Array von Werten an den **listeneroption** -Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden. Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert. Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt ein Array von PowerShell-Komponenten an, die nachverfolgt werden. Geben Sie den Namen der Ablaufverfolgungsquelle jeder Komponente ein. Platzhalter sind zulässig. Geben Sie ein, um die Ablauf Verfolgungs Quellen auf Ihrem Computer zu finden `Get-TraceSource` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Option

Bestimmt den Typ der Ereignisse, die verfolgt werden. Zulässige Werte für diesen Parameter:

- `None`
- `Constructor`
- `Dispose`
- `Finalizer`
- `Method`
- `Property`
- `Delegates`
- `Events`
- `Exception`
- `Lock`
- `Error`
- `Errors`
- `Warning`
- `Verbose`
- `WriteLine`
- `Data`
- `Scope`
- `ExecutionFlow`
- `Assert`
- `All`

`All` ist die Standardeinstellung.

Die folgenden Werte sind Kombinationen von anderen Werten:

- `ExecutionFlow`: `Constructor`, `Dispose`, `Finalizer`, `Method`, `Delegates`, `Events`, `Scope`
- `Data`: `Constructor`, `Dispose`, `Finalizer`, `Property`, `Verbose`, `WriteLine`
- `Errors`: `Error`, `Exception`

Diese Werte werden als Flag-basierte Enumeration definiert. Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen. Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden. Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert. Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pshost

Gibt an, dass das Cmdlet die Ablauf Verfolgungs Ausgabe an den PowerShell-Host sendet. Dieser Parameter wählt auch den PSHost-Ablaufverfolgungslistener aus.

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

## Eingaben

### System. Management. Automation. psobject

Sie können Objekte, die Eingaben darstellen, an den Ausdruck übergeben `Trace-Command` .

## Ausgaben

### System. Management. Automation. psobject

Gibt die Befehlsablaufverfolgung im Debug-Stream zurück.

## Notizen

- Die Ablaufverfolgung ist eine Methode, die Entwickler zum Debuggen und Optimieren von Programmen verwenden. Bei der Ablaufverfolgung erzeugt das Programm ausführliche Meldungen zu den einzelnen Schritten in der internen Verarbeitung.

- Die PowerShell-Ablaufverfolgungs-Cmdlets sind für die Unterstützung von PowerShell-Entwicklern konzipiert, aber Sie stehen allen Benutzern zur Verfügung. Damit können Sie fast jeden Aspekt der Shell-Funktionalität überwachen.

- Zum Ermitteln der PowerShell-Komponenten, die für die Ablauf Verfolgung aktiviert sind, geben Sie ein `Get-Help Get-TraceSource` .

  Eine Ablauf Verfolgungs Quelle ist der Teil jeder PowerShell-Komponente, die die Ablauf Verfolgung verwaltet und Ablauf Verfolgungs Meldungen für die Komponente generiert. Um eine Komponente zu verfolgen, identifizieren Sie die Ablaufverfolgungsquelle.

  Ein Ablaufverfolgungslistener empfängt die Ausgabe der Ablauf Verfolgung und zeigt Sie dem Benutzer an. Sie können festlegen, dass die Ablauf Verfolgungs Daten an einen Benutzermodus-oder Kernel Modus-Debugger, an den Host oder die Konsole, an eine Datei oder an einen benutzerdefinierten Listener gesendet werden, der von der **System. Diagnostics. TraceListener** -Klasse abgeleitet wird.

- Wenn Sie den CommandSet-Parametersatz verwenden, verarbeitet PowerShell den Befehl genauso wie in einer Pipeline. Beispielsweise wird die Befehlsermittlung nicht für jedes eingehende Objekt wiederholt.

- Die Namen der Parameter " **Name**", " **Ausdruck**", " **Option**" und " **Command** " sind optional. Wenn Sie die Parameternamen weglassen, müssen die unbenannten Parameterwerte in dieser Reihenfolge angezeigt werden: **Name**, **Ausdruck**, **Option** oder **Name**, **Befehl**, **Option**. Wenn Sie die Parameternamen angeben, können die Parameter in beliebiger Reihenfolge angegeben werden.

## Ähnliche Themen

[Get-TraceSource](Get-TraceSource.md)

[Measure-Command](Measure-Command.md)

[Set-TraceSource](Set-TraceSource.md)

[Show-Command](Show-Command.md)
