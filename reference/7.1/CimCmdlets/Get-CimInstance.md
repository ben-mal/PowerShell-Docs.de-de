---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/21/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-ciminstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimInstance
ms.openlocfilehash: 01a2ba8f4a377e1e37e30d666ecb2c777b138bdd
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218815"
---
# Get-CimInstance

## ZUSAMMENFASSUNG
Ruft die CIM-Instanzen einer Klasse von einem CIM-Server ab.

## SYNTAX

### Classnamecomputerset (Standard)

```
Get-CimInstance [-ClassName] <String> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### Resourceurisessionset

```
Get-CimInstance -CimSession <CimSession[]> -ResourceUri <Uri> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### Querysessionset

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

### Classnamesessionset

```
Get-CimInstance -CimSession <CimSession[]> [-ClassName] <String> [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-QueryDialect <String>] [-Shallow] [-Filter <String>]
 [-Property <String[]>] [<CommonParameters>]
```

### Ciminstancesessionset

```
Get-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### Ciminstancecomputerset

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [<CommonParameters>]
```

### Resourceuricomputerset

```
Get-CimInstance -ResourceUri <Uri> [-ComputerName <String[]>] [-KeyOnly] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-Shallow] [-Filter <String>] [-Property <String[]>]
 [<CommonParameters>]
```

### Querycomputerset

```
Get-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] -Query <String> [-QueryDialect <String>] [-Shallow]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-CimInstance` Cmdlet werden die CIM-Instanzen einer Klasse von einem CIM-Server abgerufen. Sie können entweder den Klassennamen oder eine Abfrage für dieses Cmdlet angeben. Dieses Cmdlet gibt mindestens ein CIM-Instanzobjekt zurück, das eine Momentaufnahme der CIM-Instanzen darstellt, die auf dem CIM-Server vorhanden sind.

Wenn der **Inputobject** -Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:

- Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).
- Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.

Wenn der **Inputobject** -Parameter angegeben wird, funktioniert das Cmdlet auf eine der folgenden Arten:

- Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, verwendet dieses Cmdlet die CIM-Sitzung oder den Computernamen aus dem Eingabe Objekt.
- Wenn der **Computername** -Parameter oder der **cimsession** -Parameter angegeben wird, verwendet dieses Cmdlet entweder den Wert des cimsession-Parameter Werts oder den Wert des **Computername** -Parameters.

## BEISPIELE

### Beispiel 1: Holen Sie sich die CIM-Instanzen einer bestimmten Klasse.

In diesem Beispiel werden die CIM-Instanzen einer Klasse mit dem Namen **Win32_Process** abgerufen.

```powershell
Get-CimInstance -ClassName Win32_Process
```

### Beispiel 2: erhalten einer Liste von Namespaces von einem WMI-Server

In diesem Beispiel wird eine Liste von Namespaces **unter dem Stamm** Namespace auf einem WMI-Server abgerufen.

```powershell
Get-CimInstance -Namespace root -ClassName __Namespace
```

### Beispiel 3: Abfragen von Instanzen einer Klasse, die mithilfe einer Abfrage gefiltert werden

In diesem Beispiel werden alle CIM-Instanzen abgerufen, die mit dem Buchstaben " **P** " einer Klasse mit dem Namen " **Win32_Process** " unter Verwendung der von einem **Abfrage** Parameter angegebenen Abfrage beginnen.

```powershell
Get-CimInstance -Query "SELECT * from Win32_Process WHERE name LIKE 'P%'"
```

### Beispiel 4: Get-Instanzen einer Klasse, gefiltert mithilfe eines Klassen namens und eines Filter Ausdrucks

In diesem Beispiel werden alle CIM-Instanzen abgerufen, die mit dem Buchstaben " **P** " einer Klasse namens " **Win32_Process** " mit dem Filter-Parameter beginnen.

```powershell
Get-CimInstance -ClassName Win32_Process -Filter "Name like 'P%'"
```

### Beispiel 5: Holen Sie sich die CIM-Instanzen, für die nur Schlüsseleigenschaften ausgefüllt sind.

In diesem Beispiel wird eine neue CIM-Instanz im Arbeitsspeicher für eine Klasse mit dem Namen **Win32_Process** mit der Schlüsseleigenschaft erstellt `@{ "Handle"=0 }` und in einer Variablen mit dem Namen gespeichert `$x` . Die Variable wird als CIM-Instanz an das `Get-CimInstance` Cmdlet übergeben, um eine bestimmte Instanz zu erhalten.

```powershell
$x = New-CimInstance -ClassName Win32_Process -Namespace root\cimv2 -Property @{ "Handle"=0 } -Key Handle -ClientOnly
Get-CimInstance -CimInstance $x
```

