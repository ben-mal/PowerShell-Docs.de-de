---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resume-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Service
ms.openlocfilehash: f5bf1eab12b65b6e6ffeeb92c983777a576c503b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211863"
---
# Resume-Service

## ZUSAMMENFASSUNG
Setzt angehaltene (unterbrochene) Dienste fort.

## SYNTAX

### Inputobject (Standard)

```
Resume-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Standard

```
Resume-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayName

```
Resume-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das **Resume-Service-** Cmdlet sendet für jeden der angegebenen Dienste eine Fortsetzungs Meldung an den Windows-Dienst Controller.
Wenn ein Dienst angehalten wird, wird er fortgesetzt.
Wenn er gerade ausgeführt wird, wird die Meldung ignoriert.
Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem *Inputobject* -Parameter ein Dienst Objekt übergeben, das die wiederherzustellenden Dienste darstellt.

## BEISPIELE

### Beispiel 1: Fortsetzen eines Dienstanbieter auf dem lokalen Computer

```
PS C:\> Resume-Service "sens"
```

Mit diesem Befehl wird der System Ereignis Benachrichtigungsdienst auf dem lokalen Computer fortgesetzt.
Der Dienst Name wird im Befehl von Sens dargestellt.
Der Befehl verwendet den *Name* -Parameter, um den Dienstnamen des Dienstanbieter anzugeben, aber der Befehl lässt den Parameternamen aus, da der Parameter Name optional ist.

### Beispiel 2: Fortsetzen aller angehaltenen Dienste

```
PS C:\> Get-Service | Where-Object {$_.Status -eq "Paused"} | Resume-Service
```

Mit diesem Befehl werden alle angehaltenen Dienste auf dem Computer fortgesetzt.
Mit dem Befehl "Get-Service Cmdlet" werden alle Dienste auf dem Computer abgerufen.
Der Pipeline Operator (|) übergibt die Ergebnisse an das Where-Object-Cmdlet, das die Dienste auswählt, deren **Status** -Eigenschaft angehalten ist.
Der nächste Pipeline Operator sendet die Ergebnisse an **Resume-Service** , wodurch die angehaltenen Dienste fortgesetzt werden.

In der Praxis verwenden Sie den *WhatIf* -Parameter, um die Auswirkung des Befehls zu ermitteln, bevor Sie ihn ausführen.

## PARAMETERS

### -DisplayName

Gibt die Anzeigenamen der fortzusetzenden Dienste an.
Platzhalterzeichen sind zulässig.

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

Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden.
Der Wert dieses Parameters qualifiziert den *Name* -Parameter.
Geben Sie ein Namenselement oder-Muster ein, z. b. s *.
Platzhalterzeichen sind zulässig.

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

### -Include

Gibt Dienste zum Fortsetzen an.
Der Wert dieses Parameters qualifiziert den *Name* -Parameter.
Geben Sie ein Namenselement oder-Muster ein, z. b. s *.
Platzhalterzeichen sind zulässig.

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

Gibt **ServiceController** -Objekte an, die die fort zusetzenden Dienste darstellen.
Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

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

Gibt die Dienstnamen der fortzusetzenden Dienste an.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das den Dienst darstellt.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

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

Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den fortgesetzten Dienst darstellt, wenn Sie den *passthru* -Parameter angeben.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* Der Status von Diensten, die angehalten wurden, wurde angehalten. Wenn Dienste fortgesetzt werden, lautet Ihr Status wird ausgeführt.
* **Resume-Service** kann Dienste nur steuern, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt. Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.
* Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` . Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.

## VERWANDTE LINKS

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)

