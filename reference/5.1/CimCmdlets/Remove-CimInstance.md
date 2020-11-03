---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-ciminstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimInstance
ms.openlocfilehash: ac4435d0bf246273ad21c56ca7640204372d9133
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218159"
---
# Remove-CimInstance

## ZUSAMMENFASSUNG
Entfernt eine CIM-Instanz von einem Computer.

## SYNTAX

### Ciminstancecomputerset (Standard)

```
Remove-CimInstance [-ResourceUri <Uri>] [-ComputerName <String[]>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Ciminstancesessionset

```
Remove-CimInstance -CimSession <CimSession[]> [-ResourceUri <Uri>] [-OperationTimeoutSec <UInt32>]
 [-InputObject] <CimInstance> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Querysessionset

```
Remove-CimInstance -CimSession <CimSession[]> [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Querycomputerset

```
Remove-CimInstance [-ComputerName <String[]>] [[-Namespace] <String>]
 [-OperationTimeoutSec <UInt32>] [-Query] <String> [-QueryDialect <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Mit diesem Cmdlet wird eine CIM-Instanz von einem CIM-Server entfernt. Sie können die CIM-Instanz angeben, die entfernt werden soll, indem Sie entweder ein CIM-Instanzobjekt verwenden, das vom `Get-CimInstance` Cmdlet abgerufen wurde, oder eine Abfrage angeben.

Wenn der **Inputobject** -Parameter nicht angegeben ist, funktioniert das Cmdlet auf eine der folgenden Arten:

- Wenn weder der **Computername** -Parameter noch der **cimsession** -Parameter angegeben ist, funktioniert dieses Cmdlet mit einer Component Object Model (com)-Sitzung auf dem lokalen Windows-Verwaltungsinstrumentation (WMI).
- Wenn entweder der **Computername** -Parameter oder der **cimsession** -Parameter angegeben ist, wird dieses Cmdlet für den CIM-Server verwendet, der entweder durch den **Computername** -Parameter oder den **cimsession** -Parameter angegeben wird.

## BEISPIELE

### Beispiel 1: Entfernen der CIM-Instanz

In diesem Beispiel wird der **Query** -Parameter verwendet, um CIM-Instanzen aus der Klasse mit dem Namen **Win32_Environment** zu entfernen, die mit der Zeichenfolge **TestVar** beginnen.

```powershell
Remove-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"'
```

### Beispiel 2: Entfernen der CIM-Instanz mithilfe des CIM-Instanzobjekts

In diesem Beispiel werden die CIM-Instanzobjekte, die vom **Abfrage** Parameter gefiltert werden, abgerufen und `$var` mit dem-Cmdlet in der Variablen mit dem Namen gespeichert `Get-CimInstance` . Der Inhalt der Variablen wird dann an das `Remove-CimInstance` Cmdlet übergeben, das die CIM-Instanzen entfernt.

```powershell
notepad.exe
$var = Get-CimInstance -Query 'Select * from Win32_Process where name LIKE "notepad%"'
Remove-CimInstance -InputObject $var
```

## PARAMETERS

### -CimSession

Führt den Befehl mit der angegebenen CIM-Sitzung aus. Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, mit dem die CIM-Sitzung erstellt oder abgerufen wird, z `New-CimSession` `Get-CimSession` . b. die Cmdlets oder. Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimInstanceSessionSet, QuerySessionSet
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
Parameter Sets: CimInstanceComputerSet, QueryComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt ein CIM-Instanzobjekt an, das vom CIM-Server entfernt werden soll. Das an das Cmdlet weiter gegebene Objekt wird nicht geändert, sondern nur die Instanz auf dem CIM-Server.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: CimInstanceComputerSet, CimInstanceSessionSet
Aliases: CimInstance

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Namespace

Gibt den Namespace für den CIM-Vorgang an. Der Standard Namespace ist **root/cimv2**. Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: False
Position: 2
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

### -Query

Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt werden soll. Sie können den Abfrage Dialekt mithilfe des **querydialekt** -Parameters angeben.

Wenn der angegebene Wert doppelte Anführungszeichen ("), einfache Anführungszeichen (') oder einen umgekehrten Schrägstrich ( \\ ) enthält, müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich () vorangestellt werden \\ . Wenn für den angegebenen Wert der WQL Like-Operator verwendet wird, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern ( \[ \] ) einschließen: Prozent (%), Unterstrich (_) oder öffnende eckige Klammer ( \[ ).

```yaml
Type: System.String
Parameter Sets: QuerySessionSet, QueryComputerSet
Aliases:

Required: True
Position: 1
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
Default value: WQL
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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Dieses Cmdlet akzeptiert keine Eingabe Objekte.

## AUSGABEN

### Keine

Dieses Cmdlet erzeugt keine Ausgaben.

## HINWEISE

## VERWANDTE LINKS

[New-CimInstance](New-CimInstance.md)

[Get-CimInstance](get-ciminstance.md)

[Set-CimInstance](Set-CimInstance.md)
