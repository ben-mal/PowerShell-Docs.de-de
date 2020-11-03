---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimassociatedinstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimAssociatedInstance
ms.openlocfilehash: adf6c1ac6f6f9288233d530b7ea2101f4b7688e4
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218279"
---
# Get-CimAssociatedInstance

## ZUSAMMENFASSUNG
Ruft die CIM-Instanzen ab, die durch eine Zuordnung mit einer bestimmten CIM-Instanz verbunden sind.

## SYNTAX

### Computergruppe (Standard)

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] [-ComputerName <String[]>] [-KeyOnly] [<CommonParameters>]
```

### Sessionset

```
Get-CimAssociatedInstance [[-Association] <String>] [-ResultClassName <String>]
 [-InputObject] <CimInstance> [-Namespace <String>] [-OperationTimeoutSec <UInt32>]
 [-ResourceUri <Uri>] -CimSession <CimSession[]> [-KeyOnly] [<CommonParameters>]
```

## DESCRIPTION

Das- `Get-CimAssociatedInstance` Cmdlet ruft die CIM-Instanzen ab, die mit einer bestimmten CIM-Instanz, der sogenannten Quell Instanz, verbunden sind.

In einer Zuordnung hat jede CIM-Instanz eine benannte Rolle, und dieselbe CIM-Instanz kann an einer Zuordnung in verschiedenen Rollen teilnehmen.

Wenn der Inputobject-Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:

- Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).
- Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.

## BEISPIELE

### Beispiel 1: alle zugeordneten Instanzen einer bestimmten Instanz

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1]
```

Dieser Satz von Befehlen ruft die Instanzen der-Klasse mit dem Namen Win32_LogicalDisk ab und speichert die Informationen in einer Variablen `$disk` mit dem Namen mithilfe des- `Get-CimInstance` Cmdlets. Die erste logische Datenträger Instanz in der Variablen wird dann als Eingabe Objekt für das `Get-CimAssociatedInstance` Cmdlet verwendet, um alle zugeordneten CIM-Instanzen der angegebenen CIM-Instanz zu erhalten.

### Beispiel 2: alle zugeordneten Instanzen eines bestimmten Typs

```powershell
$disk = Get-CimInstance -ClassName Win32_LogicalDisk -KeyOnly
Get-CimAssociatedInstance -InputObject $disk[1] -ResultClass Win32_DiskPartition
```

Dieser Satz von Befehlen ruft alle Instanzen der **Win32_LogicalDisk** -Klasse ab und speichert Sie in einer Variablen mit dem Namen `$disk` . Die erste logische Datenträger Instanz in der Variablen wird dann als Eingabe Objekt für das `Get-CimAssociatedInstance` Cmdlet verwendet, um alle zugeordneten-Instanzen zu erhalten, die über die angegebene Association-Klasse **Win32_DiskPartition** verknüpft sind.

### Beispiel 3: alle zugeordneten Instanzen über den Qualifizierer einer bestimmten Klasse

```powershell
$s = Get-CimInstance -Query "Select * from Win32_Service where name like 'Winmgmt'"
Get-CimClass -ClassName *Service* -Qualifier "Association"
$c.CimClasName
```

```Output
Win32_LoadOrderGroupServiceDependencies
Win32_DependentService
Win32_SystemServices
Win32_LoadOrderGroupServiceMembers
Win32_ServiceSpecificationService
```

```powershell
Get-CimAssociatedInstance -InputObject $s -Association Win32_DependentService
```

Dieser Satz von Befehlen ruft die Dienste ab, die vom WMI-Dienst abhängig sind, und speichert Sie in einer Variablen mit dem Namen `$s` . Der Zuordnungs Klassenname für den **Win32_DependentService** wird mithilfe des `Get-CimClass` Cmdlets abgerufen, **Association** indem die Zuordnung als Qualifizierer angegeben und dann mit $s an das Cmdlet übergeben wird, `Get-CimAssociatedInstance` um alle zugeordneten Instanzen der abgerufenen Zuordnungs Klasse abzurufen.

## PARAMETERS

### -Association

Gibt den Namen der Association-Klasse an. Wenn Sie diesen Parameter nicht angeben, gibt das Cmdlet alle vorhandenen Zuordnungs Objekte eines beliebigen Typs zurück.

Wenn z. B. Class a mit Class B über zwei Zuordnungen, AB1 und AB2, verknüpft ist, kann dieser Parameter verwendet werden, um den Typ der Zuordnung anzugeben, entweder AB1 oder AB2.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession

Führt den Befehl mit der angegebenen CIM-Sitzung aus. Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, der die CIM-Sitzung erstellt oder abruft, z `New-CimSession` `Get-CimSession` . b. oder. Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: SessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName

Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten. Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) oder einen NetBIOS-Namen angeben.

Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.

Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.

Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet eine Verbindung mit einer CIM-Sitzung eine bessere Leistung.

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die Eingabe für dieses Cmdlet an. Verwenden Sie diesen Parameter, außerdem können Sie die Eingabe für dieses Cmdlet übergeben.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases: CimInstance

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Keyonly

Gibt Objekte zurück, für die nur Schlüsseleigenschaften aufgefüllt wurden. Dadurch wird die Menge der Daten reduziert, die über das Netzwerk übertragen werden.

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

### -Namespace

Gibt den Namespace für den CIM-Vorgang an. Der Standard Namespace ist root/cimv2.

> [!NOTE]
> Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.

```yaml
Type: System.String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Resultclassname

Gibt den Klassennamen der zugeordneten-Instanzen an. Eine CIM-Instanz kann einer oder mehreren CIM-Instanzen zugeordnet werden. Wenn Sie den Namen der Ergebnis Klasse nicht angeben, werden alle zugeordneten CIM-Instanzen zurückgegeben.

Standardmäßig ist der Wert dieses Parameters NULL, und alle zugeordneten CIM-Instanzen werden zurückgegeben.

Sie können die Zuordnungs Ergebnisse nach einem bestimmten Klassennamen filtern. Die Filterung erfolgt auf dem Server. Wenn dieser Parameter nicht angegeben wird, `Get-CIMAssociatedInstance` gibt alle vorhandenen Zuordnungen zurück. Wenn class a z. b. den Klassen B, c und d zugeordnet ist, kann dieser Parameter verwendet werden, um die Ausgabe auf einen bestimmten Typ (B, c oder d) zu beschränken.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Dieses Cmdlet akzeptiert keine Eingabe Objekte.

## AUSGABEN

### System.Object

Dieses Cmdlet gibt ein Objekt zurück.

## HINWEISE

## VERWANDTE LINKS

[Get-CimClass](get-cimclass.md)

[Get-CimInstance](get-ciminstance.md)
