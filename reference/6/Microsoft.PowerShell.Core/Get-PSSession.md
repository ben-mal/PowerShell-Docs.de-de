---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSession
ms.openlocfilehash: cee14ce93af87d33b4d9d9665c3ef5aaa2aec1d5
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387446"
---
# Get-PSSession

## ZUSAMMENFASSUNG
Ruft die PowerShell-Sitzungen auf lokalen Computern und Remote Computern ab.

## SYNTAX

### Name (Standard)

```
Get-PSSession [-Name <String[]>] [<CommonParameters>]
```

### Computerinstanceid

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### Computername

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### Connectionuriinstanceid

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-ThrottleLimit <Int32>] [-State <SessionFilterState>]
 [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### ConnectionUri

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-ThrottleLimit <Int32>] [-State <SessionFilterState>]
 [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### VMName

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -VMName <String[]> [<CommonParameters>]
```

### ContainerId

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### Containeridinstanceid

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### VMId

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -VMId <Guid[]> [<CommonParameters>]
```

### Vmidinstanceid

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -VMId <Guid[]> [<CommonParameters>]
```

### Vmnameingestanceid

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -VMName <String[]> [<CommonParameters>]
```

### InstanceId

```
Get-PSSession [-InstanceId <Guid[]>] [<CommonParameters>]
```

### Id

```
Get-PSSession [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

`Get-PSSession`Mit dem-Cmdlet werden die vom Benutzer verwalteten PowerShell-Sitzungen ( **pssessions** ) auf lokalen Computern und Remote Computern abgerufen.

Ab Windows PowerShell 3,0 werden Sitzungen auf den Computern am Remote Ende jeder Verbindung gespeichert. Sie können die Parameter **Computername** oder **ConnectionUri** von verwenden, `Get-PSSession` um die Sitzungen zu erhalten, die eine Verbindung mit dem lokalen Computer oder Remote Computern herstellen, auch wenn Sie nicht in der aktuellen Sitzung erstellt wurden.

Ohne Parameter ruft `Get-PSSession` alle Sitzungen ab, die in der aktuellen Sitzung erstellt wurden.

Verwenden Sie die Filter Parameter, einschließlich **Name** , **ID** , **InstanceId** , **State** , **ApplicationName** und **ConfigurationName** , um eine Auswahl aus den zurückgegebenen Sitzungen zu treffen `Get-PSSession` .

Verwenden Sie die verbleibenden Parameter, um die temporäre Verbindung zu konfigurieren, in der der Befehl ausgeführt wird, `Get-PSSession` Wenn Sie die Parameter **Computername** oder **ConnectionUri** verwenden.

Hinweis: Ruft in Windows PowerShell 2,0 ohne Parameter `Get-PSSession` alle Sitzungen ab, die in der aktuellen Sitzung erstellt wurden. Der **Computername** -Parameter ruft die Sitzungen ab, die in der aktuellen Sitzung erstellt wurden, und eine Verbindung mit dem angegebenen Computer.

Weitere Informationen zu PowerShell-Sitzungen finden Sie unter [about_PSSessions](about/about_PSSessions.md).

## BEISPIELE

### Beispiel 1: Get-Sitzungen, die in der aktuellen Sitzung erstellt wurden

```powershell
Get-PSSession
```

Dieser Befehl ruft alle **pssessions** ab, die in der aktuellen Sitzung erstellt wurden. Er ruft keine **pssessions** ab, die in anderen Sitzungen oder auf anderen Computern erstellt wurden, auch wenn Sie eine Verbindung mit diesem Computer herstellen.

### Beispiel 2: Get-Sitzungen, die mit dem lokalen Computer verbunden sind

```powershell
Get-PSSession -ComputerName "localhost"
```

Dieser Befehl ruft die **pssessions** ab, die mit dem lokalen Computer verbunden sind. Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.

Der Befehl gibt alle Sitzungen auf dem lokalen Computer zurück, auch wenn sie in anderen Sitzungen oder auf anderen Computern erstellt wurden.

### Beispiel 3: erhalten von Sitzungen, die mit einem Computer verbunden sind

```powershell
Get-PSSession -ComputerName "Server02"
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  2 Session3        Server02       Disconnected  ITTasks                       Busy
  1 ScheduledJobs   Server02       Opened        Microsoft.PowerShell     Available
  3 Test            Server02       Disconnected  Microsoft.PowerShell          Busy
```

Dieser Befehl ruft die **pssessions** ab, die mit dem Server02-Computer verbunden sind.

Der Befehl gibt alle Sitzungen auf dem Computer „Server02“ zurück, auch wenn sie in anderen Sitzungen oder auf anderen Computern erstellt wurden.

Die Ausgabe zeigt, dass zwei Sitzungen den Status „Getrennt“ und die Verfügbarkeit „Ausgelastet“ haben. Sie wurden in verschiedenen Sitzungen erstellt und werden derzeit verwendet. Die scheduledjobs-Sitzung, die geöffnet und verfügbar ist, wurde in der aktuellen Sitzung erstellt.

### Beispiel 4: Speichern der Ergebnisse dieses Befehls

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
$s1, $s2, $s3 = Get-PSSession
```

Dieses Beispiel zeigt, wie die Ergebnisse eines `Get-PSSession` Befehls in mehreren Variablen gespeichert werden.

Der erste Befehl verwendet das `New-PSSession` Cmdlet, um **pssessions** auf drei Remote Computern zu erstellen.

Der zweite Befehl verwendet ein `Get-PSSession` Cmdlet, um die drei **pssessions** zu erhalten. Anschließend werden alle **pssessions** in einer separaten Variablen gespeichert.

Wenn PowerShell ein Array von Objekten einem Array von Variablen zuweist, wird das erste Objekt der ersten Variablen, das zweite Objekt der zweiten Variablen usw. zugewiesen. Wenn es mehr Objekte als Variablen gibt, werden alle verbleibenden Objekte der letzten Variablen im Array zugewiesen. Wenn es mehr Variablen als Objekte gibt, werden die zusätzlichen Variablen nicht genutzt.

### Beispiel 5: Löschen einer Sitzung mit einer Instanz-ID

```powershell
Get-PSSession | Format-Table -Property ComputerName, InstanceID
$s = Get-PSSession -InstanceID a786be29-a6bb-40da-80fb-782c67f7db0f
Remove-PSSession -Session $s
```

Dieses Beispiel zeigt, wie Sie eine **PSSession** mit der Instanz-ID erhalten und dann die **PSSession** löschen.

Der erste Befehl ruft alle **pssessions** ab, die in der aktuellen Sitzung erstellt wurden. Die **pssessions** werden an das Format-Table-Cmdlet gesendet, das die **Computername** -und **InstanceId-** Eigenschaften der einzelnen **PSSession** anzeigt.

Der zweite Befehl verwendet das `Get-PSSession` Cmdlet, um eine bestimmte **PSSession** abzurufen und in der Variablen zu speichern `$s` . Der Befehl verwendet den **InstanceId-** Parameter, um die **PSSession** zu identifizieren.

Der dritte Befehl verwendet das Cmdlet "Remove-PSSession", um die **PSSession** in der Variablen zu löschen `$s` .

### Beispiel 6: erhalten einer Sitzung mit einem bestimmten Namen

Mit den Befehlen in diesem Beispiel finden Sie eine Sitzung, die über ein bestimmtes Namensformat verfügt und eine bestimmte Sitzungskonfiguration verwendet, und stellen dann eine Verbindung zur Sitzung her. Sie können einen Befehl wie diesen dazu verwenden, eine Sitzung zu suchen, in der ein Kollege eine Aufgabe gestartet hat, und eine Verbindung herstellen, um die Aufgabe abzuschließen.

```powershell
Get-PSSession -ComputerName Server02, Server12 -Name BackupJob* -ConfigurationName ITTasks -SessionOption @{OperationTimeout=240000}
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  3 BackupJob04     Server02        Disconnected        ITTasks                  None
```

```powershell
$s = Get-PSSession -ComputerName Server02 -Name BackupJob04 -ConfigurationName ITTasks | Connect-PSSession
$s
```

```Output
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 5 BackupJob04     Server02        Opened        ITTasks                  Available
```

Der erste Befehl ruft die Sitzungen auf den Remote Computern Server02 und Server12 ab, deren Namen mit backupjob beginnen und die ittasks-Sitzungs Konfiguration verwenden. Der Befehl verwendet den **Name** -Parameter, um das Namensmuster anzugeben, und den **ConfigurationName** -Parameter, um die Sitzungs Konfiguration anzugeben. Der Wert des **SessionOption** -Parameters ist eine Hashtabelle, die den **OperationTimeout** -Wert auf 240000 Millisekunden (4 Minuten) festlegt. Diese Einstellung gibt dem Befehl mehr Zeit für den Abschluss. Der **ConfigurationName** -Parameter und der **sessionoption** -Parameter werden verwendet, um die temporären Sitzungen zu konfigurieren, in denen das `Get-PSSession` Cmdlet auf jedem Computer ausgeführt wird. Die Ausgabe zeigt, dass der Befehl die BackupJob04-Sitzung zurückgibt. Die Sitzung wird getrennt, und die **Verfügbarkeit** ist None. Dies bedeutet, dass Sie nicht verwendet wird.

Der zweite Befehl verwendet das `Get-PSSession` Cmdlet, um die BackupJob04-Sitzung zu erhalten, und das Cmdlet "Connect-PSSession", um eine Verbindung mit der Sitzung herzustellen. Der Befehl speichert die Sitzung in der $s-Variablen.

Der dritte Befehl ruft die Sitzung in der Variablen „$s“ ab. Die Ausgabe zeigt, dass der `Connect-PSSession` Befehl erfolgreich war. Die Sitzung hat den Status **Opened** und steht zur Verwendung zur Verfügung.

### Beispiel 7: eine Sitzung mithilfe ihrer ID erhalten

```powershell
Get-PSSession -Id 2
```

Mit diesem Befehl wird die **PSSession** mit der ID 2 abgerufen. Da der Wert der **ID** -Eigenschaft nur in der aktuellen Sitzung eindeutig ist, ist der **ID** -Parameter nur für lokale Befehle gültig.

## PARAMETERS

### -Zuweisung Richtung

Gibt an, dass dieses Cmdlet die Umleitung dieser Verbindung an eine Alternative Uniform Resource Identifier (URI) zulässt. Standardmäßig leitet PowerShell Verbindungen nicht um.

Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem **ConnectionUri** -Parameter auszuführen.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Gibt den Namen einer Anwendung an. Dieses Cmdlet stellt nur Verbindungen mit Sitzungen her, die die angegebene Anwendung verwenden.

Geben Sie das Anwendungsnamensegment des Verbindungs-URI ein. Im folgenden Verbindungs-URI lautet der Anwendungsname beispielsweise WSMAN: `http://localhost:5985/WSMAN` . Der Anwendungsname einer Sitzung wird in der **Runspace.ConnectionInfo.AppName** -Eigenschaft der Sitzung gespeichert.

Der Wert dieses Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern. Er ändert nicht die von der Sitzung verwendete Anwendung.

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Authentifizierung

Gibt den Mechanismus an, der zum Authentifizieren der Anmelde Informationen für die Sitzung verwendet wird, in der der Befehl ausgeführt wird `Get-PSSession` .

Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem Parameter **Computername** oder **ConnectionUri** auszuführen.

Zulässige Werte für diesen Parameter:

- Standard
- Standard
- CredSSP
- Digest
- Kerberos
- Aushandeln
- NegotiateWithImplicitCredential.

Der Standardwert ist Default.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

Vorsicht: die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certifiupethumschlag-Print

Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Erstellen der Sitzung verfügt, in der der Befehl ausgeführt wird `Get-PSSession` . Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.

Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem Parameter **Computername** oder **ConnectionUri** auszuführen.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.

Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie im PowerShell-Laufwerk "CERT:" einen Get-Item oder Get-ChildItem Befehl.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt ein Array von Namen von Computern an. Ruft die Sitzungen ab, die eine Verbindung zu den angegebenen Computern herstellen.
Platzhalterzeichen sind nicht zulässig. Es gibt keinen Standardwert.

Ab Windows PowerShell 3,0 werden **PSSession** -Objekte auf den Computern am Remote Ende jeder Verbindung gespeichert. Um die Sitzungen auf den angegebenen Computern zu erhalten, erstellt PowerShell eine temporäre Verbindung mit den einzelnen Computern und führt einen `Get-PSSession` Befehl aus.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen vollqualifizierten Domänennamen mindestens eines Computers ein. Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.

Hinweis: dieser Parameter ruft nur Sitzungen von Computern ab, auf denen Windows PowerShell 3,0 oder eine höhere Version von PowerShell ausgeführt wird. In früheren Versionen werden keine Sitzungen gespeichert.

```yaml
Type: System.String[]
Parameter Sets: ComputerInstanceId, ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationName

Gibt den Namen einer Konfiguration an. Dieses Cmdlet bezieht sich nur auf Sitzungen, die die angegebene Sitzungs Konfiguration verwenden.

Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein. Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/powershell` . Der Konfigurationsname einer Sitzung befindet sich in der **ConfigurationName** -Eigenschaft der Sitzung.

Der Wert dieses Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern. Er ändert nicht die von der Sitzung verwendete Sitzungskonfiguration.

Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri, VMNameInstanceId, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Gibt einen URI an, der den Verbindungs Endpunkt für die temporäre Sitzung definiert, in der der Befehl ausgeführt wird `Get-PSSession` . Der URI muss vollqualifiziert sein.

Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem **ConnectionUri** -Parameter auszuführen.

Das Format dieser Zeichenfolge lautet:

`<Transport>://<ComputerName>:<Port\>/<ApplicationName>`

Standardwert: `http://localhost:5985/WSMAN`.

Wenn Sie keinen **ConnectionUri** angeben, können Sie die **ConnectionUri** -Werte mit den Parametern " **US** ", " **Computername** ", " **Port** " und " **ApplicationName** " angeben. Gültige Werte für das Transport-Segment des URI sind „HTTP“ und „HTTPS“. Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS. Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.

Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

Dieser Parameter ruft nur Sitzungen von Computern ab, auf denen Windows PowerShell 3,0 oder höhere Versionen von Windows PowerShell ausgeführt wird. In früheren Versionen werden keine Sitzungen gespeichert.

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUriInstanceId, ConnectionUri
Aliases: URI, CU

Required: True
Position: 0
Default value: Http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Containerid

Gibt ein Array von IDs von Containern an. Mit diesem Cmdlet wird eine interaktive Sitzung mit jedem der angegebenen Container gestartet. Verwenden Sie den `docker ps` Befehl, um eine Liste der Container-IDs abzurufen. Weitere Informationen finden Sie in der Hilfe zum [docker PS](https://docs.docker.com/engine/reference/commandline/ps/) -Befehl.

```yaml
Type: System.String[]
Parameter Sets: ContainerId, ContainerIdInstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Gibt Benutzer Anmelde Informationen an. Dieses Cmdlet führt den Befehl mit den Berechtigungen des angegebenen Benutzers aus. Geben Sie ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit dem Remote Computer und Ausführen eines `Get-PSSession` Befehls verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem Parameter **Computername** oder **ConnectionUri** auszuführen.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Gibt ein Array von Sitzungs-IDs an. Dieses Cmdlet ruft nur die Sitzungen mit den angegebenen IDs ab. Geben Sie eine oder mehrere IDs ein, die durch Kommas getrennt sind, oder verwenden Sie den Bereichs Operator (..), um einen Bereich von IDs anzugeben. Der ID-Parameter kann nicht in Verbindung mit dem **Computername** -Parameter verwendet werden.

Eine ID ist eine Ganzzahl, die die vom Benutzer verwalteten Sitzungen in der aktuellen Sitzung eindeutig identifiziert. Es ist einfacher zu merken und einzugeben als die **InstanceId** , aber nur innerhalb der aktuellen Sitzung eindeutig. Die ID einer Sitzung wird in der ID-Eigenschaft der Sitzung gespeichert.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Gibt ein Array von Instanz-IDs von Sitzungen an. Dieses Cmdlet ruft nur die Sitzungen mit den angegebenen Instanz-IDs ab.

Die Instanz-ID ist eine GUID, die eine Sitzung auf einem lokalen oder Remotecomputer eindeutig identifiziert. Die **InstanceId** ist eindeutig, auch wenn mehrere Sitzungen in PowerShell ausgeführt werden.

Die Instanz-ID einer Sitzung wird in der **InstanceID** -Eigenschaft der Sitzung gespeichert.

```yaml
Type: System.Guid[]
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, VMNameInstanceId, ContainerIdInstanceId, VMIdInstanceId
Aliases:

Required: True (ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId), False (InstanceId)
Position: Named
Default value: All sessions
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt ein Array von Sitzungs Namen an. Dieses Cmdlet ruft nur die Sitzungen mit den angegebenen anzeigen Amen ab. Platzhalterzeichen sind zulässig.

Der Anzeigename einer Sitzung wird in der **Name** -Eigenschaft der Sitzung gespeichert.

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri, ContainerId, VMId, VMName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Port

Gibt den angegebenen Netzwerkport an, der für die temporäre Verbindung verwendet wird, in der der Befehl ausgeführt wird `Get-PSSession` . Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören. Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).

Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren. Um den Listener zu konfigurieren, geben Sie die folgenden beiden Befehle an der PowerShell-Eingabeaufforderung ein:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem Parameter **Computername** oder **ConnectionUri** auszuführen.

Verwenden Sie den **Port** -Parameter nur, wenn es unbedingt notwendig ist. Der im Befehl festgelegte **Port** gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird. Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: 5985, 5986
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessionoption

Gibt erweiterte Optionen für die Sitzung an. Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem Cmdlet "New-PSSessionOption" erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.

Die Standardwerte für die Optionen werden durch den Wert der $PSSessionOption-Einstellungsvariablen bestimmt, sofern festgelegt. Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.

Die Sitzungsoptionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der $PSSessionOption-Einstellungsvariablen und in der Sitzungskonfiguration festgelegt sind. Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.

Eine Beschreibung der Sitzungs Optionen, einschließlich der Standardwerte, finden Sie unter `New-PSSessionOption` .
Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md). Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State

