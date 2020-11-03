---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-variable?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Variable
ms.openlocfilehash: 6db5d6693e7e42b5563baa3dbaebb495f97f53a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213788"
---
# New-Variable

## ZUSAMMENFASSUNG
Erstellt eine neue Variable.

## SYNTAX

```
New-Variable [-Name] <String> [[-Value] <Object>] [-Description <String>] [-Option <ScopedItemOptions>]
 [-Visibility <SessionStateEntryVisibility>] [-Force] [-PassThru] [-Scope <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Das **New-Variable-** Cmdlet erstellt eine neue Variable in Windows PowerShell.
Sie können der Variablen beim Erstellen einen Wert zuweisen oder den Wert zuweisen bzw. ändern, nachdem die Variable erstellt wurde.

Sie können die Parameter von **New-Variable** verwenden, um die Eigenschaften der Variablen festzulegen, den Gültigkeitsbereich einer Variablen festzulegen und zu bestimmen, ob Variablen öffentlich oder privat sind.

In der Regel erstellen Sie eine neue Variable durch Eingabe des Variablen namens und seines Werts, wie z `$Var = 3` . b., aber Sie können das Cmdlet **New-Variable** verwenden, um die zugehörigen Parameter zu verwenden.

## BEISPIELE

### Beispiel 1: Erstellen einer Variablen

```
PS C:\> New-Variable days
```

Dieser Befehl erstellt eine neue Variable mit dem Namen Days.
Sie müssen den *Name* -Parameter nicht eingeben.

### Beispiel 2: Erstellen einer Variablen und Zuweisen eines Werts zu einem Wert

```
PS C:\> New-Variable -Name "zipcode" -Value 98033
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

Dieses Beispiel zeigt, wie Sie die Option "schreibgeschützt" von **New-Variable** verwenden, um zu verhindern, dass eine Variable überschrieben wird.

Der erste Befehl erstellt eine neue Variable namens "Max" und legt ihren Wert auf 256 fest.
Er verwendet den *Option* -Parameter mit dem Wert "schreibgeschützt".

Der zweite Befehl versucht, eine zweite Variable mit demselben Namen zu erstellen.
Dieser Befehl gibt einen Fehler zurück, da für diese Variable die Option „schreibgeschützt“ festgelegt ist.

Der dritte Befehl verwendet den *Force* -Parameter, um den schreibgeschützten Schutz der Variablen zu überschreiben.
In diesem Fall ist der Befehl zum Erstellen einer neuen Variable mit dem gleichen Namen erfolgreich.

### Beispiel 4: Erstellen einer privaten Variablen

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

Mit diesem Befehl wird das Verhalten einer privaten Variable in einem Modul veranschaulicht.
Das Modul enthält das Cmdlet "Get-Counter", das eine private Variable namens "Counter" aufweist.
Der Befehl verwendet den *Visibility* -Parameter mit dem Wert "private", um die Variable zu erstellen.

Die Beispielausgabe zeigt das Verhalten einer privaten Variable.
Der Benutzer, der das Modul geladen hat, kann den Wert der Counter-Variable nicht anzeigen oder ändern, die Counter-Variable kann jedoch durch die Befehle im Modul gelesen und geändert werden.

### Beispiel 5: Erstellen einer Variablen mit einem Leerzeichen

```
PS C:\> New-Variable -Name 'with space' -Value 'abc123xyz'

PS C:\> Get-Variable -Name 'with space'

Name                           Value
----                           -----
with space                     abc123xyz

PS C:\> ${with space}
abc123xyz
```

Mit diesem Befehl wird veranschaulicht, dass Variablen mit Leerzeichen erstellt werden können.
Auf die Variablen kann mithilfe des Cmdlets " **Get-Variable** " oder direkt durch das Trennen einer Variablen mit geschweiften Klammern zugegriffen werden.

## PARAMETERS

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

