---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-typedata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-TypeData
ms.openlocfilehash: e8ac450e6681a6bfb9c0b50c8b9cb593ced3bdf3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211364"
---
# Update-TypeData

## Übersicht
Aktualisiert die erweiterten Typdaten in der Sitzung.

## Syntax

### Fileset (Standard)

```
Update-TypeData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Dynamictypeset

```
Update-TypeData [-MemberType <PSMemberTypes>] [-MemberName <String>] [-Value <Object>]
 [-SecondValue <Object>] [-TypeConverter <Type>] [-TypeAdapter <Type>]
 [-SerializationMethod <String>] [-TargetTypeForDeserialization <Type>]
 [-SerializationDepth <Int32>] [-DefaultDisplayProperty <String>]
 [-InheritPropertySerializationSet <Nullable`1>] [-StringSerializationSource <String>]
 [-DefaultDisplayPropertySet <String[]>] [-DefaultKeyPropertySet <String[]>]
 [-PropertySerializationSet <String[]>] -TypeName <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Typedataset

```
Update-TypeData [-Force] [-TypeData] <TypeData[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## BESCHREIBUNG

`Update-TypeData`Mit dem-Cmdlet werden die erweiterten Typdaten in der Sitzung aktualisiert, indem die Dateien erneut in den Arbeits `Types.ps1xml` Speicher geladen und neue erweiterte Typdaten hinzugefügt werden.

Standardmäßig lädt PowerShell erweiterte Typdaten nach Bedarf. Ohne Parameter `Update-TypeData` lädt alle Dateien, die Sie `Types.ps1xml` in die Sitzung geladen hat, einschließlich aller von Ihnen hinzugefügten Typdateien neu. Sie können die Parameter von verwenden `Update-TypeData` , um neue Typdateien hinzuzufügen und erweiterte Typdaten hinzuzufügen und zu ersetzen.

Das- `Update-TypeData` Cmdlet kann verwendet werden, um alle Typdaten vorab zu laden. Diese Funktion ist besonders nützlich, wenn Sie Typen entwickeln und diese neuen Typen zu Testzwecken laden möchten.

Ab Windows PowerShell 3,0 können Sie verwenden, `Update-TypeData` um erweiterte Typdaten in der Sitzung hinzuzufügen und zu ersetzen, ohne eine Datei zu verwenden `Types.ps1xml` . Typdaten die dynamisch, d. h. ohne Datei, hinzugefügt werden, werden nur zur aktuellen Sitzung hinzugefügt. Fügen Sie Ihrem PowerShell-Profil einen Befehl hinzu, um die Typdaten zu allen Sitzungen hinzuzufügen `Update-TypeData` . Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

Außerdem können Sie ab Windows PowerShell 3,0 das `Get-TypeData` Cmdlet verwenden, um die erweiterten Typen in der aktuellen Sitzung zu erhalten, und das `Remove-TypeData` Cmdlet, um erweiterte Typen aus der aktuellen Sitzung zu löschen.

Ausnahmen, die in Eigenschaften auftreten, oder das Hinzufügen von Eigenschaften zu einem `Update-TypeData` Befehl, melden keine Fehler. Dadurch werden Ausnahmen unterdrückt, die während der Formatierung und Ausgabe in vielen gängigen Typen auftreten würden. Wenn Sie .net-Eigenschaften erhalten, können Sie die Unterdrückung von Ausnahmen umgehen, indem Sie stattdessen die Methoden Syntax verwenden, wie im folgenden Beispiel gezeigt:

`"hello".get_Length()`

Beachten Sie, dass die Methoden Syntax nur mit .net-Eigenschaften verwendet werden kann. Eigenschaften, die durch das Ausführen des `Update-TypeData` Cmdlets hinzugefügt werden, können keine Methoden Syntax verwenden.

Weitere Informationen zu den `Types.ps1xml` Dateien in PowerShell finden Sie unter [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).

## Beispiele

### Beispiel 1: Aktualisieren erweiterter Typen

```powershell
Update-TypeData
```

Dieser Befehl aktualisiert die Konfiguration des erweiterten Typs aus den `Types.ps1xml` Dateien, die bereits in der Sitzung verwendet wurden.

### Beispiel 2: mehrmals Aktualisieren von Typen

In diesem Beispiel wird gezeigt, wie die Typen in einer Typdatei mehrmals in der gleichen Sitzung aktualisiert werden.

Der erste Befehl aktualisiert die Konfiguration des erweiterten Typs aus den `Types.ps1xml` Dateien, wobei `TypesA.types.ps1xml` die `TypesB.types.ps1xml` Dateien und zuerst verarbeitet werden.

Der zweite Befehl zeigt, wie Sie den `TypesA.types.ps1xml` erneut aktualisieren können, z. b. Wenn Sie einen Typ in der Datei hinzugefügt oder geändert haben. Sie können entweder den vorherigen Befehl für die Datei wiederholen `TypesA.types.ps1xml` oder einen `Update-TypeData` Befehl ohne Parameter ausführen, da `TypesA.types.ps1xml` bereits in der Liste der Typdateien für die aktuelle Sitzung vorhanden ist.

```powershell
Update-TypeData -PrependPath TypesA.types.ps1xml, TypesB.types.ps1xml
Update-TypeData -PrependPath TypesA.types.ps1xml
```

### Beispiel 3: Hinzufügen einer Skript Eigenschaft zu DateTime-Objekten

In diesem Beispiel `Update-TypeData` wird verwendet, um die **Quarter** -Skript Eigenschaft zu **System. DateTime** -Objekten in der aktuellen Sitzung hinzuzufügen, z. b. die vom `Get-Date` Cmdlet zurückgegebenen.

```powershell
Update-TypeData -TypeName "System.DateTime" -MemberType ScriptProperty -MemberName "Quarter" -Value {
  if ($this.Month -in @(1,2,3)) {"Q1"}
  elseif ($this.Month -in @(4,5,6)) {"Q2"}
  elseif ($this.Month -in @(7,8,9)) {"Q3"}
  else {"Q4"}
}
(Get-Date).Quarter
```

```Output
Q1
```

Der `Update-TypeData` Befehl verwendet den **tykame** -Parameter, um **den System. DateTime** -Typ anzugeben, den **Mitgliedschafts Namen** Parameter, um einen Namen für die neue Eigenschaft anzugeben, die Eigenschaft " **mitgliedschaftentyp** ", um den **scriptproperty** -Typ anzugeben, und den **value** -Parameter, um das Skript anzugeben, das das jährliche Quartal bestimmt.

Der Wert der **Value** -Eigenschaft ist ein Skript, das das aktuelle Quartal berechnet. Der Skriptblock verwendet die `$this` Automatische Variable zur Darstellung der aktuellen Instanz des Objekts und den in-Operator, um zu bestimmen, ob der Monatswert in jedem ganzzahligen Array angezeigt wird. Weitere Informationen zum- `-in` Operator finden Sie unter [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).

Der zweite Befehl ruft die neue Quarter-Eigenschaft des aktuellen Datums ab.

### Beispiel 4: Aktualisieren eines Typs, der standardmäßig in Listen angezeigt wird

In diesem Beispiel wird gezeigt, wie die Eigenschaften eines Typs festgelegt werden, der standardmäßig in Listen angezeigt wird, d. h., wenn keine Eigenschaften angegeben sind. Da die Typdaten nicht in einer Datei angegeben sind `Types.ps1xml` , sind Sie nur in der aktuellen Sitzung gültig.

```powershell
Update-TypeData -TypeName "System.DateTime" -DefaultDisplayPropertySet "DateTime, DayOfYear, Quarter"
Get-Date | Format-List
```

```Output
Thursday, March 15, 2012 12:00:00 AM
DayOfYear : 75
Quarter   : Q1
```

Der erste Befehl verwendet das `Update-TypeData` Cmdlet, um die Standard Listen Eigenschaften für den **System. DateTime** -Typ festzulegen. Der Befehl verwendet den **TypeName** -Parameter, um den Typ anzugeben, und den **DefaultDisplayPropertySet** -Parameter, um die Standardeigenschaften für eine Liste anzugeben. Die ausgewählten Eigenschaften enthalten die neue **Quarter** -Skript Eigenschaft, die in einem vorherigen Beispiel hinzugefügt wurde.

Der zweite Befehl verwendet das `Get-Date` Cmdlet, um ein **System. DateTime** -Objekt zu erhalten, das das aktuelle Datum darstellt. Der Befehl verwendet einen Pipeline Operator ( `|` ), um das **DateTime** -Objekt an das `Format-List` Cmdlet zu senden. Da der `Format-List` Befehl nicht die Eigenschaften angibt, die in der Liste angezeigt werden sollen, verwendet PowerShell die Standardwerte, die vom Befehl festgelegt wurden `Update-TypeData` .

### Beispiel 5: Aktualisieren von Typdaten für ein weitergeleitete Objekt

```powershell
Get-Module | Update-TypeData -MemberType ScriptProperty -MemberName "SupportsUpdatableHelp" -Value {
  if ($this.HelpInfoUri) {$True} else {$False}
}
Get-Module -ListAvailable | Format-Table Name, SupportsUpdatableHelp
```

```Output
Name                             SupportsUpdatableHelp
----                             ---------------------
Microsoft.PowerShell.Diagnostics                  True
Microsoft.PowerShell.Host                         True
Microsoft.PowerShell.Management                   True
Microsoft.PowerShell.Security                     True
Microsoft.PowerShell.Utility                      True
Microsoft.WSMan.Management                        True
PSDiagnostics                                    False
PSScheduledJob                                    True
PSWorkflow                                        True
ServerManager                                     True
TroubleshootingPack                              False
```

In diesem Beispiel wird veranschaulicht, dass beim Übergeben eines Objekts an `Update-TypeData` `Update-TypeData` Erweiterte Typdaten für den Objekttyp hinzufügt.

Diese Technik ist schneller als die Verwendung des- `Get-Member` Cmdlets oder der- `Get-Type` Methode, um den Objekttyp zu erhalten. Wenn Sie jedoch eine Auflistung von Objekten an weiterleiten `Update-TypeData` , aktualisiert Sie die Typdaten des ersten Objekt Typs und gibt dann einen Fehler für alle anderen Objekte in der Auflistung zurück, da der Member bereits für den Typ definiert ist.

Der erste Befehl verwendet das `Get-Module` Cmdlet, um das psscheduledjob-Modul abzurufen. Der Befehl übergibt das Modul Objekt an das `Update-TypeData` Cmdlet, das die Typdaten für den **System. Management. Automation. psmoduleinfo** -Typ und die von ihm abgeleiteten Typen aktualisiert, wie z. b. den moduleinfogruppierung-Typ, der `Get-Module` zurückgibt, wenn Sie den **listavailable** -Parameter im Befehl verwenden.

Die `Update-TypeData` Befehle fügen der **supportsupdatablehelp** -Skript Eigenschaft alle importierten Module hinzu. Der Wert des **value** -Parameters ist ein Skript, das zurückgibt, `$True` Wenn die **helpinfouri** -Eigenschaft des Moduls aufgefüllt ist, und `$False` andernfalls.

Mit dem zweiten Befehl werden die Modul Objekte `Get-Module` an das `Format-Table` Cmdlet weitergeleitet, das die Eigenschaften " **Name** " und " **supportsupdatablehelp** " aller Module in einer Liste anzeigt.

## Parameter

### -Appendpath

Gibt den Pfad zu optionalen `.ps1xml` Dateien an. Die angegebenen Dateien werden in der Reihenfolge geladen, in der sie nach dem Laden der integrierten Dateien aufgelistet sind. Sie können einen **appendpath** -Wert auch über die Pipeline an senden `Update-TypeData` .

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Defaultdisplayproperty

Gibt die Eigenschaft des Typs an, der vom `Format-Wide` Cmdlet angezeigt wird, wenn keine anderen Eigenschaften angegeben sind.

Geben Sie den Namen einer Standardeigenschaft oder erweiterten Eigenschaft des Typs ein. Der Wert dieses Parameters kann der Name eines Typs sein, der im selben Befehl hinzugefügt wird.

Dieser Wert ist nur wirksam, wenn keine breiten Ansichten für den Typ in einer Datei definiert sind `Format.ps1xml` .

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Defaultdisplaypropertyset

Gibt eine oder mehrere Eigenschaften des Typs an. Diese Eigenschaften werden durch das `Format-List` Cmdlet angezeigt, wenn keine anderen Eigenschaften angegeben werden.

Geben Sie die Namen der Standardeigenschaften oder erweiterten Eigenschaften des Typs ein. Der Wert dieses Parameters kann der Name von Typen sein, die im selben Befehl hinzugefügt werden.

Dieser Wert ist nur wirksam, wenn keine Listenansichten für den Typ in einer Datei definiert sind `Format.ps1xml` .

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Defaultkeypropertyset

Gibt eine oder mehrere Eigenschaften des Typs an. Diese Eigenschaften werden von den `Group-Object` -und- `Sort-Object` Cmdlets verwendet, wenn keine anderen Eigenschaften angegeben werden.

Geben Sie die Namen der Standardeigenschaften oder erweiterten Eigenschaften des Typs ein. Der Wert dieses Parameters kann der Name von Typen sein, die im selben Befehl hinzugefügt werden.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Gibt an, dass das Cmdlet die angegebenen Typdaten verwendet, auch wenn für diesen Typ bereits Typdaten angegeben wurden.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DynamicTypeSet, TypeDataSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vererpropertyserializationset

Gibt an, ob der Satz von Eigenschaften, die serialisiert werden, geerbt wird. Der Standardwert ist `$Null`. Zulässige Werte für diesen Parameter:

- `$True`. Der Eigenschaftensatz wird geerbt.
- `$False`. Der Eigenschaftensatz wird nicht geerbt.
- `$Null`. Die Vererbung ist nicht definiert.

Dieser Parameter ist nur gültig, wenn der Wert des **serializationmethod** -Parameters ist `SpecificProperties` . Wenn der Wert dieses Parameters ist `$False` , ist der **propertyserializationset** -Parameter erforderlich.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mitgliedsname

Gibt den Namen einer Eigenschaft oder Methode an.

Verwenden Sie diesen Parameter mit den Parametern **TypeName** , **MemberType** , **Value** und **SecondValue** , um eine Eigenschaft oder Methode eines Typs hinzuzufügen oder zu ändern.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mitgliedstyp

Gibt den Typ des Members an, der hinzugefügt oder geändert werden soll.

Verwenden Sie diesen Parameter mit den Parametern **TypeName** , **MemberType** , **Value** und **SecondValue** , um eine Eigenschaft oder Methode eines Typs hinzuzufügen oder zu ändern. Zulässige Werte für diesen Parameter:

- AliasProperty
- CodeMethod
- CodeProperty
- NoteProperty
- ScriptMethod
- ScriptProperty

Weitere Informationen zu diesen Werten finden Sie unter [psmembership types-Enumeration](/dotnet/api/system.management.automation.psmembertypes).

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: DynamicTypeSet
Aliases:
Accepted values: NoteProperty, AliasProperty, ScriptProperty, CodeProperty, ScriptMethod, CodeMethod

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prepdpath

Gibt den Pfad zu den optionalen `.ps1xml` Dateien an. Die angegebenen Dateien werden in der Reihenfolge geladen, in der sie vor dem Laden der integrierten Dateien aufgelistet sind.

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Propertyserializationset

Gibt die Namen der Eigenschaften an, die serialisiert werden. Verwenden Sie diesen Parameter, wenn der Wert des **SerializationMethod** -Parameters **SpecificProperties** ist.

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondValue

Gibt zusätzliche Werte für die Member **AliasProperty** , **ScriptProperty** , **CodeProperty** oder **CodeMethod** an.

Verwenden Sie diesen Parameter mit den Parametern **tykame** , **Membership Type** , **value** und **SecondValue** , um eine Eigenschaft oder Methode eines Typs hinzuzufügen oder zu ändern.

Wenn der Wert des **Membership Type** -Parameters ist `AliasProperty` , muss der Wert des **SecondValue** -Parameters ein-Datentyp sein. PowerShell konvertiert (d. h. Umwandlungen) den Wert der Alias Eigenschaft in den angegebenen Typ. Wenn Sie z. b. eine Alias Eigenschaft hinzufügen, die einen alternativen Namen für eine Zeichen folgen Eigenschaft bereitstellt, können Sie auch einen **SecondValue** von **System. Int32** angeben, um den Alias-Zeichen folgen Wert in eine ganze Zahl zu konvertieren.

Wenn der Wert des **Membership Type** -Parameters ist `ScriptProperty` , können Sie den **SecondValue** -Parameter verwenden, um einen zusätzlichen Skriptblock anzugeben. Der Skriptblock im Wert des **Value** -Parameters ruft den Wert einer Variablen ab. Der Skriptblock im Wert des **SecondValue** -Parameters legt den Wert der Variablen fest.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Serializationtiefe

Gibt an, wie viele Ebenen von Objekten des Typs als Zeichenfolgen serialisiert werden. Der Standardwert `1` serialisiert das Objekt und seine Eigenschaften. `0`Der Wert serialisiert das Objekt, aber nicht seine Eigenschaften. `2`Der Wert serialisiert das Objekt, dessen Eigenschaften und alle Objekte in den Eigenschafts Werten.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Serializationmethod

Gibt eine Serialisierungsmethode für den Typ an. Eine Serialisierungsmethode bestimmt, welche Eigenschaften des Typs serialisiert werden und mit welchem Verfahren sie serialisiert werden. Zulässige Werte für diesen Parameter:

- `AllPublicProperties`. Serialisieren alle öffentlichen Eigenschaften des Typs. Sie können den **SerializationDepth** -Parameter verwenden, um zu bestimmen, ob die untergeordneten Eigenschaften serialisiert werden sollen.
- `String`. Serialisieren den Typ als eine Zeichenfolge. Sie können **StringSerializationSource** verwenden, um eine Eigenschaft des Typs anzugeben, die als das Ergebnis der Serialisierung verwendet werden soll. Andernfalls wird der Typ mit der **ToString** -Methode des Objekts serialisiert.
- `SpecificProperties`. Serialisiert nur die angegebenen Eigenschaften dieses Typs. Verwenden Sie den **PropertySerializationSet** -Parameter, um die Eigenschaften des Typs anzugeben, die serialisiert werden sollen.
  Sie können auch den **InheritPropertySerializationSet** -Parameter verwenden, um zu bestimmen, ob der Eigenschaftensatz geerbt werden soll, sowie den **SerializationDepth** -Parameter, um zu bestimmen, ob die untergeordneten Eigenschaften serialisiert werden sollen.

In PowerShell werden Serialisierungsmethoden in internen **psstandardmembers** -Objekten gespeichert.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stringserializationsource

Gibt den Namen einer Eigenschaft des Typs an. Der Wert der angegebenen Eigenschaft wird als das Ergebnis der Serialisierung verwendet. Dieser Parameter ist nur gültig, wenn der Wert des **serializationmethod** -Parameters String ist.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Targettypeer fordeserialization

Gibt den Typ an, in den Objekte dieses Typs konvertiert werden, wenn sie deserialisiert werden.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Typeadapter

Gibt den Typ eines typadapters an, z. b. **Microsoft. PowerShell. CIM. ciminstanceadapter** . Ein Typadapter ermöglicht es PowerShell, die Member eines Typs zu erhalten.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeConverter

Gibt einen Typkonverter zum Konvertieren von Werten zwischen verschiedenen Typen an. Wenn ein Typkonverter für einen Typ definiert ist, wird eine Instanz des Typkonverters für die Konvertierung verwendet.

Geben Sie einen **System.Type** -Wert ein, der von den **System.ComponentModel.TypeConverter** - oder **System.Management.Automation.PSTypeConverter** -Klassen abgeleitet ist.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Typedata

Gibt ein Array vom Typ Daten an, das von diesem Cmdlet der Sitzung hinzugefügt wird. Geben Sie eine Variable ein, die ein **typedata** -Objekt oder einen Befehl enthält, der ein **typedata** -Objekt abruft, z `Get-TypeData` . b. einen Befehl. Sie können ein **typedata** -Objekt auch über die Pipeline an senden `Update-TypeData` .

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.Runspaces.TypeData[]
Parameter Sets: TypeDataSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Typname

Gibt den Namen des zu erweiternden Typs an.

Geben Sie für Typen im **System** -Namespace den Kurznamen ein. Für andere Typen ist der vollständige Typname erforderlich. Platzhalter werden nicht unterstützt.

Sie können Typnamen an übergeben `Update-TypeData` . Wenn Sie ein Objekt an die Pipeline übergeben `Update-TypeData` , ruft `Update-TypeData` den Typnamen des Objekts ab, und geben Sie Daten in den Objekttyp ein.

Verwenden Sie diesen Parameter mit den Parametern " **Membership Name** ", " **Membership Type** ", " **value** " und " **SecondValue** " zum Hinzufügen oder Ändern einer Eigenschaft oder Methode eines Typs.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Value

Gibt den Wert der Eigenschaft oder Methode an.

Wenn Sie ein-,-,-oder-Element hinzufügen `AliasProperty` `CodeProperty` `ScriptProperty` `CodeMethod` , können Sie den **SecondValue** -Parameter verwenden, um zusätzliche Informationen hinzuzufügen.

Verwenden Sie diesen Parameter mit den Parametern " **Membership Name** ", " **Membership Type** ", " **value** " und " **SecondValue** " zum Hinzufügen oder Ändern einer Eigenschaft oder Methode eines Typs.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

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

### System.String

Sie können eine Zeichenfolge, die die Werte der Parameter **appendpath** , **TypeName** oder **typedata** enthält, über die Pipeline an übergeben `Update-TypeData` .

## Ausgaben

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## Notizen

## Verwandte Links

[about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[Get-TypeData](Get-TypeData.md)

[Remove-TypeData](Remove-TypeData.md)
