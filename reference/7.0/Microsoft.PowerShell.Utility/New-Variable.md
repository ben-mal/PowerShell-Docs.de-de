---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: f23f725a92d5157001a1327cff3dbb3e785fd776
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072783"
---
# New-Variable

## Übersicht
Erstellt eine neue Variable.

## Syntax

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## BESCHREIBUNG

Das- `New-Variable` Cmdlet erstellt eine neue Variable in Windows PowerShell. Sie können der Variablen beim Erstellen einen Wert zuweisen oder den Wert zuweisen bzw. ändern, nachdem die Variable erstellt wurde.

Sie können die Parameter von verwenden, `New-Variable` um die Eigenschaften der Variablen festzulegen, den Gültigkeitsbereich einer Variablen festzulegen und zu bestimmen, ob Variablen öffentlich oder privat sind.

In der Regel erstellen Sie eine neue Variable durch Eingabe des Variablen namens und seines Werts, wie z `$Var = 3` . b., aber Sie können das `New-Variable` Cmdlet verwenden, um dessen Parameter zu verwenden.

## Beispiele

### Beispiel 1: Erstellen einer Variablen

```
New-Variable days
```

Dieser Befehl erstellt eine neue Variable mit dem Namen Days. Sie müssen den **Name** -Parameter nicht eingeben.

### Beispiel 2: Erstellen einer Variablen und Zuweisen eines Werts zu einem Wert

```
New-Variable -Name "zipcode" -Value 98033
```

Dieser Befehl erstellt eine Variable namens "ZipCode" und weist ihr den Wert "98033" zu.

### Beispiel 3: Erstellen einer Variablen mit der Option "Read only"

```
PS C:\> New-Variable -Name Max -Value 256 -Option ReadOnly
PS C:\> New-Variable -Name max -Value 1024

New-Variable : A variable with name 'max' already exists.
At line:1 char:1
+ New-Variable -Name max -Value 1024
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ResourceExists: (max:String) [New-Variable], SessionStateException
    + FullyQualifiedErrorId : VariableAlreadyExists,Microsoft.PowerShell.Commands.NewVariableCommand

PS C:\> New-Variable -Name max -Value 1024 -Force
```

In diesem Beispiel wird gezeigt, wie die- `ReadOnly` Option von verwendet `New-Variable` wird, um eine Variable vor dem Überschreiben zu schützen.

Der erste Befehl erstellt eine neue Variable namens "Max" und legt ihren Wert auf 256 fest. Er verwendet den **Option** -Parameter mit dem Wert `ReadOnly` .

Der zweite Befehl versucht, eine zweite Variable mit demselben Namen zu erstellen. Dieser Befehl gibt einen Fehler zurück, da für diese Variable die Option „schreibgeschützt“ festgelegt ist.

Der dritte Befehl verwendet den **Force** -Parameter, um den schreibgeschützten Schutz der Variablen zu überschreiben.
In diesem Fall ist der Befehl zum Erstellen einer neuen Variable mit dem gleichen Namen erfolgreich.

### Beispiel 4: zuweisen mehrerer Optionen zu einer Variablen

```powershell
New-Variable -Name 'TestVariable' -Value 'Test Value' -Option AllScope,Constant
```

In diesem Beispiel wird eine-Variable erstellt und die `AllScope` Optionen und zugewiesen, `Constant` sodass die Variable im aktuellen Bereich verfügbar ist und alle neuen Bereiche erstellt und nicht geändert oder gelöscht werden können.

### Beispiel 5: Erstellen einer privaten Variablen

```
PS C:\> New-Variable -Name counter -Visibility Private

#Effect of private variable in a module.

PS C:\> Get-Variable c*

Name                           Value
----                           -----
Culture                        en-US
ConsoleFileName
ConfirmPreference              High
CommandLineParameters          {}

PS C:\> $counter
"Cannot access the variable '$counter' because it is a private variable"
At line:1 char:1
+ $counter
+ ~~~~~~~~
    + CategoryInfo          : PermissionDenied: (counter:String) [], SessionStateException
    + FullyQualifiedErrorId : VariableIsPrivate

PS C:\> Get-Counter
Name         Value
----         -----
Counter1     3.1415
...
```

Mit diesem Befehl wird das Verhalten einer privaten Variable in einem Modul veranschaulicht. Das Modul enthält das `Get-Counter` Cmdlet, das über eine private Variable namens "Counter" verfügt. Der Befehl verwendet den **Visibility** -Parameter mit dem Wert "private", um die Variable zu erstellen.

Die Beispielausgabe zeigt das Verhalten einer privaten Variable. Der Benutzer, der das Modul geladen hat, kann den Wert der Counter-Variable nicht anzeigen oder ändern, die Counter-Variable kann jedoch durch die Befehle im Modul gelesen und geändert werden.

### Beispiel 6: Erstellen einer Variablen mit einem Leerzeichen

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

