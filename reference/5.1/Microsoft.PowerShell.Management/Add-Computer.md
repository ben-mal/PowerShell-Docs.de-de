---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Computer
ms.openlocfilehash: e3d1c5c071a334bddbfbc547ef2cc07e9e5c90aa
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388347"
---
# Add-Computer

## ZUSAMMENFASSUNG
Fügt den lokalen Computer einer Domäne oder Arbeitsgruppe hinzu.

## SYNTAX

### Domäne (Standard)

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>]
 [-UnjoinDomainCredential <PSCredential>] -Credential <PSCredential> [-DomainName] <String> [-OUPath <String>]
 [-Server <String>] [-Unsecure] [-Options <JoinOptions>] [-Restart] [-PassThru] [-NewName <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Arbeitsgruppe

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>] [-Credential <PSCredential>]
 [-WorkgroupName] <String> [-Restart] [-PassThru] [-NewName <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Add-Computer` Cmdlet werden der lokale Computer oder Remote Computer einer Domäne oder Arbeitsgruppe hinzugefügt oder von einer Domäne in eine andere verschoben. Außerdem erstellt das Cmdlet ein Domänenkonto, falls der Computer der Domäne ohne Konto hinzugefügt wird.

Mit den Parametern dieses Cmdlets können Sie eine Organisationseinheit und einen Domänencontroller angeben oder einen unsicheren Beitritt ausführen.

Rufen Sie die Ergebnisse des Befehls mit dem **Verbose** - und dem **PassThru** -Parameter ab.

## BEISPIELE

### Beispiel 1: Hinzufügen eines lokalen Computers zu einer Domäne und Neustarten des Computers

```powershell
Add-Computer -DomainName Domain01 -Restart
```

Mit diesem Befehl wird der lokale Computer der Domäne %%amp;quot;Domain01%%amp;quot; hinzugefügt und anschließend neu gestartet, damit die Änderung wirksam wird.

### Beispiel 2: Hinzufügen eines lokalen Computers zu einer Arbeitsgruppe

```powershell
Add-Computer -WorkgroupName WORKGROUP-A
```

Mit diesem Befehl wird der lokale Computer der Arbeitsgruppe %%amp;quot;Workgroup-A%%amp;quot; hinzugefügt.

### Beispiel 3: Hinzufügen eines lokalen Computers zu einer Domäne

```powershell
Add-Computer -DomainName Domain01 -Server Domain01\DC01 -PassThru -Verbose
```

Dieser Befehl fügt den lokalen Computer unter Verwendung des Domänencontrollers %%amp;quot;Domain01\DC01%%amp;quot; der Domäne %%amp;quot;Domain01%%amp;quot; hinzu.

Der Befehl ruft mit dem **PassThru** -Parameter und dem **Verbose** -Parameter ausführliche Informationen zu den Ergebnissen des Befehls ab.

### Beispiel 4: Hinzufügen eines lokalen Computers zu einer Domäne mithilfe des oupath-Parameters

```powershell
Add-Computer -DomainName Domain02 -OUPath "OU=testOU,DC=domain,DC=Domain,DC=com"
```

Mit diesem Befehl wird der lokale Computer der Domäne %%amp;quot;Domain02%%amp;quot; hinzugefügt.
Dabei wird mit dem Parameter %%amp;quot;OUPath%%amp;quot; die Organisationseinheit für die neuen Konten angegeben.

### Beispiel 5: Hinzufügen eines lokalen Computers zu einer Domäne mithilfe von Anmelde Informationen

```powershell
Add-Computer -ComputerName Server01 -LocalCredential Server01\Admin01 -DomainName Domain02 -Credential Domain02\Admin02 -Restart -Force
```

Mit diesem Befehl wird der Computer %%amp;quot;Server01%%amp;quot; der Domäne %%amp;quot;Domain02%%amp;quot; hinzugefügt. Mit dem **LocalCredential** -Parameter wird ein Benutzerkonto angegeben, das über die Berechtigung zum Herstellen einer Verbindung mit dem Computer %%amp;quot;Server01%%amp;quot; verfügt. Mit dem **Credential** -Parameter wird ein Benutzerkonto angegeben, das über die Berechtigung zum Hinzufügen von Computern zur Domäne verfügt. Mit dem **Restart** -Parameter wird der Computer nach Abschluss des Beitrittsvorgangs neu gestartet. Mit dem **Force** -Parameter werden Meldungen zur Benutzerbestätigung unterdrückt.

### Beispiel 6: Verschieben einer Gruppe von Computern in eine neue Domäne

```powershell
Add-Computer -ComputerName Server01, Server02, localhost -DomainName Domain02 -LocalCredential Domain01\User01 -UnjoinDomainCredential Domain01\Admin01 -Credential Domain02\Admin01 -Restart
```

Mit diesem Befehl werden der Computer %%amp;quot;Server01%%amp;quot;, der Computer %%amp;quot;Server02%%amp;quot; und der lokale Computer von %%amp;quot;Domain01%%amp;quot; in %%amp;quot;Domain02%%amp;quot; verschoben.

Mit dem **LocalCredential** -Parameter wird ein Benutzerkonto angegeben, das über die Berechtigung zum Herstellen einer Verbindung mit den drei betroffenen Computern verfügt. Mit dem **UnjoinDomainCredential** -Parameter wird ein Benutzerkonto angegeben, das über die Berechtigung zum Trennen der Computer von der Domäne %%amp;quot;Domain01%%amp;quot; verfügt, und mit dem **Credential** -Parameter wird ein Benutzerkonto angegeben, das über die Berechtigung zum Entfernen der Computer aus der Domäne %%amp;quot;Domain02%%amp;quot; verfügt. Mit dem **Restart** -Parameter werden alle drei Computer nach dem Verschieben neu gestartet.

### Beispiel 7: Verschieben eines Computers in eine neue Domäne und Ändern des Namens des Computers

```powershell
Add-Computer -ComputerName Server01 -DomainName Domain02 -NewName Server044 -Credential Domain02\Admin01 -Restart
```

Mit diesem Befehl wird der Computer %%amp;quot;Server01%%amp;quot; in die Domäne %%amp;quot;Domain02%%amp;quot; verschoben, und der Computername wird in %%amp;quot;Server044%%amp;quot; geändert.

Der Befehl verwendet die Anmeldeinformationen des aktuellen Benutzers, um eine Verbindung mit dem Computer %%amp;quot;Server01%%amp;quot; herzustellen und ihn aus der aktuellen Domäne zu entfernen. Er verwendet den **Credential** -Parameter, um ein Benutzerkonto anzugeben, das über die Berechtigung zum Hinzufügen des Computers zur Domain02-Domäne verfügt.

### Beispiel 8: Hinzufügen von in einer Datei aufgeführten Computern zu einer neuen Domäne

```powershell
Add-Computer -ComputerName (Get-Content Servers.txt) -DomainName Domain02 -Credential Domain02\Admin02 -Options Win9xUpgrade  -Restart
```

Mit diesem Befehl werden die in der Datei %%amp;quot;Servers.txt%%amp;quot; aufgeführten Computer der Domäne %%amp;quot;Domain02%%amp;quot; hinzugefügt. Mit dem **Options** -Parameter wird die **Win9xUpgrade** -Option angegeben. Mit dem **Restart** -Parameter werden alle neu hinzugefügten Computer nach dem Beitrittsvorgang neu gestartet.

### Beispiel 9: Hinzufügen eines Computers zu einer Domäne mithilfe vordefinierter Computer Anmelde Informationen

Der erste Befehl sollte von einem Administrator auf einem Computer ausgeführt werden, der bereits der Domäne beigetreten ist `Domain03` :

```powershell
New-ADComputer -Name "Server02" -AccountPassword (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)

# Then this command is run from `Server02` which is not yet domain-joined:

$joinCred = New-Object pscredential -ArgumentList ([pscustomobject]@{
    UserName = $null
    Password = (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)[0]
})
Add-Computer -Domain "Domain03" -Options UnsecuredJoin,PasswordPass -Credential $joinCred
```

Diese Kombination von Befehlen erstellt ein neues Computer Konto mit einem vordefinierten Namen und einem temporären joinkennwort in einer Domäne mithilfe eines vorhandenen, in die Domäne eingebundenen Computers. Ein Computer mit dem vordefinierten Namen wird dann separat mit dem Computernamen und dem Kennwort für den temporären Join verknüpft.
Das vordefinierte Kennwort wird nur zur Unterstützung des Join-Vorgangs verwendet und als Teil der normalen Computer Konto Prozeduren ersetzt, nachdem der Computer den Join abgeschlossen hat.

## PARAMETERS

### -ComputerName

Gibt die einer Domäne oder Arbeitsgruppe hinzuzufügenden Computer an.
Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den voll qualifizierten Domänen Namen der einzelnen Remote Computer ein. Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt ( `.` ) oder "localhost" ein.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting. Sie können den **Computername** -Parameter `Add-Computer` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Hinzufügen der Computer zu einer neuen Domäne verfügt.
Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

Geben Sie ein Benutzerkonto, das über die Berechtigung zum Entfernen des Computers aus der aktuellen Domäne verfügt, mit dem **UnjoinDomainCredential** -Parameter an. Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit einem Remotecomputer verfügt, mit dem **LocalCredential** -Parameter an.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain, Workgroup
Aliases: DomainCredential

Required: True (Domain), False (Workgroup)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName

Gibt die Domäne an, der die Computer hinzugefügt werden. Dieser Parameter ist beim Hinzufügen der Computer zu einer Domäne erforderlich.

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DN, Domain

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Unterdrückt die Bestätigungsaufforderung. Ohne diesen Parameter erfordert, dass `Add-Computer` Sie das Hinzufügen jedes Computers bestätigen.

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Localcredential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit den durch den **ComputerName** -Parameter angegebenen Computern verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

Geben Sie ein Benutzerkonto, das über die Berechtigung zum Hinzufügen der Computer zu einer neuen Domäne verfügt, mit dem **Credential** -Parameter an. Geben Sie ein Benutzerkonto, das über die Berechtigung zum Entfernen der Computer aus der aktuellen Domäne verfügt, mit dem **UnjoinDomainCredential** -Parameter an.

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Newname

Gibt einen neuen Namen für den Computer in der neuen Domäne an. Dieser Parameter ist nur gültig, wenn ein Computer hinzugefügt oder verschoben wird.

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

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

### -Optionen

Gibt erweiterte Optionen für den **Add-Computer-** Joinvorgang an. Geben Sie Werte in einer durch Trennzeichen getrennten Zeichenfolge ein.

Zulässige Werte für diesen Parameter:

- **Accountcreate** : erstellt ein Domänen Konto. Das **Add-Computer-** Cmdlet erstellt beim Hinzufügen eines Computers zu einer Domäne automatisch ein Domänen Konto. Diese Option ist aus Gründen der Vollständigkeit enthalten.

- **Win9XUpgrade** : gibt an, dass der Joinvorgang Teil eines Upgrades für das Windows-Betriebssystem ist.

- **Unsecuredjoin** : führt einen ungesicherten Join aus. Verwenden Sie zum Anfordern eines unsicheren Joins den *unsecure* -Parameter oder diese Option. Wenn Sie ein Computer Kennwort übergeben möchten, müssen Sie diese Option in Kombination mit der `PasswordPass` Option verwenden.

- **Passwordpass** : legt das Computer Kennwort auf den Wert des *Credential* (domaincredential)-Parameters fest, nachdem ein unsicherer Join durchgeführt wurde. Diese Option gibt darüber hinaus an, dass es sich beim Wert des *Credential* (DomainCredential)-Parameters um ein Computerkennwort und nicht um ein Benutzerkennwort handelt. Diese Option ist nur gültig, wenn die `UnsecuredJoin` Option angegeben ist. Wenn diese Option verwendet wird, müssen die für den-Parameter bereitgestellten Anmelde Informationen `-Credential` über einen NULL- *must* Benutzernamen verfügen.

- **Joinwithnewname** : benennt den Computernamen in der neuen Domäne in den durch den *NewName* -Parameter angegebenen Namen um. Bei Verwendung des *NewName* -Parameters wird diese Option automatisch festgelegt. Diese Option ist für die Verwendung mit dem Cmdlet "Rename-Computer" konzipiert. Wenn Sie das Cmdlet **Rename-Computer** zum Umbenennen des Computers verwenden, den Computer jedoch nicht neu starten, damit die Änderung wirksam wird, können Sie diesen Parameter verwenden, um den Computer einer Domäne mit dem neuen Namen hinzuzufügen.

- **Joinschreib only** : verwendet ein vorhandenes Computer Konto, um den Computer einem schreibgeschützten Domänen Controller hinzuzufügen. Das Computer Konto muss der Liste der zulässigen Kenn Wort Replikations Richtlinien hinzugefügt werden, und das Konto Kennwort muss vor dem Join-Vorgang auf den schreibgeschützten Domänen Controller repliziert werden.

- **Installrufe** : legt die Create (0x2)-und DELETE (0x4)-Flags des **FJoinOptions** -Parameters der **JoinDomainOrWorkgroup** -Methode fest. Weitere Informationen zur **JoinDomainOrWorkgroup** -Methode finden Sie unter [JoinDomainOrWorkgroup-Methode der Win32_ComputerSystem-Klasse](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).
  Weitere Informationen zu diesen Optionen finden Sie unter " [NetJoinDomain](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain)"-Funktion.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: Microsoft.PowerShell.Commands.JoinOptions
Parameter Sets: Domain
Aliases:
Accepted values: AccountCreate, Win9XUpgrade, UnsecuredJoin, PasswordPass, DeferSPNSet, JoinWithNewName, JoinReadOnly, InstallInvoke

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Oupath

Gibt eine Organisationseinheit für das Domänenkonto an. Geben Sie den vollständigen definierten Namen der Organisationseinheit in Anführungszeichen ein. Der Standardwert ist die Standardorganisationseinheit für Computerobjekte in der Domäne.

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: OU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

Startet die Computer neu, die der Domäne oder Arbeitsgruppe hinzugefügt wurden. Ein Neustart ist häufig erforderlich, damit die Änderung wirksam wird.

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Gibt den Namen eines Domänencontrollers an, der den Computer der Domäne hinzufügt. Geben Sie den Namen im Format %%amp;quot;Domänenname\Computername%%amp;quot; ein. Standardmäßig ist kein Domänencontroller angegeben.

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unjoindomaincredential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Entfernen der Computer aus ihren aktuellen Domänen verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. B. %%amp;quot;User01%%amp;quot; oder %%amp;quot;Domain01\User01%%amp;quot;, oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein vom `Get-Credential`-Cmdlet generiertes Objekt. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

Verwenden Sie diesen Parameter, wenn Sie Computer in eine andere Domäne verschieben. Geben Sie ein Benutzerkonto, das über die Berechtigung zum Beitreten zur neuen Domäne verfügt, mit dem **Credential** -Parameter an. Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit einem Remotecomputer verfügt, mit dem **LocalCredential** -Parameter an.

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unsicher

Führt einen unsicheren Beitritt zur angegebenen Domäne durch.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Workgroupname

Gibt den Namen einer Arbeitsgruppe an, der der Computer hinzugefügt wird. Der Standardwert ist %%amp;quot;WORKGROUP%%amp;quot;.

```yaml
Type: System.String
Parameter Sets: Workgroup
Aliases: WGN

Required: True
Position: 0
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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String

Sie können Computernamen und neue Namen über die Pipeline an das `Add-Computer` Cmdlet übergeben.

## AUSGABEN

### Microsoft. PowerShell. Commands. computerchangeingefo

Wenn Sie den **passthru** -Parameter verwenden, wird `Add-Computer` ein **computerchangeinfo** -Objekt zurückgegeben.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

- In Windows PowerShell 2,0 schlägt der **Server** Parameter von `Add-Computer` auch dann fehl, wenn der Server vorhanden ist. In Windows PowerShell 3.0 wurde die Implementierung des **Server** -Parameters geändert, sodass er zuverlässig funktioniert.

## VERWANDTE LINKS

[Checkpoint-Computer](Checkpoint-Computer.md)

[Remove-Computer](Remove-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Rename-Computer](Rename-Computer.md)

[Restore-Computer](Restore-Computer.md)

[Stop-Computer](Stop-Computer.md)

[Test-Connection](Test-Connection.md)
