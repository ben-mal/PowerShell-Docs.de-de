---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmiObject
ms.openlocfilehash: ed759ff3d0dd35cd55f9dac5a2d76e36eac4dc6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215391"
---
# Get-WmiObject

## ZUSAMMENFASSUNG
Ruft Instanzen von Klassen der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) oder Informationen zu den verfügbaren Klassen ab.

## SYNTAX

### Abfrage (Standard)

```
Get-WmiObject [-Class] <String> [[-Property] <String[]>] [-Filter <String>] [-Amended] [-DirectRead]
 [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### list

```
Get-WmiObject [[-Class] <String>] [-Recurse] [-Amended] [-List] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### Wqlquery

```
Get-WmiObject [-Amended] [-DirectRead] -Query <String> [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### class

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### path

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

## DESCRIPTION

Ab PowerShell 3,0 wurde dieses Cmdlet durch ersetzt `Get-CimInstance` .

Mit dem- `Get-WmiObject` Cmdlet werden Instanzen von WMI-Klassen oder Informationen zu den verfügbaren WMI-Klassen abgerufen. Geben Sie einen Remotecomputer mit dem **ComputerName** -Parameter an. Wenn der **List** -Parameter angegeben wird, ruft das Cmdlet Informationen zu den WMI-Klassen ab, die in einem angegebenen Namespace verfügbar sind. Wenn der **Query** -Parameter angegeben ist, wird vom Cmdlet eine WQL (WMI Query Language)-Anweisung ausgeführt.

Das `Get-WmiObject` Cmdlet verwendet Windows PowerShell-Remoting nicht zum Ausführen von Remote Vorgängen.
Sie können den **Computername** -Parameter des `Get-WmiObject` Cmdlets auch dann verwenden, wenn der Computer die Anforderungen für Windows PowerShell-Remoting nicht erfüllt oder nicht für das Remoting in Windows PowerShell konfiguriert ist.

Ab Windows PowerShell 3,0 hat die **__Server** -Eigenschaft des-Objekts, das `Get-WmiObject` zurückgibt, einen **pscomputername** -Alias. Dadurch kann der Quellcomputername leichter in die Ausgabe und in Berichte aufgenommen werden.

## BEISPIELE

### Beispiel 1: erhalten Sie Prozesse auf dem lokalen Computer.

In diesem Beispiel werden die Prozesse auf dem lokalen Computer angezeigt.

```powershell
Get-WmiObject -Class Win32_Process
```

### Beispiel 2: Abrufen von Diensten auf einem Remote Computer

In diesem Beispiel werden die Dienste auf einem Remote Computer abgerufen. Der **Computername** -Parameter gibt die IP-Adresse eines Remote Computers an. Standardmäßig muss das aktuelle Benutzerkonto Mitglied der Gruppe " **Administratoren** " auf dem Remote Computer sein.

```powershell
Get-WmiObject -Class Win32_Service -ComputerName 10.1.4.62
```

### Beispiel 3: WMI-Klassen im Stamm-oder Standard Namespace des lokalen Computers

In diesem Beispiel werden die WMI-Klassen im Stamm-oder Standard Namespace des lokalen Computers abgerufen.

```powershell
Get-WmiObject -Namespace "root/default" -List
```

### Beispiel 4: erhalten eines benannten Dienstanbieter auf mehreren Computern

In diesem Beispiel wird der WinRM-Dienst auf den Computern abgerufen, die durch den Wert des **Computername** -Parameters angegeben werden.

```powershell
Get-WmiObject -Query "select * from win32_service where name='WinRM'" -ComputerName Server01, Server02 |
  Format-List -Property PSComputerName, Name, ExitCode, Name, ProcessID, StartMode, State, Status
```

```Output
PSComputerName : SERVER01
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 844
StartMode      : Auto
State          : Running
Status         : OK

