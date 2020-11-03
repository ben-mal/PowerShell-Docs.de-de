---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 3a281786f99b2a46d0aeb9785480f02b35b2b433
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212103"
---
# Disable-PSRemoting

## ZUSAMMENFASSUNG
Verhindert, dass PowerShell-Endpunkte Remote Verbindungen empfangen.

## SYNTAX

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Disable-PSRemoting` Cmdlet wird der Remote Zugriff auf alle Konfigurationen von Windows PowerShell-Sitzungs Endpunkten auf dem lokalen Computer blockiert. Dies schließt alle Endpunkte ein, die von PowerShell 6 oder höher erstellt wurden.

Verwenden Sie das-Cmdlet, um den Remote Zugriff auf alle Sitzungs Konfigurationen wieder zu aktivieren `Enable-PSRemoting` . Dies schließt alle Endpunkte ein, die von PowerShell 6 oder höher erstellt wurden. Um den Remote Zugriff auf ausgewählte Sitzungs Konfigurationen zu aktivieren, verwenden Sie den **AccessMode** -Parameter des `Set-PSSessionConfiguration` Cmdlets.
Sie können auch die `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` Cmdlets und verwenden, um Sitzungs Konfigurationen für alle Benutzer zu aktivieren und zu deaktivieren. Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

> [!NOTE]
> Auch nach `Disable-PSRemoting` der Ausführung können Sie Loopback Verbindungen auf dem lokalen Computer durchführen. Eine Loopback Verbindung ist eine PowerShell-Remote Sitzung, die aus stammt und eine Verbindung mit dem gleichen lokalen Computer herstellt. Remote Sitzungen aus externen Quellen bleiben blockiert. Für Loopback Verbindungen müssen Sie die impliziten Anmelde Informationen für den **enablenetworkaccess** -Parameter verwenden. Weitere Informationen zu Loopback Verbindungen finden Sie unter [New-PSSession](New-PSSession.md).

Um dieses Cmdlet auszuführen, starten Sie Windows PowerShell mit der Option **als Administrator ausführen** .

## BEISPIELE

### Beispiel 1: verhindern des Remote Zugriffs auf alle Sitzungs Konfigurationen

In diesem Beispiel wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer verhindert.

```powershell
Disable-PSRemoting
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### Beispiel 2: verhindern des Remote Zugriffs auf alle Sitzungs Konfigurationen ohne Bestätigungsaufforderung

In diesem Beispiel wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer ohne Eingabeaufforderung verhindert.

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
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
New-PSSession -ComputerName localhost
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
Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow BUILTIN\Administrators AccessAllowed
microsoft.powershell32        BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   BUILTIN\Administrators AccessAllowed
```

Mit dem `Enable-PSRemoting` -Cmdlet wird der Remote Zugriff auf alle PowerShell-Sitzungs Endpunkt Konfigurationen auf dem Computer erneut aktiviert. Der **Force** -Parameter unterdrückt alle Benutzer Aufforderungen und startet den WinRM-Dienst ohne Aufforderung neu. Die neue Ausgabe zeigt, dass die **AccessDenied** -Sicherheits Beschreibungen aus allen Sitzungs Konfigurationen entfernt wurden.

### Beispiel 5: Loopback Verbindungen mit deaktivierten Sitzungs Endpunkt Konfigurationen

In diesem Beispiel wird veranschaulicht, wie Endpunkt Konfigurationen deaktiviert werden, und es wird gezeigt, wie Sie eine erfolgreiche Loopback Verbindung mit einem deaktivierten Endpunkt herstellen. `Disable-PSRemoting` deaktiviert alle PowerShell-Sitzungs Endpunkt Konfigurationen.

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message : Access is
denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [New-PSSession], PSRemotin
   gTransportException
    + FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed

```

