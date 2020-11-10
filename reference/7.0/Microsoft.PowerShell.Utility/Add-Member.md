---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-member?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Member
ms.openlocfilehash: 8c27ebe1c5f1a0c53f5012f1faa17a9fdb1cdcff
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391033"
---
# Add-Member

## ZUSAMMENFASSUNG
Fügt einer Instanz eines PowerShell-Objekts benutzerdefinierte Eigenschaften und Methoden hinzu.

## SYNTAX

### Tytzameset (Standard)

```
Add-Member -InputObject <PSObject> -TypeName <String> [-PassThru] [<CommonParameters>]
```

### Notepropertymultimembership Set

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru]
 [-NotePropertyMembers] <IDictionary> [<CommonParameters>]
```

### Notepropertysinglemembership Set

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru] [-NotePropertyName] <String>
 [-NotePropertyValue] <Object> [<CommonParameters>]
```

### MemberSet

```
Add-Member -InputObject <PSObject> [-MemberType] <PSMemberTypes> [-Name] <String> [[-Value] <Object>]
 [[-SecondValue] <Object>] [-TypeName <String>] [-Force] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Add-Member` Cmdlet können Sie einer Instanz eines PowerShell-Objekts Elemente (Eigenschaften und Methoden) hinzufügen. Beispielsweise können Sie ein NoteProperty-Element hinzufügen, das eine Beschreibung des Objekts enthält, oder ein **ScriptMethod** -Element, das ein Skript zum Ändern des Objekts ausführt.

Um zu verwenden `Add-Member` , übergeben Sie das-Objekt an `Add-Member` , oder verwenden Sie den **Inputobject** -Parameter, um das-Objekt anzugeben.

Der Parameter " **Membership Type** " gibt den Typ des Members an, den Sie hinzufügen möchten. Der **Name** -Parameter weist dem neuen Member einen Namen zu, und der **value** -Parameter legt den Wert des Members fest.

Die Eigenschaften und Methoden, die Sie hinzufügen, werden nur der angegebenen bestimmten Instanz des Objekts hinzugefügt. `Add-Member` der Objekttyp wird nicht geändert. Um einen neuen Objekttyp zu erstellen, verwenden Sie das- `Add-Type` Cmdlet.

Sie können auch das- `Export-Clixml` Cmdlet verwenden, um die Instanz des Objekts, einschließlich der zusätzlichen Elemente, in einer Datei zu speichern. Anschließend können Sie mit dem `Import-Clixml` Cmdlet die Instanz des Objekts aus den Informationen, die in der exportierten Datei gespeichert sind, neu erstellen.

Ab Windows PowerShell 3,0 `Add-Member` verfügt über neue Funktionen, die das Hinzufügen von Hinweis Eigenschaften zu Objekten vereinfachen.
Sie können die Parameter **NotePropertyName** und **NotePropertyValue** verwenden, um eine Hinweiseigenschaft zu definieren, oder aber den **NotePropertyMembers** -Parameter verwenden, der eine Hashtabelle mit Hinweiseigenschaftsnamen und -werten akzeptiert.

Ab Windows PowerShell 3.0 wird außerdem der **PassThru** -Parameter zum Generieren eines Ausgabeobjekts seltener benötigt. `Add-Member` fügt jetzt die neuen Elemente direkt dem Eingabe Objekt anderer Typen hinzu. Weitere Informationen finden Sie in der Beschreibung zum **PassThru** -Parameter.

## BEISPIELE

### Beispiel 1: Hinzufügen einer Note-Eigenschaft zu einem psobject

Im folgenden Beispiel wird dem **FileInfo** -Objekt, das die Datei darstellt, eine **Status** Hinweis Eigenschaft mit dem Wert "Done" hinzugefügt `Test.txt` .

Der erste Befehl verwendet das `Get-ChildItem` Cmdlet, um ein **FileInfo** -Objekt zu erhalten, das die `Test.txt` Datei darstellt. Sie speichert Sie in der `$a` Variablen.

Mit dem zweiten Befehl wird die Note-Eigenschaft dem-Objekt in hinzugefügt `$a` .

