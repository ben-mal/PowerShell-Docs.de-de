---
description: Beschreibt die Parameter, die mit jedem Cmdlet verwendet werden können.
Locale: en-US
ms.date: 11/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_commonparameters?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CommonParameters
ms.openlocfilehash: 44503e9c251cd3cccf9b879ceb71262c65d8e5e9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598399"
---
# <a name="about-commonparameters"></a>Informationen zu CommonParameters

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt die Parameter, die mit jedem Cmdlet verwendet werden können.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Bei den allgemeinen Parametern handelt es sich um einen Satz von Cmdlet-Parametern, die Sie mit jedem Cmdlet verwenden können. Sie werden von PowerShell implementiert, nicht vom Cmdlet-Entwickler und sind automatisch für jedes Cmdlet verfügbar.

Sie können die allgemeinen Parameter mit jedem Cmdlet verwenden, aber Sie haben möglicherweise keine Auswirkung auf alle Cmdlets. Wenn ein Cmdlet z. b. keine ausführliche Ausgabe generiert, hat die Verwendung des allgemeinen **ausführliche** -Parameters keine Auswirkung.

Die allgemeinen Parameter sind auch für erweiterte Funktionen verfügbar, die das **cmdletbinding** -Attribut oder das **Parameter** -Attribut verwenden.

Mehrere allgemeine Parameter überschreiben System Standardwerte oder Einstellungen, die Sie mithilfe der PowerShell-Einstellungs Variablen festgelegt haben. Im Gegensatz zu den Einstellungs Variablen wirken sich die allgemeinen Parameter nur auf die Befehle aus, in denen Sie verwendet werden.

Weitere Informationen finden Sie unter [about_Preference_Variables](./about_Preference_Variables.md).

In der folgenden Liste werden die allgemeinen Parameter angezeigt. Ihre Aliase werden in Klammern aufgelistet.

- **Debug** (db)
- **ErrorAction** (EA)
- **ErrorVariable** (EV)
- **Informationaction** (INFA)
- **Informationvariable** (IV)
- **OutVariable** (OV)
- **OutBuffer** (ob)
- **Pipelinevariable** (PV)
- Ausführlich **(VB** )
- **WarningAction** (WA)
- **WarningVariable** (WV)

Die **Aktions** Parameter sind Werte vom Typ " **Action Preference** ".
**Action Preference** ist eine Enumeration mit den folgenden Werten:

| Name             | Wert |
|------------------|-------|
| Angehalten          | 5     |
| Ignorieren           | 4     |
| Diagnosetool          | 3     |
| Weiter         | 2     |
| Beenden             | 1     |
| SilentlyContinue | 0     |

Sie können den Namen oder den Wert mit dem-Parameter verwenden.

Zusätzlich zu den allgemeinen Parametern bieten viele Cmdlets Risiko Minderungs Parameter. Cmdlets, die das Risiko für das System oder die Benutzerdaten einschließen, bieten in der Regel diese Parameter.

Die Risiko Minderungs Parameter lauten wie folgt:

- **WhatIf** (Wi)
- **Bestätigen** (CF)

### <a name="common-parameter-descriptions"></a>allgemeine Parameter Beschreibungen

#### <a name="debug"></a>Debuggen

Zeigt Details des Programmierers zu dem Vorgang an, der mit dem Befehl ausgeführt wurde. Dieser Parameter funktioniert nur, wenn der Befehl eine Debugmeldung generiert. Beispielsweise funktioniert dieser Parameter, wenn ein Befehl das `Write-Debug` Cmdlet enthält.