```powershell
New-PSSession -ComputerName localhost -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

Bei der ersten Verwendung von wird `New-PSSession` versucht, eine Remote Sitzung mit dem lokalen Computer zu erstellen. Dieser Verbindungstyp wird durch den Netzwerk Stapel geleitet und ist kein Loopback. Folglich schlägt der Verbindungsversuch mit dem deaktivierten Endpunkt mit dem Fehler " **Zugriff verweigert** " fehl.

Bei der zweiten Verwendung von wird `New-PSSession` auch versucht, eine Remote Sitzung mit dem lokalen Computer zu erstellen.
In diesem Fall ist dies erfolgreich, weil es sich um eine Loopback Verbindung handelt, die den Netzwerk Stapel umgeht.

Eine Loopback Verbindung wird erstellt, wenn die folgenden Bedingungen erfüllt sind:

- Der Computername, mit dem eine Verbindung hergestellt werden soll, ist "localhost".
- Es werden keine Anmelde Informationen übermittelt. Der aktuell angemeldete Benutzer (implizite Anmelde Informationen) wird für die Verbindung verwendet.
- Der **enablenetworkaccess** -Schalter Parameter wird verwendet.

Weitere Informationen zu Loopback Verbindungen finden Sie im Dokument [New-PSSession](New-PSSession.md) .

### Beispiel 6: verhindern des Remote Zugriffs auf Sitzungs Konfigurationen mit benutzerdefinierten Sicherheits Deskriptoren

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
Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
DOMAIN01\User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\NETWORK AccessDenied, NTAUTHORITY\INTERACTIVE AccessAllowed,
BUILTIN\Administrators AccessAllowed, DOMAIN01\User01 AccessAllowed


[Server01] Connecting to remote server failed with the following error message : Access is denied. For more information, see the about_Rem
ote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

Die `Get-PSSessionConfiguration` `Format-Table` Cmdlets und zeigen nun, dass allen Sitzungs Konfigurationen, einschließlich der **Test** Sitzungs Konfiguration, eine **AccessDenied** -Sicherheits Beschreibung für alle Netzwerk Benutzer hinzugefügt wird. Obwohl die anderen Sicherheits Deskriptoren nicht geändert werden, hat der Sicherheits Deskriptor "network_deny_all" Vorrang. Dies wird durch den Versuch veranschaulicht, zu verwenden, `New-PSSession` um eine Verbindung mit der **Test** Sitzungs Konfiguration herzustellen.

### Beispiel 7: Erneutes Aktivieren des Remote Zugriffs auf ausgewählte Sitzungs Konfigurationen

In diesem Beispiel wird veranschaulicht, wie der Remotezugriff nur auf ausgewählte Sitzungskonfigurationen erneut aktiviert wird. Nachdem Sie alle Sitzungs Konfigurationen deaktiviert haben, aktivieren wir eine bestimmte Sitzung erneut.

Das- `Set-PSSessionConfiguration` Cmdlet wird verwendet, um **Microsoft zu ändern. Server Manager** -Sitzungs Konfiguration. Der **AccessMode** -Parameter mit dem Wert **Remote** aktiviert den Remote Zugriff auf die Konfiguration.

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name Microsoft.ServerManager -AccessMode Remote -Force
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

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
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

- Durch das Deaktivieren der Sitzungs Konfigurationen werden nicht alle Änderungen rückgängig gemacht, die von den- `Enable-PSRemoting` oder- `Enable-PSSessionConfiguration` Cmdlets vorgenommen wurden. Möglicherweise müssen Sie Änderungen wie folgt manuell rückgängig machen.

  1. Beenden und deaktivieren Sie den WinRM-Dienst.
  2. Löschen Sie den Listener, der Anforderungen auf beliebigen IP-Adressen akzeptiert.
  3. Deaktivieren Sie die Firewallausnahmen für die WS-Verwaltungskommunikation.
  4. Setzen Sie den Wert von LocalAccountTokenFilterPolicy auf 0 zurück. Dadurch wird der Remotezugriff auf Mitglieder der Gruppe „Administratoren“ auf dem Computer beschränkt.

  Eine Sitzungskonfiguration ist eine Gruppe von Einstellungen, die die Umgebung für eine Sitzung definieren. Jede Sitzung, die mit dem Computer verbunden wird, muss eine der auf dem Computer registrierten Sitzungskonfigurationen verwenden. Indem Sie den Remotezugriff auf alle Sitzungskonfigurationen verweigern, hindern Sie Remotebenutzer effektiv daran, Sitzungen einzurichten, die eine Verbindung mit dem Computer herstellen.

  Fügt in Windows PowerShell 2,0 `Disable-PSRemoting` den Sicherheits Beschreibungen aller Sitzungs Konfigurationen einen Deny_All Eintrag hinzu. Diese Einstellung verhindert, dass alle Benutzer vom Benutzer verwaltete Sitzungen auf dem lokalen Computer erstellen. Fügt in Windows PowerShell 3,0 `Disable-PSRemoting` den Sicherheits Beschreibungen aller Sitzungs Konfigurationen einen Network_Deny_All Eintrag hinzu. Mit dieser Einstellung wird verhindert, dass Benutzer auf anderen Computern vom Benutzer verwaltete Sitzungen auf dem lokalen Computer erstellen, aber Benutzern des lokalen Computers das Erstellen von Benutzer verwalteten Loopback Sitzungen ermöglicht.

  In Windows PowerShell 2,0 `Disable-PSRemoting` ist die Entsprechung von `Disable-PSSessionConfiguration -Name *` . In Windows PowerShell 3,0 und späteren Versionen `Disable-PSRemoting` ist die Entsprechung von `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`

## VERWANDTE LINKS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSRemoting](Enable-PSRemoting.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan-Anbieter](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