Der dritte Befehl verwendet die Punkt Notation, um den Wert der **Status** -Eigenschaft des Objekts in zu erhalten `$a` . Wie die Ausgabe zeigt, lautet der Wert "Done".

```powershell
$A = Get-ChildItem c:\ps-test\test.txt
$A | Add-Member -NotePropertyName Status -NotePropertyValue Done
$A.Status
```

```Output
Done
```

### Beispiel 2: Hinzufügen einer Alias Eigenschaft zu einem psobject

Im folgenden Beispiel wird dem-Objekt, das die Datei darstellt, eine **size** -Alias Eigenschaft hinzugefügt `Test.txt` . Die neue Eigenschaft ist ein Alias für die **length** -Eigenschaft.

Der erste Befehl verwendet das `Get-ChildItem` Cmdlet, um das `Test.txt` **FileInfo** -Objekt zu erhalten.

Mit dem zweiten Befehl wird die **size** -Alias Eigenschaft hinzugefügt.
Der dritte Befehl verwendet die Punkt Notation, um den Wert der neuen **size** -Eigenschaft zu erhalten.

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$A | Add-Member -MemberType AliasProperty -Name Size -Value Length
$A.Size
```

```Output
2394
```

### Beispiel 3: Hinzufügen einer stringuse-Notiz Eigenschaft zu einer Zeichenfolge

In diesem Beispiel wird eine Zeichenfolge der Eigenschaft " **stringuse** Note" hinzugefügt.
Da `Add-Member` Typen zu **Zeichen** folgen Eingabe Objekten keine Typen hinzufügen können, können Sie den **passthru** -Parameter angeben, um ein Ausgabe Objekt zu generieren. Der letzte Befehl im Beispiel zeigt die neue Eigenschaft an.

In diesem Beispiel wird der **notepropertymembers** -Parameter verwendet. Der Wert des **NotePropertyMembers** -Parameters ist eine Hashtabelle. Der Schlüssel ist der Name der Hinweis Eigenschaft ( **stringuse** ), und der Wert ist der Wert der Note-Eigenschaft, **Display**.

```powershell
$A = "A string"
$A = $A | Add-Member -NotePropertyMembers @{StringUse="Display"} -PassThru
$A.StringUse
```

```Output
Display
```

### Beispiel 4: Hinzufügen einer Skript Methode zu einem FileInfo-Objekt

In diesem Beispiel wird die **sizeinmb** -Skript Methode einem **FileInfo** -Objekt hinzugefügt, das die Dateigröße auf das nächste Megabyte berechnet. Mit dem zweiten Befehl wird ein **ScriptBlock** erstellt, der die statische Methode " **Round** " vom `[math]` Typ verwendet, um die Dateigröße auf die zweite Dezimalstelle zu runden.

Der **value** -Parameter verwendet auch die `$This` Automatische Variable, die das aktuelle Objekt darstellt. Die `$This` Variable ist nur in Skript Blöcken gültig, die neue Eigenschaften und Methoden definieren.

Der letzte Befehl verwendet die Punkt Notation, um die neue **sizeinmb** -Skript Methode für das Objekt in der Variablen aufzurufen `$A` .

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$S = {[math]::Round(($this.Length / 1MB), 2)}
$A | Add-Member -MemberType ScriptMethod -Name "SizeInMB" -Value $S
$A.SizeInMB()
```

```Output
0.43
```

### Beispiel 5: Kopieren aller Eigenschaften eines Objekts in ein anderes

Diese Funktion kopiert alle Eigenschaften eines Objekts in ein anderes Objekt.

Die- `foreach` Schleife verwendet das- `Get-Member` Cmdlet, um alle Eigenschaften des **from** -Objekts zu erhalten. Die Befehle in der `foreach` Schleife werden in Reihen für jede der Eigenschaften ausgeführt.

Der- `Add-Member` Befehl fügt die-Eigenschaft des **from** -Objekts dem **to** -Objekt als **NoteProperty** hinzu. Der Wert wird mithilfe des **value** -Parameters kopiert. Er verwendet den **Force** -Parameter, um Member mit demselben Elementnamen hinzuzufügen.