Standardmäßig können Sie eine Variable überschreiben, es sei denn, die Variable weist den Optionswert „ReadOnly“ oder „Constant“ auf.
Weitere Informationen finden Sie unter dem *Option* -Parameter.

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
Gibt den Wert der **options** -Eigenschaft der Variablen an. Die zulässigen Werte für diesen Parameter sind:

- Keine
Legt keine Optionen fest.
("None" ist die Standardeinstellung.)
- ReadOnly.
Kann gelöscht werden.
Kann nicht geändert werden, außer mit dem *Force* -Parameter.
- Privat.
Die Variable ist nur im aktuellen Bereich verfügbar.
- AllScope.
Die Variable wird in neu erstellte Bereiche kopiert.
- Konstante.
Kann nicht gelöscht oder geändert werden.
Die Konstante ist nur gültig, wenn Sie eine Variable erstellen.
Sie können die Optionen einer vorhandenen Variablen nicht in "Constant" ändern.

Um die **options** -Eigenschaft aller Variablen in der Sitzung anzuzeigen, geben Sie ein `Get-Variable | Format-Table -Property name, options -autosize` .

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
Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.
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

### -Bereich
Gibt den Bereich der neuen Variablen an.
Zulässige Werte für diesen Parameter:

- Weltbühne.
Variablen, die im globalen Gültigkeitsbereich erstellt werden, sind überall in einem PowerShell-Prozess zugänglich.
- Lokal.
Der lokale Gültigkeitsbereich bezieht sich auf den aktuellen Bereich. Dies kann ein beliebiger Bereich sein, der vom Kontext abhängig ist.
- Skript.
Auf Variablen, die im Skript Bereich erstellt werden, kann nur innerhalb der Skriptdatei oder des Moduls zugegriffen werden, in der Sie erstellt wurden.
- Privat.
Auf Variablen, die im privaten Bereich erstellt werden, kann nicht außerhalb des Bereichs zugegriffen werden, in dem Sie vorhanden sind
Sie können den privaten Bereich verwenden, um eine private Version eines Elements zu erstellen, das denselben Namen in einem anderen Bereich hat.
- Eine Zahl relativ zum aktuellen Bereich (0 bis zur Anzahl der Bereiche, wobei 0 der aktuelle Bereich ist, 1 das übergeordnete Element, 2 das übergeordnete Element des übergeordneten Bereichs usw.).
Negative Zahlen können nicht verwendet werden.

Local ist der Standardbereich, wenn der Bereichs Parameter nicht angegeben wird.

Weitere Informationen finden Sie unter „about_Scopes“.

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
Bestimmt, ob die Variable außerhalb der Sitzung, in der sie erstellt wurde, sichtbar ist.
Dieser Parameter dient zur Verwendung in Skripts und Befehlen, die für andere Benutzer bereitgestellt werden.
Zulässige Werte für diesen Parameter:

- Öffentlich.
Die Variable wird angezeigt.
(Public ist die Standardeinstellung.)
- Privat.
Die Variable wird nicht angezeigt.

Wenn eine Variable privat ist, wird sie nicht in den Listen mit Variablen angezeigt, z. B. jene, die von Get-Variable zurückgegeben werden, oder in den Anzeigen des Variable:-Laufwerks.
Befehle zum Lesen oder Ändern des Werts einer privaten Variablen geben einen Fehler zurück.
Der Benutzer kann jedoch Befehle ausführen, die eine private Variable verwenden, wenn die Befehle in der Sitzung geschrieben wurden, in der die Variable definiert wurde.

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

### System.Object
Sie können einen Wert über die Pipeline an **New-Variable** übergeben.

## AUSGABEN

### None oder System. Management. Automation. psvariable
Wenn Sie den *passthru* -Parameter verwenden, generiert **New-Variable** ein **System. Management. Automation. psvariable** -Objekt, das die neue Variable darstellt.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

## VERWANDTE LINKS

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)