Gibt einen Sitzungszustand an. Dieses Cmdlet ruft nur Sitzungen im angegebenen Zustand ab. Die zulässigen Werte für diesen Parameter sind: alle, geöffnet, getrennt, geschlossen und beschädigt. Der Standardwert ist „Alle“.

Der Sitzungsstatuswert ist relativ zu aktuellen Sitzungen. Sitzungen, die nicht in den aktuellen Sitzungen erstellt wurden und nicht mit der aktuellen Sitzung verbunden sind, haben den Status Disconnected, auch wenn sie mit einer anderen Sitzung verbunden sind.

Der Status einer Sitzung wird in der **State** -Eigenschaft der Sitzung gespeichert.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: Microsoft.PowerShell.Commands.SessionFilterState
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri, VMNameInstanceId, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName
Aliases:
Accepted values: All, Opened, Disconnected, Closed, Broken

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Gibt die maximale Anzahl gleichzeitiger Verbindungen an, die zum Ausführen des Befehls hergestellt werden können `Get-PSSession` . Wenn Sie diesen Parameter weglassen oder den Wert „0“ (Null) eingeben, wird der Standardwert „32“ verwendet. Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -US-

Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll verwendet, um die Verbindung herzustellen, in der der Befehl ausgeführt wird `Get-PSSession` . Standardmäßig wird SSL nicht verwendet. Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port für den Befehl nicht verfügbar ist, tritt ein Fehler beim Befehl auf.