```powershell
function Copy-Property ($From, $To)
{
    $properties = Get-Member -InputObject $From -MemberType Property
    foreach ($p in $properties)
    {
        $To | Add-Member -MemberType NoteProperty -Name $p.Name -Value $From.$($p.Name) -Force
    }
}
```

### Beispiel 6: Erstellen eines benutzerdefinierten Objekts

In diesem Beispiel wird **ein Benutzer** definiertes Medienobjekt erstellt.

Mit dem- `New-Object` Cmdlet wird ein **psobject-Objekt** erstellt. Im Beispiel wird das **psobject** in der `$Asset` Variablen gespeichert.

Mit dem zweiten Befehl wird die `[ordered]` typbeschleunigung verwendet, um ein geordnetes Wörterbuch mit Namen und Werten zu erstellen. Der Befehl speichert das Ergebnis in der `$D` Variablen.

Der dritte Befehl verwendet den **notepropertymembers** -Parameter des `Add-Member` Cmdlets, um das Wörterbuch in der `$D` Variablen dem **psobject** hinzuzufügen.
Die **typame** -Eigenschaft weist dem **psobject** einen neuen Namen, **Asset** , zu.

Mit dem letzten Befehl wird das neue **Asset** -Objekt an das `Get-Member` Cmdlet weitergeleitet. Die Ausgabe zeigt, dass das Objekt den Typnamen **Asset** und die im geordneten Wörterbuch definierten Hinweis Eigenschaften aufweist.

```powershell
$Asset = New-Object -TypeName PSObject
$d = [ordered]@{Name="Server30";System="Server Core";PSVersion="4.0"}
$Asset | Add-Member -NotePropertyMembers $d -TypeName Asset
$Asset | Get-Member
```

```Output
   TypeName: Asset

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty System.String Name=Server30
PSVersion   NoteProperty System.String PSVersion=4.0
System      NoteProperty System.String System=Server Core
```

## PARAMETERS

### -Force

Gibt an, dass dieses Cmdlet ein neues Element hinzufügt, auch wenn das Objekt über einen benutzerdefinierten Member mit demselben Namen verfügt.
Der **Force** -Parameter kann nicht verwendet werden, um einen Standardmember eines Typs zu ersetzen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt das Objekt an, dem das neue Element hinzugefügt wird.
Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Mitgliedstyp

Gibt den Typ des hinzu zufügenden Members an.
Dieser Parameter ist erforderlich.
Zulässige Werte für diesen Parameter:

- NoteProperty
- AliasProperty
- ScriptProperty
- CodeProperty
- ScriptMethod
- CodeMethod

Weitere Informationen zu diesen Werten finden Sie unter [psmembership types-Enumeration](/dotnet/api/system.management.automation.psmembertypes) im PowerShell SDK.

Nicht alle Objekte verfügen über jeden Membertyp.
Wenn Sie einen Elementtyp angeben, der für das Objekt nicht vorhanden ist, gibt PowerShell einen Fehler zurück.

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: MemberSet
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt den Namen des Members an, den dieses Cmdlet hinzufügt.

