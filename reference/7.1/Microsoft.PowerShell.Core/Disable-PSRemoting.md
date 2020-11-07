---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: f2f9fb5ac13413b1ace74a995db9c3e78ac22d41
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347005"
---
# Disable-PSRemoting

## ZUSAMMENFASSUNG
Verhindert, dass PowerShell-Endpunkte Remote Verbindungen empfangen.

## SYNTAX

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Disable-PSRemoting`Mit dem-Cmdlet wird der Remote Zugriff auf alle PowerShell-Konfigurationen, Version 6, und eine größere Sitzungs Endpunkt Konfiguration auf dem lokalen Computer blockiert. Es wirkt sich nicht auf Windows PowerShell-Endpunkt Konfigurationen aus. Zum Deaktivieren der Konfigurationen von Windows PowerShell-Sitzungs Endpunkten führen Sie den `Disable-PSRemoting` Befehl in einer Windows PowerShell-Sitzung aus.

Verwenden Sie das-Cmdlet, um den Remote Zugriff auf alle PowerShell-Konfigurationen der Version 6 und einer größeren Sitzungs Endpunkt-Konfiguration wieder zu aktivieren `Enable-PSRemoting` . Um den Remote Zugriff auf alle Konfigurationen von Windows PowerShell-Sitzungs Endpunkten wieder zu aktivieren, führen Sie `Enable-PSRemoting` in einer Windows PowerShell-Sitzung aus.

> [!NOTE]
> Wenn Sie den gesamten PowerShell-Remote Zugriff auf einen lokalen Windows-Computer deaktivieren möchten, müssen Sie diesen Befehl sowohl innerhalb von PowerShell, Version 6 oder höher, als auch innerhalb einer Windows PowerShell-Sitzung ausführen. Windows PowerShell ist standardmäßig auf allen Windows-Computern installiert.

Verwenden Sie die `Enable-PSSessionConfiguration` Cmdlets und, um den Remote Zugriff auf bestimmte Sitzungs Endpunkt Konfigurationen zu deaktivieren und erneut zu aktivieren `Disable-PSSessionConfiguration` . Um spezifische Zugriffs Konfigurationen einzelner Endpunkte festzulegen, verwenden Sie das `Set-PSSessionConfiguration` Cmdlet zusammen mit dem **AccessMode** -Parameter. Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

> [!NOTE]
> Auch nach `Disable-PSRemoting` der Ausführung können Sie Loopback Verbindungen auf dem lokalen Computer durchführen. Eine Loopback Verbindung ist eine PowerShell-Remote Sitzung, die aus stammt und eine Verbindung mit dem gleichen lokalen Computer herstellt. Remote Sitzungen aus externen Quellen bleiben blockiert. Für Loopback Verbindungen müssen Sie die impliziten Anmelde Informationen für den **enablenetworkaccess** -Parameter verwenden. Weitere Informationen zu Loopback Verbindungen finden Sie unter [New-PSSession](New-PSSession.md).

Dieses Cmdlet ist nur auf der Windows-Plattform verfügbar. Sie ist unter Linux-oder macOS-Versionen von PowerShell nicht verfügbar. Starten Sie PowerShell mit der Option **als Administrator ausführen** , um dieses Cmdlet auszuführen.

## BEISPIELE

### Beispiel 1: verhindern des Remote Zugriffs auf alle PowerShell-Sitzungs Konfigurationen

In diesem Beispiel wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer verhindert.

```powershell
Disable-PSRemoting
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### Beispiel 2: verhindern des Remote Zugriffs auf alle PowerShell-Sitzungs Konfigurationen ohne Bestätigungsaufforderung

In diesem Beispiel wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer ohne Eingabeaufforderung verhindert.

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### Beispiel 3: Auswirkungen der Ausführung dieses Cmdlets

In diesem Beispiel werden die Auswirkungen der Verwendung des- `Disable-PSRemoting` Cmdlets veranschaulicht. Starten Sie PowerShell mit der Option **als Administrator ausführen** , um diese Befehlssequenz auszuführen.

Nachdem Sie die Sitzungs Konfigurationen deaktiviert haben, `New-PSSession` versucht das Cmdlet, eine Remote Sitzung mit dem lokalen Computer (auch als "Loopback" bezeichnet) zu erstellen. Da der Remote Zugriff auf dem lokalen Computer deaktiviert ist, schlägt der Befehl fehl.

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error
 message : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

### Beispiel 4: Auswirkungen der Ausführung dieses Cmdlets und Enable-PSRemoting

Dieses Beispiel zeigt die Auswirkung auf die Sitzungs Konfigurationen von mithilfe der `Disable-PSRemoting` `Enable-PSRemoting` Cmdlets und.