```yaml
Type: SwitchParameter
Aliases: db

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

Standardmäßig werden keine Debugmeldungen angezeigt, da der Wert der `$DebugPreference` Variablen **SilentlyContinue** lautet.

Im interaktiven Modus überschreibt der **Debug** -Parameter den Wert der `$DebugPreference` Variablen für den aktuellen Befehl, wobei der Wert von auf "wird nach" festgelegt wird `$DebugPreference` . 

Im nicht interaktiven Modus überschreibt der **Debug** -Parameter den Wert der `$DebugPreference` Variablen für den aktuellen Befehl, wobei der Wert von `$DebugPreference` auf **Continue** festgelegt wird.

`-Debug:$true` hat denselben Effekt wie `-Debug` . Verwenden `-Debug:$false` Sie, um die Anzeige von Debugmeldungen zu unterdrücken `$DebugPreference` , wenn nicht **SilentlyContinue** ist. Dies ist die Standardeinstellung.

#### <a name="erroraction"></a>ErrorAction

Bestimmt, wie das Cmdlet auf einen Fehler ohne Abbruch vom Befehl antwortet.
Dieser Parameter funktioniert nur, wenn der Befehl einen Fehler ohne Abbruch generiert, z. b. die des `Write-Error` Cmdlets.

```yaml
Type: ActionPreference
Aliases: ea
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

Der **ErrorAction** -Parameter überschreibt den Wert der `$ErrorActionPreference` Variablen für den aktuellen Befehl. Da der Standardwert der `$ErrorActionPreference` Variablen **Continue** lautet, werden Fehlermeldungen angezeigt, und die Ausführung wird fortgesetzt, es sei denn, Sie verwenden den **ErrorAction** -Parameter.

Der **ErrorAction** -Parameter hat keine Auswirkung auf das Beenden von Fehlern (z. b. fehlende Daten, ungültige Parameter oder unzureichende Berechtigungen), die eine erfolgreiche Ausführung eines Befehls verhindern.

`-ErrorAction:Continue` zeigen Sie die Fehlermeldung an, und führen Sie den Befehl weiter aus. `Continue` ist die Standardeinstellung.

`-ErrorAction:Ignore` unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort. Anders als **SilentlyContinue** fügt **Ignore** die Fehlermeldung nicht zur `$Error` automatischen Variablen hinzu. Der Wert **Ignore** wird in PowerShell 3,0 eingeführt.

`-ErrorAction:Inquire` zeigt die Fehlermeldung an und fordert Sie zur Bestätigung auf, bevor die Ausführung fortgesetzt wird. Dieser Wert wird nur selten verwendet.

`-ErrorAction:SilentlyContinue` unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort.

`-ErrorAction:Stop` zeigt die Fehlermeldung an und beendet die Ausführung des Befehls.

`-ErrorAction:Suspend` ist nur für Workflows verfügbar, die in PowerShell 6 und höher nicht unterstützt werden.

> [!NOTE]
> Der **ErrorAction** -Parameter überschreibt, ersetzt jedoch nicht den Wert der `$ErrorAction` Preference-Variablen, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.

#### <a name="errorvariable"></a>ErrorVariable

**ErrorVariable** speichert Fehlermeldungen über den Befehl in der angegebenen Variablen und in der `$Error` automatischen Variablen. Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).

```yaml
Type: String
Aliases: ev

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Standardmäßig werden Fehlermeldungen, die bereits in der Variablen gespeichert sind, durch neue Fehlermeldungen überschrieben. Um die Fehlermeldung an den Inhalt der Variablen anzufügen, geben Sie ein Pluszeichen ( `+` ) vor dem Variablennamen ein.

Der folgende Befehl erstellt z. b. die `$a` Variable und speichert alle darin auftretenden Fehler:

```powershell
Get-Process -Id 6 -ErrorVariable a
```

Mit dem folgenden Befehl werden alle Fehlermeldungen der `$a` Variablen hinzugefügt:

```powershell
Get-Process -Id 2 -ErrorVariable +a
```

Mit dem folgenden Befehl wird der Inhalt von angezeigt `$a` :

```powershell
$a
```

Sie können diesen Parameter verwenden, um eine Variable zu erstellen, die nur Fehlermeldungen aus bestimmten Befehlen enthält und das Verhalten der `$Error` automatischen Variablen nicht beeinträchtigt. Die `$Error` Automatische Variable enthält Fehlermeldungen von allen Befehlen in der Sitzung. Sie können die Array Notation, z. b. oder, verwenden, `$a[0]` `$error[1,2]` um auf bestimmte in den Variablen gespeicherte Fehler zu verweisen.

> [!NOTE]
> Die benutzerdefinierte Fehler Variable enthält alle Fehler, die vom Befehl generiert wurden, einschließlich Fehlern aus Aufrufen von in der Liste von Funktionen oder Skripts.

#### <a name="informationaction"></a>"Informationaction"

Eingeführt in PowerShell 5,0. Innerhalb des Befehls oder Skripts, in dem es verwendet wird, überschreibt der allgemeine **informationaction** -Parameter den Wert der `$InformationPreference` Preference-Variablen, die standardmäßig auf **SilentlyContinue** festgelegt ist. Wenn Sie `Write-Information` in einem Skript mit **informationaction** verwenden, `Write-Information` werden Werte abhängig vom Wert des **informationaction** -Parameters angezeigt. Weitere Informationen zu `$InformationPreference` finden Sie unter [about_Preference_Variables](./about_Preference_Variables.md).

```yaml
Type: ActionPreference
Aliases: ia
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