### Beispiel 6: Abrufen von CIM-Instanzen und wieder verwenden

In diesem Beispiel werden die CIM-Instanzen einer Klasse mit dem Namen **Win32_Process** abgerufen und in den Variablen `$x` und gespeichert `$y` . Die Variable `$x` wird dann in einer Tabelle formatiert, die nur die Eigenschaften **Name** und **kernelmodetime** enthält, wobei die Tabelle auf **AutoSize** festgelegt ist.

```powershell
$x,$y = Get-CimInstance -ClassName Win32_Process
$x | Format-Table -Property Name,KernelModeTime -AutoSize
```

```Output
Name                 KernelModeTime
----                 --------------
System Idle Process 157238797968750
```

### Beispiel 7: erhalten von CIM-Instanzen vom Remote Computer

In diesem Beispiel werden die CIM-Instanzen einer Klasse mit dem Namen **Win32_ComputerSystem** von den Remote Computern namens **Server01** und **Server02** abgerufen.

```powershell
Get-CimInstance -ClassName Win32_ComputerSystem -ComputerName Server01,Server02
```

### Beispiel 8: erhalten von nur die Schlüsseleigenschaften anstelle aller Eigenschaften

In diesem Beispiel werden nur die Schlüsseleigenschaften abgerufen, wodurch die Größe des Objekts und der Netzwerk Datenverkehr reduziert wird.

```powershell
$x = Get-CimInstance -Class Win32_Process -KeyOnly
$x | Invoke-CimMethod -MethodName GetOwner
```

### Beispiel 9: nur eine Teilmenge der Eigenschaften anstelle aller Eigenschaften

In diesem Beispiel wird nur eine Teilmenge der Eigenschaften abgerufen, wodurch die Größe des Objekts und der Netzwerk Datenverkehr reduziert wird.

```powershell
Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x = Get-CimInstance -Class Win32_Process -Property Name,KernelModeTime
$x | Invoke-CimMethod -MethodName GetOwner
```

Die-Instanz, die mit dem **Property** -Parameter abgerufen wird, kann verwendet werden, um andere CIM-Vorgänge auszuführen, z.b. `Set-CimInstance` oder `Invoke-CimMethod` .

### Beispiel 10: erhalten der CIM-Instanz mithilfe der CIM-Sitzung

In diesem Beispiel wird eine CIM-Sitzung auf den Computern namens **Server01** und **Server02** mithilfe des `New-CimSession` Cmdlets erstellt und die Sitzungsinformationen in einer Variablen mit dem Namen gespeichert `$s` . Der Inhalt der Variablen wird dann `Get-CimInstance` mithilfe des **cimsession** -Parameters an übergeben, um die CIM-Instanzen der Klasse mit dem Namen " **Win32_ComputerSystem** " zu erhalten.

```powershell
$s = New-CimSession -ComputerName Server01,Server02
Get-CimInstance -ClassName Win32_ComputerSystem -CimSession $s
```

## PARAMETERS

### -CimSession

Gibt die CIM-Sitzung an, die für dieses Cmdlet verwendet werden soll. Geben Sie eine Variable ein, die die CIM-Sitzung oder einen Befehl enthält, der die CIM-Sitzung erstellt `New-CimSession` oder `Get-CimSession` abruft, z. b. die Cmdlets oder. Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, CimInstanceSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClassName

Gibt den Namen der CIM-Klasse an, für die die CIM-Instanzen abgerufen werden sollen. Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName

Gibt den Computer an, auf dem Sie den CIM-Vorgang ausführen möchten. Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN), einen NetBIOS-Namen oder eine IP-Adresse angeben. Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.

Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.

Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, stellen Sie eine Verbindung mithilfe einer CIM-Sitzung her, um die Leistung zu verbessern.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, CimInstanceComputerSet, ResourceUriComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Filter

Gibt eine WHERE-Klausel an, die als Filter verwendet werden soll. Geben Sie die-Klausel entweder in der **WQL** -oder der **CQL** -Abfragesprache an. Fügen Sie das- `WHERE` Schlüsselwort nicht in den Wert des-Parameters ein.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Gibt ein CIM-Instanzobjekt an, das als Eingabe verwendet wird.

Wenn Sie bereits mit einem CIM-Instanzobjekt arbeiten, können Sie diesen Parameter verwenden, um das CIM-Instanzobjekt zu übergeben, um die neueste Momentaufnahme vom CIM-Server zu erhalten. Wenn Sie ein CIM-Instanzobjekt als Eingabe übergeben, wird `Get-CimInstance` das Objekt vom Server mit einem Get-CIM-Vorgang anstelle eines auflisten-oder Abfrage Vorgangs zurückgegeben. Die Verwendung eines Get-CIM-Vorgangs ist effizienter als das Abrufen aller Instanzen und das anschließende filtern.

