---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/reset-computermachinepassword?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ComputerMachinePassword
ms.openlocfilehash: 1484bc83b9503ce43420b833a1b78b3c4215d98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214487"
---
# Reset-ComputerMachinePassword

## ZUSAMMENFASSUNG
Setzt das Kennwort für das Computerkonto des Computers zurück.

## SYNTAX

```
Reset-ComputerMachinePassword [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Mit dem " **Reset-ComputerMachinePassword"-** Cmdlet wird das Computer Konto Kennwort geändert, das die Computer für die Authentifizierung bei den Domänen Controllern in der Domäne verwenden.
Sie können hiermit das Kennwort des lokalen Computers zurücksetzen.

## BEISPIELE

### Beispiel 1: Zurücksetzen des Kennworts für den lokalen Computer

```
PS C:\> Reset-ComputerMachinePassword
```

Mit diesem Befehl wird das Computer Kennwort für den lokalen Computer zurückgesetzt.
Der Befehl wird mit den Anmeldeinformationen des aktuellen Benutzers ausgeführt.

### Beispiel 2: Zurücksetzen des Kennworts für den lokalen Computer mithilfe eines angegebenen Domänen Controllers

```
PS C:\> Reset-ComputerMachinePassword -Server "DC01" -Credential Domain01\Admin01
```

Dieser Befehl setzt das Computer Kennwort des lokalen Computers mithilfe des DC01-Domänen Controllers zurück.
Er verwendet den *Credential* -Parameter, um ein Benutzerkonto anzugeben, das über die Berechtigung zum Zurücksetzen eines Computer Kennworts in der Domäne verfügt.

### Beispiel 3: Zurücksetzen des Kennworts auf einem Remote Computer

```
$cred = Get-Credential
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Reset-ComputerMachinePassword -Credential $using:cred}
```

Dieser Befehl verwendet das Cmdlet "Invoke-Command", um einen **Reset-ComputerMachinePassword-** Befehl auf dem Remote Computer Server01 auszuführen.

Weitere Informationen zu Remotebefehlen in Windows PowerShell finden Sie unter about_Remote und **Invoke-Command** .

## PARAMETERS

### -Credential
Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.
Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. das vom Cmdlet Get-Credential generierte.
Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Gibt den Namen eines Domänen Controllers an, der verwendet werden soll, wenn dieses Cmdlet das Kennwort des Computer Kontos festlegt.

Dieser Parameter ist optional.
Wenn Sie diesen Parameter weglassen, wird ein Domänencontroller zum Behandeln des Befehls ausgewählt.

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

### Keine
Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

## VERWANDTE LINKS

## VERWANDTE LINKS
