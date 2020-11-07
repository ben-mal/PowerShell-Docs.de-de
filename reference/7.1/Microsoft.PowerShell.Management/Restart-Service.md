---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: fee113e20b178c2b86b8f95cd3147f991aed8efe
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346631"
---
# Restart-Service

## ZUSAMMENFASSUNG
Beendet Dienste und startet diese anschließend.

## SYNTAX

### Inputobject (Standard)

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Standard

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### DisplayName

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das `Restart-Service` -Cmdlet sendet eine Nachricht zum Abbrechen und eine Start Meldung an den Windows-Dienst Controller für einen angegebenen Dienst. Wenn ein Dienst bereits beendet wurde, wird er gestartet, ohne dass ein Fehler ausgegeben wird. Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem **Inputobject** -Parameter ein Objekt übergeben, das die einzelnen neu zu startenden Dienste darstellt.

## BEISPIELE

### Beispiel 1: Neustarten eines Dienstanbieter auf dem lokalen Computer

```powershell
PS C:\> Restart-Service -Name winmgmt
```

Mit diesem Befehl wird der WMI-Dienst (WinMgmt) auf dem lokalen Computer neu gestartet.

### Beispiel 2: Ausschließen eines Dienstanbieter

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

Mit diesem Befehl werden die Dienste neu gestartet, deren Anzeige Name mit "NET" beginnt, mit Ausnahme des Anmelde Diensts.

### Beispiel 3: Starten aller beendeten Netzwerkdienste

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

Mit diesem Befehl werden alle beendeten Netzwerkdienste auf dem Computer gestartet.

Dieser Befehl verwendet das `Get-Service` Cmdlet, um Objekte zu erhalten, die die Dienste darstellen, deren Dienst Name mit "NET" beginnt. Der Pipeline Operator ( `|` ) sendet das Dienst Objekt an das `Where-Object` Cmdlet, das nur die Dienste auswählt, die den Status "beendet" aufweisen. Ein weiterer Pipeline Operator sendet die ausgewählten Dienste an `Restart-Service` .

In der Praxis verwenden Sie den **WhatIf** -Parameter, um die Auswirkung des Befehls zu ermitteln, bevor Sie ihn ausführen.

## PARAMETERS

### -DisplayName

Gibt die anzeigen Amen von Diensten an, die neu gestartet werden sollen. Platzhalterzeichen sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Ausschließen

Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden. Der Wert dieses Parameters qualifiziert den **Name** -Parameter. Geben Sie ein Namenselement oder-Muster ein, z. b. s *. Platzhalterzeichen sind zulässig.

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

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

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

### -Include

Gibt die Dienste an, die von diesem Cmdlet neu gestartet werden. Der Wert dieses Parameters qualifiziert den **Name** -Parameter. Geben Sie ein Namenselement oder-Muster ein, z. b. s *. Platzhalterzeichen sind zulässig.

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

### -InputObject

Gibt **ServiceController** -Objekte an, die die neu zu Start-Dienste darstellen. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die Dienstnamen der neu zu startenden Dienste an.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -PassThru

Gibt ein Objekt zurück, das den Dienst darstellt. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### System. ServiceProcess. ServiceController, System. String

Sie können ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine, System. ServiceProcess. ServiceController

Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den neu gestarteten Dienst darstellt, wenn Sie den **passthru** -Parameter angeben. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

- `Restart-Service` Dienste können nur von gesteuert werden, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt. Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.
- Geben Sie "ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .
  Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.

## VERWANDTE LINKS

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)
