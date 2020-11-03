---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WmiMethod
ms.openlocfilehash: e9743488e86429e5cc3252162e51268a7978b79d
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "93217991"
---
# Invoke-WmiMethod

## ZUSAMMENFASSUNG
Ruft WMI-Methoden auf.

## SYNTAX

### Class (Standard)

```
Invoke-WmiMethod [-Class] <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Objekt

```
Invoke-WmiMethod -InputObject <ManagementObject> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### path

```
Invoke-WmiMethod -Path <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Wqlquery

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Abfrage

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### list

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Invoke-WmiMethod` Cmdlet ruft die Methoden von Windows-Verwaltungsinstrumentation (WMI)-Objekten auf.

New Common Information Model (CIM)-Cmdlets, die in Windows PowerShell 3,0 eingeführt wurden, führen dieselben Aufgaben wie die WMI-Cmdlets aus. Die CIM-Cmdlets entsprechen den WS-Management (WSMAN)-Standards und dem CIM-Standard, mit dem die Cmdlets die gleichen Techniken zum Verwalten von Windows-Computern und von Computern mit anderen Betriebssystemen verwenden können. Verwenden Sie anstelle von die Verwendung von " `Invoke-WmiMethod` [aufrufen-cimmethod](../cimcmdlets/invoke-cimmethod.md)".

## BEISPIELE

### Beispiel 1: Auflisten der erforderlichen Reihenfolge von WMI-Objekten

```powershell
([wmiclass]'Win32_Volume').GetMethodParameters('Format')
```

```Output
__GENUS           : 2
__CLASS           : __PARAMETERS
__SUPERCLASS      :
__DYNASTY         : __PARAMETERS
__RELPATH         :
__PROPERTY_COUNT  : 6
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
ClusterSize       : 0
EnableCompression : False
FileSystem        : NTFS
Label             :
QuickFormat       : False
Version           : 0
PSComputerName    :
```

In diesem Befehl ist die erforderliche Reihenfolge der Objekte aufgeführt. Das Aufrufen von WMI in PowerShell 3.0 unterscheidet sich von anderen Methoden. Darüber hinaus müssen Objektwerte in einer bestimmten Reihenfolge eingegeben werden.

### Beispiel 2: Starten einer Instanz einer Anwendung

```powershell
([Wmiclass]'Win32_Process').GetMethodParameters('Create')
```

```Output
__GENUS                   : 2
__CLASS                   : __PARAMETERS
__SUPERCLASS              :
__DYNASTY                 : __PARAMETERS
__RELPATH                 :
__PROPERTY_COUNT          : 3
__DERIVATION              : {}
__SERVER                  :
__NAMESPACE               :
__PATH                    :
CommandLine               :
CurrentDirectory          :
ProcessStartupInformation :
PSComputerName            :
```

```powershell
Invoke-WmiMethod -Path win32_process -Name create -ArgumentList notepad.exe
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 2
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ProcessId        : 11312
ReturnValue      : 0
PSComputerName   :
```

Mit diesem Befehl wird eine Instanz von Editor gestartet, indem die- `Create` Methode der **Win32_Process** -Klasse aufgerufen wird.

Die **ReturnValue** -Eigenschaft wird mit 0 aufgefüllt, und die **ProcessID-** Eigenschaft wird mit einer ganzen Zahl (der nächsten Prozess-ID-Nummer) aufgefüllt, wenn der Befehl abgeschlossen ist.

### Beispiel 3: Umbenennen einer Datei

```powershell
Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\scripts\test.txt'" -Name Rename -ArgumentList "C:\scripts\test_bu.txt"
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ReturnValue      : 0
```

Mit diesem Befehl wird eine Datei umbenannt. Er verwendet den **path** -Parameter, um auf eine Instanz der **CIM_Datafile** -Klasse zu verweisen. Anschließend wird die Rename-Methode auf die betreffende Instanz angewendet.

Die **ReturnValue** -Eigenschaft wird mit 0 aufgefüllt, wenn der Befehl abgeschlossen ist.

### Beispiel 4: Übergeben eines Arrays von Werten mithilfe von `-ArgumentList`

Ein Beispiel mit einem Array von-Objekten, `$binSD` auf das ein- `$null` Wert folgt.

```powershell
$acl = get-acl test.txt
$binSD = $acl.GetSecurityDescriptorBinaryForm()
Invoke-WmiMethod -class Win32_SecurityDescriptorHelper -Name BinarySDToSDDL -ArgumentList $binSD, $null
```

## PARAMETERS

### -Argumentlist

Gibt die Parameter an, die an die aufgerufene Methode übergeben werden sollen. Der Wert dieses Parameters muss ein Array von-Objekten sein, und Sie müssen in der Reihenfolge angezeigt werden, die von der aufgerufenen Methode benötigt wird. Für das `Invoke-CimCommand` Cmdlet gelten diese Einschränkungen nicht.

Um die Reihenfolge zu bestimmen, in der diese Objekte aufgeführt werden sollen, führen Sie die- `GetMethodParameters()` Methode für die WMI-Klasse aus, wie in Beispiel 1 am Ende dieses Themas veranschaulicht.

> [!IMPORTANT]
> Handelt es sich beim ersten Wert um ein Array, das mehrere Elemente enthält, ist der zweite Wert $null erforderlich. Andernfalls wird vom Befehl ein Fehler generiert, z. B. %%amp;quot;Das Objekt des Typs "System.Byte" kann nicht in Typ "System.Array" umgewandelt werden.%%amp;quot; Siehe Beispiel 4 oben.

