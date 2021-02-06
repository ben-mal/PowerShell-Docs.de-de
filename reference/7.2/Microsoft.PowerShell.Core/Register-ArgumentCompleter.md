---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-argumentcompleter?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ArgumentCompleter
ms.openlocfilehash: e98de608630a59ff77ca701876986ffb29780a4a
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "99599630"
---
# Register-ArgumentCompleter

## ZUSAMMENFASSUNG

Registriert ein benutzerdefiniertes Argument, das vervollständigt werden soll.

## SYNTAX

### Nativeset

```
Register-ArgumentCompleter -CommandName <String[]> -ScriptBlock <ScriptBlock> [-Native]
 [<CommonParameters>]
```

### PowerShellSet

```
Register-ArgumentCompleter [-CommandName <String[]>] -ParameterName <String>
 -ScriptBlock <ScriptBlock> [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Register-ArgumentCompleter` Cmdlet wird ein benutzerdefiniertes Argument zum Vervollständigen registriert. Mit einem Argument Vervollständigung können Sie zur Laufzeit für jeden von Ihnen angegebenen Befehl eine dynamische Vervollständigung der Tab-Taste bereitstellen.

## BEISPIELE

### Beispiel 1: Registrieren eines Completers für ein benutzerdefiniertes Argument

Im folgenden Beispiel wird ein Argument Vervollständigung für den **ID** -Parameter des `Set-TimeZone` Cmdlets registriert.

```powershell
$scriptBlock = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)

    (Get-TimeZone -ListAvailable).Id | Where-Object {
        $_ -like "$wordToComplete*"
    } | ForEach-Object {
          "'$_'"
    }
}
Register-ArgumentCompleter -CommandName Set-TimeZone -ParameterName Id -ScriptBlock $scriptBlock
```

Mit dem ersten Befehl wird ein Skriptblock erstellt, der die erforderlichen Parameter annimmt, die beim Drücken der <kbd>Tab</kbd>-Taste durch den Benutzer übermittelt werden. Weitere Informationen finden Sie in der Beschreibung des **ScriptBlock** -Parameters.

Innerhalb des Skript Blocks werden die verfügbaren Werte für die **ID** mithilfe des- `Get-TimeZone` Cmdlets abgerufen. Die **ID** -Eigenschaft für jede Zeitzone wird an das `Where-Object` Cmdlet weitergeleitet. Mit dem- `Where-Object` Cmdlet werden alle IDs herausgefiltert, die nicht mit dem von bereitgestellten Wert beginnen `$wordToComplete` . dieser stellt den Text dar, den der Benutzer vor dem Drücken der <kbd>Registerkarte</kbd>eingegeben hat. Die gefilterten IDs werden an das `ForEach-Object` Cmdlet weitergeleitet, das die einzelnen Werte in Anführungszeichen einschließt, wenn der Wert Leerzeichen enthält.

Mit dem zweiten Befehl wird das Argument Vervollständigung registriert, indem der ScriptBlock, die **Parameter Name** - **ID** und der **CommandName** übergeben werden `Set-TimeZone` .

### Beispiel 2: Hinzufügen von Details zu den Vervollständigungs Werten der Registerkarte

Im folgenden Beispiel wird die Vervollständigung mit der Tab-Taste für den **Name** -Parameter des `Stop-Service` Cmdlets überschrieben

```powershell
$s = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)
    $services = Get-Service | Where-Object {$_.Status -eq "Running" -and $_.Name -like "$wordToComplete*"}
    $services | ForEach-Object {
        New-Object -Type System.Management.Automation.CompletionResult -ArgumentList $_.Name,
            $_.Name,
            "ParameterValue",
            $_.Name
    }
}
Register-ArgumentCompleter -CommandName Stop-Service -ParameterName Name -ScriptBlock $s
```