`Disable-PSRemoting` wird verwendet, um den Remote Zugriff auf alle Konfigurationen von PowerShell-Sitzungs Endpunkten zu deaktivieren. Mit dem **Force** -Parameter werden alle Eingabeaufforderungen unterdrückt. `Get-PSSessionConfiguration`Mit den-und- `Format-Table` Cmdlets werden die Sitzungs Konfigurationen auf dem Computer angezeigt.

Die Ausgabe zeigt, dass allen Remote Benutzern mit einem Netzwerk Token der Zugriff auf die Endpunkt Konfigurationen verweigert wird. Die Gruppe "Administratoren" auf dem lokalen Computer verfügt über Zugriff auf die Endpunkt Konfigurationen, solange Sie lokal (auch als Loopback bezeichnet) eine Verbindung herstellen und implizite Anmelde Informationen verwenden.

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed ...
```

Mit dem `Enable-PSRemoting` -Cmdlet wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer erneut aktiviert. Der **Force** -Parameter unterdrückt alle Benutzer Aufforderungen und startet den WinRM-Dienst ohne Aufforderung neu. Die neue Ausgabe zeigt, dass die **AccessDenied** -Sicherheits Beschreibungen aus allen Sitzungs Konfigurationen entfernt wurden.

### Beispiel 5: Loopback Verbindungen mit deaktivierten Sitzungs Endpunkt Konfigurationen

In diesem Beispiel wird veranschaulicht, wie Endpunkt Konfigurationen deaktiviert werden, und es wird gezeigt, wie Sie eine erfolgreiche Loopback Verbindung mit einem deaktivierten Endpunkt herstellen. `Disable-PSRemoting` deaktiviert alle PowerShell-Sitzungs Endpunkt Konfigurationen.

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -Credential (Get-Credential)
```

```Output
PowerShell credential request
Enter your credentials.
User: UserName
Password for user UserName: ************

New-PSSession: [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
```

```powershell
New-PSSession -ComputerName localhost -ConfigurationName powershell.6 -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

Bei der ersten Verwendung von wird `New-PSSession` versucht, eine Remote Sitzung mit dem lokalen Computer zu erstellen. Der **ConfigurationName** -Parameter wird verwendet, um einen deaktivierten PowerShell-Endpunkt anzugeben. Anmelde Informationen werden explizit über den **Credential** -Parameter an den Befehl übergeben. Dieser Verbindungstyp wird durch den Netzwerk Stapel geleitet und ist kein Loopback. Folglich schlägt der Verbindungsversuch mit dem deaktivierten Endpunkt mit dem Fehler " **Zugriff verweigert** " fehl.

Bei der zweiten Verwendung von wird `New-PSSession` auch versucht, eine Remote Sitzung mit dem lokalen Computer zu erstellen.
In diesem Fall ist dies erfolgreich, weil es sich um eine Loopback Verbindung handelt, die den Netzwerk Stapel umgeht.

Eine Loopback Verbindung wird erstellt, wenn die folgenden Bedingungen erfüllt sind:

- Der Computername, mit dem eine Verbindung hergestellt werden soll, ist "localhost".
- Es werden keine Anmelde Informationen übermittelt. Der aktuell angemeldete Benutzer (implizite Anmelde Informationen) wird für die Verbindung verwendet.
- Der **enablenetworkaccess** -Schalter Parameter wird verwendet.

Weitere Informationen zu Loopback Verbindungen finden Sie im Dokument [New-PSSession](New-PSSession.md) .

### Beispiel 6: Deaktivieren aller PowerShell-Remoting-Endpunkt Konfigurationen

In diesem Beispiel wird veranschaulicht, wie die Ausführung des `Disable-PSRemoting` Befehls keine Auswirkungen auf Windows PowerShell-Endpunkt Konfigurationen hat. `Get-PSSessionConfiguration` in Windows PowerShell ausführen werden alle Endpunkt Konfigurationen angezeigt. Wir sehen, dass die Windows PowerShell-Endpunkt Konfigurationen nicht deaktiviert sind.

```powershell
Disable-PSRemoting -Force
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: PowerShell remoting has been disabled only for PowerShell 6+ configurations and does not affect
 Windows PowerShell remoting configurations. Run this cmdlet in Windows PowerShell to affect all PowerShell
 remoting configurations.

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote
                Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

