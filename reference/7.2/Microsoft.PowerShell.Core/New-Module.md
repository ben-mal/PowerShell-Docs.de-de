---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Module
ms.openlocfilehash: 487fd85bdcc918b7fb360f9c9d23388a06b35f86
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602541"
---
# New-Module

## ZUSAMMENFASSUNG
Erstellt ein neues dynamisches Modul, das nur im Arbeitsspeicher vorhanden ist.

## SYNTAX

### ScriptBlock (Standard)

```
New-Module [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>] [-ReturnResult]
 [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### Name

```
New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-Function <String[]>] [-Cmdlet <String[]>]
 [-ReturnResult] [-AsCustomObject] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `New-Module` Cmdlet wird ein dynamisches Modul aus einem Skriptblock erstellt. Die Elemente des dynamischen Moduls, wie z. B. Funktionen und Variablen, sind in der Sitzung sofort verfügbar und bleiben verfügbar, bis Sie die Sitzung schließen.

Wie bei statischen Modulen werden in einem dynamischen Modul die Cmdlets und Funktionen standardmäßig exportiert, die Variablen und Aliase jedoch nicht. Sie können jedoch das Export-ModuleMember-Cmdlet und die Parameter von verwenden `New-Module` , um die Standardwerte zu überschreiben.

Sie können auch den **ascustomobject** -Parameter von verwenden `New-Module` , um das dynamische Modul als benutzerdefiniertes Objekt zurückzugeben. Die Elemente der Module, wie z. B. Funktionen, werden als Skriptmethoden des benutzerdefinierten Objekts implementiert, statt in die Sitzung importiert zu werden.

Dynamische Module sind nur im Arbeitsspeicher vorhanden, nicht auf dem Datenträger. Wie bei allen Modulen werden die Elemente von dynamischen Modulen in einem privaten Modulbereich ausgeführt, der ein untergeordnetes Element des globalen Bereichs ist. Get-Module kann kein dynamisches Modul abrufen; Get-Command kann jedoch die exportierten Elemente abrufen.

Um ein dynamisches Modul für verfügbar zu machen, übergeben Sie `Get-Module` einen `New-Module` Befehl an Import-Module, oder übergeben Sie das Modul Objekt, das `New-Module` an zurückgegeben wird `Import-Module` . Durch diese Aktion wird das dynamische Modul der `Get-Module` Liste hinzugefügt, aber das Modul wird nicht auf dem Datenträger gespeichert oder persistent gemacht.

## BEISPIELE

### Beispiel 1: Erstellen eines dynamischen Moduls

In diesem Beispiel wird ein neues dynamisches Modul mit einer Funktion mit dem Namen erstellt `Hello` . Der Befehl gibt ein Modulobjekt zurück, das das neue dynamische Modul darstellt.

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

### Beispiel 2: Arbeiten mit dynamischen Modulen und Get-Module und Get-Command

Dieses Beispiel zeigt, dass dynamische Module nicht vom `Get-Module` Cmdlet zurückgegeben werden. Die Elemente, die Sie exportieren, werden vom `Get-Command` Cmdlet zurückgegeben.

```powershell
new-module -scriptblock {function Hello {"Hello!"}}
```

```Output
Name              : __DynamicModule_2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Path              : 2ceb1d0a-990f-45e4-9fe4-89f0f6ead0e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Module

Get-Command Hello
```

```Output
CommandType     Name   Definition
-----------     ----   ----------
Function        Hello  "Hello!"
```

### Beispiel 3: Exportieren einer Variablen in die aktuelle Sitzung

In diesem Beispiel wird das- `Export-ModuleMember` Cmdlet zum Exportieren einer Variablen in die aktuelle Sitzung verwendet.
Ohne den `Export-ModuleMember` Befehl wird nur die Funktion exportiert.

```powershell
New-Module -ScriptBlock {$SayHelloHelp="Type 'SayHello', a space, and a name."; function SayHello ($name) { "Hello, $name" }; Export-ModuleMember -function SayHello -Variable SayHelloHelp}
$SayHelloHelp
```

```Output
Type 'SayHello', a space, and a name.
```

```powershell
SayHello Jeffrey
```

```Output
Hello, Jeffrey
```

Die Ausgabe zeigt, dass die Variable und die Funktion in die Sitzung exportiert wurden.

### Beispiel 4: Bereitstellen eines dynamischen Moduls für Get-Module

In diesem Beispiel wird veranschaulicht, dass Sie ein dynamisches Modul für verfügbar machen können, `Get-Module` indem Sie das dynamische Modul an weiterleiten `Import-Module` .

`New-Module` erstellt ein Modul Objekt, das an das `Import-Module` Cmdlet weitergeleitet wird. Der **Name** -Parameter von `New-Module` weist dem Modul einen anzeigen Amen zu. Da keine `Import-Module` Objekte standardmäßig zurückgibt, gibt es keine Ausgabe dieses Befehls. `Get-Module` Das **greetingmodule** wurde in die aktuelle Sitzung importiert.

```powershell
New-Module -ScriptBlock {function Hello {"Hello!"}} -name GreetingModule | Import-Module
Get-Module
```

```Output
Name              : GreetingModule
Path              : d54dfdac-4531-4db2-9dec-0b4b9c57a1e5
Description       :
Guid              : 00000000-0000-0000-0000-000000000000
Version           : 0.0
ModuleBase        :
ModuleType        : Script
PrivateData       :
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Hello, Hello]}
ExportedVariables : {}
NestedModules     : {}
```

```powershell
Get-Command hello
```

```Output
CommandType     Name                                                               Definition
-----------     ----                                                               ----------
Function        Hello                                                              "Hello!"
```