Mit dem ersten Befehl wird ein Skriptblock erstellt, der die erforderlichen Parameter annimmt, die beim Drücken der <kbd>Tab</kbd>-Taste durch den Benutzer übermittelt werden. Weitere Informationen finden Sie in der Beschreibung des **ScriptBlock** -Parameters.

Im Skriptblock ruft der erste Befehl alle laufenden Dienste mithilfe des- `Where-Object` Cmdlets ab. Die Dienste werden an das `ForEach-Object` Cmdlet weitergeleitet. Das `ForEach-Object` -Cmdlet erstellt ein neues [System. Management. Automation. completionresult](/dotnet/api/system.management.automation.completionresult) -Objekt und füllt es mit dem Namen des aktuellen Dienstanbieter (dargestellt durch die Pipeline Variable `$_.Name` ).

Mit dem **completionresult** -Objekt können Sie für jeden zurückgegebenen Wert weitere Details angeben:

- **completiontext** (Zeichenfolge): der Text, der als Ergebnis der automatischen Vervollständigung verwendet werden soll. Dies ist der Wert, der an den Befehl gesendet wird.
- **listitemtext** (Zeichenfolge): der Text, der in einer Liste angezeigt werden soll, z. b. wenn der Benutzer <kbd>STRG</kbd>- + <kbd>Taste</kbd>drückt. Diese Option wird nur zur Anzeige verwendet und nicht an den Befehl übermittelt, wenn Sie ausgewählt ist.
- **ResultType** ([completionresulttype](/dotnet/api/system.management.automation.completionresulttype)): der Typ des Vervollständigungs Ergebnisses.
- **ToolTip** (Zeichenfolge): der Text für die QuickInfo mit Details, die für das Objekt angezeigt werden sollen.
  Dies ist sichtbar, wenn der Benutzer nach Drücken von <kbd>STRG</kbd> + <kbd>LEERTASTE</kbd>ein Element auswählt.

Mit dem letzten Befehl wird veranschaulicht, dass beendete Dienste weiterhin manuell an das `Stop-Service` Cmdlet übergeben werden können. Die Vervollständigung mit der Tab-Taste ist der einzige betroffene Aspekt.

### Beispiel 3: Registrieren eines benutzerdefinierten Completers für das Native Argument

Mit dem systemeigenen **Parameter können** Sie die Vervollständigung mit der Tab-Taste für einen nativen Befehl bereitstellen. Im folgenden Beispiel wird die `dotnet` Befehlszeilenschnittstelle (Command Line Interface, CLI) mit der Befehlszeilenschnittstelle fertiggestellt.

> [!NOTE]
> Der `dotnet complete` Befehl ist nur in Version 2,0 und höher der dotnet-CLI verfügbar.

```powershell
$scriptblock = {
    param($wordToComplete, $commandAst, $cursorPosition)
        dotnet complete --position $cursorPosition $commandAst.ToString() | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
        }
}
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock $scriptblock
```

Mit dem ersten Befehl wird ein Skriptblock erstellt, der die erforderlichen Parameter annimmt, die beim Drücken der <kbd>Tab</kbd>-Taste durch den Benutzer übermittelt werden. Weitere Informationen finden Sie in der Beschreibung des **ScriptBlock** -Parameters.

Innerhalb des Skript Blocks wird der `dotnet complete` Befehl verwendet, um die Vervollständigung mit der Tab-Taste auszuführen.
Die Ergebnisse werden an das `ForEach-Object` Cmdlet weitergeleitet, das die **neue** statische Methode der [System. Management. Automation. completionresult](/dotnet/api/system.management.automation.completionresult) -Klasse verwendet, um ein neues **completionresult** -Objekt für jeden Wert zu erstellen.

## PARAMETERS

### -CommandName

Gibt den Namen der Befehle als Array an.