```powershell
powershell.exe -command 'Disable-PSRemoting -Force'
powershell.exe -command 'Get-PSSessionConfiguration'
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting or
Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the
Administrators group on the computer.

Name          : microsoft.powershell
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : microsoft.powershell.workflow
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management
                Users AccessAllowed

Name          : microsoft.powershell32
PSVersion     : 5.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6.2.2
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators
                AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

Um diese Endpunkt Konfigurationen zu deaktivieren, `Disable-PSRemoting` muss der Befehl innerhalb einer Windows PowerShell-Sitzung ausgeführt werden. Jetzt können Sie `Get-PSSessionConfiguration` in Windows PowerShell ausführen, um zu sehen, dass alle Endpunkt Konfigurationen deaktiviert sind.

### Beispiel 7: verhindern des Remote Zugriffs auf Sitzungs Konfigurationen mit benutzerdefinierten Sicherheits Deskriptoren

Dieses Beispiel zeigt, dass das `Disable-PSRemoting` Cmdlet den Remote Zugriff auf alle Sitzungs Konfigurationen deaktiviert, die Sitzungs Konfigurationen mit benutzerdefinierten Sicherheits Beschreibungen einschließen.

`Register-PSSessionConfiguration` erstellt die **Test** Sitzungs Konfiguration. Der **FilePath** -Parameter gibt eine Sitzungs Konfigurationsdatei an, die die Sitzung anpasst. Der **showsecuritydescriptorui** -Parameter zeigt ein Dialogfeld an, in dem Berechtigungen für die Sitzungs Konfiguration festgelegt werden. Im Dialogfeld "Berechtigungen" erstellen wir benutzerdefinierte voll Zugriffsberechtigungen für den angezeigten Benutzer.

Die `Get-PSSessionConfiguration` -und- `Format-Table` Cmdlets zeigen die Sitzungs Konfigurationen und deren Eigenschaften an. Die Ausgabe zeigt, dass die **Test** Sitzungs Konfiguration interaktiven Zugriff und spezielle Berechtigungen für den Benutzer ermöglicht.

`Disable-PSRemoting` deaktiviert den Remote Zugriff auf alle Sitzungs Konfigurationen.

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
                   User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name               Permission
----               ----------
PowerShell.6       NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
PowerShell.6.2.0   NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
Test               NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed,
                   BUILTIN\Administrators AccessAllowed, User01 AccessAllowed

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message
 : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName Test
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

Die `Get-PSSessionConfiguration` `Format-Table` Cmdlets und zeigen nun, dass allen Sitzungs Konfigurationen, einschließlich der **Test** Sitzungs Konfiguration, eine **AccessDenied** -Sicherheits Beschreibung für alle Netzwerk Benutzer hinzugefügt wird. Obwohl die anderen Sicherheits Deskriptoren nicht geändert werden, hat der Sicherheits Deskriptor "network_deny_all" Vorrang. Dies wird durch den Versuch veranschaulicht, zu verwenden, `New-PSSession` um eine Verbindung mit der **Test** Sitzungs Konfiguration herzustellen.

### Beispiel 8: Erneutes Aktivieren des Remote Zugriffs auf ausgewählte Sitzungs Konfigurationen

In diesem Beispiel wird veranschaulicht, wie der Remotezugriff nur auf ausgewählte Sitzungskonfigurationen erneut aktiviert wird. Nachdem Sie alle Sitzungs Konfigurationen deaktiviert haben, aktivieren wir eine bestimmte Sitzung erneut.

Das- `Set-PSSessionConfiguration` Cmdlet wird verwendet, um die Konfiguration der **PowerShell. 6** -Sitzung zu ändern. Der **AccessMode** -Parameter mit dem Wert **Remote** aktiviert den Remote Zugriff auf die Konfiguration.

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name PowerShell.6 -AccessMode Remote -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...

Name                 Permission
----                 ----------
PowerShell.6         NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\ ...
PowerShell.6.2.0     NT AUTHORITY\NETWORK AccessDenied, NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Adm ...
```

## PARAMETERS

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

Sie können keine Objekte über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

- Durch das Deaktivieren der Sitzungs Konfigurationen werden nicht alle Änderungen rückgängig gemacht, die von den- `Enable-PSRemoting` oder- `Enable-PSSessionConfiguration` Cmdlets vorgenommen wurden. Möglicherweise müssen Sie Änderungen wie folgt manuell rückgängig machen.

  1. Beenden und deaktivieren Sie den WinRM-Dienst.
  2. Löschen Sie den Listener, der Anforderungen auf beliebigen IP-Adressen akzeptiert.
  3. Deaktivieren Sie die Firewallausnahmen für die WS-Verwaltungskommunikation.
  4. Setzen Sie den Wert von LocalAccountTokenFilterPolicy auf 0 zurück. Dadurch wird der Remotezugriff auf Mitglieder der Gruppe „Administratoren“ auf dem Computer beschränkt.

- Eine Sitzungs Endpunkt Konfiguration ist eine Gruppe von Einstellungen, die die Umgebung für eine Sitzung definieren.
  Jede Sitzung, die eine Verbindung mit dem Computer herstellt, muss eine der auf dem Computer registrierten Sitzungs Endpunkt Konfigurationen verwenden. Indem Sie den Remote Zugriff auf alle Sitzungs Endpunkt Konfigurationen verweigern, verhindern Sie, dass Remote Benutzersitzungen einrichten, die eine Verbindung mit dem Computer herstellen.

## VERWANDTE LINKS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSRemoting](Enable-PSRemoting.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan-Anbieter](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
