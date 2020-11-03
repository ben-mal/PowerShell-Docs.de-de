---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-ciminstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimInstance
ms.openlocfilehash: 5d1394a6689471e3ea65bcbdc87ec0ef5e1fc6a6
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218180"
---
# New-CimInstance

## ZUSAMMENFASSUNG
Erstellt eine CIM-Instanz.

## SYNTAX

### Classnamecomputerset (Standard)

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Classnamesessionset

```
New-CimInstance [-ClassName] <String> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-ClientOnly]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Resourceurisessionset

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] -CimSession <CimSession[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Resourceuricomputerset

```
New-CimInstance -ResourceUri <Uri> [-Key <String[]>] [[-Property] <IDictionary>]
 [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-ComputerName <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Cimclasssessionset

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Cimclasscomputerset

```
New-CimInstance [-CimClass] <CimClass> [[-Property] <IDictionary>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-ClientOnly] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `New-CimInstance` Cmdlet erstellt eine Instanz einer CIM-Klasse auf der Grundlage der Klassendefinition auf dem lokalen Computer oder einem Remote Computer. Standardmäßig erstellt das `New-CimInstance` Cmdlet eine Instanz auf dem lokalen Computer.

## BEISPIELE

### Beispiel 1: Erstellen einer Instanz einer CIM-Klasse

In diesem Beispiel wird eine Instanz einer CIM-Klasse mit dem Namen Win32_Environment im root/cimv2-Namespace auf dem Computer erstellt.

```powershell
New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";VariableValue="testvalue";UserName="domain\user"}
```

Es wird keine Client seitige Validierung ausgeführt, wenn die Klasse nicht vorhanden ist, die Eigenschaften falsch sind oder der Server den-Befehl ablehnt. Wenn die Instanz erfolgreich erstellt wurde, gibt das Cmdlet die neu erstellte Instanz aus.

### Beispiel 2: Erstellen einer Instanz einer CIM-Klasse mithilfe eines Klassen Schemas

In diesem Beispiel wird ein CIM-Klassenobjekt abgerufen und in einer Variablen mit dem Namen gespeichert `$class` . Der Inhalt der Variablen wird dann an das `New-CimInstance` Cmdlet übergeben.

```powershell
$class = Get-CimClass -ClassName Win32_Environment
New-CimInstance -CimClass $class -Property @{Name="testvar";VariableValue="testvalue";UserName="Contoso\User1"}
```

### Beispiel 3: Erstellen einer dynamischen Instanz auf dem Client

In diesem Beispiel wird eine dynamische Instanz einer CIM-Klasse mit dem Namen **Win32_Process** auf dem Client Computer erstellt, ohne die Instanz vom Server zu erhalten. Die neue-Instanz wird in der-Variable gespeichert `$a` . Diese dynamische Instanz kann verwendet werden, um Vorgänge auszuführen, wenn die Instanz mit diesem Schlüssel auf dem Server vorhanden ist.

```powershell
$a = New-CimInstance -ClassName Win32_Process -Property @{Handle=0} -Key Handle -ClientOnly
Get-CimInstance -CimInstance $a
Invoke-CimMethod -CimInstance $a -MethodName GetOwner
```

```Output
ProcessId Name                HandleCount WorkingSetSize VirtualSize
--------- ----                ----------- -------------- -----------
0         System Idle Process 0           8192           8192

Domain         :
ReturnValue    : 2
User           :
PSComputerName :
```

Das `Get-CimInstance` Cmdlet ruft dann eine bestimmte einzelne Instanz ab. Das- `Invoke-CimMethod` Cmdlet ruft die **GetOwner** -Methode für die abgerufene-Instanz auf.

### Beispiel 4: Erstellen einer Instanz für eine CIM-Klasse eines bestimmten Namespace

In diesem Beispiel wird eine Instanz einer CIM-Klasse mit dem Namen **MSFT_Something** im Namespace **root/irgendwo** abgerufen und in einer Variablen mit dem Namen gespeichert `$class` . Die-Variable wird an das `New-CimInstance` Cmdlet übergeben, um eine neue CIM-Instanz zu erstellen und Client seitige Validierungen für die neue-Instanz auszuführen.

```powershell
$class = Get-CimClass -ClassName MSFT_Something -Namespace root/somewhere
New-CimInstance -CimClass $class -Property @{"Prop1"=1;"Prop2"="value"} -ClientOnly
```

In diesem Beispiel überprüft die Verwendung des **cimclass** -Parameters anstelle des **className** -Parameters, ob **Eigenschaft PROP1** und **Prop2** tatsächlich vorhanden sind und dass die Schlüssel ordnungsgemäß gekennzeichnet sind.

Der Parameter " **Computername** " oder " **cimsession** " kann nicht mit dem **clientonly** -Parameter verwendet werden.

## PARAMETERS

### -Cimclass

Gibt ein CIM-Klassenobjekt an, das den Typ der Instanz darstellt. Verwenden `Get-CimClass` Sie das Cmdlet, um die Klassen Deklaration von einem Computer abzurufen. Die Verwendung dieses Parameters führt zu besseren Client seitigen Schema Überprüfungen.

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassSessionSet, CimClassComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimSession

Führt den Befehl mit der angegebenen CIM-Sitzung aus. Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, mit dem die CIM-Sitzung erstellt oder abgerufen wird, z `New-CimSession` `Get-CimSession` . b. die Cmdlets oder. Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: ClassNameSessionSet, ResourceUriSessionSet, CimClassSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClassName

Gibt den Namen der CIM-Klasse an, für die der Vorgang eine Instanz erstellt. Hinweis: mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.

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

### -Clientonly

Gibt an, dass die Instanz nur in PowerShell erstellt wird, ohne dass der CIM-Server verwendet wird. Sie können diesen Parameter verwenden, um eine in-Memory-CIM-Instanz für die Verwendung in nachfolgenden PowerShell-Vorgängen zu erstellen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, CimClassSessionSet, CimClassComputerSet
Aliases: Local

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten. Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN), einen NetBIOS-Namen oder eine IP-Adresse angeben.

Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.

Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.

Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet eine Verbindung mit einer CIM-Sitzung eine bessere Leistung.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Key

Gibt die Eigenschaften an, die als Schlüssel verwendet werden. **Cimsession** und **Computername** können nicht verwendet werden, wenn **Key** angegeben wird.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace

Gibt den Namespace der-Klasse für die neue-Instanz an. Der Standard Namespace ist **root/cimv2**.
Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Operationtimeoutsec

Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort vom CIM-Server wartet. Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet. Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.

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

Gibt die Eigenschaften der CIM-Instanz mithilfe einer Hash Tabelle (Name/Wert-Paare) an.

Wenn Sie den **cimclass** -Parameter angeben, `New-CimInstance` führt das Cmdlet eine Eigenschafts Überprüfung auf dem Client aus, um sicherzustellen, dass die angegebenen Eigenschaften mit der Klassen Deklaration auf dem Server übereinstimmen. Wenn der **cimclass** -Parameter nicht angegeben wird, erfolgt die Überprüfung der Eigenschaft auf dem Server.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases: Arguments

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceUri

Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an. Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.

Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource. Beispiel:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.

**ResourceUri** kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der **Computername** -Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt. Wenn Sie diesen Parameter ohne Angabe des **Computername** -Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie eine Fehlermeldung, da das DCOM-Protokoll den **resourceUri** -Parameter nicht unterstützt.

Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.

```yaml
Type: System.Uri
Parameter Sets: ResourceUriSessionSet, ResourceUriComputerSet
Aliases:

Required: True
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

### Keine

Dieses Cmdlet akzeptiert keine Eingabe Objekte.

## AUSGABEN

### System.Object

Dieses Cmdlet gibt ein Objekt zurück, das die CIM-Instanzinformationen enthält.

## HINWEISE

## VERWANDTE LINKS

[Get-CimClass](get-cimclass.md)

[Get-CimInstance](get-ciminstance.md)

[Remove-CimInstance](remove-ciminstance.md)

[Set-CimInstance](Set-CimInstance.md)
