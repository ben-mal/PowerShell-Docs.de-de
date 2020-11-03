---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: 4f80fb0a980da81cf3da0e0ea4ae7ca8e4ad2a39
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217124"
---
# Where-Object

## ZUSAMMENFASSUNG
Wählt Objekte aus einer Auflistung basierend auf ihren Eigenschaftswerten aus.

## SYNTAX

### Equalset (Standard)

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### Scriptblockset

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### Casesensitivegreaterorequalset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### Casesensitiveequalset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### Notequalset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### Casesensitivenotequalset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### Greaterthanset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### Casesensitivegreaterthanset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### Lessthanset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### Casesensitiveless thanset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### Greaterorequalset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### Lessorequalset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### Casesensitivelesorequalset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### Likeset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### Casesensitivelikeset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### Notlikeset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### Casesensitivenotlikeset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### Matchset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### Casesensitivematchset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### Notmatchset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### Casesensitivenotmatchset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### Kontainsset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### Casesensitivekontainsset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### Notkontainsset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### Casesensitivenotkontainsset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### Einfügen

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### Casesensitiveinset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### Notinset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### Casesensitivenotinset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### Isset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### Isnotset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### Not

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## DESCRIPTION

Das `Where-Object` Cmdlet wählt Objekte aus, die bestimmte Eigenschaftswerte aus der Auflistung von-Objekten aufweisen, die an das Cmdlet übergeben werden. Beispielsweise können Sie mit dem `Where-Object` Cmdlet Dateien auswählen, die nach einem bestimmten Datum erstellt wurden, Ereignisse mit einer bestimmten ID oder Computer, auf denen eine bestimmte Version von Windows verwendet wird.

Ab Windows PowerShell 3,0 gibt es zwei verschiedene Möglichkeiten, einen Befehl zu erstellen `Where-Object` .

- **Skriptblock**. Sie können einen Skriptblock verwenden, um den Namen der Eigenschaft, einen Vergleichsoperator und einen Eigenschaftswert anzugeben. `Where-Object` Gibt alle-Objekte zurück, für die die script Block-Anweisung den Wert true hat.

  Beispielsweise ruft der folgende Befehl Prozesse in der normalen Prioritäts Klasse ab, d. h. Prozesse, bei denen der Wert der **PriorityClass** -Eigenschaft Normal ist.

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  Alle PowerShell-Vergleichs Operatoren sind im Skriptblock Format gültig. Weitere Informationen zu Vergleichs Operatoren finden Sie unter [about_Comparison_Operators](./About/about_Comparison_Operators.md).

- **Vergleichs Anweisung**. Sie können auch eine Vergleichsanweisung schreiben, was der natürlichen Sprache sehr viel ähnlicher ist. Vergleichsanweisungen wurden in Windows PowerShell 3.0 eingeführt.

  Beispielsweise werden mit den folgenden Befehlen auch Prozesse mit der Prioritäts Klasse "Normal" angezeigt. Diese Befehle sind gleichwertig und austauschbar.

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  Ab Windows PowerShell 3,0 `Where-Object` fügt Vergleichs Operatoren als Parameter in einem `Where-Object` Befehl hinzu. Sofern nicht anders angegeben, wird bei allen Operatoren die Groß-und Kleinschreibung nicht berücksichtigt. Vor Windows PowerShell 3,0 konnten die Vergleichs Operatoren in der PowerShell-Sprache nur in Skript Blöcken verwendet werden.

Wenn Sie eine einzelne **Eigenschaft** für angeben `Where-Object` , wird der Wert der Eigenschaft als boolescher Ausdruck behandelt. Wenn der Wert von **length** nicht 0 (null) ist, wird der Ausdruck als **true** ausgewertet. Beispiel: `('hi', '', 'there') | Where-Object Length`

Das vorherige Beispiel ist funktional äquivalent zu:

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## BEISPIELE

### Beispiel 1: erhalten von beendeten Diensten

Mit diesen Befehlen wird eine Liste aller Dienste angezeigt, die zurzeit beendet sind. Die `$_` Automatische Variable stellt jedes Objekt dar, das an das `Where-Object` Cmdlet übergeben wird.

Der erste Befehl verwendet das Skriptblock Format, der zweite Befehl verwendet das Vergleichs Anweisungs Format. Diese Befehle sind gleichwertig und austauschbar.

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### Beispiel 2: erhalten von Prozessen basierend auf dem Workingset

Mit diesen Befehlen werden Prozesse aufgelistet, die über ein Workingset verfügen, das größer ist als 250 Megabyte (KB). Die ScriptBlock-und die-Anweisungs Syntax sind gleichwertig und können austauschbar verwendet werden.

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### Beispiel 3: erhalten von Prozessen basierend auf dem Prozessnamen