```yaml
Type: System.String
Parameter Sets: MemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notepropertymembers

Gibt eine Hashtabelle oder ein sortiertes Wörterbuch mit Hinweiseigenschaftsnamen und -werten an.
Geben Sie eine Hashtabelle oder ein Wörterbuch ein, in dem die Schlüssel Hinweiseigenschaftsnamen und die Werte Hinweiseigenschaftswerte sind.

Weitere Informationen zu Hash Tabellen und geordneten Wörterbüchern in PowerShell finden Sie unter [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: NotePropertyMultiMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notepropertyname

Gibt den Hinweis Eigenschaftsnamen an.

Verwenden Sie diesen Parameter mit dem **NotePropertyValue** -Parameter.
Dieser Parameter ist optional.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notepropertyvalue

Gibt den Wert der Note-Eigenschaft an.

Verwenden Sie diesen Parameter mit dem **notepropertyname** -Parameter.
Dieser Parameter ist optional.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Object
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

Bei den meisten-Objekten werden `Add-Member` die neuen Elemente dem Eingabe Objekt hinzugefügt.
Wenn das Eingabe Objekt jedoch eine Zeichenfolge ist, `Add-Member` kann das Element nicht dem Eingabe Objekt hinzufügen.
Verwenden Sie für diese den **PassThru** -Parameter, um ein Ausgabeobjekt zu erstellen.

In Windows PowerShell 2,0 wurden Elemente `Add-Member` nur dem **psobject** -Wrapper von Objekten, nicht dem Objekt hinzugefügt.
Verwenden Sie den **passthru** -Parameter, um ein Ausgabe Objekt für ein Objekt zu erstellen, das über einen **psobject** -Wrapper verfügt.

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

### -SecondValue

Gibt optionale weitere Informationen zu **AliasProperty** -, **ScriptProperty** -, **CodeProperty** - oder **CodeMethod** -Elementen an.

Wenn Sie beim Hinzufügen einer **aliasproperty** verwendet wird, muss dieser Parameter ein-Datentyp sein.
Eine Konvertierung in den angegebenen Datentyp wird dem Wert der **aliasproperty** hinzugefügt.

Wenn Sie z. b. eine **aliasproperty** hinzufügen, die einen alternativen Namen für eine Zeichen folgen Eigenschaft bereitstellt, können Sie auch einen **SecondValue** -Parameter von **System. Int32** angeben, um anzugeben, dass der Wert dieser Zeichen folgen Eigenschaft in eine ganze Zahl konvertiert werden soll, wenn über die entsprechende **aliasproperty** darauf zugegriffen wird.

Mit dem **SecondValue** -Parameter können Sie einen zusätzlichen **ScriptBlock** angeben, wenn Sie ein **scriptproperty** -Element hinzufügen. Der erste **ScriptBlock** , der im **value** -Parameter angegeben wird, wird verwendet, um den Wert einer Variablen zu erhalten. Der zweite **ScriptBlock** , der im **SecondValue** -Parameter angegeben wird, wird verwendet, um den Wert einer Variablen festzulegen.

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Gibt den Anfangswert des hinzugefügten Elements an.
Wenn Sie einen **aliasproperty** -, **CodeProperty** -, **scriptproperty** -oder **codemethod** -Member hinzufügen, können Sie optionale, zusätzliche Informationen mithilfe des **SecondValue** -Parameters angeben.

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Typname

Gibt einen Namen für den Typ an.

Wenn der Typ eine Klasse im **System** -Namespace oder ein Typ mit einer typbeschleunigung ist, können Sie den Kurznamen des Typs eingeben. Für andere Typen ist der vollständige Typname erforderlich.
Dieser Parameter ist nur wirksam, wenn **Inputobject** ein **psobject** ist.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: TypeNameSet, NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: True (TypeNameSet), False (NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System. Management. Automation. psobject

Sie können einen beliebigen Objekttyp an dieses Cmdlet übergeben.

## AUSGABEN

### None oder System. Object

Wenn Sie den **passthru** -Parameter verwenden, gibt dieses Cmdlet das neu erweiterte Objekt zurück.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

Sie können nur Elemente zu **psobject** -Objekten hinzufügen. Verwenden Sie den-Operator, um zu bestimmen, ob ein Objekt ein **psobject** -Objekt ist `-is` .

Um z. b. ein in der Variablen gespeichertes Objekt zu testen `$obj` , geben Sie ein `$obj -is [PSObject]` .

Die Namen der Parameter " **Membership Type** ", " **Name** ", " **value** " und " **SecondValue** " sind optional.
Wenn Sie die Parameternamen weglassen, müssen die unbenannten Parameterwerte in der folgenden Reihenfolge angezeigt werden: **Mitgliedschaftstyp** , **Name** , **Wert** und **SecondValue**.

Wenn Sie die Parameternamen angeben, können die Parameter in beliebiger Reihenfolge angegeben werden.

Sie können die `$this` Automatische Variable in Skript Blöcken verwenden, die die Werte der neuen Eigenschaften und Methoden definieren.
Die- `$this` Variable verweist auf die Instanz des Objekts, dem die Eigenschaften und Methoden hinzugefügt werden. Weitere Informationen zur- `$this` Variablen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

## VERWANDTE LINKS

[Export-Clixml](Export-Clixml.md)

[Get-Member](Get-Member.md)

[Import-Clixml](Import-Clixml.md)

[New-Object](New-Object.md)

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)