Dieser Parameter konfiguriert die temporäre Verbindung, die erstellt wird, um einen `Get-PSSession` Befehl mit dem **Computername** -Parameter auszuführen.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMID

Gibt ein Array mit der ID der virtuellen Computer an. Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer. Verwenden Sie den folgenden Befehl, um die verfügbaren virtuellen Computer anzuzeigen:

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId, VMIdInstanceId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Gibt ein Array von Namen von virtuellen Computern an. Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer. Verwenden Sie das-Cmdlet, um die für Sie verfügbaren virtuellen Maschinen anzuzeigen `Get-VM` .

```yaml
Type: System.String[]
Parameter Sets: VMNameInstanceId, VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. Runspaces. PSSession

## HINWEISE

- Mit diesem Cmdlet werden von Benutzern verwaltete Sitzungen **PSSession** -Objekte abgerufen, z. b. solche, die mit den Cmdlets New-PSSession, `Enter-PSSession` und Invoke-Command erstellt werden. Sie ruft nicht die vom System verwaltete Sitzung ab, die beim Starten von PowerShell erstellt wird.
- Ab Windows PowerShell 3,0 werden **PSSession** -Objekte auf dem Server gespeichert, der sich auf dem Server oder am Ende einer Verbindung befindet. Um die Sitzungen zu erhalten, die auf dem lokalen Computer oder einem Remote Computer gespeichert sind, stellt PowerShell eine temporäre Sitzung mit dem angegebenen Computer her und führt Abfrage Befehle in der Sitzung aus.
- Verwenden Sie zum Abrufen von Sitzungen, die eine Verbindung zu einem Remotecomputer herstellen, den Parameter **ComputerName** oder **ConnectionUri** , um den Remotecomputer anzugeben. Um die Sitzungen zu filtern `Get-PSSession` , die abrufen, verwenden Sie die Parameter **Name** , **ID** , **InstanceId** und **State** . Verwenden Sie die restlichen Parameter, um die temporäre Sitzung zu konfigurieren, die von `Get-PSSession` verwendet wird.
- Wenn Sie die Parameter **Computername** oder **ConnectionUri** verwenden, ruft `Get-PSSession` nur Sitzungen von Computern ab, auf denen Windows PowerShell 3,0 und höhere Versionen von PowerShell ausgeführt wird.
- Der Wert der **State** -Eigenschaft einer **PSSession** ist relativ zur aktuellen Sitzung.
  Daher bedeutet der Wert " **getrennt** ", dass die **PSSession** nicht mit der aktuellen Sitzung verbunden ist. Dies bedeutet jedoch nicht, dass die **PSSession** von allen Sitzungen getrennt ist. Sie kann mit einer anderen Sitzung verbunden sein. Verwenden Sie die **Availability** -Eigenschaft, um zu bestimmen, ob Sie die **PSSession** in der aktuellen Sitzung verbinden oder wiederherstellen können.

Ein **Availability** -Wert von **None** gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann. Der Wert **ausgelastet** gibt an, dass keine Verbindung mit der **PSSession** hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.

Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate-Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).

Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability-Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

## VERWANDTE LINKS

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)