`-InformationAction:Stop` beendet einen Befehl oder ein Skript bei einem Vorkommen des `Write-Information` Befehls.

`-InformationAction:Ignore` unterdrückt die Informations Meldung und setzt die Ausführung des Befehls fort. Anders als **SilentlyContinue** vergisst **Ignore** die Informations Meldung vollständig. die Informations Meldung wird nicht dem Informationsdaten Strom hinzugefügt.

`-InformationAction:Inquire` zeigt die Informations Meldung an, die Sie in einem `Write-Information` Befehl angeben, und fragt dann, ob Sie den Vorgang fortsetzen möchten.

`-InformationAction:Continue` zeigt die Informations Meldung an und wird weiterhin ausgeführt.

`-InformationAction:Suspend` wird von PowerShell Core nicht unterstützt, da es nur für Workflows verfügbar ist.

`-InformationAction:SilentlyContinue` keine Auswirkung, weil die Informations Meldung nicht (Standard) angezeigt wird und das Skript ohne Unterbrechung fortgesetzt wird.

> [!NOTE]
> Der **informationaction** -Parameter überschreibt, ersetzt jedoch nicht den Wert der `$InformationAction` Preference-Variablen, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.

#### <a name="informationvariable"></a>"Informationvariable"

Eingeführt in PowerShell 5,0. Innerhalb des Befehls oder Skripts, in dem es verwendet wird, speichert der allgemeine **informationvariable** -Parameter in einer Variablen eine Zeichenfolge, die Sie durch Hinzufügen des `Write-Information` Befehls angeben. `Write-Information` Werte werden abhängig vom Wert des allgemeinen **informationaction** -Parameters angezeigt. Wenn Sie den allgemeinen **informationaction** -Parameter nicht hinzufügen, werden Zeichen folgen `Write-Information` abhängig vom Wert der `$InformationPreference` Preference-Variablen angezeigt. Weitere Informationen zu `$InformationPreference` finden Sie unter [about_Preference_Variables](./about_Preference_Variables.md).

> [!NOTE]
> Die Information-Variable enthält alle vom Befehl generierten Informationsmeldungen, einschließlich der Informationsmeldungen von Aufrufen von in die Liste der Funktionen oder Skripts.

```yaml
Type: String
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

#### <a name="outbuffer"></a>OutBuffer

Bestimmt die Anzahl der Objekte, die in einem Puffer gesammelt werden, bevor Objekte über die Pipeline gesendet werden. Wenn Sie diesen Parameter weglassen, werden Objekte beim Generieren gesendet.

```yaml
Type: Int32
Aliases: ob

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Dieser Parameter für die Ressourcenverwaltung ist für fortgeschrittene Benutzer konzipiert. Wenn Sie diesen Parameter verwenden, sendet PowerShell Daten in Batches von an das nächste Cmdlet `OutBuffer + 1` .

Im folgenden Beispiel wird die Anzeige zwischen und `ForEach-Object` Prozess Blöcken, die das `Write-Host` Cmdlet verwenden, angezeigt. Die Anzeige wechselt in Batches von 2 oder `OutBuffer + 1` .

```powershell
1..4 | ForEach-Object {
        Write-Host "$($_): First"; $_
      } -OutBuffer 1 | ForEach-Object {
                        Write-Host "$($_): Second" }
```

```Output
1: First
2: First
1: Second
2: Second
3: First
4: First
3: Second
4: Second
```

#### <a name="outvariable"></a>OutVariable