Mit diesen Befehlen werden die Prozesse mit einem **ProcessName** -Eigenschafts Wert, der mit dem Buchstaben beginnt, angezeigt `p` . Mit dem **Match** -Operator können Sie reguläre Ausdrucks Übereinstimmungen verwenden.

Die ScriptBlock-und die-Anweisungs Syntax sind gleichwertig und können austauschbar verwendet werden.

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### Beispiel 4: Verwenden des Vergleichs Anweisungs Formats

In diesem Beispiel wird gezeigt, wie das neue Vergleichs Anweisungs Format des `Where-Object` Cmdlets verwendet wird.

Der erste Befehl verwendet das Vergleichsanweisungsformat.
In diesem Befehl werden keine Aliase verwendet, und alle Parameter enthalten den Parameternamen.

Der zweite Befehl stellt eine natürlichere Verwendung des Vergleichsbefehlsformats dar. Der `where` Alias wird durch den `Where-Object` Cmdlet-Namen ersetzt, und alle optionalen Parameternamen werden ausgelassen.

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### Beispiel 5: Get-Befehle basierend auf Eigenschaften

In diesem Beispiel wird veranschaulicht, wie Sie Befehle schreiben können, mit denen Elemente zurückgegeben werden, die „true“ oder „false“ sind oder die einen beliebigen Wert für eine angegebene Eigenschaft aufweisen. Jedes Beispiel zeigt sowohl den Skriptblock als auch Vergleichs Anweisungs Formate für den Befehl.

```powershell
# Use Where-Object to get commands that have any value for the OutputType property of the command.
# This omits commands that do not have an OutputType property and those that have an OutputType property, but no property value.
Get-Command | where OutputType
Get-Command | where {$_.OutputType}
```

```powershell
# Use Where-Object to get objects that are containers.
# This gets objects that have the **PSIsContainer** property with a value of $True and excludes all others.
Get-ChildItem | where PSIsContainer
Get-ChildItem | where {$_.PSIsContainer}
```

```powershell
# Finally, use the Not operator (!) to get objects that are not containers.
# This gets objects that do have the **PSIsContainer** property and those that have a value of $False for the **PSIsContainer** property.
Get-ChildItem | where {!$_.PSIsContainer}
# You cannot use the Not operator (!) in the comparison statement format of the command.
Get-ChildItem | where PSIsContainer -eq $False
```

### Beispiel 6: Verwenden mehrerer Bedingungen

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

Dieses Beispiel zeigt, wie Sie einen `Where-Object` Befehl mit mehreren Bedingungen erstellen.

Dieser Befehl ruft Nicht-Kern-Module ab, die die aktualisierbare Hilfefunktion unterstützen. Der Befehl verwendet den **listavailable** -Parameter des `Get-Module` Cmdlets, um alle Module auf dem Computer zu erhalten. Ein Pipeline Operator ( `|` ) sendet die Module an das `Where-Object` Cmdlet, das Module abruft, deren Namen nicht mit Microsoft oder PS beginnen, und einen Wert für die **helpinfouri** -Eigenschaft hat, der PowerShell mitteilt, wo aktualisierte Hilfedateien für das Modul zu finden sind. Die Vergleichs Anweisungen werden durch den logischen **and-** Operator miteinander verbunden.

Im Beispiel wird das Skriptblock-Befehlsformat verwendet. Logische Operatoren, wie z. b. **and** und **or** , sind nur in Skript Blöcken gültig. Sie können Sie nicht im Vergleichs Anweisungs Format eines `Where-Object` Befehls verwenden.

- Weitere Informationen zu logischen PowerShell-Operatoren finden Sie unter [about_Logical_Operators](./About/about_logical_operators.md).
- Weitere Informationen zur aktualisierbaren Hilfe Funktion finden Sie unter [about_Updatable_Help](./About/about_Updatable_Help.md).

## PARAMETERS

### -Centhält

Gibt an, dass dieses Cmdlet Objekte aus einer Auflistung abruft, wenn der Eigenschafts Wert des Objekts eine genaue Entsprechung für den angegebenen Wert ist. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Beispiel: `Get-Process | where ProcessName -CContains "svchost"`

**CIS** bezieht sich auf eine Auflistung von Werten und ist true, wenn die Auflistung ein Element enthält, das eine genaue Entsprechung für den angegebenen Wert aufweist. Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ceq

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen Wert übereinstimmt.
Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CGE

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert oder gleich dem angegebenen Wert ist. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CGT

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert ist.
Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CIN

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert den angegebenen Wert enthält. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Beispiel: `Get-Process | where -Value "svchost" -CIn ProcessName`

