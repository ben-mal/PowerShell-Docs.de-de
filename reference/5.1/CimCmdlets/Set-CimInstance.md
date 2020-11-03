---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/set-ciminstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-CimInstance
ms.openlocfilehash: 7f44ddf52c2ad3ce68c5eccf0e8f952a0fa1873e
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218095"
---
# Set-CimInstance

## ZUSAMMENFASSUNG
Ändert eine CIM-Instanz auf einem CIM-Server durch Aufrufen der modifyinstance-Methode der CIM-Klasse.

## SYNTAX

### Ciminstancecomputerset (Standard)

```
Set-CimInstance [-ComputerName <String[]>] [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Ciminstancesessionset

```
Set-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-Property <IDictionary>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Querysessionset

```
Set-CimInstance -CimSession <CimSession[]> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Querycomputerset

```
Set-CimInstance [-ComputerName <String[]>] [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-Query] <String> [-QueryDialect <String>] -Property <IDictionary> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Dieses Cmdlet ändert eine CIM-Instanz auf einem CIM-Server.

Wenn der **Inputobject** -Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:

- Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).
- Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.

Wenn der **Inputobject** -Parameter angegeben wird, funktioniert das Cmdlet auf eine der folgenden Arten:

- Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, verwendet dieses Cmdlet die CIM-Sitzung oder den Computernamen aus dem Eingabe Objekt.
- Wenn der **Computername** -Parameter oder der **cimsession** -Parameter angegeben wird, verwendet dieses Cmdlet entweder den Wert des **cimsession** -Parameter Werts oder den Wert des **Computername** -Parameters. Dies ist nicht sehr üblich.

## BEISPIELE

### Beispiel 1: Festlegen der CIM-Instanz

In diesem Beispiel wird der Wert der **VariableValue** -Eigenschaft mithilfe des **Abfrage** Parameters auf **ABCD** festgelegt. Sie können-Instanzen ändern, die mit einer WQL-Abfrage (Windows-Verwaltungsinstrumentation Query Language) übereinstimmen.

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"}
```

### Beispiel 2: Festlegen der CIM-Instanzeigenschaft mithilfe der Pipeline

In diesem Beispiel wird das CIM-Instanzobjekt, das durch den **Abfrage** Parameter gefiltert wird, mithilfe des- `Get-CimInstance` Cmdlets abgerufen. Das `Set-CimInstance` Cmdlet ändert den Wert der **VariableValue** -Eigenschaft in **ABCD**.

```powershell
Get-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' |
  Set-CimInstance -Property @{VariableValue="abcd"}
```

### Beispiel 3: Festlegen der CIM-Instanzeigenschaft mithilfe des Eingabe Objekts

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where Name="testvar"'
Set-CimInstance -InputObject $x -Property @{VariableValue="somevalue"} -PassThru
```

In diesem Beispiel werden die CIM-Instanzobjekte, die vom Abfrage Parameter in gefiltert werden, mithilfe von zu einer Variablen abgerufen `$x` `Get-CimInstance` und dann der Inhalt der Variablen an das `Set-CimInstance` Cmdlet übergeben. `Set-CimInstance` ändert dann die **VariableValue** -Eigenschaft in " **someValue** ". Da der **passthru** -Parameter verwendet wird, gibt dieses Beispiel ein geändertes CIM-Instanzobjekt zurück.

### Beispiel 4: Festlegen der CIM-Instanzeigenschaft

In diesem Beispiel wird das CIM-Instanzobjekt, das im- **Abfrage** Parameter angegeben ist `$x` , mithilfe des `Get-CimInstance` -Cmdlets in eine Variable abgerufen, und der **VariableValue** -Eigenschafts Wert des-Objekts wird geändert. Das CIM-Instanzobjekt wird dann mithilfe des `Set-CimInstance` Cmdlets gespeichert.
Da der **passthru** -Parameter verwendet wird, gibt dieses Beispiel ein geändertes CIM-Instanzobjekt zurück.

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Environment where name="testvar"'
$x.VariableValue = "Change"
Set-CimInstance -CimInstance $x -PassThru
```

### Beispiel 5: Anzeigen der Liste der CIM-Instanzen, die mit WhatIf geändert werden sollen

In diesem Beispiel wird der allgemeine Parameter **WhatIf** verwendet, um anzugeben, dass die Änderung nicht durchgeführt werden soll, sondern nur, was geschehen würde, wenn dies geschehen wäre.

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -WhatIf
```