Speichert Ausgabe Objekte aus dem Befehl in der angegebenen Variablen, zusätzlich zum Senden der Ausgabe entlang der Pipeline.

```yaml
Type: String
Aliases: ov

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Um die Ausgabe der Variablen hinzuzufügen, geben Sie `+` vor dem Variablennamen ein Pluszeichen () vor dem Variablennamen ein, anstatt eine Ausgabe zu ersetzen, die möglicherweise bereits dort gespeichert ist.

Der folgende Befehl erstellt z. b. die `$out` Variable und speichert das Prozess Objekt darin:

```powershell
Get-Process PowerShell -OutVariable out
```

Mit dem folgenden Befehl wird das Prozess Objekt der `$out` Variablen hinzugefügt:

```powershell
Get-Process iexplore -OutVariable +out
```

Der folgende Befehl zeigt den Inhalt der `$out` Variablen an:

```powershell
$out
```

> [!NOTE]
> Die vom Parameter " **OutVariable** " erstellte Variable ist "a" `[System.Collections.ArrayList]` .

#### <a name="pipelinevariable"></a>Pipeline Variable

**Pipelinevariable** speichert den Wert des aktuellen Pipeline Elements als Variable für jeden benannten Befehl, während er durch die Pipeline fließt.

```yaml
Type: String
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Gültige Werte sind Zeichen folgen, die identisch mit denen für beliebige Variablennamen sind.

Im folgenden finden Sie ein Beispiel für die Funktionsweise von **pipelinevariable** . In diesem Beispiel wird der **pipelinevariable** -Parameter einem Befehl hinzugefügt, `Foreach-Object` um die Ergebnisse des Befehls in Variablen zu speichern. Ein Bereich von Zahlen, 1 bis 10, wird an den ersten Befehl weitergeleitet `Foreach-Object` , und die Ergebnisse werden in einer Variablen mit dem Namen **left** gespeichert.

Die Ergebnisse des ersten `Foreach-Object` Befehls werden an einen zweiten Befehl weitergeleitet `Foreach-Object` , der die vom ersten Befehl zurückgegebenen Objekte filtert `Foreach-Object` . Die Ergebnisse des zweiten Befehls werden in einer Variablen mit dem Namen **right** gespeichert.

Im dritten `Foreach-Object` Befehl werden die Ergebnisse der ersten beiden weitergeleiteten `Foreach-Object` Befehle, die durch die Variablen **left** und **right** dargestellt werden, mithilfe eines Multiplikations Operators verarbeitet. Der Befehl weist die in der **linken** und **rechten** Variablen gespeicherten Objekte an, die multipliziert werden sollen, und gibt an, dass die Ergebnisse als "Left Range Member * right Range Member = Product" angezeigt werden sollen.

```powershell
1..10 | Foreach-Object -PipelineVariable Left -Process { $_ } |
  Foreach-Object -PV Right -Process { 1..10 } |
  Foreach-Object -Process { "$Left * $Right = " + ($Left*$Right) }
```

```output
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
...
```

#### <a name="verbose"></a>Ausführlich

Zeigt ausführliche Informationen zu dem Vorgang an, den der Befehl ausgeführt hat. Diese Informationen ähneln den Informationen in einer Ablauf Verfolgung oder einem Transaktionsprotokoll. Dieser Parameter funktioniert nur, wenn der Befehl eine ausführliche Nachricht generiert. Beispielsweise funktioniert dieser Parameter, wenn ein Befehl das `Write-Verbose` Cmdlet enthält.

```yaml
Type: SwitchParameter
Aliases: vb

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

Der **verbose** -Parameter überschreibt den Wert der `$VerbosePreference` Variablen für den aktuellen Befehl. Da der Standardwert der `$VerbosePreference` Variablen **SilentlyContinue** lautet, werden ausführliche Meldungen standardmäßig nicht angezeigt.

`-Verbose:$true` hat denselben Effekt wie `-Verbose`

`-Verbose:$false` unterdrückt die Anzeige von ausführlichen Meldungen. Verwenden Sie diesen Parameter, wenn der Wert von `$VerbosePreference` nicht **SilentlyContinue** (Standard) ist.

#### <a name="warningaction"></a>WarningAction

Bestimmt, wie das Cmdlet auf eine Warnung vom Befehl antwortet. **Continue** ist der Standardwert. Dieser Parameter funktioniert nur, wenn der Befehl eine Warnmeldung generiert. Beispielsweise funktioniert dieser Parameter, wenn ein Befehl das `Write-Warning` Cmdlet enthält.

```yaml
Type: ActionPreference
Aliases: wa
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