**CIN** ähnelt **Care** , mit dem Unterschied, dass die Eigenschaften-und Wert Positionen umgekehrt werden. Die folgenden Anweisungen sind z. B. beide „true“.

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CLE

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner oder gleich dem angegebenen Wert ist. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Clike

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert einem Wert entspricht, der Platzhalter Zeichen enthält. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Beispiel: `Get-Process | where ProcessName -CLike "*host"`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CLT

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner als der angegebene Wert ist. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cmatch

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen regulären Ausdruck übereinstimmt. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet. Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.

Beispiel: `Get-Process | where ProcessName -CMatch "Shell"`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CNE

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert sich vom angegebenen Wert unterscheidet.
Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cnotenthält

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert des Objekts keine genaue Entsprechung für den angegebenen Wert ist. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Beispiel: `Get-Process | where ProcessName -CNotContains "svchost"`

**Notare** und **cnotenthält** Verweise auf eine Auflistung von Werten und sind true, wenn die Auflistung keine Elemente enthält, die eine genaue Entsprechung für den angegebenen Wert sind. Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cnotin

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine genaue Entsprechung für den angegebenen Wert ist. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Beispiel: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`

**NOTIN** -und **cnotin** -Operatoren ähneln **Notare** und **cnotare** , mit dem Unterschied, dass die Eigenschaften-und Wert Positionen umgekehrt werden. Die folgenden Anweisungen sind z. B. „true“.

`"abc", "def" -CNotContains "Abc"`

`"abc" -CNotIn "Abc", "def"`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cnotlike

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit einem Wert identisch ist, der Platzhalter Zeichen enthält. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet.

Beispiel: `Get-Process | where ProcessName -CNotLike "*host"`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cnotmatch

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit dem angegebenen regulären Ausdruck identisch ist. Bei diesem Vorgang wird die Groß-/Kleinschreibung beachtet. Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.

Beispiel: `Get-Process | where ProcessName -CNotMatch "Shell"`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enthält

Gibt an, dass dieses Cmdlet Objekte abruft, wenn ein Element im Eigenschafts Wert des Objekts eine genaue Entsprechung für den angegebenen Wert ist.

Beispiel: `Get-Process | where ProcessName -Contains "Svchost"`

Wenn der Eigenschafts Wert ein einzelnes Objekt enthält, konvertiert PowerShell es in eine Auflistung von einem Objekt.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainsSet
Aliases: IContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EQ

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen Wert übereinstimmt.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EqualSet
Aliases: IEQ

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filterscript

Gibt den Skriptblock an, der zum Filtern der Objekte verwendet wird. Schließen Sie den Skriptblock in geschweifte Klammern ( `{}` ) ein.

Der Parameter Name, **Filterscript** , ist optional.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GE

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert oder gleich dem angegebenen Wert ist.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterOrEqualSet
Aliases: IGE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GT

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert größer als der angegebene Wert ist.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterThanSet
Aliases: IGT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -In

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit einem der angegebenen Werte übereinstimmt.
Beispiel:

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

Wenn der Wert des **value** -Parameters ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.

Wenn der Eigenschafts Wert eines Objekts ein Array ist, verwendet PowerShell die Verweis Gleichheit, um eine Übereinstimmung zu ermitteln. `Where-Object` Gibt das-Objekt nur dann zurück, wenn der Wert des **Property** -Parameters und der Wert des **Werts** dieselbe Instanz eines Objekts sind.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InSet
Aliases: IIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt das zu filternde Objekt an. Sie können die Objekte auch über die Pipeline an übergeben `Where-Object` .

Wenn Sie den **Inputobject** -Parameter mit verwenden `Where-Object` , anstatt Befehls Ergebnisse an zu übergeben `Where-Object` , wird der **Inputobject** -Wert als einzelnes Objekt behandelt. Dies gilt auch, wenn der Wert eine Auflistung ist, die das Ergebnis eines Befehls ist, z `-InputObject (Get-Process)` . b.. Da **Inputobject** keine einzelnen Eigenschaften aus einem Array oder einer Auflistung von Objekten zurückgeben kann, wird empfohlen, dass `Where-Object` Sie in der Pipeline verwenden, wenn Sie zum Filtern einer Auflistung von Objekten für Objekte verwenden, die bestimmte Werte in definierten Eigenschaften aufweisen, `Where-Object` wie in den Beispielen in diesem Thema gezeigt.

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

### -Ist

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert eine Instanz des angegebenen .net-Typs ist. Schließen Sie den Typnamen in eckige Klammern ein.

Zum Beispiel, `Get-Process | where StartTime -Is [DateTime]`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsNot

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine Instanz des angegebenen .net-Typs ist.

Zum Beispiel, `Get-Process | where StartTime -IsNot [DateTime]`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsNotSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Le

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner oder gleich dem angegebenen Wert ist.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessOrEqualSet
Aliases: ILE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Like

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert einem Wert entspricht, der Platzhalter Zeichen enthält.

Beispiel: `Get-Process | where ProcessName -Like "*host"`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LikeSet
Aliases: ILike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LT

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert kleiner als der angegebene Wert ist.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessThanSet
Aliases: ILT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Match

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert mit dem angegebenen regulären Ausdruck übereinstimmt. Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.

Beispiel: `Get-Process | where ProcessName -Match "shell"`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MatchSet
Aliases: IMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NE

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert sich vom angegebenen Wert unterscheidet.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotEqualSet
Aliases: INE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Not

Gibt an, dass dieses Cmdlet Objekte abruft, wenn die Eigenschaft nicht vorhanden ist oder den Wert NULL oder false aufweist.

Beispiel: `Get-Service | where -Not "DependentServices"`

Dieser Parameter wurde in Windows PowerShell 6,1 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Not
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notenthält

Gibt an, dass dieses Cmdlet Objekte abruft, wenn keines der Elemente im Eigenschafts Wert eine genaue Entsprechung für den angegebenen Wert ist.

Beispiel: `Get-Process | where ProcessName -NotContains "Svchost"`

**Notare** verweist auf eine Auflistung von Werten und ist true, wenn die Auflistung keine Elemente enthält, die eine genaue Entsprechung für den angegebenen Wert sind. Wenn die Eingabe ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotContainsSet
Aliases: INotContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NOTIN

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert keine genaue Entsprechung für einen der angegebenen Werte ist.

Beispiel: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`

