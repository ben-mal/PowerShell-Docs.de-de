---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: 6bffe41f1efd42c686d06f59cf86b374b596d80d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214351"
---
# Stop-Service

## ZUSAMMENFASSUNG
Beendet ausgeführte Dienste.

## SYNTAX

### Inputobject (Standard)

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Standard

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisplayName

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das Cmdlet "End **-Service** " sendet für jeden der angegebenen Dienste eine Nachricht zum Abbrechen an den Windows-Dienst Controller.
Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können den **Inputobject** -Parameter verwenden, um ein Dienst Objekt zu übergeben, das den Dienst darstellt, den Sie abbrechen möchten.

## BEISPIELE

### Beispiel 1: beendet einen Dienst auf dem lokalen Computer.

```
PS C:\> Stop-Service -Name "sysmonlog"
```

Mit diesem Befehl wird der Dienst für Leistungsprotokolle und -benachrichtigungen (SysmonLog) auf dem lokalen Computer beendet.

### Beispiel 2: Beendigung eines dienstandens mit dem anzeigen Amen

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

Mit diesem Befehl wird der Dienst %%amp;quot;Telnet%%amp;quot; auf dem lokalen Computer beendet.
Der Befehl verwendet **Get-Service** , um ein Objekt zu erhalten, das den Telnet-Dienst darstellt.
Der Pipeline Operator (|) übergibt das Objekt an den **Stopp-Dienst** , wodurch der Dienst beendet wird.

### Beispiel 3: beendet einen Dienst, der über abhängige Dienste verfügt.

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

In diesem Beispiel wird der IISAdmin-Dienst auf dem lokalen Computer angehalten.
Da durch das Beenden dieses Diensts auch die Dienste angehalten werden, die vom IISAdmin-Dienst abhängen, empfiehlt es sich, dem **Stop-Service** mit einem Befehl voranzugehen, der die Dienste auflistet, die vom IISAdmin-Dienst abhängen.

Mit dem ersten Befehl werden die Dienste aufgelistet, die von %%amp;quot;IISAdmin%%amp;quot; abhängen.
Er verwendet **Get-Service** , um ein Objekt zu erhalten, das den IISAdmin-Dienst darstellt.
Der Pipelineoperator (|) übergibt das Ergebnis an das Cmdlet %%amp;quot;Format-List%%amp;quot;.
Der Befehl verwendet den *Property* -Parameter von " **Format-List** ", um nur die Eigenschaften " **Name** " und " **DependentServices** " des Diensts aufzulisten.

Mit dem zweiten Befehl wird der IISAdmin-Dienst beendet.
Der *Force* -Parameter ist erforderlich, um einen Dienst zu unterbinden, der über abhängige Dienste verfügt.
Der Befehl verwendet den *Confirm* -Parameter, um eine Bestätigung vom Benutzer anzufordern, bevor die einzelnen Dienste beendet werden.

## PARAMETERS

### -DisplayName

Gibt die anzeigen amen der zu stoppenden Dienste an.
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

### -Force

Erzwingt, dass das Cmdlet einen Dienst beendet, auch wenn dieser Dienst über abhängige Dienste verfügt.

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

Gibt die Dienste an, die von diesem Cmdlet beendet werden.
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

Gibt **ServiceController** -Objekte an, die die zu stoppenden Dienste darstellen.
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

Gibt die Dienstnamen der zu stoppenden Dienste an.
Platzhalterzeichen sind zulässig.

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

### -Nowait

Gibt an, dass dieses Cmdlet die Option No Wait verwendet.

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

Sie können ein Dienst Objekt oder eine Zeichenfolge, die den Namen eines diensnamens enthält, über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine, System. ServiceProcess. ServiceController

Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den Dienst darstellt, wenn Sie den *passthru* -Parameter verwenden.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* Sie können auch über den integrierten Alias **spsv** auf "End **-Service** " verweisen. Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.

  " **Beenden": der Dienst** kann die Dienste nur steuern, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt.
Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.

  Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .
Die Dienstnamen werden in der Spalte " **Name** " angezeigt, und die anzeigen Amen werden in der Spalte " **Display Name** " angezeigt.

*

## VERWANDTE LINKS

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Suspend-Service](Suspend-Service.md)
