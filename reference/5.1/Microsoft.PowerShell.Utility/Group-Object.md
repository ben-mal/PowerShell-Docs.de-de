---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: df06d5cd83472c80a395e3dcf63c4d331c5da6bb
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219287"
---
# Group-Object

## ZUSAMMENFASSUNG
Gruppiert Objekte, die den gleichen Wert für die angegebenen Eigenschaften enthalten.

## SYNTAX

### Hash Tabelle

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## DESCRIPTION

Das- `Group-Object` Cmdlet zeigt Objekte in Gruppen basierend auf dem Wert einer angegebenen Eigenschaft an.
`Group-Object` gibt eine Tabelle mit einer Zeile für jeden Eigenschafts Wert und eine Spalte zurück, die die Anzahl der Elemente mit diesem Wert anzeigt.

Wenn Sie mehr als eine Eigenschaft angeben, werden `Group-Object` diese zuerst nach den Werten der ersten Eigenschaft und dann innerhalb jeder Eigenschaften Gruppe nach dem Wert der nächsten Eigenschaft gruppiert.

## BEISPIELE

### Beispiel 1: Gruppieren von Dateien nach Erweiterung

In diesem Beispiel werden die Dateien unter rekursiv abgerufen `$PSHOME` und nach der Dateinamenerweiterung gruppiert. Die Ausgabe wird an das `Sort-Object` Cmdlet gesendet, das Sie nach den für die angegebene Erweiterung gefundenen Anzahl Dateien sortiert. Der leere **Name** stellt Verzeichnisse dar.

In diesem Beispiel wird der **noelement** -Parameter verwendet, um die Member der Gruppe auszulassen.

```powershell
$files = Get-ChildItem -Path $PSHOME -Recurse
$files | Group-Object -Property extension -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  365 .xml
  231 .cdxml
  197
  169 .ps1xml
  142 .txt
  114 .psd1
   63 .psm1
   49 .xsd
   36 .dll
   15 .mfl
   15 .mof
...
```

### Beispiel 2: Gruppieren von ganzen Zahlen nach Wahrscheinlichkeit und Evens

In diesem Beispiel wird gezeigt, wie Skriptblöcke als Wert des **Property** -Parameters verwendet werden. Dieser Befehl zeigt die ganzen Zahlen von 1 bis 20 an, gruppiert nach Wahrscheinlichkeit und sogar.

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### Beispiel 3: Gruppieren von Ereignisprotokoll Ereignissen nach EntryType

In diesem Beispiel werden die 1.000 letzten Einträge im System Ereignisprotokoll angezeigt, gruppiert nach **entryType**.

In der Ausgabe stellt die Spalte " **count** " die Anzahl der Einträge in jeder Gruppe dar. Die **Name** -Spalte stellt die **eventType** -Werte dar, die eine Gruppe definieren. Die Spalte " **Group** " stellt die Objekte in jeder Gruppe dar.

```powershell
Get-WinEvent -LogName System -MaxEvents 1000 | Group-Object -Property LevelDisplayName
```

```Output
Count Name          Group
----- ----          -----
  153 Error         {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  722 Information   {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  125 Warning       {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
```

### Beispiel 4: Gruppieren von Prozessen nach Prioritäts Klasse

In diesem Beispiel werden die Auswirkungen des **noelement** -Parameters veranschaulicht. Diese Befehle gruppieren die Prozesse auf dem Computer nach Prioritätsklasse.

Der erste Befehl verwendet das `Get-Process` Cmdlet, um die Prozesse auf dem Computer zu erhalten, und sendet die Objekte in der Pipeline. `Group-Object`gruppiert die Objekte nach dem Wert der **PriorityClass** -Eigenschaft des Prozesses.

Im zweiten Beispiel wird der **noelement** -Parameter verwendet, um die Member der Gruppe aus der Ausgabe auszuschließen. Das Ergebnis ist eine Tabelle, die nur den Wert für die **Anzahl** und den **Namen** der Eigenschaft hat.

Die Ergebnisse werden in der folgenden Beispielausgabe gezeigt.

```powershell
Get-Process | Group-Object -Property PriorityClass
```