Wenn der Wert von **value** ein einzelnes Objekt ist, konvertiert PowerShell es in eine Auflistung von einem Objekt.

Wenn der Eigenschafts Wert eines Objekts ein Array ist, verwendet PowerShell die Verweis Gleichheit, um eine Übereinstimmung zu ermitteln. `Where-Object` Gibt das-Objekt nur dann zurück, wenn der Wert der- **Eigenschaft** und der Wert des **Werts** nicht dieselbe Instanz eines-Objekts sind.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotInSet
Aliases: INotIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notlike

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit einem Wert identisch ist, der Platzhalter Zeichen enthält.

Beispiel: `Get-Process | where ProcessName -NotLike "*host"`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotLikeSet
Aliases: INotLike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notmatch

Gibt an, dass dieses Cmdlet Objekte abruft, wenn der Eigenschafts Wert nicht mit dem angegebenen regulären Ausdruck identisch ist. Wenn die Eingabe Skalar ist, wird der übereinstimmende Wert in der `$Matches` automatischen Variablen gespeichert.

Beispiel: `Get-Process | where ProcessName -NotMatch "PowerShell"`

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotMatchSet
Aliases: INotMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Eigenschaft

Gibt den Namen einer Objekteigenschaft an. Der Parameter Name " **Property** " ist optional.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: EqualSet, CaseSensitiveNotLikeSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Gibt einen Eigenschaftswert an. Der Parameter Name, **value** , ist optional. Dieser Parameter akzeptiert Platzhalter Zeichen, wenn er mit den folgenden vergleichsparametern verwendet wird:

- **Clike**
- **Cnotlike**
- **mögen**
- **NotLike**

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: Object
Parameter Sets: EqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können die Objekte über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Object

Mit diesem Cmdlet werden ausgewählte Elemente aus dem Eingabe Objekt Satz zurückgegeben.

## HINWEISE

Ab Windows PowerShell 4,0 `Where` wurden-und-Methoden für die Verwendung mit-Auflistungen `ForEach` hinzugefügt.

Weitere Informationen zu diesen neuen Methoden finden Sie hier [about_arrays](./About/about_Arrays.md)

## VERWANDTE LINKS

[Compare-Object](../Microsoft.PowerShell.Utility/Compare-Object.md)

[ForEach-Object](ForEach-Object.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Measure-Object](../Microsoft.PowerShell.Utility/Measure-Object.md)

[New-Object](../Microsoft.PowerShell.Utility/New-Object.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Tee-Object](../Microsoft.PowerShell.Utility/Tee-Object.md)
