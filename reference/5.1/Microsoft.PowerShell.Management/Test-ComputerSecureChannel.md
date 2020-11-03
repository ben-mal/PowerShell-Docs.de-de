---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-computersecurechannel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ComputerSecureChannel
ms.openlocfilehash: 20ea76e725a8ab53d7090078dc819a6297a639ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214343"
---
# Test-ComputerSecureChannel

## ZUSAMMENFASSUNG
Testet und repariert den sicheren Channel zwischen dem lokalen Computer und seiner Domäne.

## SYNTAX

```
Test-ComputerSecureChannel [-Repair] [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Mit dem Cmdlet " **Test-computersecurechannel** " wird überprüft, ob der Kanal zwischen dem lokalen Computer und seiner Domäne ordnungsgemäß funktioniert, indem der Status der Vertrauens Stellungen überprüft wird.
Wenn eine Verbindung nicht hergestellt werden kann, können Sie den *Repair* -Parameter verwenden, um Sie wiederherzustellen.

" **Test-computersecurechannel** " gibt $true zurück, wenn der Kanal ordnungsgemäß funktioniert, und $false andernfalls.
Durch dieses Ergebnis können Sie das Cmdlet in bedingten Anweisungen in Features und Skripts verwenden.
Um ausführlichere Testergebnisse zu erhalten, verwenden Sie den *verbose* -Parameter.

Die Funktion dieses Cmdlets ist vergleichbar mit %%amp;quot;NetDom.exe%%amp;quot;.
Netdom und **Test-computersecurechannel** verwenden den **Anmelde** Dienst, um die Aktionen auszuführen.

## BEISPIELE

### Beispiel 1: Testen eines Kanals zwischen dem lokalen Computer und seiner Domäne

```
PS C:\> Test-ComputerSecureChannel
True
```

Dieser Befehl testet den Kanal zwischen dem lokalen Computer und der Domäne, der er hinzugefügt wurde.

### Beispiel 2: Testen eines Kanals zwischen dem lokalen Computer und einem Domänen Controller

```
PS C:\> Test-ComputerSecureChannel -Server "DCName.fabrikam.com"
True
```

Dieser Befehl gibt einen bevorzugten Domänencontroller für den Test an.

### Beispiel 3: Zurücksetzen des Kanals zwischen dem lokalen Computer und seiner Domäne

```
PS C:\> Test-ComputerSecureChannel -Repair
True
```

Dieser Befehl setzt den Kanal zwischen dem lokalen Computer und seiner Domäne zurück.

### Beispiel 4: Anzeigen detaillierter Informationen zum Test

```
PS C:\> Test-ComputerSecureChannel -verbose
VERBOSE: Performing operation "Test-ComputerSecureChannel" on Target "SERVER01".
True
VERBOSE: "The secure channel between 'SERVER01' and 'net.fabrikam.com' is alive and working correctly."
```

Dieser Befehl verwendet den allgemeinen *verbose* -Parameter, um ausführliche Meldungen zum Vorgang anzufordern.
Weitere Informationen zu " *verbose* " finden Sie unter about_CommonParameters.

### Beispiel 5: Testen einer Verbindung vor dem Ausführen eines Skripts

```
PS C:\> Set-Alias tcsc Test-ComputerSecureChannel
if (!(tcsc))
{Write-Host "Connection failed. Reconnect and retry."}
else { &(.\Get-Servers.ps1) }
```

Dieses Beispiel zeigt, wie Sie mit **Test-computersecurechannel** eine Verbindung testen, bevor Sie ein Skript ausführen, das die Verbindung erfordert.

Der erste Befehl erstellt mit dem Cmdlet %%amp;quot;Set-Alias%%amp;quot; einen Alias für den Cmdlet-Namen.
So wird Speicherplatz gespart, und Tippfehler werden verhindert.

Die **if** -Anweisung überprüft den von **Test-computersecurechannel** zurückgegebenen Wert, bevor ein Skript ausgeführt wird.

## PARAMETERS

### -Credential
Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.
Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. das vom Get-Credential-Cmdlet zurückgegebene.
Standardmäßig verwendet das Cmdlet die Anmeldeinformationen des aktuellen Benutzers.

Der *Credential* -Parameter ist für die Verwendung in Befehlen konzipiert, die den *Repair* -Parameter verwenden, um den Kanal zwischen dem Computer und der Domäne zu reparieren.

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

### -Repair
Gibt an, dass dieses Cmdlet den vom Anmeldedienst eingerichteten Kanal entfernt und anschließend neu erstellt.
Verwenden Sie diesen Parameter, um eine Verbindung wiederherzustellen, bei der der Test nicht erfolgreich war.

Um diesen Parameter zu verwenden, muss der aktuelle Benutzer Mitglied der Gruppe %%amp;quot;Administratoren%%amp;quot; auf dem lokalen Computer sein.

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

### -Server
Gibt den Domänen Controller an, auf dem der Befehl ausgeführt wird.
Wenn dieser Parameter nicht angegeben wird, wählt dieses Cmdlet einen Standard Domänen Controller für den Vorgang aus.

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

### System.Boolean
Dieses Cmdlet gibt $true zurück, wenn die Verbindung ordnungsgemäß funktioniert, und $false andernfalls.

## HINWEISE

* Öffnen Sie Windows PowerShell mit der Option als Administrator ausführen, um einen **Test-computersecurechannel** -Befehl unter Windows Vista und höheren Versionen des Windows-Betriebssystems auszuführen.
* **Test-computersecurechannel** wird mithilfe der **I_NetLogonControl2** -Funktion implementiert, die verschiedene Aspekte des Netlogon-Diensts steuert.

## VERWANDTE LINKS

[Checkpoint-Computer](Checkpoint-Computer.md)

[Reset-ComputerMachinePassword](Reset-ComputerMachinePassword.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