PSComputerName : SERVER02
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 932
StartMode      : Auto
State          : Running
Status         : OK
```

Ein Pipelineoperator (|) sendet die Ausgabe an das Cmdlet `Format-List`, wodurch die **PSComputerName** -Eigenschaft der Standardausgabe hinzugefügt wird. **Pscomputername** ist ein Alias der **__Server** -Eigenschaft der Objekte, die `Get-WmiObject` zurückgibt. Dieser Alias wurde in PowerShell 3,0 eingeführt.

### Beispiel 5: Beendigung eines Dienstanbieter auf einem Remote Computer

In diesem Beispiel wird der WinRM-Dienst auf einem Remote Computer angehalten. `Get-WmiObject` Ruft die Instanz des WinRM-Dienst Objekts auf SERVER01 ab. Anschließend wird die **Stop Service** -Methode der **Win32_Service** WMI-Klasse für dieses Objekt aufgerufen.

```powershell
(Get-WmiObject -Class Win32_Service -Filter "name='WinRM'" -ComputerName Server01).StopService()
```

Dies entspricht der Verwendung des- `Stop-Service` Cmdlets.

### Beispiel 6: das BIOS auf dem lokalen Computer

In diesem Beispiel werden die BIOS-Informationen vom lokalen Computer abgerufen. Der **Property** -Parameter des `Format-List` Cmdlets wird verwendet, um alle Eigenschaften des zurückgegebenen Objekts in einer Liste anzuzeigen. Standardmäßig wird nur die Teilmenge der in der `Types.ps1xml` Konfigurationsdatei definierten Eigenschaften angezeigt.

```powershell
Get-WmiObject -Class Win32_Bios | Format-List -Property *
```

```Output
Status                : OK
Name                  : Phoenix ROM BIOS PLUS Version 1.10 A05
Caption               : Phoenix ROM BIOS PLUS Version 1.10 A05
SMBIOSPresent         : True
__GENUS               : 2
__CLASS               : Win32_BIOS
__SUPERCLASS          : CIM_BIOSElement
__DYNASTY             : CIM_ManagedSystemElement
__RELPATH             : Win32_BIOS.Name="Phoenix ROM BIOS PLUS Version 1.10
__PROPERTY_COUNT      : 27
__DERIVATION          : {CIM_BIOSElement, CIM_SoftwareElement, CIM_LogicalElement,
__SERVER              : Server01
__NAMESPACE           : root\cimv2
__PATH                : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
BiosCharacteristics   : {7, 9, 10, 11...}
BIOSVersion           : {DELL   - 15, Phoenix ROM BIOS PLUS Version 1.10 A05}
BuildNumber           :
CodeSet               :
CurrentLanguage       : en|US|iso8859-1
Description           : Phoenix ROM BIOS PLUS Version 1.10 A05
IdentificationCode    :
InstallableLanguages  : 1
InstallDate           :
LanguageEdition       :
ListOfLanguages       : {en|US|iso8859-1}
Manufacturer          : Dell Inc.
OtherTargetOS         :
PrimaryBIOS           : True
ReleaseDate           : 20101103000000.000000+000
SerialNumber          : 8VDM9P1
SMBIOSBIOSVersion     : A05
SMBIOSMajorVersion    : 2
SMBIOSMinorVersion    : 6
SoftwareElementID     : Phoenix ROM BIOS PLUS Version 1.10 A05
SoftwareElementState  : 3
TargetOperatingSystem : 0
Version               : DELL   - 15
Scope                 : System.Management.ManagementScope
Path                  : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
Options               : System.Management.ObjectGetOptions
ClassPath             : \\JUNE-PC\root\cimv2:Win32_BIOS
Properties            : {BiosCharacteristics, BIOSVersion, BuildNumber, Caption...}
SystemProperties      : {__GENUS, __CLASS, __SUPERCLASS, __DYNASTY...}
Qualifiers            : {dynamic, Locale, provider, UUID}
Site                  :
Container             :
```

### Beispiel 7: erhalten der Dienste auf einem Remote Computer

In diesem Beispiel wird der **Credential** -Parameter des `Get-WmiObject` Cmdlets verwendet, um die Dienste auf einem Remote Computer zu erhalten. Beim Wert des **Credential** -Parameters handelt es sich um einen Benutzerkontonamen. Der Benutzer wird zur Eingabe eines Kennworts aufgefordert.

```powershell
Get-WmiObject Win32_Service -Credential FABRIKAM\administrator -ComputerName Fabrikam
```

> [!NOTE]
> Anmelde Informationen können nicht für den lokalen Computer verwendet werden.

## PARAMETERS

### -Geändert

Ruft einen Wert ab, der angibt, ob die von WMI zurückgegebenen Objekte ergänzte Informationen enthalten sollen, oder legt diesen Wert fest. Normalerweise handelt es sich bei ergänzten Informationen um lokalisierbare Informationen, die an das WMI-Objekt angefügt sind, z. B. Objekt- und Eigenschaftenbeschreibungen.

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

### -AsJob

Führt den Befehl als Hintergrundauftrag aus. Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.

Wenn Sie den **AsJob** -Parameter verwenden, gibt der Befehl ein Objekt zurück, das den Hintergrundauftrag darstellt, und zeigt dann die Eingabeaufforderung an. Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird. Wenn `Get-WmiObject` auf einem Remote Computer verwendet wird, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse von Remote Computern werden automatisch an den lokalen Computer zurückgegeben. Verwenden Sie zum Verwalten des Auftrags die Cmdlets, die die Job-Cmdlets enthalten. Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.

> [!NOTE]
> Um diesen Parameter für Remotecomputer zu verwenden, müssen lokale Computer und Remotecomputer für Remoting konfiguriert werden. Außerdem müssen Sie Windows PowerShell in Windows Vista und höheren Versionen von Windows mit der Option %%amp;quot;Als Administrator ausführen%%amp;quot; starten. Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).

Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).

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
Gültige Werte sind:

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
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autorität

Gibt die Autorität an, die zum Authentifizieren der WMI-Verbindung verwendet werden soll. Sie können die Standard-NTLM- oder Kerberos-Authentifizierung angeben. Legen Sie für die Verwendung von NTLM die Authority-Einstellung auf fest `ntlmdomain:<DomainName>` , wobei `<DomainName>` einen gültigen NTLM-Domänen Namen angibt. Wenn Sie Kerberos verwenden möchten, geben Sie an `kerberos:<DomainName>\<ServerName>` . Sie können die Authority-Einstellung nicht einschließen, wenn Sie eine Verbindung mit dem lokalen Computer herstellen.

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

### -Klasse

Gibt den Namen einer WMI-Klasse an. Wenn dieser Parameter verwendet wird, ruft das Cmdlet Instanzen der WMI-Klasse ab.

```yaml
Type: System.String
Parameter Sets: query, list
Aliases: ClassName

Required: True (query), False (list)
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt den Zielcomputer für den Verwaltungsvorgang an. Geben Sie einen voll qualifizierten Domänen Namen (FQDN), einen NetBIOS-Namen oder eine IP-Adresse ein. Wenn sich der Remotecomputer in einer anderen Domäne als der lokale Computer befindet, ist der vollqualifizierte Domänenname erforderlich.

Die Standardeinstellung ist der lokale Computer. Verwenden Sie zum Angeben des lokalen Computers (z. B. in einer Liste mit Computernamen) %%amp;quot;localhost%%amp;quot;, den Namen des lokalen Computers oder einen Punkt (.).

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting, bei dem die WS-Verwaltung verwendet wird. Sie können den **Computername** -Parameter `Get-WmiObject` auch dann verwenden, wenn der Computer nicht für das Ausführen WS-Management Remote Befehle konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer. Geben Sie einen Benutzernamen ein, z. b. "USER01", "Domain01\User01" oder User@Contoso.com . Oder geben Sie ein **PSCredential** -Objekt ein, z. B. ein Objekt, das vom Cmdlet `Get-Credential` zurückgegeben wird. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert. Anmelde Informationen können nicht für den lokalen Computer verwendet werden.

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

### -Directread

Gibt an, ob der Direktzugriff auf den WMI-Anbieter für die angegebene Klasse angefordert wird, unabhängig von deren Basisklasse oder abgeleiteten Klassen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: query, WQLQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enableallprivileges

Aktiviert alle Berechtigungen des aktuellen Benutzers, bevor der Befehl den WMI-Aufruf ausführt.

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

### -Filter

Gibt eine als Filter zu verwendende **Where** -Klausel an. Verwendet die WQL (WMI Query Language)-Syntax.

> [!IMPORTANT]
> Schließen Sie das **Where** -Schlüsselwort nicht in den Wert des Parameters ein. Die folgenden Befehle geben z. B. nur die logischen Datenträger zurück, deren **DeviceID** %%amp;quot;c:%%amp;quot; entspricht, und die Dienste, deren Name %%amp;quot;WinRM%%amp;quot; entspricht, ohne das **Where** -Schlüsselwort zu verwenden:

`Get-WmiObject Win32_LogicalDisk -filter "DeviceID = 'c:' "`

`Get-WmiObject win32_service -filter "name='WinRM'"`

```yaml
Type: System.String
Parameter Sets: query
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

- 0: Default. Liest die lokale Registrierung für die Standard Ebene des Identitäts Wechsels. Der Standardwert **ist in der Regel auf Identitäts** Wechsel festgelegt.
- 1: Anonymous. Verbirgt die Anmeldeinformationen des Aufrufers.
- 2: Identify. Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers abzufragen.
- 3: Impersonate. Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers zu verwenden.
- 4: Delegate. Ermöglicht es Objekten, anderen Objekten die Verwendung der Anmeldeinformationen des Aufrufers zu gestatten.

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -List

Ruft die Namen der WMI-Klassen im WMI-Repositorynamespace, der im **Namespace** -Parameter angegeben ist, ab.

Wenn Sie den **List** -Parameter, aber nicht den **Namespace** -Parameter angeben, `Get-WmiObject` verwendet standardmäßig den **root\cimv2** -Namespace. Dieses Cmdlet verwendet nicht den **standardmäßigen Namespace** -Registrierungs Eintrag im `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` Registrierungsschlüssel, um den Standard Namespace zu ermitteln.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Gebiets Schema

Gibt das bevorzugte Gebietsschema für WMI-Objekte an.
Geben Sie einen Wert im Format %%amp;quot;MS_\<LCID\>%%amp;quot; an.

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

### -Namespace

Bei Verwendung mit dem **Class** -Parameter gibt der **Namespace** -Parameter den WMI-Repository-Namespace an, in dem sich die angegebene WMI-Klasse befindet. Bei Verwendung mit dem **List** -Parameter gibt er den Namespace an, aus dem die WMI-Klasseninformationen abgerufen werden sollen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Eigenschaft

Gibt die WMI-Klasseneigenschaften an, von denen dieses Cmdlet Informationen abruft. Geben Sie die Eigenschaftennamen an.

```yaml
Type: System.String[]
Parameter Sets: query
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

Führt die angegebene WMI Query Language (WQL)-Anweisung aus. Von diesem Parameter werden keine Ereignisabfragen unterstützt.

```yaml
Type: System.String
Parameter Sets: WQLQuery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recurse

Durchsucht den aktuellen Namespace und alle anderen Namespaces nach dem im **Class** -Parameter angegebenen Klassennamen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Gibt die maximale Anzahl der WMI-Vorgänge an, die gleichzeitig ausgeführt werden können. Dieser Parameter ist nur gültig, wenn der **AsJob** -Parameter im Befehl verwendet wird.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an übergeben werden `Get-WmiObject` .

## AUSGABEN

### Psobject oder System. Management. Automation. remotingjob

Wenn Sie den **AsJob** -Parameter verwenden, wird vom Cmdlet ein Auftragsobjekt zurückgegeben. Andernfalls hängt das Objekt, das `Get-WmiObject` zurückgibt, von dem Wert des **Class** -Parameters ab.

## HINWEISE

Für den Zugriff auf WMI-Informationen auf einem Remotecomputer muss das Cmdlet unter einem Konto ausgeführt werden, das auf dem Remotecomputer Mitglied der lokalen Administratorengruppe ist. Die Standardzugriffssteuerung für den WMI-Namespace des Remote-Repositorys kann auch so geändert werden, dass anderen Konten Zugriffsrechte gewährt werden.

Standardmäßig werden nur einige Eigenschaften einer WMI-Klasse angezeigt. Welche Eigenschaften für die einzelnen WMI-Klassen angezeigt werden, ist in der Konfigurationsdatei %%amp;quot;Types.ps1xml%%amp;quot; festgelegt. Um alle Eigenschaften eines WMI-Objekts zu erhalten, verwenden Sie die `Get-Member` `Format-List` Cmdlets oder.

## VERWANDTE LINKS

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Remove-WmiObject](Remove-WmiObject.md)

[Set-WmiInstance](Set-WmiInstance.md)

[Get-WSManInstance](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[Invoke-WSManAction](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[New-WSManInstance](../Microsoft.WsMan.Management/New-WSManInstance.md)

[Remove-WSManInstance](../Microsoft.WsMan.Management/Remove-WSManInstance.md)
