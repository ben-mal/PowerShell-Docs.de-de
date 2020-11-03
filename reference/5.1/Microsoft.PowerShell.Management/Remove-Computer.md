---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Computer
ms.openlocfilehash: 89e43220a8d5ac675ea232db09cf3edec2ca2b97
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214559"
---
# Remove-Computer

## ZUSAMMENFASSUNG
Entfernt den lokalen Computer aus seiner Domäne.

## SYNTAX

### Local (Standard)

```
Remove-Computer [[-UnjoinDomainCredential] <PSCredential>] [-Restart] [-Force] [-PassThru]
 [-WorkgroupName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Remote

```
Remove-Computer -UnjoinDomainCredential <PSCredential> [-LocalCredential <PSCredential>] [-Restart]
 [-ComputerName <String[]>] [-Force] [-PassThru] [-WorkgroupName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem `Remove-Computer` -Cmdlet werden der lokale Computer und Remote Computer aus den aktuellen Domänen entfernt.

Wenn Sie einen Computer aus einer Domäne entfernen, wird `Remove-Computer` von auch das Domänen Konto des Computers deaktiviert. Sie müssen explizite Anmelde Informationen angeben, um den Computer aus seiner Domäne zu entfernen, selbst wenn es sich um die Anmelde Informationen des aktuellen Benutzers handelt. Sie müssen den Computer neu starten, damit die Änderung wirksam wird. Darüber hinaus muss ein Computer, wenn er aus einer Domäne entfernt wird, in eine Arbeitsgruppe verschoben werden. Geben Sie mithilfe des **WorkgroupName** -Parameters die Arbeitsgruppe an.

Mit dem Cmdlet `Add-Computer` verschieben Sie einen Computer von einer Arbeitsgruppe in eine Domäne, von einer Arbeitsgruppe in eine andere Arbeitsgruppe oder von einer Domäne in eine andere Domäne.

Rufen Sie die Ergebnisse des Befehls mit dem **Verbose** - und dem **PassThru** -Parameter ab. Unterdrücken Sie die Benutzerbestätigung mithilfe des **Force** -Parameters.

`Remove-Computer` entfernt den lokalen Computer und Remote Computer aus Domänen. Das Cmdlet enthält Anmeldeinformationsparameter, die alternative Anmeldeinformationen für das Herstellen einer Verbindung mit Remotecomputern und das Entfernen aus einer Domäne angeben. Außerdem enthält es einen **Restart** -Parameter zum Neustarten der betroffenen Computer und einen **WorkgroupName** -Parameter zum Angeben des Namens der Arbeitsgruppe, der Computer hinzugefügt werden.

## BEISPIELE

### Beispiel 1: Entfernen des lokalen Computers aus seiner Domäne

In diesem Beispiel wird der lokale Computer aus der Domäne entfernt, der er hinzugefügt wurde.

```powershell
Remove-Computer -UnjoinDomaincredential Domain01\Admin01 -PassThru -Verbose -Restart
```

Der **unjoindomaincredential** -Parameter stellt die Anmelde Informationen eines Domänen Administrators bereit. Der **passthru** -Parameter und der ausführliche allgemeine Parameter zeigen Informationen zum Erfolg oder fehl **schlagen** des Befehls an. Mit dem **Restart** -Parameter wird der Computer neu gestartet, um den Entfernungs Vorgang abzuschließen.

Wenn kein Arbeitsgruppen Name angegeben wird, wird der Computer nach dem Entfernen aus der Domäne in die Arbeitsgruppe verschoben.

### Beispiel 2: Verschieben mehrerer Computer in eine ältere Arbeitsgruppe

In diesem Beispiel werden alle Computer, die in der Datei aufgelistet sind, `OldServers.txt` aus Ihren Domänen entfernt und in die **Legacy** Arbeitsgruppe verschoben.

```powershell
Remove-Computer -ComputerName (Get-Content OldServers.txt) -LocalCredential Domain01\Admin01 -UnJoinDomainCredential Domain01\Admin01 -WorkgroupName "Legacy" -Force -Restart
```

Der **localcredential** -Parameter stellt die Anmelde Informationen eines Benutzers bereit, der über die Berechtigung zum Herstellen einer Verbindung mit Remote Computern verfügt. Der **unjoindomaincredential** -Parameter stellt die Anmelde Informationen eines Benutzers bereit, der über die Berechtigung zum Entfernen der Computer aus Ihren Domänen verfügt. Der **Force** -Parameter unterdrückt die Bestätigungs Aufforderungen für die einzelnen Computer. Mit dem **Restart** -Parameter werden die Computer neu gestartet, nachdem Sie aus der Domäne entfernt wurden.

### Beispiel 3: Entfernen von Computern aus einer Arbeitsgruppe ohne Bestätigung

In diesem Beispiel werden der Remote Computer, Server01 und der lokale Computer aus den Domänen entfernt und der **lokalen** Arbeitsgruppe hinzugefügt.

```powershell
Remove-Computer -ComputerName "Server01", "localhost" -UnjoinDomainCredential Domain01\Admin01 -WorkgroupName "Local" -Restart -Force
```

Der **Force** -Parameter unterdrückt die Bestätigungsaufforderung für jeden Computer. Mit dem **Restart** -Parameter werden die Computer neu gestartet, damit die Änderung wirksam wird.

## PARAMETERS

### -ComputerName

Gibt die Computer an, die aus ihren Domänen entfernt werden sollen. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) der Remote Computer ein. Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.