```Output
Count Name         Group
----- ----         -----
   55 Normal       {System.Diagnostics.Process (AdtAgent), System.Diagnosti...
    1              {System.Diagnostics.Process (Idle)}
    3 High         {System.Diagnostics.Process (Newproc), System.Diagnostic...
    2 BelowNormal  {System.Diagnostics.Process (winperf),
```

```powershell
Get-Process | Group-Object -Property PriorityClass -NoElement
```

```Output
Count Name
----- ----
   55 Normal
    1
    3 High
    2 BelowNormal
```

### Beispiel 5: Gruppieren von Prozessen nach Name

Im folgenden Beispiel wird verwendet `Group-Object` , um mehrere Instanzen von Prozessen zu gruppieren, die auf dem lokalen Computer ausgeführt werden. `Where-Object` zeigt Prozesse mit mehr als einer Instanz an.

```powershell
Get-Process | Group-Object -Property Name -NoElement | Where-Object {$_.Count -gt 1}
```

```Output
Count Name
----- ----
2     csrss
5     svchost
2     winlogon
2     wmiprvse
```

### Beispiel 6: Gruppieren von Objekten in einer Hash Tabelle

In diesem Beispiel werden die **ashashtable** -und **AsString** -Parameter verwendet, um die Gruppen in einer Hash Tabelle als eine Auflistung von Schlüssel-Wert-Paaren zurückzugeben.

In der resultierenden Hashtabelle ist jeder Eigenschaftswert ein Schlüssel und die Gruppenelemente sind die Werte.
Da jeder Schlüssel eine Eigenschaft des Hashtabellenobjekts ist, können Sie die Werte mithilfe der punktierten Schreibweise anzeigen.

Der erste Befehl ruft die `Get` `Set` Cmdlets und in der Sitzung ab, gruppiert Sie nach Verb, gibt die Gruppen als Hash Tabelle zurück und speichert die Hash Tabelle in der `$A` Variablen.

Mit dem zweiten Befehl wird die Hash Tabelle in angezeigt `$A` . Es gibt zwei Schlüssel-Wert-Paare, eine für die `Get` Cmdlets und eine für die `Set` Cmdlets.

Der dritte Befehl verwendet die Punkt Notation, `$A.Get` um die Werte der **Get** -Taste in anzuzeigen `$A` . Die Werte sind **cmdletinfo** -Objekte. Der **AsString** -Parameter konvertiert die Objekte in den Gruppen nicht in Zeichen folgen.

```powershell
$A = Get-Command Get-*, Set-* -CommandType cmdlet | Group-Object -Property Verb -AsHashTable -AsString
$A
```

```Output
Name     Value
----     -----
Get      {Get-Acl, Get-Alias, Get-AppLockerFileInformation, Get-AppLockerPolicy...}
Set      {Set-Acl, Set-Alias, Set-AppBackgroundTaskResourcePolicy, Set-AppLockerPolicy...}
```

```powershell
$A.Get
```

```Output
CommandType     Name                               Version    Source
-----------     ----                               -------    ------
Cmdlet          Get-Acl                            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                          3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AppLockerFileInformation       2.0.0.0    AppLocker
Cmdlet          Get-AppLockerPolicy                2.0.0.0    AppLocker
...
```

## PARAMETERS

### -Ashashtable

Gibt an, dass dieses Cmdlet die Gruppe als Hash Tabelle zurückgibt. Die Schlüssel der Hashtabelle sind die Eigenschaftswerte, nach denen die Objekte gruppiert werden. Die Werte der Hashtabelle sind die Objekte, die diesen Eigenschaftswert aufweisen.

Der **ashashtable** -Parameter gibt allein jede Hash Tabelle zurück, in der jeder Schlüssel eine Instanz des gruppierten Objekts ist. Bei Verwendung mit dem **AsString** -Parameter sind die Schlüssel in der Hash Tabelle Zeichen folgen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: AHT

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsString

Gibt an, dass dieses Cmdlet die Hash Tabellenschlüssel in Zeichen folgen konvertiert. Standardmäßig sind die Schlüssel in der Hashtabelle Instanzen des gruppierten Objekts. Dieser Parameter ist nur gültig, wenn er mit dem **ashashtable** -Parameter verwendet wird.

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