Der **WarningAction** -Parameter überschreibt den Wert der `$WarningPreference` Variablen für den aktuellen Befehl. Da der Standardwert der `$WarningPreference` Variablen **Continue** lautet, werden Warnungen angezeigt, und die Ausführung wird fortgesetzt, es sei denn, Sie verwenden den **WarningAction** -Parameter.

`-WarningAction:Continue` zeigt die Warnmeldungen an und setzt die Ausführung des Befehls fort. `Continue` ist die Standardeinstellung.

`-WarningAction:Inquire` zeigt die Warnmeldung an und fordert Sie zur Bestätigung auf, bevor die Ausführung fortgesetzt wird. Dieser Wert wird nur selten verwendet.

`-WarningAction:SilentlyContinue` unterdrückt die Warnmeldung und setzt die Ausführung des Befehls fort.

`-WarningAction:Stop` zeigt die Warnmeldung an und beendet die Ausführung des Befehls.

> [!NOTE]
> Der **WarningAction** -Parameter überschreibt, ersetzt jedoch nicht den Wert der `$WarningAction` Preference-Variablen, wenn der-Parameter in einem Befehl zum Ausführen eines Skripts oder einer Funktion verwendet wird.

#### <a name="warningvariable"></a>WarningVariable

Speichert Warnungen zum Befehl in der angegebenen Variablen.

```yaml
Type: String
Aliases: wv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

Alle generierten Warnungen werden in der Variablen gespeichert, auch wenn die Warnungen für den Benutzer nicht angezeigt werden.

Geben Sie `+` vor dem Variablennamen ein Pluszeichen () vor dem Variablennamen ein, um die Warnungen an den Inhalt der Variablen anzufügen.

Der folgende Befehl erstellt z. b. die `$a` Variable und speichert alle darin aufgeführten Warnungen:

```powershell
Get-Process -Id 6 -WarningVariable a
```

Mit dem folgenden Befehl werden alle Warnungen zur-Variablen hinzugefügt `$a` :

```powershell
Get-Process -Id 2 -WarningVariable +a
```

Mit dem folgenden Befehl wird der Inhalt von angezeigt `$a` :

```powershell
$a
```

Sie können diesen Parameter verwenden, um eine Variable zu erstellen, die nur Warnungen von bestimmten Befehlen enthält. Sie können die Array Notation, z. b. oder, verwenden, um `$a[0]` `$warning[1,2]` auf bestimmte in der Variablen gespeicherte Warnungen zu verweisen.

> [!NOTE]
> Die Warnungs Variable enthält alle Warnungen, die vom Befehl generiert werden, einschließlich Warnungen von Aufrufen von in einer Funktion oder in der Liste der Funktionen.

### <a name="risk-management-parameter-descriptions"></a>Beschreibungen von Risiko Management-Parametern

#### <a name="whatif"></a>WhatIf

Zeigt eine Meldung an, in der die Auswirkungen des Befehls beschrieben werden, anstatt den Befehl auszuführen.

```yaml
Type: SwitchParameter
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

Der **WhatIf** -Parameter überschreibt den Wert der `$WhatIfPreference` Variablen für den aktuellen Befehl. Da der Standardwert der `$WhatIfPreference` Variablen 0 (deaktiviert) ist, wird das **WhatIf** -Verhalten nicht ohne den **WhatIf** -Parameter durchgeführt. Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md)

`-WhatIf:$true` hat denselben Effekt wie `-WhatIf` .

`-WhatIf:$false` unterdrückt das automatische WhatIf-Verhalten, das sich ergibt, wenn der Wert der `$WhatIfPreference` Variablen 1 ist.

Der folgende Befehl verwendet z. b. den- `-WhatIf` Parameter in einem `Remove-Item` Befehl:

```powershell
Remove-Item Date.csv -WhatIf
```

