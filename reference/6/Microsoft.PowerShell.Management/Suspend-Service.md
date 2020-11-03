---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: 6e9fd5dd7a5736ef95976cb5195dd1d210d81651
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212239"
---
# Suspend-Service

## ZUSAMMENFASSUNG
Hält ausgeführte Dienste an.

## SYNTAX

### Inputobject (Standard)

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Standard

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayName

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das **Suspend-Service-** Cmdlet sendet für jeden der angegebenen Dienste eine Suspend-Nachricht an den Windows-Dienst Controller.
Obwohl der Dienst angehalten wird, wird der Dienst weiterhin ausgeführt, die Aktion wird jedoch bis zum fortsetzen angehalten, wie z. b. durch das Resume-Service Cmdlet.
Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem *Inputobject* -Parameter ein Dienst Objekt übergeben, das die anzuhaltenden Dienste darstellt.

## BEISPIELE

### Beispiel 1: aussetzen eines Dienstanbieter

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

Mit diesem Befehl wird der Telnet-Dienst (Tlntsvr) auf dem lokalen Computer angehalten.

### Beispiel 2: anzeigen, was passiert, wenn Sie Dienste aussetzen

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

Dieser Befehl gibt Aufschluss darüber, was passieren würde, wenn Sie die Dienste mit einem Dienstnamen angehalten haben, der mit LanMan beginnt.
Führen Sie den Befehl ohne den *WhatIf* -Parameter erneut aus, um die Dienste anzuhalten.

### Beispiel 3: Get und Suspend a Service

```
PS C:\> Get-Service schedule | Suspend-Service
```

Dieser Befehl verwendet das **Get-Service-** Cmdlet, um ein Objekt zu erhalten, das den Taskplaner (Schedule)-Dienst auf dem Computer darstellt.
Der Pipeline Operator (|) übergibt das Ergebnis an **Suspend-Service** , wodurch der Dienst angehalten wird.

### Beispiel 4: aussetzen aller Dienste, die angehalten werden können

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

Mit diesem Befehl werden alle Dienste auf dem Computer angehalten, die angehalten werden können.
Er verwendet **Get-Service** , um Objekte zu erhalten, die die Dienste auf dem Computer darstellen.
Der Pipeline Operator übergibt die Ergebnisse an das Cmdlet "Where-Object", das nur die Dienste auswählt, die den Wert "$true" für die **canpaustiandcontinue** -Eigenschaft aufweisen.
Ein weiterer Pipeline Operator übergibt die Ergebnisse an **Suspend-Service** .
Mit dem *Confirm* -Parameter werden Sie vor dem Anhalten der einzelnen Dienste zur Bestätigung aufgefordert.

## PARAMETERS

### -DisplayName

Gibt die Anzeigenamen der anzuhaltenden Dienste an.
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

Gibt Dienste an, die aus den angegebenen Diensten ausgelassen werden sollen.
Der Wert dieses Parameters qualifiziert den *Name* -Parameter.
Geben Sie ein Namenselement oder -muster wie %%amp;quot;s*%%amp;quot; ein.
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

Gibt Dienste zum Aussetzen an.
Der Wert dieses Parameters qualifiziert den *Name* -Parameter.
Geben Sie ein Namenselement oder -muster wie %%amp;quot;s*%%amp;quot; ein.
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

Gibt **ServiceController** -Objekte an, die die anzuhaltenden Dienste darstellen.
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

Gibt die Dienstnamen der anzuhaltenden Dienste an.
Platzhalterzeichen sind zulässig.

Der Parametername ist optional.
Sie können " *Name* " oder den zugehörigen Alias " *Service* Name" verwenden, oder Sie können den Parameternamen weglassen.

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

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.
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

Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den Dienst darstellt, wenn Sie den *passthru* -Parameter angeben.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* **Suspend-Service** kann Dienste nur steuern, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt. Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.
* **Suspend-Service** kann nur Dienste aussetzen, die angehalten und fortgesetzt werden. Um zu ermitteln, ob ein bestimmter Dienst angehalten werden kann, verwenden Sie das Get-Service-Cmdlet mit der **canpauabandcontinue** -Eigenschaft. Beispiel: `Get-Service wmi | Format-List Name, CanPauseAndContinue`. Wenn Sie alle Dienste auf dem Computer ermitteln möchten, die angehalten werden können, geben Sie ein `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` .
* Geben **Sie Get-Service** ein, um die Dienstnamen und anzeigen amen der Dienste auf Ihrem System zu ermitteln. Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.

## VERWANDTE LINKS

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Remove-Service](Remove-Service.md)