Wenn die CIM-Klasse den Get-Vorgang nicht implementiert, gibt die Angabe des **Inputobject** -Parameters einen Fehler zurück.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceSessionSet, CimInstanceComputerSet
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Keyonly

Gibt an, dass nur Objekte mit aufgefüllten Schlüsseleigenschaften zurückgegeben werden. Durch die Angabe des **keyonly** -Parameters wird die Menge der über das Netzwerk übertragenen Daten reduziert.

Verwenden Sie den **keyonly** -Parameter, um nur einen kleinen Teil des-Objekts zurückzugeben, der für andere Vorgänge, wie z `Set-CimInstance` . b. die-oder-Cmdlets, verwendet werden kann `Get-CimAssociatedInstance` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Gibt den Namespace der CIM-Klasse an.

Der Standard Namespace ist **root/cimv2**. Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
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

### -Eigenschaft

Gibt eine Gruppe von Instanzeigenschaften an, die abgerufen werden sollen. Verwenden Sie diesen Parameter, wenn Sie die Größe des Objekts, das entweder im Arbeitsspeicher oder über das Netzwerk zurückgegeben wird, verringern müssen. Das zurückgegebene Objekt enthält auch die Schlüsseleigenschaften, auch wenn Sie Sie nicht mithilfe des **Property** -Parameters aufgelistet haben. Es sind andere Eigenschaften der-Klasse vorhanden, die jedoch nicht aufgefüllt werden.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, ClassNameSessionSet, ResourceUriComputerSet
Aliases: SelectProperties

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Query

Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt werden soll. Wenn der angegebene Wert doppelte Anführungszeichen `"` , einfache Anführungszeichen `'` oder einen umgekehrten Schrägstrich enthält `\` , müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich vorangestellt werden. Wenn für den angegebenen Wert der WQL **like** -Operator verwendet wird, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern einschließen `[]` : Prozent `%` , unterstrich `_` oder öffnende eckige Klammer `[` .

Es ist nicht möglich, eine Metadatenabfrage zum Abrufen einer Liste von Klassen oder einer Ereignis Abfrage zu verwenden. Verwenden Sie das-Cmdlet, um eine Liste der Klassen abzurufen `Get-CimClass` . Verwenden Sie zum Abrufen einer Ereignis Abfrage das- `Register-CimIndicationEvent` Cmdlet.

Sie können den Abfrage Dialekt mithilfe des **querydialekt** -Parameters angeben.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Querydialekt

Gibt die Abfragesprache an, die für den Abfrage Parameter verwendet wird. Die zulässigen Werte für diesen Parameter sind: **WQL** oder **CQL**. Der Standardwert ist **WQL**.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QuerySessionSet, ClassNameSessionSet, QueryComputerSet
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

**ResourceUri** kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der **Computername** -Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt. Wenn Sie diesen Parameter ohne Angabe des **Computername** -Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie eine Fehlermeldung, da das DCOM-Protokoll den **resourceUri** -Parameter nicht unterstützt.

Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet, QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (QuerySessionSet, QueryComputerSet, CimInstanceSessionSet, CimInstanceComputerSet)
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Flach

Gibt an, dass die Instanzen einer Klasse zurückgegeben werden, ohne die Instanzen von untergeordneten Klassen einzubeziehen. Standardmäßig gibt das Cmdlet die Instanzen einer Klasse und ihrer untergeordneten Klassen zurück.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ResourceUriSessionSet, QuerySessionSet, ClassNameSessionSet, ResourceUriComputerSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### CIM-Instanz

Dieses Cmdlet akzeptiert ein Eingabe Objekt, das mit dem Inputobject-Parameter angegeben wird.

## AUSGABEN

### CIM-Instanz

Dieses Cmdlet gibt ein oder mehrere CIM-Instanzobjekte zurück, die eine Momentaufnahme der CIM-Instanzen auf dem CIM-Server darstellen.

## HINWEISE

## VERWANDTE LINKS

[Format-Table](../microsoft.powershell.utility/format-table.md)

[Get-CimAssociatedInstance](Get-CimAssociatedInstance.md)

[Get-CimClass](Get-CimClass.md)

[Invoke-CimMethod](invoke-cimmethod.md)

[New-CimInstance](New-CimInstance.md)

[Register-CimIndicationEvent](Register-CimIndicationEvent.md)

[Remove-CimInstance](remove-ciminstance.md)

[Set-CimInstance](Set-CimInstance.md)

