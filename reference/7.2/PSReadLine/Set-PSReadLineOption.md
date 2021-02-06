---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 11/23/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: cac2c2bb8ce1f3a28c0d91c7503b3ac4d038ccad
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "99602504"
---
# Set-PSReadLineOption

## Übersicht
Passt das Verhalten der Befehlszeilen Bearbeitung in **psread Line** an.

## Syntax

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func`2[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action`1[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-PredictionSource <PredictionSource>]
 [-PredictionViewStyle <PredictionViewStyle>] [-Colors <Hashtable>] [<CommonParameters>]
```

## BESCHREIBUNG

Mit dem- `Set-PSReadLineOption` Cmdlet wird das Verhalten des Moduls " **psread Line** " angepasst, wenn Sie die Befehlszeile bearbeiten. Verwenden Sie, um die **psread Line** -Einstellungen anzuzeigen `Get-PSReadLineOption` .

## Beispiele

### Beispiel 1: Festlegen der Vordergrund-und Hintergrundfarben

In diesem Beispiel wird **psread Line** so festgelegt, dass das **Kommentar** Token mit grünem Vorder Grundtext in einem grauen Hintergrund angezeigt wird. In der im Beispiel verwendeten Escapesequenz stellt **32** die Vordergrundfarbe und **47** die Hintergrundfarbe dar.

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="`e[32;47m" }
```

Sie können auswählen, dass nur eine Vorder grundtextfarbe festgelegt wird. Beispielsweise eine helle grüne Vorder grundtextfarbe für das **Kommentar** Token: ``"Comment"="`e[92m"`` .

### Beispiel 2: Festlegen des Glocken Stils

In diesem Beispiel antwortet **psread Line** auf Fehler oder Bedingungen, für die eine Benutzer Aufmerksamkeit erforderlich ist.
Der ' **bellstyle** ' ist so festgelegt, dass ein hörbares Signal bei 1221 Hz für 60 MS ausgegeben wird.

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> Diese Funktion funktioniert möglicherweise nicht in allen Hosts auf Plattformen.

### Beispiel 3: Festlegen mehrerer Optionen

`Set-PSReadLineOption` Es können mehrere Optionen mit einer Hash Tabelle festgelegt werden.

```powershell
$PSReadLineOptions = @{
    EditMode = "Emacs"
    HistoryNoDuplicates = $true
    HistorySearchCursorMovesToEnd = $true
    Colors = @{
        "Command" = "#8181f7"
    }
}
Set-PSReadLineOption @PSReadLineOptions
```

In der `$PSReadLineOptions` Hash Tabelle werden die Schlüssel und Werte festgelegt. `Set-PSReadLineOption` verwendet die Schlüssel und Werte mit `@PSReadLineOptions` , um die **psread Line** -Optionen zu aktualisieren.

Sie können die Schlüssel und Werte, die in den Hash Tabellennamen eingegeben werden, `$PSReadLineOptions` in der PowerShell-Befehlszeile anzeigen.

### Beispiel 4: Festlegen von Optionen für mehrere Farben

In diesem Beispiel wird gezeigt, wie mehr als ein Farbwert in einem einzelnen Befehl festgelegt wird.

```powershell
Set-PSReadLineOption -Colors @{
  Command            = 'Magenta'
  Number             = 'DarkGray'
  Member             = 'DarkGray'
  Operator           = 'DarkGray'
  Type               = 'DarkGray'
  Variable           = 'DarkGreen'
  Parameter          = 'DarkGreen'
  ContinuationPrompt = 'DarkGray'
  Default            = 'DarkGray'
}
```

### Beispiel 5: Festlegen von Farbwerten für mehrere Typen

Dieses Beispiel zeigt drei verschiedene Methoden zum Festlegen der Farbe von Token, die in **psread Line** angezeigt werden.

```powershell
Set-PSReadLineOption -Colors @{
 # Use a ConsoleColor enum
 "Error" = [ConsoleColor]::DarkRed

 # 24 bit color escape sequence
 "String" = "$([char]0x1b)[38;5;100m"

 # RGB value
 "Command" = "#8181f7"
}
```

### Beispiel 6: Verwenden von vimodechangehandler zum Anzeigen von Änderungen im VI-Modus

In diesem Beispiel wird eine Cursor Änderung von VT-Escapezeichen als Antwort auf eine Änderung des **VI** -Modus ausgegeben

```powershell
function OnViModeChange {
    if ($args[0] -eq 'Command') {
        # Set the cursor to a blinking block.
        Write-Host -NoNewLine "`e[1 q"
    } else {
        # Set the cursor to a blinking line.
        Write-Host -NoNewLine "`e[5 q"
    }
}
Set-PSReadLineOption -ViModeIndicator Script -ViModeChangeHandler $Function:OnViModeChange
```

Die **onvimodechange** -Funktion legt die Cursor Optionen für die **VI** -Modi fest: INSERT und Command.
**Vimodechangehandler** verwendet den- `Function:` Anbieter, um auf **onvimodechange** als Skriptblock Objekt zu verweisen.

Weitere Informationen finden Sie unter [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).

## Parameter

### -Addtohistoryhandler

Gibt einen **ScriptBlock** an, der steuert, welche Befehle dem **psles-Verlauf** hinzugefügt werden.

Der **ScriptBlock** empfängt die Befehlszeile als Eingabe. Wenn der **ScriptBlock** zurückgibt `$True` , wird die Befehlszeile zum Verlauf hinzugefügt.

```yaml
Type: System.Func`2[System.String,System.Object]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ansiescapetimeout

Diese Option ist für Windows spezifisch, wenn die Eingabe umgeleitet wird, z. b. Wenn Sie unter oder ausgeführt wird `tmux` `screen` .

Bei umgeleiteten Eingaben unter Windows werden viele Schlüssel als Sequenz von Zeichen gesendet, beginnend mit dem Escapezeichen. Es ist nicht möglich, zwischen einem einzelnen Escapezeichen, gefolgt von weiteren Zeichen und einer gültigen Escapesequenz, zu unterscheiden.

Es wird davon ausgegangen, dass das Terminal die Zeichen schneller als Benutzer Typen senden kann. **Psleline** wartet auf diesen Timeout, bevor er abschließt, dass er eine komplette Escapesequenz erhalten hat.

Wenn beim eingeben zufällige oder unerwartete Zeichen angezeigt werden, können Sie dieses Timeout anpassen.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bellstyle

Gibt an, wie **psread Line** auf verschiedene Fehler-und mehrdeutige Bedingungen antwortet.

Die folgenden Werte sind gültig:

- **Hörbar**: ein kurzes Signal.
- **Visual**: Text blinkt kurz.
- **None**: kein Feedback.

```yaml
Type: Microsoft.PowerShell.BellStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Audible
Accept pipeline input: False
Accept wildcard characters: False
```

### -Farben

Der **Colors** -Parameter gibt verschiedene Farben an, die von **psread Line** verwendet werden.

Das-Argument ist eine Hash Tabelle, in der die Schlüssel angeben, welches Element und welche Werte die Farbe angeben.
Weitere Informationen finden Sie unter [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).

Farben können entweder ein Wert aus **ConsoleColor** sein, z `[ConsoleColor]::Red` . b. oder eine gültige ANSI-Escapesequenz. Gültige Escapesequenzen sind von Ihrem Terminal abhängig. In PowerShell 5,0 ist eine Beispiel-Escapesequenz für den roten Text `$([char]0x1b)[91m` . In PowerShell 6 und höher ist die gleiche Escapesequenz `` `e[91m`` . Sie können andere Escapesequenzen angeben, einschließlich der folgenden Typen:

Es wurden zwei Farbeinstellungen hinzugefügt, um die Anpassung der `ListView` in psread Line 2.2.0 zu unterstützen:

- **Listvorhertioncolor** : Legen Sie die Farbe für das führende `>` Zeichen und den nachfolgenden Quellnamen fest, z. b. `[History]` . Standardmäßig wird `DarkYellow` als Vordergrundfarbe verwendet.
- **Listvorhertionselectedcolor** : Legen Sie die Farbe fest, die angibt, dass ein Listenelement ausgewählt ist. Standardmäßig wird `DarkBlack` als Hintergrundfarbe verwendet.

- 256-Farbe
- 24-Bit-Farbe
- Vordergrund, Hintergrund oder beides
- Inversen, Fett

Weitere Informationen zu ANSI-Farbcodes finden Sie unter [ANSI-Escapecode](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) in Wikipedia.

Gültige Schlüssel sind:

- **Continuationprompt**: die Farbe der Fortsetzungs Aufforderung.
- **Betonung**: die Fokus Farbe. Beispielsweise der übereinstimmende Text beim Durchsuchen des Verlaufs.
- **Fehler**: die Fehlerfarbe. Beispielsweise in der-Eingabeaufforderung.
- **Selection**: die Farbe, mit der die Menü Auswahl oder der ausgewählte Text hervorgehoben werden soll.
- **Standard** Wert: die standardmäßige tokenfarbe.
- **Comment**: die Farbe des Kommentar Tokens.
- **Schlüsselwort**: die Farbe für das Schlüsselwort Token.
- **String**: die Farbe des Zeichen folgen Tokens.
- **Operator**: die Farbe des Operator Tokens.
- **Variable**: die variablentokenfarbe.
- **Command**: die Farbe des Befehls Tokens.
- **Parameter**: die parametertokenfarbe.
- **Type**: die Typtoken-Farbe.
- **Number**: die nummertofarbe.
- **Member**: die tokenfarbe des Element namens.
- Inline **Vorhersage**: die Farbe für die Inline Ansicht des Vorhersage Vorschlags.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Commandvalidationhandler

Gibt einen **ScriptBlock** an, der von **validateandaccept-Line** aufgerufen wird. Wenn eine Ausnahme ausgelöst wird, schlägt die Validierung fehl, und der Fehler wird gemeldet.

Vor dem Auslösen einer Ausnahme kann der Validierungs Handler den Cursor an der Stelle des Fehlers platzieren, um die Behebung zu vereinfachen. Ein Validierungs Handler kann auch die Befehlszeile ändern, z. b., um häufige typografische Fehler zu beheben.

**Validateandaccept-Line** wird verwendet, um das Gruppieren ihres Verlaufs mit Befehlen zu vermeiden, die nicht funktionieren.

```yaml
Type: System.Action`1[System.Management.Automation.Language.CommandAst]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Completionqueryitems

Gibt die maximale Anzahl der Vervollständigungs Elemente an, die ohne Eingabeaufforderung angezeigt werden.

Wenn die Anzahl der anzuzeigenden Elemente größer als dieser Wert ist, fordert **psread Line** vor der Anzeige der Vervollständigungs Elemente **Ja/Nein** an.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -Continuationprompt

Gibt die Zeichenfolge an, die am Anfang der nachfolgenden Zeilen angezeigt wird, wenn mehrzeilige Eingaben eingegeben werden. Der Standardwert ist Double größer-als-Zeichen ( `>>` ). Eine leere Zeichenfolge ist gültig.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >>
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dingduration

Gibt die Dauer des Signal Formats an, wenn " **bellstyle** " auf " **hörbar**" festgelegt ist.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 50ms
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dingtone

Gibt den Ton in Hertz (Hz) des Signal Formats an, wenn " **bellstyle** " auf " **hörbar**" festgelegt ist.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1221
Accept pipeline input: False
Accept wildcard characters: False
```

### -EditMode

Gibt den Bearbeitungsmodus für die Befehlszeile an. Wenn Sie diesen Parameter verwenden, werden alle von festgelegten Tastenbindungen zurückgesetzt `Set-PSReadLineKeyHandler` .

Die folgenden Werte sind gültig:

- **Windows**: Tastenkombinationen emulieren PowerShell, cmd und Visual Studio.
- **Emacs**: Key-Bindungen emulieren bash oder Emacs.
- **VI**: Key-Bindungen emulieren VI.

Verwenden `Get-PSReadLineKeyHandler` Sie, um die Tasten Zuordnungen für den zurzeit konfigurierten **EditMode** anzuzeigen.

```yaml
Type: Microsoft.PowerShell.EditMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### -Extrapromptlinecount

Gibt die Anzahl der zusätzlichen Zeilen an.

Wenn Ihre Eingabeaufforderung mehr als eine Zeile umfasst, geben Sie einen Wert für diesen Parameter an. Verwenden Sie diese Option, wenn zusätzliche Zeilen verfügbar sein sollen, wenn **psread Line** die Eingabeaufforderung anzeigt, nachdem einige Ausgaben angezeigt wurden. Beispielsweise gibt **psread Line** eine Liste von Vervollständigungen zurück.

Diese Option wird weniger benötigt als in früheren Versionen von **psread Line**, ist jedoch nützlich, wenn die- `InvokePrompt` Funktion verwendet wird.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Historynoduplicates

Mit dieser Option wird das Rückruf Verhalten gesteuert. Der Verlaufs Datei werden noch doppelte Befehle hinzugefügt.
Wenn diese Option festgelegt ist, wird nur der letzte Aufruf beim Rückruf von Befehlen angezeigt. Wiederholte Befehle werden dem Verlauf hinzugefügt, um die Reihenfolge beim Rückruf beizubehalten. Der Befehl sollte jedoch in der Regel nicht mehrmals angezeigt werden, wenn Sie sich an den Verlauf erinnern oder ihn durchsuchen.

Standardmäßig ist die **historynoduplicates** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `True` . Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` . Um den Eigenschafts Wert zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistoryNoDuplicates:$False` .

Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:

`(Get-PSReadLineOption).HistoryNoDuplicates = $False`

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

### -Historysavepath

Gibt den Pfad zu der Datei an, in der der Verlauf gespeichert wird. Computer, auf denen Windows oder nicht-Windows-Plattformen ausgeführt werden, speichern die Datei an verschiedenen Speicherorten Der Dateiname wird z. b. in einer Variablen gespeichert `$($host.Name)_history.txt` `ConsoleHost_history.txt` .

Wenn Sie diesen Parameter nicht verwenden, lautet der Standardpfad wie folgt:

**Windows**

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

**nicht-Windows**

`$env:XDG_DATA_HOME/powershell/PSReadLine\$($host.Name)_history.txt`

`$env:HOME/.local/share/powershell/PSReadLine\$($host.Name)_history.txt`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: A file named $($host.Name)_history.txt in $env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine on Windows and $env:XDG_DATA_HOME/powershell/PSReadLine or $env:HOME/.local/share/powershell/PSReadLine on non-Windows platforms
Accept pipeline input: False
Accept wildcard characters: False
```

### -Historysavestyle

Gibt an, wie **psleline** den Verlauf speichert.

Gültige Werte sind:

- **Saveinkremental**: Speichern Sie den Verlauf, nachdem jeder Befehl ausgeführt und für mehrere Instanzen von PowerShell freigegeben wurde.
- **Saveatexit**: Verlaufs Datei anfügen, wenn PowerShell beendet wird.
- **Savenothing**: verwendet keine Verlaufs Datei.

```yaml
Type: Microsoft.PowerShell.HistorySaveStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SaveIncrementally
Accept pipeline input: False
Accept wildcard characters: False
```

### -Historysearchcasesensitive

Gibt an, dass bei der Suche nach Groß-/Kleinschreibung in Funktionen wie **reversesearchhistory** oder **historysearchabwärts** unterschieden wird.

Standardmäßig ist die **historysearchcasesensitive** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `False` . Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` . Um den Eigenschafts Wert zurück zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistorySearchCaseSensitive:$False` .

Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:

`(Get-PSReadLineOption).HistorySearchCaseSensitive = $False`

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

### -Historysearchcurrsormuvestoend

Gibt an, dass der Cursor an das Ende der Befehle verschoben wird, die Sie aus dem Verlauf mithilfe einer Suche laden.
Wenn dieser Parameter auf festgelegt ist `$False` , bleibt der Cursor an der Position, an der er sich befand, als Sie die Pfeile nach oben oder nach unten gedrückt haben.

Standardmäßig ist die **historysearchcursor** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `False` . Mit diesem **Switchparameter** legen Sie den-Eigenschafts Wert auf fest `True` . Um den Eigenschafts Wert zurück zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-HistorySearchCursorMovesToEnd:$False` .

Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:

`(Get-PSReadLineOption).HistorySearchCursorMovesToEnd = $False`

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

### -Maximumhistorycount

Gibt die maximale Anzahl von Befehlen an, die im **pslelinienverlauf** gespeichert werden sollen.

Der **psleline** -Verlauf ist vom PowerShell-Verlauf getrennt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maximumkillringcount

Gibt die maximale Anzahl von Elementen an, die im Kill-Ring gespeichert werden.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -PromptText

Wenn ein Analysefehler vorliegt, ändert **psread Line** einen Teil der roten Eingabeaufforderung. **Psread Line** analysiert Ihre prompt-Funktion, um zu bestimmen, wie nur die Farbe eines Teils der Eingabeaufforderung geändert wird. Diese Analyse ist nicht 100% zuverlässig.

Verwenden Sie diese Option, wenn die Eingabeaufforderung in " **psread Line** " auf unerwartete Weise geändert wird. Schließt alle nachfolgenden Leerzeichen ein.

Wenn die prompt-Funktion z. b. wie im folgenden Beispiel aussieht:

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

Legen Sie dann fest:

`Set-PSReadLineOption -PromptText "# "`

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowToolTips

Wenn Mögliche Vervollständigungen angezeigt werden, werden Quick Infos in der Liste der Vervollständigungen angezeigt.

Diese Option ist standardmäßig aktiviert. Diese Option war in früheren Versionen von **psread Line** standardmäßig nicht aktiviert. Legen Sie diese Option auf fest, um zu deaktivieren `$False` .

Standardmäßig ist die **ShowToolTips** -Eigenschaft des globalen **psconsolereadlineoptions** -Objekts auf festgelegt `True` . Mit diesem **Switchparameter** wird der-Eigenschafts Wert auf festgelegt `True` . Um den Eigenschafts Wert zu ändern, müssen Sie den Wert von **Switchparameter** wie folgt angeben: `-ShowToolTips:$False` .

Mit dem folgenden Befehl können Sie den Eigenschafts Wert direkt festlegen:

`(Get-PSReadLineOption).ShowToolTips = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vimodechangehandler

Wenn **vimodeindicator** auf festgelegt ist `Script` , wird der bereitgestellte Skriptblock jedes Mal aufgerufen, wenn der Modus geändert wird. Dem Skriptblock wird ein Argument des Typs bereitgestellt `ViMode` .

Dieser Parameter wurde in PowerShell 7 eingeführt.

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

### -Vimodeindicator

Mit dieser Option wird die visuelle Anzeige für den aktuellen **VI** -Modus festgelegt. Entweder der Einfügemodus oder der Befehlsmodus.

Die folgenden Werte sind gültig:

- **None**: Es gibt keinen Hinweis.
- **Eingabeaufforderung**: die Farbe wird von der Eingabeaufforderung geändert.
- **Cursor**: die Größe des Cursors ändert sich.
- **Skript**: vom Benutzer angegebener Text wird gedruckt.

```yaml
Type: Microsoft.PowerShell.ViModeStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Worddelimiters

Gibt die Zeichen an, die Wörter für Funktionen wie **forwardword** oder **killword** begrenzen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: ;:,.[]{}()/\|^&*-=+'"---
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prätionsource

Gibt die Quelle für psread Line an, um Vorhersage Vorschläge zu erhalten.

Gültige Werte sind:

- **Keine** : Deaktivieren Sie das Predictive IntelliSense-Feature (Standard).
-`**Verlauf** : Aktivieren Sie die Predictive IntelliSense-Funktion, und verwenden Sie den psread Line-Verlauf als einzige Quelle.
- **Plug** -in: Aktivieren Sie die Predictive IntelliSense-Funktion, und verwenden Sie die Plug-ins ( `CommandPrediction` ) als einzige Quelle. Dieser Wert wurde in psread Line 2.2.0 hinzugefügt.
- **Historyandplugin** : Aktivieren Sie das Predictive IntelliSense-Feature, und verwenden Sie den Verlauf und das Plug-in als Quellen. Dieser Wert wurde in psread Line 2.2.0 hinzugefügt.

```yaml
Type: Microsoft.PowerShell.PredictionSource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vorhertionviewstyle

Legt den Stil für die Anzeige des Vorhersage Texts fest. Der Standardwert ist **Inline View**.

- **Inline View** : der Stil, wie er heute vorhanden ist, ähnlich wie in der Fisch Shell und zsh. (Standard)
- **ListView** -Vorschläge werden in einer Dropdown Liste gerendert, und Benutzer können mithilfe von <kbd>uanrow</kbd> und <kbd>downpfeil</kbd>auswählen.

Dieser Parameter wurde in psread Line 2.2.0 hinzugefügt.

```yaml
Type: Microsoft.PowerShell.PredictionViewStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineView
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Eingaben

### Keine

Objekte können nicht an übergeben werden. `Set-PSReadLineOption.`

## Ausgaben

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## Notizen

## Verwandte Links

[about_PSReadLine](./About/about_PSReadLine.md)

[Get-psread linekeyhandler](Get-PSReadLineKeyHandler.md)

[Get-psread lineoption](Get-PSReadLineOption.md)

[Remove-psread linekeyhandler](Remove-PSReadLineKeyHandler.md)

[Set-psread linekeyhandler](Set-PSReadLineKeyHandler.md)
