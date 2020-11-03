---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 01/21/2020
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/invoke-cimmethod?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-CimMethod
ms.openlocfilehash: 691ba3396fee5a32e81ade5979cb5a5ac4bd88eb
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218820"
---
# Invoke-CimMethod

## ZUSAMMENFASSUNG
Ruft eine Methode einer CIM-Klasse auf.

## SYNTAX

### Classnamecomputerset (Standard)

```
Invoke-CimMethod [-ClassName] <String> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Classnamesessionset

```
Invoke-CimMethod [-ClassName] <String> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Resourceuricomputerset

```
Invoke-CimMethod -ResourceUri <Uri> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Ciminstancesessionset

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Ciminstancecomputerset

```
Invoke-CimMethod [-ResourceUri <Uri>] [-InputObject] <CimInstance> [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Resourceurisessionset

```
Invoke-CimMethod -ResourceUri <Uri> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-Namespace <String>] [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Cimclasscomputerset

```
Invoke-CimMethod [-CimClass] <CimClass> [-ComputerName <String[]>] [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Cimclasssessionset

```
Invoke-CimMethod [-CimClass] <CimClass> -CimSession <CimSession[]> [[-Arguments] <IDictionary>]
 [-MethodName] <String> [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Querycomputerset

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] [-ComputerName <String[]>]
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Querysessionset

```
Invoke-CimMethod -Query <String> [-QueryDialect <String>] -CimSession <CimSession[]>
 [[-Arguments] <IDictionary>] [-MethodName] <String> [-Namespace <String>]
 [-OperationTimeoutSec <UInt32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das `Invoke-CimMethod` Cmdlet ruft eine Methode einer CIM-Klasse oder CIM-Instanz mit den Name-Wert-Paaren auf, die durch den **Arguments** -Parameter angegeben werden.

Wenn der **Inputobject** -Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:

- Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).
- Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.

Wenn der **Inputobject** -Parameter angegeben wird, funktioniert das Cmdlet auf eine der folgenden Arten:

- Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, verwendet dieses Cmdlet die CIM-Sitzung oder den Computernamen aus dem Eingabe Objekt.
- Wenn der **Computername** -Parameter oder der **cimsession** -Parameter angegeben wird, verwendet dieses Cmdlet entweder den Wert des **cimsession** -Parameter Werts oder den Wert des **Computername** -Parameters. Dies ist kein gängiges Szenario.

## BEISPIELE

### Beispiel 1: Aufrufen einer Methode

In diesem Beispiel wird die Beendigungs **Methode der** **Win32_Process** -Klasse aufgerufen.

```powershell
Invoke-CimMethod -Query 'select * from Win32_Process where name like "notepad%"' -MethodName "Terminate"
```

### Beispiel 2: Aufrufen einer Methode mithilfe des CIM-Instanzobjekts

In diesem Beispiel wird das CIM-Instanzobjekt abgerufen und `$x` mithilfe des-Cmdlets in einer Variablen mit dem Namen gespeichert `Get-CimInstance` . Der Inhalt der Variablen wird dann als **Inputobject** für das `Invoke-CimMethod` Cmdlet verwendet. Die **GetOwner** -Methode wird für die **ciminstance** aufgerufen.

```powershell
$x = Get-CimInstance -Query 'Select * from Win32_Process where name like "notepad%"'
Invoke-CimMethod -InputObject $x -MethodName GetOwner
```

### Beispiel 3: Aufrufen einer statischen Methode mithilfe von Argumenten

Dieses Beispiel ruft die **Create** -Methode mit dem Namen mit dem **Arguments** -Parameter auf.

```powershell
Invoke-CimMethod -ClassName Win32_Process -MethodName "Create" -Arguments @{
  CommandLine = 'notepad.exe'; CurrentDirectory = "C:\windows\system32"
}
```

### Beispiel 4: Client seitige Validierung

Dieses Beispiel führt die Client seitige Validierung für die **XYZ** -Methode durch, indem ein **cimclass** -Objekt an übergeben wird `Invoke-CimMethod` .

```powershell
$c = Get-CimClass -ClassName Win32_Process
Invoke-CimMethod -CimClass $c -MethodName "xyz" -Arguments @{ CommandLine = 'notepad.exe' }
```

## PARAMETERS

### -Arguments

Gibt die Parameter an, die an die aufgerufene Methode übergeben werden sollen. Geben Sie die Werte für diesen Parameter als Name-Wert-Paare an, die in einer Hash Tabelle gespeichert sind. Die Reihenfolge der eingegebenen Werte ist nicht wichtig.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Cimclass

Gibt ein CIM-Klassenobjekt an, das eine CIM-Klassendefinition auf dem Server darstellt. Verwenden Sie diesen Parameter, wenn Sie eine statische Methode einer Klasse aufrufen.

Sie können das `Get-CimClass` Cmdlet verwenden, um eine Klassendefinition vom Server abzurufen.

Die Verwendung dieses Parameters führt zu besseren Client seitigen Schema Überprüfungen.

```yaml
Type: Microsoft.Management.Infrastructure.CimClass
Parameter Sets: CimClassComputerSet, CimClassSessionSet
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
Parameter Sets: ClassNameSessionSet, CimInstanceSessionSet, CimClassSessionSet, QuerySessionSet, ResourceUriSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClassName

Gibt den Namen der CIM-Klasse an, für die der Vorgang durchgeführt werden soll. Dieser Parameter wird nur für statische Methoden verwendet. Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases: Class

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName

Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten. Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN), einen NetBIOS-Namen oder eine IP-Adresse angeben.

Wenn Sie diesen Parameter verwenden, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer. Andernfalls führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.

Stellen Sie mithilfe einer CIM-Sitzung eine Verbindung her, um die Leistung zu verbessern, wenn mehrere Vorgänge auf demselben Computer ausgeführt werden.

```yaml
Type: System.String[]
Parameter Sets: ClassNameComputerSet, ResourceUriComputerSet, CimClassComputerSet, CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Gibt ein CIM-Instanzobjekt an, das als Eingabe zum Aufrufen einer Methode verwendet werden soll. Dieser Parameter kann nur zum Aufrufen von Instanzmethoden verwendet werden. Verwenden Sie den **Class** -Parameter oder den **cimclass** -Parameter, um statische Klassen Methoden aufzurufen.

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

### -MethodName

Gibt den Namen der aufzurufenden CIM-Methode an. Dieser Parameter ist erforderlich und kann nicht NULL oder leer sein. Um die statische Methode einer CIM-Klasse aufzurufen, verwenden Sie den **className** -Parameter oder den **cimclass** -Parameter.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace

Gibt den Namespace für den CIM-Vorgang an. Der Standard Namespace ist **root/cimv2**. Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet, ResourceUriComputerSet, ResourceUriSessionSet, QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Operationtimeoutsec

Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet. Standardmäßig ist der Wert 0 (null), was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.

Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als das standardmäßige Verbindungs Wiederholungs Timeout von 3 Minuten ist, sind Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wiederherstellbar.

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

### -Query

Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt werden soll. Eine-Methode wird für die Instanzen aufgerufen, die als Ergebnis der Abfrage empfangen werden. Sie können den Abfrage Dialekt mithilfe des **querydialekt** -Parameters angeben.

Wenn der angegebene Wert doppelte Anführungszeichen ( `"` ), einfache Anführungszeichen ( `'` ) oder einen umgekehrten Schrägstrich ( `\` ) enthält, müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich () vorangestellt werden `\` . Wenn der angegebene Wert den WQL Like-Operator verwendet, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern ( `[]` ) einschließen: Prozent ( `%` ), Unterstrich ( `_` ) oder öffnende eckige Klammer ( `[` ).

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

Gibt die Abfragesprache an, die für den Abfrage Parameter verwendet wird. Die zulässigen Werte für diesen Parameter sind: **WQL** oder **CQL**.

Der Standardwert ist **WQL**.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceUri

Gibt den Ressourcen-URI (Uniform Resource Identifier) der Ressourcen Klasse oder-Instanz an.
Der URI wird verwendet, um einen bestimmten Ressourcentyp auf einem Computer zu identifizieren, z. B. Datenträger oder Prozesse.

Ein URI besteht aus einem Präfix und einem Pfad zu einer Ressource. Beispiel:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://intel.com/wbem/wscim/1/amt-schema/1/AMT_GeneralSettings`

Wenn Sie diesen Parameter nicht angeben, wird standardmäßig der DMTF-Standard Ressourcen `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` -URI verwendet, und der Klassenname wird an ihn angefügt.

**ResourceUri** kann nur mit CIM-Sitzungen verwendet werden, die mithilfe des WSMAN-Protokolls erstellt wurden, oder wenn der **Computername** -Parameter angegeben wird, der eine CIM-Sitzung mithilfe von WSMAN erstellt.

Wenn Sie diesen Parameter ohne Angabe des **Computername** -Parameters angeben oder wenn Sie eine CIM-Sitzung angeben, die mithilfe des DCOM-Protokolls erstellt wurde, erhalten Sie einen Fehler. Das DCOM-Protokoll unterstützt den **resourceUri** -Parameter nicht.

Wenn sowohl der **resourceUri** -Parameter als auch der **Filter** -Parameter angegeben werden, wird der **Filter** Parameter ignoriert.

```yaml
Type: System.Uri
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases:

Required: True (ResourceUriSessionSet, ResourceUriComputerSet), False (CimInstanceSessionSet, CimInstanceComputerSet)
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

### CIM-Klasse

Dieses Cmdlet akzeptiert eine CIM-Klasse als Eingabe Objekt.

### CIM-Instanz

Dieses Cmdlet akzeptiert eine CIM-Instanz als Eingabe Objekt.

## AUSGABEN

### System. Management. Automation. pscustomobject

Dieses Cmdlet gibt ein Objekt zurück.

## HINWEISE

## VERWANDTE LINKS

[Get-CimClass](get-cimclass.md)

[Get-CimInstance](get-ciminstance.md)

[Get-CimSession](Get-CimSession.md)

[New-CimSession](New-CimSession.md)