Das `Get-Command` Cmdlet zeigt die `Hello` Funktion an, die das dynamische Modul exportiert.

### Beispiel 5: Generieren eines benutzerdefinierten Objekts mit exportierten Funktionen

Dieses Beispiel zeigt, wie der **ascustomobject** -Parameter von verwendet wird `New-Module` , um ein benutzerdefiniertes Objekt zu generieren, das über Skript Methoden verfügt, die die exportierten Funktionen darstellen

Das `New-Module` -Cmdlet erstellt ein dynamisches Modul mit zwei Funktionen: `Hello` und `Goodbye` . Der **ascustomobject** -Parameter erstellt anstelle des **psmoduleinfo** -Objekts, das `New-Module` standardmäßig generiert, ein benutzerdefiniertes-Objekt. Dieses benutzerdefinierte Objekt wird in der `$m` Variablen gespeichert.
Der `$m` Variablen scheint kein Wert zugewiesen zu sein.

```powershell
$m = New-Module -ScriptBlock {
  function Hello ($name) {"Hello, $name"}
  function Goodbye ($name) {"Goodbye, $name"}
} -AsCustomObject
$m
$m | Get-Member
```

```Output
TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Goodbye     ScriptMethod System.Object Goodbye();
Hello       ScriptMethod System.Object Hello();
```

```powershell
$m.goodbye("Jane")
```

```Output
Goodbye, Jane
```

```powershell
$m.hello("Manoj")
```

```Output
Hello, Manoj
```

`$m`Bei der Weiterleitung an das `Get-Member` Cmdlet werden die Eigenschaften und Methoden des benutzerdefinierten Objekts angezeigt. Die Ausgabe zeigt, dass das Objekt über Skript Methoden verfügt, die die `Hello` Funktionen und darstellen `Goodbye` .
Zum Schluss werden diese Skript Methoden aufgerufen und die Ergebnisse angezeigt.

### Beispiel 6: erhalten der Ergebnisse des Skript Blocks

In diesem Beispiel wird der **ReturnResult** -Parameter verwendet, um die Ergebnisse der Ausführung des Skript Blocks statt eines Modul Objekts anzufordern. Der Skriptblock im neuen Modul definiert die `SayHello` Funktion und ruft dann die Funktion auf.

```powershell
New-Module -ScriptBlock {function SayHello {"Hello, World!"}; SayHello} -ReturnResult
```

```Output
Hello, World!
```

## PARAMETERS

### -Argumentlist

Gibt ein Array von Argumenten an, bei denen es sich um Parameterwerte handelt, die an den Skriptblock übergeben werden. Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ascustomobject

Gibt an, dass dieses Cmdlet ein benutzerdefiniertes Objekt zurückgibt, das das dynamische Modul darstellt. Die Modulelemente werden als Skriptmethoden des benutzerdefinierten Objekts implementiert, aber sie werden nicht in die Sitzung importiert. Sie können das benutzerdefinierte Objekt in einer Variablen speichern und die punktierte Schreibweise verwenden, um die Elemente aufzurufen.

Wenn das Modul über mehrere Member mit demselben Namen verfügt, z. b. eine Funktion und eine Variable, die beide den Namen a aufweisen, kann vom benutzerdefinierten Objekt nur auf ein Element mit jedem Namen zugegriffen werden.

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

### -Cmdlet

Gibt ein Array von Cmdlets an, die dieses Cmdlet aus dem Modul in die aktuelle Sitzung exportiert.
Geben Sie eine kommagetrennte Liste von Cmdlets ein. Platzhalterzeichen sind zulässig. Standardmäßig werden alle Cmdlets im Modul exportiert.

Sie können keine Cmdlets in einem Skriptblock definieren, aber ein dynamisches Modul kann Cmdlets enthalten, wenn es die Cmdlets aus einem binären Modul importiert.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Funktion

Gibt ein Array von Funktionen an, die dieses Cmdlet aus dem Modul in die aktuelle Sitzung exportiert.
Geben Sie eine kommagetrennte Liste von Funktionen ein. Platzhalterzeichen sind zulässig. Standardmäßig werden alle in einem Modul definierten Funktionen exportiert.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

Gibt einen Namen für das neue Modul an. Sie können auch einen Modulnamen an New-Module übergeben.

Der Standardwert ist ein automatisch generierter Name, der mit beginnt, `__DynamicModule_` gefolgt von einer GUID, die den Pfad des dynamischen Moduls angibt.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ReturnResult

Gibt an, dass dieses Cmdlet den Skriptblock ausführt und die Skriptblock Ergebnisse zurückgibt, anstatt ein Modul Objekt zurückzugeben.

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

### -ScriptBlock

Gibt den Inhalt des dynamischen Moduls an. Schließen Sie den Inhalt in geschweifte Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen. Dieser Parameter ist erforderlich.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können einen Modulnamen über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### System. Management. Automation. psmoduleinfo, System. Management. Automation. pscustomobject oder None

Dieses Cmdlet generiert standardmäßig ein **psmoduleinfo** -Objekt. Wenn Sie den **ascustomobject** -Parameter verwenden, generiert er ein **pscustomobject** -Objekt. Wenn Sie den **ReturnResult** -Parameter verwenden, wird das Ergebnis der Auswertung des Skript Blocks im dynamischen Modul zurückgegeben.

## HINWEISE

Sie können auch auf `New-Module` den Alias verweisen `nmo` . Weitere Informationen finden Sie unter [about_Aliases](About/about_Aliases.md).

## VERWANDTE LINKS

[Export-ModuleMember](Export-ModuleMember.md)

[Get-Module](Get-Module.md)

[Import-Module](Import-Module.md)

[Remove-Module](Remove-Module.md)