### Beispiel 6: Festlegen der CIM-Instanz nach der Bestätigung durch den Benutzer

In diesem Beispiel wird der allgemeine Parameter **Confirm** verwendet, um anzugeben, dass die Änderung erst nach der Bestätigung durch den Benutzer vorgenommen werden soll.

```powershell
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"} -Confirm
```

### Beispiel 7: Festlegen der erstellten CIM-Instanz

In diesem Beispiel wird mithilfe des-Cmdlets eine CIM-Instanz mit den angegebenen Eigenschaften erstellt `New-CimInstance` und der Inhalt in eine Variable abgerufen `$x` . Die Variable wird dann an das `Set-CimInstance` Cmdlet übergeben, das den Wert der **VariableValue** -Eigenschaft in " **someValue** " ändert.
Da der **passthru** -Parameter verwendet wird, gibt dieses Beispiel ein geändertes CIM-Instanzobjekt zurück.

```powershell
$x = New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";UserName="domain\user"} -Keys Name,UserName -ClientOnly
Set-CimInstance -CimInstance $x -Property @{VariableValue="somevalue"} -PassThru
```

## PARAMETERS

### -CimSession

Führt die Cmdlets auf einem Remote Computer aus. Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines- `New-CimSession` oder- `Get-CimSession` Cmdlets.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: QuerySessionSet, CimInstanceSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName

Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten. Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) oder einen NetBIOS-Namen angeben.

Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.

Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.

Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet eine Verbindung mit einer CIM-Sitzung eine bessere Leistung.

```yaml
Type: System.String[]
Parameter Sets: CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt ein CIM-Instanzobjekt an, das als Eingabe verwendet wird.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Namespace

Gibt den Namespace für den CIM-Vorgang an. Der Standard Namespace ist root/cimv2. Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Operationtimeoutsec

Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet. Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.

Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

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

### -Eigenschaft

Gibt die Eigenschaften der CIM-Instanz als Hash Tabelle an (unter Verwendung von Name-Wert-Paaren). Nur die Eigenschaften, die mit diesem Parameter angegeben werden, werden geändert. Andere Eigenschaften der CIM-Instanz werden nicht geändert.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet, QuerySessionSet, QueryComputerSet
Aliases: Arguments

Required: True (QuerySessionSet, QueryComputerSet), False (CimInstanceComputerSet, CimInstanceSessionSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Query

Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt wird, um CIM-Instanzen abzurufen, für die das Cmdlet ausgeführt werden soll. Sie können den Abfrage Dialekt mithilfe des querydialekt-Parameters angeben.

Wenn der angegebene Wert doppelte Anführungszeichen ( `"` ), einfache Anführungszeichen ( `'` ) oder einen umgekehrten Schrägstrich ( `\` ) enthält, müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich () vorangestellt werden `\` . Wenn der angegebene Wert den WQL **like** -Operator verwendet, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern ( `[]` ) einschließen: Prozent ( `%` ), Unterstrich ( `_` ) oder öffnende eckige Klammer ( `[` ).

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Querydialekt

Gibt die Abfragesprache an, die für den Abfrage Parameter verwendet wird. Die zulässigen Werte für diesen Parameter sind: **WQL** oder **CQL**. Der Standardwert ist **WQL**.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceUri

Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an. Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.

Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource. Beispiel:

- `http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`
- `http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.

ResourceUri kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der Computername-Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt. Wenn Sie diesen Parameter ohne Angabe des Computername-Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie eine Fehlermeldung, da das DCOM-Protokoll den resourceUri-Parameter nicht unterstützt.

Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### Microsoft.Management.Infrastructure.CimInstance

## AUSGABEN

### Microsoft.Management.Infrastructure.CimInstance

Wenn der **passthru** -Parameter angegeben wird, gibt dieses Cmdlet ein geändertes CIM-Instanzobjekt zurück.

## HINWEISE

## VERWANDTE LINKS

[Get-CimInstance](get-ciminstance.md)

[New-CimInstance](New-CimInstance.md)

[Remove-CimInstance](remove-ciminstance.md)