Dieser Parameter beruht nicht auf PowerShell-Remoting. Sie können den **Computername** -Parameter `Remove-Computer` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Force

Unterdrückt die Benutzeraufforderung. Standardmäßig werden `Remove-Computer` Sie von zur Bestätigung aufgefordert, bevor die einzelnen Computer entfernt werden.

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

### -Localcredential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit den Computern verfügt, die vom Parameter **Computername** angegeben werden. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt. Wenn Sie einen Benutzernamen eingeben, werden Sie vom Cmdlet zur Eingabe eines Kennworts aufgefordert. Geben Sie ein Benutzerkonto, das über die Berechtigung zum Entfernen des Computers aus der aktuellen Domäne verfügt, mit dem **UnjoinDomainCredential** -Parameter an.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt die Ergebnisse des Befehls zurück. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

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

### -Restart

Gibt an, dass mit diesem Cmdlet die zu entfernende Computer neu gestartet werden. Ein Neustart ist häufig erforderlich, damit die Änderung wirksam wird.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

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

### -Unjoindomaincredential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Entfernen der Computer aus ihren aktuellen Domänen verfügt.
Explizite Anmeldeinformationen, wie sie von diesem Parameter bereitgestellt werden, sind erforderlich, um Remotecomputer aus einer Domäne zu entfernen, auch wenn der Wert die Anmeldeinformationen des aktuellen Benutzers darstellt.

Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. das von generierte `Get-Credential` . Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.

Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit Remotecomputern verfügt, mit dem **LocalCredential** -Parameter an.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Local, Remote
Aliases: Credential

Required: False (Local), True (Remote)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Workgroupname

Gibt den Namen einer Arbeitsgruppe an, der die Computer nach dem Entfernen aus den Domänen hinzugefügt werden. Der Standardwert ist **Workgroup** . Wenn ein Computer aus einer Domäne entfernt wird, muss er einer Arbeitsgruppe hinzugefügt werden.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

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

### System.String

Sie können Computernamen an das thiscmdlet weiterreichen.

## AUSGABEN

### Microsoft. PowerShell. Commands. computerchangeingefo

Wenn Sie den **passthru** -Parameter verwenden, wird `Remove-Computer` ein **computerchangeinfo** -Objekt zurückgegeben.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

Mit diesem Cmdlet werden keine Computer aus Arbeitsgruppen entfernt.

## VERWANDTE LINKS

[Add-Computer](Add-Computer.md)

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Stop-Computer](Stop-Computer.md)

[Test-Connection](Test-Connection.md)
