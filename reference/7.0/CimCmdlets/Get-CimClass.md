---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimclass?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimClass
ms.openlocfilehash: 2fd87935e2594a643327d2ae07fad112b1b9386f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210031"
---
# Get-CimClass

## ZUSAMMENFASSUNG
Ruft eine Liste von CIM-Klassen in einem bestimmten Namespace ab.

## SYNTAX

### Computergruppe (Standard)

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 [-ComputerName <String[]>] [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

### Sessionset

```
Get-CimClass [[-ClassName] <String>] [[-Namespace] <String>] [-OperationTimeoutSec <UInt32>]
 -CimSession <CimSession[]> [-MethodName <String>] [-PropertyName <String>]
 [-QualifierName <String>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-CimClass` Cmdlet wird eine Liste der CIM-Klassen in einem bestimmten Namespace abgerufen. Wenn kein Klassenname angegeben wird, gibt das Cmdlet alle Klassen im-Namespace zurück. Im Gegensatz zu einer CIM-Instanz enthalten CIM-Klassen nicht die CIM-Sitzung oder den Computernamen, von dem Sie abgerufen werden.

## BEISPIELE

### Beispiel 1: alle Klassendefinitionen

In diesem Beispiel werden alle Klassendefinitionen unter dem Namespace **root/cimv2** abgerufen.

```powershell
Get-CimClass
```

### Beispiel 2: erhalten der Klassen mit einem bestimmten Namen

**In diesem** Beispiel werden die Klassen abgerufen, die den Word-Datenträger in ihren Namen enthalten.

```powershell
Get-CimClass -ClassName *disk*
```

### Beispiel 3: erhalten der Klassen mit einem bestimmten Methodennamen

In diesem Beispiel werden die Klassen abgerufen, die mit dem Namen **Win32** beginnen und einen Methodennamen aufweisen, der mit dem **Begriff** beginnt.

```powershell
Get-CimClass -ClassName Win32* -MethodName Term*
```

### Beispiel 4: erhalten der Klassen mit einem bestimmten Eigenschaftsnamen

In diesem Beispiel werden die Klassen abgerufen, die mit dem Namen **Win32** beginnen und über eine Eigenschaft mit dem Namen **handle** verfügen.

```powershell
Get-CimClass -ClassName Win32* -PropertyName Handle
```

### Beispiel 5: erhalten der Klassen mit einem bestimmten Qualifizierernamen

In diesem Beispiel werden die Klassen abgerufen, die mit dem Namen **Win32** beginnen, das Wort **Disk** in ihren Namen enthalten und über die angegebene qualifiziererzuordnung verfügen. **Association**

```powershell
Get-CimClass -ClassName Win32*Disk* -QualifierName Association
```

### Beispiel 6: erhalten der Klassendefinitionen aus einem bestimmten Namespace

In diesem Beispiel werden die Klassendefinitionen mit dem Wort **net** in ihren Namen aus dem angegebenen Namespace **root/standardCimv2** abgerufen.

```powershell
Get-CimClass -Namespace root/standardCimv2 -ClassName *Net*
```

### Beispiel 7: erhalten der Klassendefinitionen von einem Remote Server

**In diesem** Beispiel werden die Klassendefinitionen abgerufen, die den Word-Datenträger in ihren Namen aus den angegebenen Remote Servern **Server01** und **Server02** enthalten.

```powershell
Get-CimClass -ClassName *disk* -ComputerName Server01, Server02
```

### Beispiel 8: erhalten der Klassen mithilfe einer CIM-Sitzung

```powershell
$s = New-CimSession -ComputerName Server01, Server02
Get-CimClass -ClassName *disk* -CimSession $s
```

Dieser Satz von Befehlen erstellt eine Sitzung mit mehreren Computern und speichert Sie `$s` mithilfe des `New-CimSession` Cmdlets in einer Variablen und ruft dann die Klassen mithilfe des `Get-CimClass` Cmdlets ab.

## PARAMETERS

### -CimSession

Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus. Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines- `New-CimSession` oder- `Get-CimSession` Cmdlets. Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.

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

### -ClassName

Gibt den Namen der CIM-Klasse an, für die der Vorgang durchgeführt werden soll. Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ComputerName

Gibt den Computer an, auf dem Sie den CIM-Vorgang ausführen möchten. Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) als NetBIOS-Namen oder eine IP-Adresse angeben.

Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer.

Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet den Vorgang auf dem lokalen Computer mithilfe von Component Object Model (com) aus.

Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, bietet die Verwendung einer CIM-Sitzung eine bessere Leistung.

```yaml
Type: System.String[]
Parameter Sets: ComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MethodName

Sucht die Klassen, die über eine Methode verfügen, die diesem Namen entspricht. Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Namespace

Gibt den Namespace für den CIM-Vorgang an. Der Standard Namespace ist **root/cimv2**. Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.

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

### -PropertyName

Sucht die Klassen, die über eine Eigenschaft verfügen, die diesem Namen entspricht. Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.

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

### -Qualifiername

Filtert die Klassen nach dem Qualifizierernamen auf Klassenebene. Mit diesem Parameter können Sie Platzhalter Zeichen verwenden.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Dieses Cmdlet akzeptiert keine Eingabe Objekte.

## AUSGABEN

### Microsoft. Management. Infrastructure. cimclass

Dieses Cmdlet gibt ein CIM-Klassenobjekt zurück.

## HINWEISE

## VERWANDTE LINKS

[New-CimSession](New-CimSession.md)
