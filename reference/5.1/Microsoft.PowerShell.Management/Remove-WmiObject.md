---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmiObject
ms.openlocfilehash: 287eb02e7de2f4182e0ecfd7f6b6a7cafb66969e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214543"
---
# Remove-WmiObject

## ZUSAMMENFASSUNG
Löscht eine Instanz einer vorhandenen Klasse der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI).

## SYNTAX

### Class (Standard)

```
Remove-WmiObject [-Class] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Objekt

```
Remove-WmiObject -InputObject <ManagementObject> [-AsJob] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### path

```
Remove-WmiObject -Path <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Wqlquery

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Abfrage

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### list

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Das **Remove-WMIObject-** Cmdlet löscht eine Instanz einer vorhandenen WMI-Klasse (Windows-Verwaltungsinstrumentation).

## BEISPIELE

### Beispiel 1: Schließen aller Instanzen eines Win32-Prozesses

```
PS C:\> notepad
PS C:\> $np = Get-WmiObject -Query "select * from win32_process where name='notepad.exe'"
PS C:\> $np | Remove-WmiObject
```

In diesem Beispiel werden alle Instanzen von Notepad.exe geschlossen.

Der erste Befehl startet eine Instanz von Editor.

Der zweite Befehl verwendet das Cmdlet "Get-WmiObject", um die Instanzen der Win32_Process abzurufen, die Notepad.exe entsprechen, und speichert Sie dann in der $NP Variable.

Der dritte Befehl übergibt das Objekt in der $NP-Variablen an **Remove-WMIObject** , das alle Instanzen von Notepad.exe löscht.

### Beispiel 2: Löschen eines Ordners

```
PS C:\> $a = Get-WMIObject -Query "Select * From Win32_Directory Where Name ='C:\\Test'"
PS C:\> $a | Remove-WMIObject
```

Mit diesem Befehl wird der Ordner "c:\Test" gelöscht.

Der erste Befehl verwendet **Get-WMIObject** , um den Ordner "c:\Test" abzufragen, und speichert dann das Objekt in der $a Variable.

Mit dem zweiten Befehl wird die $a Variable an **Remove-WMIObject** übergeben, wodurch der Ordner gelöscht wird.

## PARAMETERS

### -AsJob
Gibt an, dass dieses Cmdlet als Hintergrund Auftrag ausgeführt wird.
Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.

Mit den neuen in Windows PowerShell 3.0 eingeführten CIM-Cmdlets werden die gleichen Aufgaben wie mit WMI-Cmdlets ausgeführt.
Die CIM-Cmdlets entsprechen den WS-Management (WSMAN)-Standards und dem CIM-Standard (Common Information Model), mit dem die Cmdlets dieselben Verfahren zum Verwalten von Computern verwenden können, auf denen das Windows-Betriebssystem ausgeführt wird, und auf denen andere Betriebssysteme ausgeführt werden.
Anstelle von **Remove-WmiObject** können Sie das Cmdlet Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 verwenden.

Wenn Sie den *AsJob* -Parameter verwenden, gibt der Befehl ein Objekt zurück, das den Hintergrundauftrag darstellt, und zeigt dann die Eingabeaufforderung an.
Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird.
Wenn **Remove-WmiObject** für einen Remotecomputer verwendet wird, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben.
Verwenden Sie zum Verwalten des Auftrags die Cmdlets, die das **Auftrags** Substantiv (die **Job** -Cmdlets) enthalten.
Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.

Um diesen Parameter für Remote Computer zu verwenden, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein.
Starten Sie Windows PowerShell mit der Option als Administrator ausführen.
Weitere Informationen finden Sie unter %%amp;quot;about_Remote_Requirements%%amp;quot;.

Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter about_Jobs und about_Remote_Jobs.

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

### -Authentifizierung
Gibt die für die WMI-Verbindung zu verwendende Authentifizierungsebene an.
Zulässige Werte für diesen Parameter:

- -1: unverändert.
- 0: Default.
- 1: keine.
Es wird keine Authentifizierung durchgeführt.
- 2: verbinden.
Die Authentifizierung wird nur ausgeführt, wenn der Client eine Beziehung mit der Anwendung herstellt.
- 3: wird aufgerufen.
Die Authentifizierung wird nur zu Beginn jedes Aufrufes ausgeführt, wenn die Anwendung die Anforderung empfängt.
- 4: Paket.
Die Authentifizierung wird für alle Daten ausgeführt, die vom Client empfangen werden.
- 5: packetintegrity.
Alle Daten, die zwischen dem Client und der Anwendung übertragen werden, werden authentifiziert und überprüft.
- 6: PacketPrivacy.
Die Eigenschaften der anderen Authentifizierungs Ebenen werden verwendet, und alle Daten werden verschlüsselt.

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autorität
Gibt die Autorität an, die zum Authentifizieren der WMI-Verbindung verwendet werden soll.
Sie können die Standard-NTLM- oder Kerberos-Authentifizierung angeben.
Legen Sie für die Verwendung von NTLM die Authority-Einstellung auf %%amp;quot;ntlmdomain:\<DomainName\>%%amp;quot; fest, wobei \<DomainName\> einen gültigen NTLM-Domänennamen darstellt.
Wenn Sie Kerberos verwenden möchten, geben Sie Kerberos: an \<DomainName\> \\ \<ServerName\> .
Sie können die Authority-Einstellung nicht einschließen, wenn Sie eine Verbindung mit dem lokalen Computer herstellen.

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Klasse
Gibt den Namen einer WMI-Klasse an, die von diesem Cmdlet gelöscht wird.

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Gibt den Namen des Computers an, auf dem dieses Cmdlet ausgeführt wird.
Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer ein.
Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.
Sie können den *ComputerName* -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.
Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. das vom Cmdlet Get-Credential generierte.
Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enableallprivileges
Gibt an, dass dieses Cmdlet alle Berechtigungen des aktuellen Benutzers vor dem Befehl aktiviert, den der WMI aufruft.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identitätswechsel
Gibt die zu verwendende Identitätswechselebene an.
Zulässige Werte für diesen Parameter:

- 0: Default.
Liest die lokale Registrierung für die standardmäßige Identitätswechsel Ebene, die normalerweise auf 3 festgelegt ist: Identität annehmen.
- 1: Anonymous.
Verbirgt die Anmeldeinformationen des Aufrufers.
- 2: Identify.
Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers abzufragen.
- 3: Impersonate.
Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers zu verwenden.
- 4: Delegate.
Ermöglicht es Objekten, anderen Objekten die Verwendung der Anmeldeinformationen des Aufrufers zu gestatten.

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Gibt ein **ManagementObject** -Objekt an, das als Eingabe verwendet werden soll.
Wenn dieser Parameter verwendet wird, werden alle anderen Parameter ignoriert.

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Gebiets Schema
Gibt das bevorzugte Gebietsschema für WMI-Objekte an.
Der *locale* -Parameter wird als Array im MS_ \<LCID\> Format in der bevorzugten Reihenfolge angegeben.

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace
Gibt den WMI-Repository-Namespace an, in dem sich die referenzierte WMI-Klasse befindet, wenn Sie mit dem *Class* -Parameter verwendet wird.

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Gibt den WMI-Objektpfad einer WMI-Klasse oder den WMI-Objektpfad einer Instanz einer zu löschenden WMI-Klasse an.

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.
Dieser Parameter wird in Verbindung mit dem *AsJob* -Parameter verwendet.
Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

```yaml
Type: System.Int32
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

### System. Management. ManagementObject
Sie können ein Verwaltungs Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine, System. Management. Automation. remotingjob
Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den *AsJob* -Parameter angeben.
Andernfalls wird keine Ausgabe generiert.

## HINWEISE

## VERWANDTE LINKS

[Get-WmiObject](Get-WmiObject.md)

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Set-WmiInstance](Set-WmiInstance.md)