Mit diesem Befehl wird veranschaulicht, dass Variablen mit Leerzeichen erstellt werden können. Der Zugriff auf die Variablen erfolgt mithilfe des `Get-Variable` Cmdlets oder direkt durch das begrenzen einer Variablen mit geschweiften Klammern.

## Parameter

### -Description

Gibt eine Beschreibung der Variablen an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Gibt an, dass das Cmdlet eine Variable mit dem gleichen Namen wie eine vorhandene schreibgeschützte Variable erstellt.

Standardmäßig können Sie eine Variable überschreiben, es sei denn, die Variable hat den Optionswert `ReadOnly` oder `Constant` . Weitere Informationen finden Sie unter dem **Option** -Parameter.

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

### -Name

Gibt einen Namen für die neue Variable an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Option

Gibt den Wert der **options** -Eigenschaft der Variablen an. Zulässige Werte für diesen Parameter:

- `None` -Legt keine Optionen fest. `None` ist die Standardeinstellung.
- `ReadOnly` -Kann gelöscht werden. Kann nicht geändert werden, außer mit dem **Force** -Parameter.
- `Private` -Die Variable ist nur im aktuellen Bereich verfügbar.
- `AllScope` -Die Variable wird in neue Bereiche kopiert, die erstellt werden.
- `Constant` -Kann nicht gelöscht oder geändert werden. `Constant` ist nur gültig, wenn Sie eine Variable erstellen. Die Optionen einer vorhandenen Variablen können nicht in geändert werden `Constant` .

Diese Werte werden als Flag-basierte Enumeration definiert. Sie können mehrere Werte kombinieren, um mehrere Flags mithilfe dieses Parameters festzulegen. Die Werte können als Array von Werten an den **options** Parameter oder als durch Trennzeichen getrennte Zeichenfolge dieser Werte übergeben werden. Mit dem-Cmdlet werden die Werte mithilfe eines binären OR-Vorgangs kombiniert. Das übergeben von Werten als Array ist die einfachste Option und ermöglicht Ihnen außerdem, die Vervollständigung mit der Tab-Taste für die Werte zu verwenden.

Um die Options-Eigenschaft aller Variablen in der Sitzung anzuzeigen, geben Sie ein `Get-Variable | Format-Table -Property name, options -AutoSize` .

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### -Bereich

Gibt den Bereich der neuen Variablen an. Zulässige Werte für diesen Parameter:

- `Global` -Variablen, die im globalen Gültigkeitsbereich erstellt werden, sind überall in einem PowerShell-Prozess zugänglich.
- `Local` -Der lokale Gültigkeitsbereich bezieht sich auf den aktuellen Bereich. Dies kann ein beliebiger Bereich sein, der vom Kontext abhängig ist.
- `Script` -Die im Skript Bereich erstellten Variablen sind nur in der Skriptdatei oder im Modul verfügbar, in der Sie erstellt wurden.
- `Private` -Die im privaten Bereich erstellten Variablen können nicht außerhalb des Bereichs, in dem Sie vorhanden sind, aufgerufen werden. Sie können den privaten Bereich verwenden, um eine private Version eines Elements zu erstellen, das denselben Namen in einem anderen Bereich hat.
- Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich ist, 1 das übergeordnete Element, 2 das übergeordnete Element des übergeordneten Bereichs usw.). Negative Zahlen können nicht verwendet werden.

`Local` der Standardbereich, wenn der Bereichs Parameter nicht angegeben wird.

Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Gibt den Anfangswert der Variablen an.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Sichtbarkeit

Bestimmt, ob die Variable außerhalb der Sitzung, in der sie erstellt wurde, sichtbar ist. Dieser Parameter ist für die Verwendung in Skripts und Befehlen konzipiert, die an andere Benutzer übermittelt werden. Zulässige Werte für diesen Parameter:

- `Public` -Die Variable ist sichtbar. `Public` ist die Standardeinstellung.
- `Private` -Die Variable ist nicht sichtbar.

Wenn eine Variable privat ist, wird Sie nicht in Listen mit Variablen angezeigt, z. b. den von zurückgegebenen Variablen `Get-Variable` oder in Anzeigen des `Variable:` Laufwerks. Befehle zum Lesen oder Ändern des Werts einer privaten Variablen geben einen Fehler zurück. Der Benutzer kann jedoch Befehle ausführen, die eine private Variable verwenden, wenn die Befehle in der Sitzung geschrieben wurden, in der die Variable definiert wurde.

```yaml
Type: System.Management.Automation.SessionStateEntryVisibility
Parameter Sets: (All)
Aliases:
Accepted values: Public, Private

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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

## Eingaben

### System.Object

Sie können einen Wert über die Pipeline an übergeben `New-Variable` .

## Ausgaben

### None oder System. Management. Automation. psvariable

Wenn Sie den **passthru** -Parameter verwenden, `New-Variable` generiert ein **System. Management. Automation. psvariable** -Objekt, das die neue Variable darstellt. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## Hinweise

## Ähnliche Themen

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)