### -CaseSensitive

Gibt an, dass mit diesem Cmdlet die Groß-/Kleinschreibung berücksichtigt wird. Ohne diesen Parameter können die Eigenschaftswerte von Objekten in einer Gruppe groß- oder kleingeschrieben sein.

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

### -Kultur

Gibt die Kultur an, die beim Vergleichen von Zeichenfolgen verwendet werden soll.

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

### -InputObject

Gibt die zu gruppierenden Objekte an. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

Wenn Sie den **Inputobject** -Parameter verwenden, um eine Auflistung von Objekten an zu senden `Group-Object` , `Group-Object` empfängt ein Objekt, das die Auflistung darstellt. Daher erstellt es eine einzelne Gruppe mit diesem Objekt als Member.

Um die Objekte in einer Auflistung zu gruppieren, übergeben Sie die Objekte über die Pipeline an `Group-Object` .

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

### -Noelement

Gibt an, dass dieses Cmdlet die Mitglieder einer Gruppe aus den Ergebnissen auslässt.

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

### -Eigenschaft

Gibt die Eigenschaften für die Gruppierung an. Die Objekte werden basierend auf dem Wert der angegebenen Eigenschaft in Gruppen angeordnet.

Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein. Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein. Gültige Schlüssel-Wert-Paare sind:

- Ausdruck `<string>` oder `<script block>`

Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt an die Pipeline übergeben `Group-Object` .

## AUSGABEN

### Microsoft. PowerShell. Commands. groupInfo oder System. Collections. Hashtable

Wenn Sie den **ashashtable** -Parameter verwenden, `Group-Object` gibt ein **Hashtable** -Objekt zurück.
Andernfalls wird ein **groupInfo** -Objekt zurückgegeben.

## HINWEISE

Sie können den **GroupBy** -Parameter der Formatierungs-Cmdlets, z `Format-Table` . b. und `Format-List` , verwenden, um-Objekte zu gruppieren. Anders als bei `Group-Object` , das eine einzelne Tabelle mit einer Zeile für jeden Eigenschafts Wert erstellt, erstellen die **GroupBy** -Parameter eine Tabelle für jeden Eigenschafts Wert mit einer Zeile für jedes Element, das über den Eigenschafts Wert verfügt.

`Group-Object` erfordert nicht, dass die gruppierten Objekte denselben Microsoft .net Frameworktyp haben. Beim Gruppieren von Objekten unterschiedlicher .NET Framework Typen `Group-Object` verwendet die folgenden Regeln:

- Die gleichen Eigenschaftsnamen und-Typen.

  Wenn die Objekte über eine Eigenschaft mit dem angegebenen Namen verfügen und die Eigenschaftswerte denselben .NET Framework-Typ aufweisen, werden die Eigenschaftswerte nach den gleichen Regeln wie für Objekte desselben Typs gruppiert.

- Dieselben Eigenschaftsnamen, verschiedene Typen.

  Wenn die Objekte über eine Eigenschaft mit dem angegebenen Namen verfügen, die Eigenschaftswerte jedoch unterschiedliche .NET Framework Typen in unterschiedlichen Objekten aufweisen, `Group-Object` verwendet den .NET Framework Typ des ersten Vorkommens der Eigenschaft als .NET Framework Typ für diese Eigenschaften Gruppe. Wenn ein Objekt eine Eigenschaft mit einem anderen Typ aufweist, wird der Eigenschaftswert in den Typ für diese Gruppe konvertiert. Wenn bei der Typkonvertierung ein Fehler auftritt, ist das Objekt nicht in der Gruppe enthalten.

- Fehlende Eigenschaften.

  Objekte, die über keine angegebene Eigenschaft verfügen, können nicht gruppiert werden. Nicht gruppierte Objekte werden in der endgültigen **groupInfo** -Objekt Ausgabe in einer Gruppe mit dem Namen angezeigt `AutomationNull.Value` .

## VERWANDTE LINKS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Measure-Object](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