```yaml
Type: System.Object[]
Parameter Sets: class, object, path
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt. Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.

Wenn Sie den **AsJob** -Parameter verwenden, gibt der Befehl ein Objekt zurück, das den Hintergrundauftrag darstellt, und zeigt dann die Eingabeaufforderung an. Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird. Wenn für `Invoke-WmiMethod` einen Remote Computer verwendet wird, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse von Remote Computern werden automatisch an den lokalen Computer zurückgegeben. Verwenden Sie zum Verwalten des Auftrags die Cmdlets, die das Substantiv %%amp;quot;Job%%amp;quot; enthalten (die Job-Cmdlets). Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.

Um diesen Parameter für Remotecomputer zu verwenden, müssen lokale Computer und Remotecomputer für Remoting konfiguriert werden. Außerdem müssen Sie Windows PowerShell starten, indem Sie die Option als Administrator ausführen in Windows Vista und höheren Versionen von Windows verwenden. Weitere Informationen finden Sie unter %%amp;quot;about_Remote_Requirements%%amp;quot;.

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

Gibt die für die WMI-Verbindung zu verwendende Authentifizierungsebene an. Zulässige Werte für diesen Parameter:

- -1: Unchanged
- 0: Default
- 1: None (Es wird keine Authentifizierung ausgeführt.)
- 2: Connect (Die Authentifizierung wird nur ausgeführt, wenn der Client eine Beziehung mit der Anwendung herstellt.)
- 3: Call (Die Authentifizierung wird nur zu Beginn eines Aufrufs ausgeführt, wenn die Anwendung die Anforderung empfängt.)
- 4: Packet (Die Authentifizierung wird für alle Daten ausgeführt, die vom Client empfangen werden.)
- 5: packetintegrity (alle Daten, die zwischen dem Client und der Anwendung übertragen werden, werden authentifiziert und überprüft.)
- 6: PacketPrivacy (Die Eigenschaften der anderen Authentifizierungsebenen werden verwendet, und alle Daten werden verschlüsselt.)

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

Gibt die Autorität an, die zum Authentifizieren der WMI-Verbindung verwendet werden soll. Sie können die standardmäßige NTLM (Windows NT LAN Manager)-oder Kerberos-Authentifizierung angeben. Legen Sie für die Verwendung von NTLM die Authority-Einstellung auf %%amp;quot;ntlmdomain:\<DomainName\>%%amp;quot; fest, wobei \<DomainName\> einen gültigen NTLM-Domänennamen darstellt. Geben Sie für die Verwendung von Kerberos %%amp;quot;kerberos:\<DomainName\ServerName\>%%amp;quot; an. Sie können die Authority-Einstellung nicht einschließen, wenn Sie eine Verbindung mit dem lokalen Computer herstellen.

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

Gibt die WMI-Klasse an, die eine aufzurufende statische Methode enthält.

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

Gibt die Computer, auf denen dieses Cmdlet den Befehl ausführt, als Zeichen folgen Array an. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer ein. Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting. Sie können den **ComputerName** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.

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

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer. Geben Sie einen Benutzernamen ein, `User01` z `Domain01\User01` . b `User@Contoso.com` ., oder. Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein Objekt, das vom Get-Credential-Cmdlet zurückgegeben wird. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

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

Gibt an, dass dieses Cmdlet alle Berechtigungen des aktuellen Benutzers aktiviert, bevor der Befehl den WMI-Aufrufe ausführt.

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

Gibt die zu verwendende Identitätswechselebene an. Zulässige Werte für diesen Parameter:

- 0: Default (Liest die lokale Registrierung für die Standard-Identitätswechselebene, die normalerweise auf %%amp;quot;3: Impersonate%%amp;quot; festgelegt ist.)
- 1: Anonymous (Verbirgt die Anmeldeinformationen des Aufrufers.)
- 2: Identify (Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers abzufragen.)
- 3: Impersonate (Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers zu verwenden.)
- 4: Delegate (Ermöglicht es Objekten, anderen Objekten die Verwendung der Anmeldeinformationen des Aufrufers zu gestatten.)

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

Gibt ein **ManagementObject** -Objekt an, das als Eingabe verwendet werden soll. Wenn dieser Parameter verwendet wird, werden alle anderen Parameter Außer dem **Flag** und den **Argument** Parametern ignoriert.

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

Gibt das bevorzugte Gebietsschema für WMI-Objekte an. Geben Sie den Wert des **locale** -Parameters als Array im `MS_<LCID>` Format in der bevorzugten Reihenfolge an.

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

### -Name

Gibt den Namen der aufzurufenden Methode an. Dieser Parameter ist erforderlich und kann nicht NULL oder leer sein.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

Bei Verwendung mit dem **Class** -Parameter gibt dieser Parameter den WMI-Repository-Namespace an, in dem sich die WMI-Klasse oder das referenzierte Objekt befindet.

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

Gibt den WMI-Objektpfad einer WMI-Klasse oder den WMI-Objektpfad einer Instanz einer WMI-Klasse an. Die Klasse oder die Instanz, die Sie angeben, muss die im **Name** -Parameter angegebene Methode enthalten.

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

Gibt einen Drosselungs Wert für die Anzahl der WMI-Vorgänge an, die gleichzeitig ausgeführt werden können.
Dieser Parameter wird in Verbindung mit dem **AsJob** -Parameter verwendet. Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

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

Dieses Cmdlet nimmt keine Eingabe an.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

## VERWANDTE LINKS

[Get-WSManInstance](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[Invoke-WSManAction](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[New-WSManInstance](../Microsoft.WsMan.Management/New-WSManInstance.md)

[Remove-WSManInstance](../Microsoft.WsMan.Management/Remove-WSManInstance.md)

[Get-WmiObject](Get-WmiObject.md)

[Remove-WmiObject](Remove-WmiObject.md)

[Set-WmiInstance](Set-WmiInstance.md)