Anstatt das Element zu entfernen, listet PowerShell die Vorgänge und die betroffenen Elemente auf. Dieser Befehl erstellt die folgende Ausgabe:

```output
What if: Performing operation "Remove File" on
Target "C:\ps-test\date.csv".
```

#### <a name="confirm"></a>Confirm

Fordert eine Bestätigung an, bevor der Befehl ausgeführt wird.

```yaml
Type: SwitchParameter
Aliases: cf

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

Der **Confirm** -Parameter überschreibt den Wert der `$ConfirmPreference` Variablen für den aktuellen Befehl. Der Standardwert lautet „true“. Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md)

`-Confirm:$true` hat denselben Effekt wie `-Confirm` .

`-Confirm:$false` unterdrückt die automatische Bestätigung, die auftritt, wenn der Wert von `$ConfirmPreference` kleiner oder gleich dem geschätzten Risiko des Cmdlets ist.

Der folgende Befehl verwendet z. b. den **Confirm** -Parameter mit einem- `Remove-Item` Befehl. Vor dem Entfernen des Elements listet PowerShell die Vorgänge auf, die durchzuführen sind, sowie die betroffenen Elemente und fordert die Genehmigung an.

```
PS C:\ps-test> Remove-Item tmp*.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target " C:\ps-test\tmp1.txt
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

Die Antwort Optionen bestätigen lauten wie folgt:

|Antwort       |Ergebnis                                                     |
|---------------|-----------------------------------------------------------|
|Ja (Y)        |Führen Sie die Aktion aus.                                        |
|Ja für alle (A) |Alle Aktionen ausführen und nachfolgende Confirm-Abfragen unterdrücken|
|               |für diesen Befehl.                                          |
|Nein (N):        |Führen Sie die Aktion nicht aus.                                 |
|Nein (L): |Keine Aktionen ausführen und nachfolgende Bestätigung unterdrücken |
|               |fragt diesen Befehl ab.                                  |
|Aussetzen (e):   |Halten Sie den Befehl an, und erstellen Sie eine temporäre Sitzung.          |
|Hilfe (?)       |Anzeigen der Hilfe zu diesen Optionen.                            |

Mit **der Option anhalten** wird der Befehl angehalten, und es wird eine temporäre Sitzung erstellt, in der Sie arbeiten können, bis Sie bereit sind, eine **Bestätigungs** Option auszuwählen. Die Eingabeaufforderung für die-Sitzung enthält zwei zusätzliche Caretzeichen (>>), um anzugeben, dass es sich um einen untergeordneten Vorgang des ursprünglichen übergeordneten Befehls handelt. Sie können Befehle und Skripts in der-Sitzung ausführen. Geben Sie "Exit" ein, um die-Sitzung zu beenden und zu den Confirm-Optionen für den ursprünglichen Befehl zurückzukehren.

Im folgenden Beispiel wird die **Suspend** -Option (S) verwendet, um einen Befehl vorübergehend anzuhalten, während der Benutzer die Hilfe für einen Befehlsparameter prüft. Nachdem Sie die erforderlichen Informationen erhalten haben, gibt der Benutzer "Exit" ein, um die Eingabeaufforderung zu beenden, und wählt dann die ja (y)-Antwort auf die Confirm-Abfrage aus.

```
PS C:\ps-test> New-Item -ItemType File -Name Test.txt -Confirm

Confirm
Are you sure you want to perform this action?

Performing operation "Create File" on Target "Destination:
C:\ps-test\test.txt".
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default
is "Y"): s

PS C:\ps-test> Get-Help New-Item -Parameter ItemType

-ItemType <string>
Specifies the provider-specified type of the new item.

Required?                    false
Position?                    named
Default value
Accept pipeline input?       true (ByPropertyName)
Accept wildcard characters?  false

PS C:\ps-test> exit

Confirm
Are you sure you want to perform this action?
Performing operation "Create File" on Target "Destination: C:\ps-test\test
.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (defau
lt is "Y"): y

Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         8/27/2010   2:41 PM          0 test.txt
```

## <a name="keywords"></a>Keywords

about_Common_Parameters

## <a name="see-also"></a>SIEHE AUCH

[about_Preference_Variables](about_Preference_Variables.md)

[Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)

[Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning)

[Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error)

[Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)