```yaml
Type: System.String[]
Parameter Sets: NativeSet, PowerShellSet
Aliases:

Required: True (NativeSet), False (PowerShellSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Native

Gibt an, dass das Argument Vervollständigung für einen nativen Befehl gilt, bei dem PowerShell Parameternamen nicht vervollständigen kann.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NativeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter Name

Gibt den Namen des Parameters an, dessen Argument abgeschlossen wird. Der angegebene Parameter Name kann kein Enumerationswert sein, z. b. der **ForegroundColor** -Parameter des `Write-Host` Cmdlets.

Weitere Informationen zu-Aufständen finden Sie unter [about_Enum](./About/about_Enum.md).

```yaml
Type: System.String
Parameter Sets: PowerShellSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Gibt die Befehle an, die ausgeführt werden sollen, um die Vervollständigung der Der von Ihnen bereitgestellte Skriptblock sollte die Werte zurückgeben, die die Eingabe vervollständigen. Der Skriptblock muss die Registrierung der Werte mithilfe der Pipeline ( `ForEach-Object` , `Where-Object` , usw.) oder einer anderen geeigneten Methode aufheben. Das Zurückgeben eines Arrays von Werten bewirkt, dass PowerShell das gesamte Array als **einen** Vervollständigungs Wert mit der Tab-Taste behandelt.

Der Skriptblock muss die folgenden Parameter in der unten angegebenen Reihenfolge akzeptieren. Die Namen der Parameter sind nicht wichtig, da PowerShell die Werte nach Position übergibt.

- `$commandName` (Position 0): dieser Parameter wird auf den Namen des Befehls festgelegt, für den der Skriptblock die Vervollständigung mit der Tab-Taste bereitstellt.
- `$parameterName` (Position 1): dieser Parameter ist auf den Parameter festgelegt, dessen Wert die Vervollständigung der Tab-Taste erfordert.
- `$wordToComplete` (Position 2): dieser Parameter ist auf den Wert festgelegt, den der Benutzer vor dem Drücken der <kbd>Tab</kbd>-Taste angegeben hat. Der Skriptblock sollte diesen Wert verwenden, um die Vervollständigungs Werte der Registerkarte zu ermitteln.
- `$commandAst` (Position 3): dieser Parameter ist für die aktuelle Eingabezeile auf die abstrakte Syntax Struktur (AST, Abstract Syntax Tree) festgelegt. Weitere Informationen finden Sie unter [AST-Klasse](/dotnet/api/system.management.automation.language.ast).
- `$fakeBoundParameters` (Position 4): dieser Parameter wird auf eine Hash Tabelle festgelegt, die den `$PSBoundParameters` für das Cmdlet enthält, bevor der Benutzer die <kbd>Tab</kbd>-Taste gedrückt hat. Weitere Informationen finden Sie unter [about_Automatic_Variables](./About/about_Automatic_Variables.md).

Wenn Sie den **nativen** Parameter angeben, muss der Skriptblock die folgenden Parameter in der angegebenen Reihenfolge verwenden. Die Namen der Parameter sind nicht wichtig, da PowerShell die Werte nach Position übergibt.

- `$wordToComplete` (Position 0): dieser Parameter ist auf den Wert festgelegt, den der Benutzer vor dem Drücken der <kbd>Tab</kbd>-Taste angegeben hat. Der Skriptblock sollte diesen Wert verwenden, um die Vervollständigungs Werte der Registerkarte zu ermitteln.
- `$commandAst` (Position 1): dieser Parameter wird auf die abstrakte Syntax Struktur (AST) für die aktuelle Eingabezeile festgelegt. Weitere Informationen finden Sie unter [AST-Klasse](/dotnet/api/system.management.automation.language.ast).
- `$cursorPosition` (Position 2): dieser Parameter wird auf die Position des Cursors festgelegt, wenn der Benutzer die <kbd>Tab</kbd>-Taste gedrückt hat.

Sie können auch **argumentcompleter** als Parameter Attribut bereitstellen. Weitere Informationen finden Sie unter [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](./About/about_CommonParameters.md).

## EINGABEN

### Keine

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

## VERWANDTE LINKS

