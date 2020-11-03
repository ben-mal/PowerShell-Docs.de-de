---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Command
ms.openlocfilehash: b4e065ba0055c43a0ab4475878a049e4f9fde3e2
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218844"
---
# Invoke-Command

## ZUSAMMENFASSUNG
Führt Befehle auf lokalen Computern und Remotecomputern aus.

## SYNTAX

### InProcess (Standard)

```
Invoke-Command [-ScriptBlock] <ScriptBlock> [-NoNewScope] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### Filepathrunspace

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### Sitzung

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### Filepathcomputername

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-FilePath] <String> [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### Computername

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### Uri

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### Filepaar

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### VMId

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### VMName

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### Filepathvmid

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### Filepathvmname

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-RemoteDebug] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### Sshhost

```
Invoke-Command [-Port <Int32>] [-AsJob] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> -HostName <String[]> [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-Subsystem <String>] [<CommonParameters>]
```

### ContainerId

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RunAsAdministrator] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### Filepathcontainerid

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RunAsAdministrator] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### Sshhusthashparam

```
Invoke-Command [-AsJob] [-HideComputerName] [-JobName <String>] [-ScriptBlock] <ScriptBlock>
 -SSHConnection <Hashtable[]> [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### Filepathsshhost

```
Invoke-Command [-AsJob] [-HideComputerName] -FilePath <String> -HostName <String[]>
 [-UserName <String>] [-KeyFilePath <String>] [-SSHTransport] [-RemoteDebug]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### Filepathsshhusthash

```
Invoke-Command [-AsJob] [-HideComputerName] -FilePath <String> -SSHConnection <Hashtable[]>
 [-RemoteDebug] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## DESCRIPTION

Das `Invoke-Command` -Cmdlet führt Befehle auf einem lokalen Computer oder einem Remote Computer aus und gibt alle Ausgaben der Befehle zurück, einschließlich der Fehler. Mit einem einzigen `Invoke-Command` Befehl können Sie Befehle auf mehreren Computern ausführen.

Um einen einzelnen Befehl auf einem Remotecomputer auszuführen, verwenden Sie den **ComputerName** -Parameter. Um eine Reihe verwandter Befehle auszuführen, die Daten gemeinsam nutzen, verwenden Sie das `New-PSSession` -Cmdlet, um eine **PSSession** (eine permanente Verbindung) auf dem Remote Computer zu erstellen, und verwenden Sie dann den **Session** -Parameter von, `Invoke-Command` um den Befehl in der **PSSession** auszuführen. Verwenden Sie zum Ausführen eines Befehls in einer getrennten Sitzung den **InDisconnectedSession** -Parameter. Verwenden Sie zum Ausführen eines Befehls in einem Hintergrundauftrag den **AsJob** -Parameter.

Sie können auch `Invoke-Command` auf einem lokalen Computer mit einem Skriptblock als Befehl verwenden. PowerShell führt den Skriptblock direkt in einem untergeordneten Bereich des aktuellen Gültigkeits Bereichs aus.

`Invoke-Command`Lesen Sie vor der Verwendung von zum Ausführen von Befehlen auf einem Remote Computer [about_Remote](./About/about_Remote.md).

Ab PowerShell 6,0 können Sie Secure Shell (SSH) verwenden, um eine Verbindung mit herzustellen und Befehle auf Remote Computern aufzurufen. SSH muss auf dem lokalen Computer installiert sein, und der Remote Computer muss mit einem PowerShell-SSH-Endpunkt konfiguriert werden. Der Vorteil einer SSH-basierten PowerShell-Remote Sitzung besteht darin, dass Sie auf mehreren Plattformen (Windows, Linux, macOS) funktioniert. Bei einer SSH-basierten Sitzung verwenden Sie die Parameter " **Hostname** " oder " **SshConnection** ", um den Remote Computer und relevante Verbindungsinformationen anzugeben. Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

In einigen Codebeispielen wird Verteilung verwendet, um die Zeilenlänge zu verringern. Weitere Informationen finden Sie unter [about_Splatting](./About/about_Splatting.md).

## BEISPIELE

### Beispiel 1: Ausführen eines Skripts auf einem Server

In diesem Beispiel wird das `Test.ps1` Skript auf dem Computer Server01 ausgeführt.

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

Der **FilePath** -Parameter gibt ein Skript an, das sich auf dem lokalen Computer befindet. Das Skript wird auf dem Remotecomputer ausgeführt, und die Ergebnisse werden an den lokalen Computer zurückgegeben.

### Beispiel 2: Ausführen eines Befehls auf einem Remote Server

In diesem Beispiel wird ein `Get-Culture` Befehl auf dem Remote Computer Server01 ausgeführt.

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```

Der **Computername** -Parameter gibt den Namen des Remote Computers an. Der **Credential** -Parameter wird verwendet, um den Befehl im Sicherheitskontext von Domain01\User01 auszuführen, einem Benutzer, der über die Berechtigung zum Ausführen von Befehlen verfügt. Der **ScriptBlock** -Parameter gibt den Befehl an, der auf dem Remote Computer ausgeführt werden soll.

In der Antwort fordert PowerShell das Kennwort und eine Authentifizierungsmethode für das USER01-Konto an.
Anschließend wird der Befehl auf dem Computer „Server01“ ausgeführt und das Ergebnis zurückgegeben.

### Beispiel 3: Ausführen eines Befehls in einer permanenten Verbindung

In diesem Beispiel wird derselbe `Get-Culture` Befehl in einer Sitzung mit einer permanenten Verbindung auf dem Remote Computer mit dem Namen Server02 ausgeführt.

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

`New-PSSession`Mit dem-Cmdlet wird eine Sitzung auf dem Remote Computer Server02 erstellt und in der `$s` Variablen gespeichert. In der Regel erstellen Sie eine Sitzung nur, wenn Sie eine Reihe von Befehlen auf dem Remote Computer ausführen.

Das- `Invoke-Command` Cmdlet führt den `Get-Culture` Befehl auf Server02 aus. Der **Session** -Parameter gibt die in der Variablen gespeicherte Sitzung an `$s` .

In der Antwort führt PowerShell den Befehl in der Sitzung auf dem Server02-Computer aus.

### Beispiel 4: Verwenden einer Sitzung zum Ausführen einer Reihe von Befehlen, die Daten freigeben

In diesem Beispiel werden die Auswirkungen der Verwendung von **Computername** und **Sitzungs** Parametern von verglichen `Invoke-Command` . Es veranschaulicht, wie Sie eine Sitzung verwenden können, um eine Reihe von Befehlen auszuführen, die gemeinsam die gleichen Daten nutzen.

```powershell
Invoke-Command -ComputerName Server02 -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -ComputerName Server02 -ScriptBlock {$p.VirtualMemorySize}
$s = New-PSSession -ComputerName Server02
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -Session $s -ScriptBlock {$p.VirtualMemorySize}
```

```Output
17930240
```

Die ersten beiden Befehle verwenden den **Computername** -Parameter von `Invoke-Command` , um Befehle auf dem Remote Computer Server02 auszuführen. Der erste Befehl verwendet das `Get-Process` Cmdlet, um den PowerShell-Prozess auf dem Remote Computer zu erhalten und in der `$p` Variablen zu speichern. Der zweite Befehl ruft den Wert der **VirtualMemorySize** -Eigenschaft des PowerShell-Prozesses ab.

Wenn Sie den **Computername** -Parameter verwenden, erstellt PowerShell eine neue Sitzung, um den Befehl auszuführen.
Die Sitzung wird geschlossen, wenn der Befehl abgeschlossen ist. Die `$p` Variable wurde in einer Verbindung erstellt, ist jedoch nicht in der für den zweiten Befehl erstellten Verbindung vorhanden.

Das Problem wird gelöst, indem eine persistente Sitzung auf dem Remote Computer erstellt und dann beide Befehle in der gleichen Sitzung ausgeführt werden.

`New-PSSession`Mit dem-Cmdlet wird eine persistente Sitzung auf dem Computer Server02 erstellt und die Sitzung in der `$s` Variablen gespeichert. `Invoke-Command`In den folgenden Zeilen wird der **Session** -Parameter verwendet, um beide Befehle in der gleichen Sitzung auszuführen. Da beide Befehle in der gleichen Sitzung ausgeführt werden, `$p` bleibt der Wert aktiv.

### Beispiel 5: Eingeben eines Befehls, der in einer lokalen Variablen gespeichert ist

Dieses Beispiel zeigt, wie Sie einen Befehl erstellen, der als Skriptblock in einer lokalen Variablen gespeichert wird.
Wenn der Skriptblock in einer lokalen Variablen gespeichert wird, können Sie die Variable als Wert des **ScriptBlock** -Parameters angeben.

```powershell
$command = { Get-WinEvent -LogName PowerShellCore/Operational |
  Where-Object {$_.Message -like "*certificate*"} }
Invoke-Command -ComputerName S1, S2 -ScriptBlock $command
```

Die `$command` -Variable speichert den `Get-WinEvent` Befehl, der als Skriptblock formatiert ist. Der `Invoke-Command` führt den in gespeicherten Befehl `$command` auf den Remote Computern S1 und S2 aus.

### Beispiel 6: Ausführen eines einzelnen Befehls auf mehreren Computern

In diesem Beispiel wird veranschaulicht, wie verwendet wird, `Invoke-Command` um einen einzelnen Befehl auf mehreren Computern auszuführen.

```powershell
$parameters = @{
  ComputerName = "Server01", "Server02", "TST-0143", "localhost"
  ConfigurationName = 'MySession.PowerShell'
  ScriptBlock = { Get-WinEvent -LogName PowerShellCore/Operational }
}
Invoke-Command @parameters
```

Der Computer **Name** -Parameter gibt eine durch Trennzeichen getrennte Liste von Computernamen an. Die Liste der Computer enthält den Wert "localhost", der den lokalen Computer darstellt. Der **ConfigurationName** -Parameter gibt eine Alternative Sitzungs Konfiguration an. Der **ScriptBlock** -Parameter wird ausgeführt `Get-WinEvent` , um die powershellcore-/Operational-Ereignisprotokolle von den einzelnen Computern zu erhalten.

### Beispiel 7: erhalten der Version des Host Programms auf mehreren Computern

In diesem Beispiel wird die Version des PowerShell-Host Programms abgerufen, das auf 200 Remote Computern ausgeführt wird.

```powershell
$version = Invoke-Command -ComputerName (Get-Content Machines.txt) -ScriptBlock {(Get-Host).Version}
```

Da nur ein Befehl ausgeführt wird, müssen Sie keine permanenten Verbindungen mit den einzelnen Computern erstellen. Der Befehl verwendet stattdessen den **ComputerName** -Parameter, um die Computer anzugeben. Zum Angeben der Computer wird mit dem `Get-Content` Cmdlet der Inhalt der Machine.txt Datei (eine Datei mit Computernamen) erhalten.

Das- `Invoke-Command` Cmdlet führt einen `Get-Host` Befehl auf den Remote Computern aus. Er verwendet die Punkt Notation, um die **Versions** Eigenschaft des PowerShell-Hosts zu erhalten.

Diese Befehle werden nacheinander ausgeführt. Wenn die Befehle vollständig sind, wird die Ausgabe der Befehle von allen Computern in der Variablen gespeichert `$version` . Die Ausgabe enthält den Namen des Computers, von dem die Daten stammen.

### Beispiel 8: Ausführen eines Hintergrund Auftrags auf mehreren Remote Computern

In diesem Beispiel wird ein Befehl auf zwei Remote Computern ausgeführt. Der `Invoke-Command` Befehl verwendet den **AsJob** -Parameter, sodass der Befehl als Hintergrund Auftrag ausgeführt wird. Die Befehle werden auf den Remote Computern ausgeführt, der Auftrag ist jedoch auf dem lokalen Computer vorhanden. Die Ergebnisse werden an den lokalen Computer übertragen.

```powershell
$s = New-PSSession -ComputerName Server01, Server02
Invoke-Command -Session $s -ScriptBlock {Get-EventLog system} -AsJob
```

```Output
Id   Name    State      HasMoreData   Location           Command
---  ----    -----      -----         -----------        ---------------
1    Job1    Running    True          Server01,Server02  Get-EventLog system
```

```powershell
$j = Get-Job
$j | Format-List -Property *
```

```Output
HasMoreData   : True
StatusMessage :
Location      : Server01,Server02
Command       : Get-EventLog system
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : e124bb59-8cb2-498b-a0d2-2e07d4e030ca
Id            : 1
Name          : Job1
ChildJobs     : {Job2, Job3}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
$results = $j | Receive-Job
```

Das `New-PSSession` -Cmdlet erstellt Sitzungen auf den Remote Computern Server01 und Server02. Das- `Invoke-Command` Cmdlet führt in jeder Sitzung einen Hintergrund Auftrag aus. Bei dem Befehl wird der Befehl mithilfe des **AsJob** -Parameters als Hintergrundauftrag ausgeführt. Dieser Befehl gibt ein Auftragsobjekt zurück, das zwei untergeordnete Auftragsobjekte enthält, jeweils eins für die Aufträge, die auf zwei Remotecomputern ausgeführt werden.

Der `Get-Job` Befehl speichert das Auftrags Objekt in der `$j` Variablen. Die `$j` Variable wird dann an das `Format-List` Cmdlet weitergeleitet, um alle Eigenschaften des Auftrags Objekts in einer Liste anzuzeigen. Mit dem letzten Befehl werden die Ergebnisse der Aufträge abgerufen. Das Auftrags Objekt wird an `$j` das `Receive-Job` Cmdlet weitergeleitet, und die Ergebnisse werden in der `$results` Variablen gespeichert.

### Beispiel 9: einschließen lokaler Variablen in einem Befehl, der auf einem Remote Computer ausgeführt wird

Dieses Beispiel zeigt, wie Sie die Werte von lokalen Variablen in einem Befehl einschließen können, der auf einem Remotecomputer ausgeführt wird. Der Befehl verwendet den `Using` Scope-Modifizierer, um eine lokale Variable in einem Remote Befehl zu identifizieren. Standardmäßig wird davon ausgegangen, dass alle Variablen in der Remotesitzung definiert sind. Der bereichsmodifizierer `Using` wurde in PowerShell 3,0 eingeführt. Weitere Informationen zum bereichsmodifizierer `Using` finden Sie unter [about_Remote_Variables](./About/about_Remote_Variables.md) und [about_Scopes](./about/about_scopes.md).

```powershell
$Log = "PowerShellCore/Operational"
Invoke-Command -ComputerName Server01 -ScriptBlock {Get-WinEvent -LogName $Using:Log -MaxEvents 10}
```

Die `$Log` Variable speichert den Namen des Ereignis Protokolls, powershellcore/Operational. Das- `Invoke-Command` Cmdlet wird `Get-WinEvent` auf Server01 ausgeführt, um die zehn neuesten Ereignisse aus dem Ereignisprotokoll zu erhalten. Der Wert des **logName** -Parameters ist die Variable, der der bereichsmodifizierer `$Log` vorangestellt wird, `Using` um anzugeben, dass er in der lokalen Sitzung erstellt wurde, nicht in der Remote Sitzung.

### Beispiel 10: Ausblenden des Computer namens

Dieses Beispiel zeigt die Auswirkung der Verwendung des **hidecomputername** -Parameters von `Invoke-Command` .
**Hidecomputername** ändert nicht das Objekt, das von diesem Cmdlet zurückgegeben wird. Es ändert nur die Anzeige. Sie können weiterhin die **Format** -Cmdlets verwenden, um die **pscomputername** -Eigenschaft der betroffenen Objekte anzuzeigen.

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell}
```

```Output
PSComputerName    Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
--------------    -------  ------    -----      ----- -----   ------     --   -----------
S1                575      15        45100      40988   200     4.68     1392 PowerShell
S2                777      14        35100      30988   150     3.68     67   PowerShell
```

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell} -HideComputerName
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
575      15        45100      40988   200     4.68     1392 PowerShell
777      14        35100      30988   150     3.68     67   PowerShell
```

Die ersten beiden Befehle verwenden `Invoke-Command` , um einen `Get-Process` Befehl für den PowerShell-Prozess auszuführen. Die Ausgabe des ersten Befehls enthält die **PsComputerName** -Eigenschaft, die den Namen des Computers enthält, auf dem der Befehl ausgeführt wurde. Die Ausgabe des zweiten Befehls, der **hidecomputername** verwendet, enthält nicht die **pscomputername** -Spalte.

### Beispiel 11: Verwenden des param-Schlüssel Worts in einem Skriptblock

Das `Param` Schlüsselwort und der Argument **List** -Parameter werden verwendet, um Variablen Werte an benannte Parameter in einem Skriptblock zu übergeben. In diesem Beispiel werden Dateinamen angezeigt, die mit dem Buchstaben beginnen `a` und die `.pdf` Erweiterung aufweisen.

Weitere Informationen zum- `Param` Schlüsselwort finden Sie unter [about_Language_Keywords](./about/about_language_keywords.md#param).

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Param ($param1,$param2) Get-ChildItem -Name $param1 -Include $param2 }
    ArgumentList = "a*", "*.pdf"
}
Invoke-Command @parameters
```

```Output
aa.pdf
ab.pdf
ac.pdf
az.pdf
```

`Invoke-Command` verwendet den **ScriptBlock** -Parameter, der zwei Variablen definiert, `$param1` und `$param2` . `Get-ChildItem` verwendet die benannten Parameter **Name** und **include** mit den Variablennamen. Die Argument **List** übergibt die Werte an die Variablen.

### Beispiel 12: Verwenden der automatischen $args automatischen Variablen in einem Skriptblock

Die `$args` Automatische Variable und der Argument **List** -Parameter werden verwendet, um Array Werte an Parameter Positionen in einem Skriptblock zu übergeben. In diesem Beispiel wird der Verzeichnis Inhalt eines Servers der- `.txt` Dateien angezeigt. Der `Get-ChildItem` **path** -Parameter ist Position 0, und der **Filter** -Parameter ist Position.
1.

Weitere Informationen zur `$args` Variablen finden Sie unter [about_Automatic_Variables](./about/about_automatic_variables.md#args)

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Get-ChildItem $args[0] $args[1] }
    ArgumentList = "C:\Test", "*.txt*"
}
Invoke-Command @parameters
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           6/12/2019    15:15            128 alog.txt
-a---           7/27/2019    15:16            256 blog.txt
-a---           9/28/2019    17:10             64 zlog.txt
```

`Invoke-Command` verwendet einen **ScriptBlock** -Parameter und `Get-ChildItem` gibt `$args[0]` die `$args[1]` Array Werte und an. Die Argument **List** übergibt die `$args` Array Werte an die `Get-ChildItem` Parameter Positionen für **path** und **Filter**.

### Beispiel 13: Ausführen eines Skripts auf allen in einer Textdatei aufgeführten Computern

In diesem Beispiel wird das- `Invoke-Command` Cmdlet verwendet, um das `Sample.ps1` Skript auf allen Computern auszuführen, die in der Datei aufgelistet sind `Servers.txt` . Der Befehl verwendet den **FilePath** -Parameter, um die Skriptdatei anzugeben. Mit diesem Befehl können Sie das Skript auf den Remote Computern ausführen, selbst wenn die Skriptdatei für die Remote Computer nicht zugänglich ist.

```powershell
Invoke-Command -ComputerName (Get-Content Servers.txt) -FilePath C:\Scripts\Sample.ps1 -ArgumentList Process, Service
```

Wenn Sie den Befehl senden, wird der Inhalt der `Sample.ps1` Datei in einen Skriptblock kopiert, und der Skriptblock wird auf jedem Remote Computer ausgeführt. Dieses Verfahren entspricht der Verwendung des **ScriptBlock** -Parameters, um den Inhalt des Skripts zu übermitteln.

### Beispiel 14: Ausführen eines Befehls auf einem Remote Computer mithilfe eines URI

In diesem Beispiel wird gezeigt, wie ein Befehl auf einem Remote Computer ausgeführt wird, der durch einen Uniform Resource Identifier (URI) identifiziert wird. Dieses spezielle Beispiel führt einen `Set-Mailbox` Befehl auf einem Exchange-Remote Server aus.

```powershell
$LiveCred = Get-Credential
$parameters = @{
  ConfigurationName = 'Microsoft.Exchange'
  ConnectionUri = 'https://ps.exchangelabs.com/PowerShell'
  Credential = $LiveCred
  Authentication = 'Basic'
  ScriptBlock = {Set-Mailbox Dan -DisplayName "Dan Park"}
}
Invoke-Command @parameters
```

Die erste Zeile verwendet das `Get-Credential` Cmdlet zum Speichern der Windows Live ID-Anmelde Informationen in der `$LiveCred` Variablen. PowerShell fordert den Benutzer auf, Windows Live ID-Anmelde Informationen einzugeben.

Die- `$parameters` Variable ist eine Hash Tabelle mit den Parametern, die an das `Invoke-Command` Cmdlet übergeben werden. Das- `Invoke-Command` Cmdlet führt einen `Set-Mailbox` Befehl mithilfe der **Microsoft. Exchange** -Sitzungs Konfiguration aus. Der **ConnectionURI** -Parameter gibt den URL des Exchange-Serverendpunkts an. Der **Credential** -Parameter gibt die in der Variablen gespeicherten Anmelde Informationen an `$LiveCred` . Der **AuthenticationMechanism** -Parameter gibt die Verwendung der Standardauthentifizierung an. Der **ScriptBlock** -Parameter gibt einen Skriptblock mit dem Befehl an.

### Beispiel 15: Verwenden einer Sitzungs Option

Dieses Beispiel zeigt, wie Sie einen **sessionoption** -Parameter erstellen und verwenden.

```powershell
$so = New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck
Invoke-Command -ComputerName server01 -UseSSL -ScriptBlock { Get-HotFix } -SessionOption $so -Credential server01\user01
```

Mit dem- `New-PSSessionOption` Cmdlet wird ein Sitzungs Options Objekt erstellt, das bewirkt, dass die Zertifizierungsstelle, der kanonische Name und die Sperr Listen beim Auswerten der eingehenden HTTPS-Verbindung vom Remote Ende nicht überprüft werden. Das **sessionoption** -Objekt wird in der `$so` Variablen gespeichert.

> [!NOTE]
> Die Deaktivierung dieser Überprüfungen ist praktisch für die Problembehandlung, aber offensichtlich nicht sicher.

Das- `Invoke-Command` Cmdlet führt einen `Get-HotFix` Befehl Remote aus. Der **sessionoption** -Parameter wird der- `$so` Variablen zugewiesen.

### Beispiel 16: Verwalten der URI-Umleitung in einem Remote Befehl

In diesem Beispiel wird gezeigt, wie die Parameter " **Zuweisung** " und " **sessionoption** " verwendet werden, um die URI-Umleitung in einem Remote Befehl zu verwalten.

```powershell
$max = New-PSSessionOption -MaximumRedirection 1
$parameters = @{
  ConnectionUri = "https://ps.exchangelabs.com/PowerShell"
  ScriptBlock = { Get-Mailbox dan }
  AllowRedirection = $true
  SessionOption = $max
}
Invoke-Command @parameters
```

Mit dem- `New-PSSessionOption` Cmdlet wird ein **pssessionoption** -Objekt erstellt, das in der Variablen gespeichert wird `$max` . Der Befehl verwendet den **MaximumRedirection** -Parameter zum Festlegen der **MaximumConnectionRedirectionCount** -Eigenschaft des **PSSessionOption** -Objekts auf 1.

Das- `Invoke-Command` Cmdlet führt einen `Get-Mailbox` Befehl auf einem Microsoft Exchange-Remote Server aus. Der **Zustellungs Direction** -Parameter stellt explizite Berechtigungen zum Umleiten der Verbindung zu einem alternativen Endpunkt bereit. Der **sessionoption** -Parameter verwendet das Sitzungs Objekt, das in der Variablen gespeichert ist `$max` .

Wenn also der von **ConnectionUri** angegebene Remote Computer eine Umleitungs Meldung zurückgibt, leitet PowerShell die Verbindung um, aber wenn das neue Ziel eine andere Weiterleitungs Nachricht zurückgibt, wird der Umleitungs Zählerwert 1 überschritten, und es wird `Invoke-Command` ein Fehler ohne Abbruch zurückgegeben.

### Beispiel 17: Zugreifen auf eine Netzwerkfreigabe in einer Remote Sitzung

Dieses Beispiel zeigt, wie Sie über eine Remote Sitzung auf eine Netzwerkfreigabe zugreifen können. Zum veranschaulichen des Beispiels werden drei Computer verwendet. Server01 ist der lokale Computer, Server02 ist der Remote Computer, und Net03 enthält die Netzwerkfreigabe. Server01 stellt eine Verbindung mit Server02 her, und Server02 führt dann einen zweiten Hop zu Net03 aus, um auf die Netzwerkfreigabe zuzugreifen. Weitere Informationen zur Unterstützung von Hops durch PowerShell-Remoting zwischen Computern finden Sie unter Ausführen [des zweiten Hops in PowerShell-Remoting](/powershell/scripting/learn/remoting/ps-remoting-second-hop).

In den Client Einstellungen auf dem lokalen Computer und in den Dienst Einstellungen auf dem Remote Computer ist die erforderliche Credential Security Support Provider (kredssp)-Delegierung aktiviert. Um die Befehle in diesem Beispiel auszuführen, müssen Sie Mitglied der Gruppe " **Administratoren** " auf dem lokalen Computer und dem Remote Computer sein.

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer Server02
$s = New-PSSession Server02
Invoke-Command -Session $s -ScriptBlock {Enable-WSManCredSSP -Role Server -Force}
$parameters = @{
  Session = $s
  ScriptBlock = { Get-Item \\Net03\Scripts\LogFiles.ps1 }
  Authentication = "CredSSP"
  Credential = "Domain01\Admin01"
}
Invoke-Command @parameters
```

Mit dem- `Enable-WSManCredSSP` Cmdlet kann die "Server01"-Delegierung vom lokalen Computer auf den Server02-Remote Computer aktiviert werden. Der **Role** -Parameter gibt den **Client** an, um die Einstellung für den Client auf dem lokalen Computer zu konfigurieren.

`New-PSSession` erstellt ein **PSSession** -Objekt für Server02 und speichert das-Objekt in der `$s` Variablen.

Das `Invoke-Command` Cmdlet verwendet die- `$s` Variable, um eine Verbindung mit dem Remote Computer Server02 herzustellen. Der **ScriptBlock** -Parameter wird `Enable-WSManCredSSP` auf dem Remote Computer ausgeführt. Der **Role** -Parameter gibt den **Server** an, um die Einstellungen für den auf dem Remote Computer festgelegten Einstellungen für den ""

Die- `$parameters` Variable enthält die Parameterwerte zum Herstellen einer Verbindung mit der Netzwerkfreigabe. Das- `Invoke-Command` Cmdlet führt einen `Get-Item` Befehl in der Sitzung in aus `$s` . Mit diesem Befehl wird ein Skript aus der `\\Net03\Scripts` Netzwerkfreigabe abgerufen. Der Befehl verwendet den **Authentication** -Parameter mit dem Wert " **kredssp** " und dem **Credential** -Parameter mit dem Wert " **Domain01\Admin01** ".

### Beispiel 18: Starten von Skripts auf vielen Remote Computern

In diesem Beispiel wird ein Skript auf mehr als 100 Computern ausgeführt. Zur Minimierung der Auswirkungen auf dem lokalen Computer wird eine Verbindung mit jedem Computer hergestellt, das Skript gestartet und die Verbindung dann von jedem Computer getrennt.
Das Skript wird weiterhin in den getrennten Sitzungen ausgeführt.

```powershell
$parameters = @{
  ComputerName = (Get-Content -Path C:\Test\Servers.txt)
  InDisconnectedSession = $true
  FilePath = "\\Scripts\Public\ConfigInventory.ps1"
  SessionOption = @{OutputBufferingMode="Drop";IdleTimeout=43200000}
}
Invoke-Command @parameters
```

Der Befehl verwendet `Invoke-Command` , um das Skript auszuführen. Der Wert des **Computername** -Parameters ist ein `Get-Content` Befehl, der die Namen der Remote Computer aus einer Textdatei abruft. Der **InDisconnectedSession** -Parameter trennt Sitzungen, sobald der Befehl ausgeführt wird. Der Wert des **FilePath** -Parameters ist das Skript, das `Invoke-Command` auf jedem Computer ausgeführt wird.

Der Wert von **sessionoption** ist eine Hash Tabelle. Der Wert **outputbufferingmode** ist auf **Drop** festgelegt, und der **IdleTimeout** -Wert wird auf **43,2 Millionen** Millisekunden (12 Stunden) festgelegt.

Verwenden Sie das-Cmdlet, um die Ergebnisse von Befehlen und Skripts, die in getrennten Sitzungen ausgeführt werden, zu erhalten `Receive-PSSession` .

### Beispiel 19: Ausführen eines Befehls auf einem Remote Computer mithilfe von SSH

In diesem Beispiel wird gezeigt, wie ein Befehl auf einem Remote Computer mithilfe von Secure Shell (SSH) ausgeführt wird. Wenn SSH auf dem Remote Computer für die Eingabe von Kenn Wörtern konfiguriert ist, erhalten Sie eine Kenn Wort Eingabeaufforderung.
Andernfalls müssen Sie die SSH-Schlüssel basierte Benutzerauthentifizierung verwenden.

```powershell
Invoke-Command -HostName UserA@LinuxServer01 -ScriptBlock { Get-MailBox * }
```

### Beispiel 20: Ausführen eines Befehls auf einem Remote Computer mithilfe von SSH und Angeben eines Benutzer Authentifizierungs Schlüssels

Dieses Beispiel zeigt, wie Sie einen Befehl auf einem Remote Computer mithilfe von SSH ausführen und eine Schlüsseldatei für die Benutzerauthentifizierung angeben. Sie werden nicht zur Eingabe eines Kennworts aufgefordert, es sei denn, bei der Schlüssel Authentifizierung tritt ein Fehler auf, und der Remote Computer ist so konfiguriert, dass die

```powershell
Invoke-Command -HostName UserA@LinuxServer01 -ScriptBlock { Get-MailBox * } -KeyFilePath /UserA/UserAKey_rsa
```

### Beispiel 21: Ausführen einer Skriptdatei auf mehreren Remote Computern mithilfe von SSH als Auftrag

In diesem Beispiel wird gezeigt, wie eine Skriptdatei auf mehreren Remote Computern mithilfe von SSH und dem **SshConnection** -Parametersatz ausgeführt wird. Der **SshConnection** -Parameter nimmt ein Array von Hash Tabellen an, die Verbindungsinformationen für jeden Computer enthalten. Für dieses Beispiel ist es erforderlich, dass für die Ziel Remote Computer SSH konfiguriert ist, um die Schlüssel basierte Benutzerauthentifizierung zu unterstützen.

```powershell
$sshConnections =
@{ HostName="WinServer1"; UserName="Domain\UserA"; KeyFilePath="C:\Users\UserA\id_rsa" },
@{ HostName="UserB@LinuxServer5"; KeyFilePath="/Users/UserB/id_rsa" }
$results = Invoke-Command -FilePath c:\Scripts\CollectEvents.ps1 -SSHConnection $sshConnections
```

## PARAMETERS

### -Zuweisung Richtung

Ermöglicht die Umleitung dieser Verbindung an einen alternativen URI (Uniform Resource Identifier).

Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben. Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um die Umleitung der Verbindung zuzulassen.

Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern. Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der `$PSSessionOption` Preference-Variablen fest. Der Standardwert ist 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Gibt das Anwendungsnamenssegment des Verbindungs-URI an. Verwenden Sie diesen Parameter, um den Anwendungsnamen anzugeben, wenn Sie nicht den **ConnectionUri** -Parameter im Befehl verwenden.

Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer. Wenn diese Einstellungs Variable nicht definiert ist, lautet der Standardwert "wsman". Dieser Wert ist für die meisten Verwendungsarten geeignet. Weitere Informationen finden Sie unter [about_Preference_Variables](./About/about_Preference_Variables.md).

Der WinRM-Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus.
Der Wert dieses Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listeners auf dem Remotecomputer übereinstimmen.

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: $PSSessionApplicationName if set on the local computer, otherwise WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Argumentlist

Stellt die Werte von lokalen Variablen im Befehl bereit. Die Variablen im Befehl werden durch diese Werte ersetzt, bevor der Befehl auf dem Remotecomputer ausgeführt wird. Geben Sie die Werte in eine durch Kommas getrennte Liste ein. Werte werden Variablen in der Reihenfolge zugeordnet, in der Sie aufgelistet sind. Der Alias für Argument **List** lautet "args".

Die Werte im Argument **List** -Parameter können tatsächliche Werte sein, z. b. 1024, oder es kann sich um Verweise auf lokale Variablen handeln, z `$max` . b..

Um lokale Variablen in einem Befehl zu verwenden, verwenden Sie das folgende Befehlsformat:

`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` - oder - `<local-variable>`

Das Schlüsselwort " **param** " listet die lokalen Variablen auf, die im Befehl verwendet werden. **Argumentlist** gibt die Werte der Variablen in der Reihenfolge an, in der Sie aufgelistet sind. Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag auf einem Remote Computer ausführt. Verwenden Sie diesen Parameter, um Befehle auszuführen, deren Ausführung viel Zeit in Anspruch nimmt.

Wenn Sie den **AsJob** -Parameter verwenden, gibt der Befehl ein Objekt zurück, das den Auftrag darstellt, und zeigt dann die Eingabeaufforderung an. Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird. Verwenden Sie die-Cmdlets, um den Auftrag zu verwalten `*-Job` . Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.

Der **AsJob** -Parameter ähnelt der Verwendung des `Invoke-Command` Cmdlets zum `Start-Job` Remote Ausführen eines Cmdlets. Bei **AsJob** wird der Auftrag jedoch auf dem lokalen Computer erstellt, auch wenn der Auftrag auf einem Remote Computer ausgeführt wird. Die Ergebnisse des Remote Auftrags werden automatisch an den lokalen Computer zurückgegeben.

Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](About/about_Jobs.md) und [about_Remote_Jobs](About/about_Remote_Jobs.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentifizierung

Gibt den Mechanismus an, der zum Authentifizieren der Anmelde Informationen des Benutzers verwendet wird. Die kredssp-Authentifizierung ist nur in Windows Vista, Windows Server 2008 und höheren Versionen des Windows-Betriebssystems verfügbar.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- Standard
- Basic
- CredSSP
- Digest
- Kerberos
- Aushandeln
- NegotiateWithImplicitCredential

Der Standardwert ist Default.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Die CredSSP (Credential Security Support Provider)-Authentifizierung, bei der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle konzipiert, die die Authentifizierung auf mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remotenetzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden. Weitere Informationen finden Sie [unter Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider).

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:
Accepted values: Basic, Default, Credssp, Digest, Kerberos, Negotiate, NegotiateWithImplicitCredential

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certifiupethumschlag-Print

Gibt das digitale Zertifikat für öffentliche Schlüssel (X.509) eines Benutzerkontos mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an. Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänen Konten.

Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie einen- `Get-Item` `Get-ChildItem` Befehl oder den-Befehl im PowerShell-Laufwerk "CERT:".

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt die Computer an, auf denen der Befehl ausgeführt wird. Die Standardeinstellung ist der lokale Computer.

Wenn Sie den **Computername** -Parameter verwenden, erstellt PowerShell eine temporäre Verbindung, die nur zum Ausführen des angegebenen Befehls verwendet und dann geschlossen wird. Wenn Sie eine permanente Verbindung benötigen, verwenden Sie den **Session** -Parameter.

Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer in einer durch Trennzeichen getrennten Liste ein. Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt ( `.` ) ein.

Um eine IP-Adresse im Wert von **Computername** zu verwenden, muss der Befehl den **Credential** -Parameter enthalten. Der Computer muss für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remote Computers muss in der **WinRM-** Liste des lokalen Computers enthalten sein. Anweisungen zum Hinzufügen eines Computer namens zur Liste " **Treuhänder Hosts** " finden Sie unter [Hinzufügen eines Computers zur Liste "vertrauenswürdiger Host](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list)".

Unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option **als Administrator ausführen** ausführen, um den lokalen Computer in den Wert von **Computername** einzuschließen.

```yaml
Type: System.String[]
Parameter Sets: ComputerName, FilePathComputerName
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

Gibt die Sitzungs Konfiguration an, die für die neue **PSSession** verwendet wird.

Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein. Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/PowerShell` .

Bei Verwendung mit SSH gibt dieser Parameter das Subsystem an, das auf dem Ziel verwendet werden soll, wie in definiert `sshd_config` . Der Standardwert für SSH ist das `powershell` Subsystem.

Die Sitzungskonfiguration für eine Sitzung befindet sich auf dem Remotecomputer. Wenn die angegebene Sitzungs Konfiguration auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl fehl.

Der Standardwert ist der Wert der Einstellungs `$PSSessionConfigurationName` Variablen auf dem lokalen Computer. Wenn diese Einstellungs Variable nicht festgelegt ist, lautet der Standardwert **Microsoft. PowerShell**. Weitere Informationen finden Sie unter [about_Preference_Variables](about/about_Preference_Variables.md).

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: $PSSessionConfigurationName if set on the local computer, otherwise Microsoft.PowerShell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Gibt einen URI (Uniform Resource Identifier) an, der den Verbindungsendpunkt für die Sitzung definiert.
Der URI muss vollqualifiziert sein.

Das Format dieser Zeichenfolge lautet wie folgt:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

Der Standardwert lautet:

`http://localhost:5985/WSMAN`

Wenn Sie keinen Verbindungs-URI angeben, können Sie die Parameter " **US** " und " **Port** " verwenden, um die Verbindungs-URI-Werte anzugeben.

Gültige Werte für das **Transport** -Segment des URI sind „HTTP“ und „HTTPS“. Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit den Standardports erstellt: 80 für http und 443 für HTTPS. Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.

Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.

```yaml
Type: System.Uri[]
Parameter Sets: Uri, FilePathUri
Aliases: URI, CU

Required: False
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: False
Accept wildcard characters: False
```

### -Containerid

Gibt ein Array von Container-IDs an.

```yaml
Type: System.String[]
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName
Aliases:

Required: True (VMId, VMName, FilePathVMId, FilePathVMName), False (ComputerName, FilePathComputerName, Uri, FilePathUri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Enablenetworkaccess

Gibt an, dass mit diesem Cmdlet Loopback Sitzungen ein interaktives Sicherheits Token hinzugefügt wird. Mit dem interaktiven Token können Sie die Befehle in der Loopbacksitzung ausführen, um Daten von anderen Computern abzurufen. Beispielsweise können Sie einen Befehl in der Sitzung ausführen, mit dem XML-Dateien von einem Remotecomputer auf den lokalen Computer kopiert werden.

Eine Loopback Sitzung ist eine **PSSession** , die auf demselben computerbasiert und endet. Um eine Loopback Sitzung zu erstellen, lassen Sie den **Computername** -Parameter aus, oder legen Sie seinen Wert auf "dot ( `.` )", "localhost" oder den Namen des lokalen Computers fest.

Standardmäßig werden Loopback Sitzungen mit einem Netzwerk Token erstellt, das möglicherweise nicht über ausreichende Berechtigungen zum Authentifizieren bei Remote Computern verfügt.

Der **EnableNetworkAccess** -Parameter ist nur bei Loopbacksitzungen wirksam. Wenn Sie **enablenetworkaccess** verwenden, wenn Sie eine Sitzung auf einem Remote Computer erstellen, ist der Befehl erfolgreich, aber der-Parameter wird ignoriert.

Sie können den Remote Zugriff in einer Loopback Sitzung mithilfe des Werts " **kredssp** " des Parameters " **Authentication** " zulassen, der die Sitzungs Anmelde Informationen an andere Computer delegiert.

Um den Computer vor böswilligem Zugriff zu schützen, können getrennte Loopback Sitzungen mit interaktiven Tokens, die mithilfe von **enablenetworkaccess** erstellt wurden, nur von dem Computer wieder hergestellt werden, auf dem die Sitzung erstellt wurde. Die Verbindung von getrennten Sitzungen, die die CredSSP-Authentifizierung verwenden, kann von anderen Computern wiederhergestellt werden. Weitere Informationen finden Sie unter `Disconnect-PSSession`.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Gibt ein lokales Skript an, das dieses Cmdlet auf einem oder mehreren Remote Computern ausführt. Geben Sie den Pfad und den Dateinamen des Skripts ein, oder übergeben Sie einen Skript Pfad an `Invoke-Command` . Das Skript muss auf dem lokalen Computer oder in einem Verzeichnis vorhanden sein, auf das der lokale Computer zugreifen kann. Verwenden Sie **argumentlist** , um die Werte der Parameter im Skript anzugeben.

Wenn Sie diesen Parameter verwenden, konvertiert PowerShell den Inhalt der angegebenen Skriptdatei in einen Skriptblock, überträgt den Skriptblock an den Remote Computer und führt ihn auf dem Remote Computer aus.

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, FilePathComputerName, FilePathUri, FilePathVMId, FilePathVMName, FilePathContainerId, FilePathSSHHost, FilePathSSHHostHash
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Hidecomputername

Gibt an, dass dieses Cmdlet den Computernamen der einzelnen Objekte aus der Ausgabe Anzeige auslässt. Standardmäßig wird der Name des Computers, der das Objekt generiert, in der Anzeige angezeigt.

Dieser Parameter betrifft nur die Ausgabeanzeige. Das Objekt wird nicht geändert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases: HCN

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName

Gibt ein Array von Computernamen für eine Secure Shell (SSH)-basierte Verbindung an. Dies ähnelt dem **Computername** -Parameter, mit dem Unterschied, dass die Verbindung mit dem Remote Computer anstelle von Windows WinRM über SSH hergestellt wird.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Indisconnectedsession

Gibt an, dass dieses Cmdlet einen Befehl oder ein Skript in einer getrennten Sitzung ausführt.

Wenn Sie den **indisconnectedsession** -Parameter verwenden, wird `Invoke-Command` auf jedem Remote Computer eine persistente Sitzung erstellt, der durch den **ScriptBlock** -Parameter oder den **FilePath** -Parameter angegebene Befehl gestartet und die Verbindung mit der Sitzung getrennt. Die Befehle werden weiterhin in den getrennten Sitzungen ausgeführt. Mit **indisconnectedsession** können Sie Befehle ausführen, ohne eine Verbindung mit den Remote Sitzungen aufrechtzuerhalten. Und da die Sitzung getrennt wird, bevor Ergebnisse zurückgegeben werden, stellt " **indisconnectedsession** " sicher, dass alle Befehls Ergebnisse an die erneut verbundene Sitzung zurückgegeben werden, statt zwischen Sitzungen aufgeteilt zu werden.

Sie können " **indisconnectedsession** " nicht mit dem **Sitzungs** Parameter oder dem **AsJob** -Parameter verwenden.

Befehle, die **indisconnectedsession** verwenden, geben ein **PSSession** -Objekt zurück, das die getrennte Sitzung darstellt. Die Befehlsausgabe wird nicht zurückgegeben. Verwenden Sie zum Herstellen einer Verbindung mit der getrennten Sitzung die `Connect-PSSession` `Receive-PSSession` Cmdlets oder. Verwenden Sie das-Cmdlet, um die Ergebnisse von Befehlen zu erhalten, die in der Sitzung ausgeführt wurden `Receive-PSSession` . Um Befehle auszuführen, die eine Ausgabe in einer getrennten Sitzung generieren, legen Sie den Wert der **outputbufferingmode** -Sitzungs Option auf **Drop** fest. Wenn Sie eine Verbindung mit der getrennten Sitzung herstellen möchten, legen Sie das Leerlauf Timeout in der Sitzung fest, damit Sie genügend Zeit zum Herstellen einer Verbindung haben, bevor Sie die Sitzung löschen.

Sie können den Ausgabepuffer Modus und das Leerlauf Timeout im **sessionoption** -Parameter oder in der `$PSSessionOption` Preference-Variablen festlegen. Weitere Informationen zu Sitzungs Optionen finden Sie unter `New-PSSessionOption` und [about_Preference_Variables](./about/about_preference_variables.md).

Weitere Informationen zum Feature „Getrennte Sitzungen“ finden Sie unter [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases: Disconnected

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die Eingabe für den Befehl an. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.

Wenn Sie den **Inputobject** -Parameter verwenden, verwenden `$Input` Sie die automatische Variable im Wert des **ScriptBlock** -Parameters, um die Eingabe Objekte darzustellen.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Jobname

Gibt einen Anzeigenamen für den Hintergrundauftrag an. Standardmäßig werden Aufträge benannt `Job<n>` , wobei `<n>` eine Ordinalzahl ist.

Wenn Sie den **Jobname** -Parameter in einem Befehl verwenden, wird der Befehl als Auftrag ausgeführt, und es wird `Invoke-Command` ein Auftrags Objekt zurückgegeben, auch wenn Sie **AsJob** nicht in den Befehl einschließen.

Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](./About/about_Jobs.md).

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam
Aliases:

Required: False
Position: Named
Default value: Job<n>
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyFilePath

Gibt einen Schlüssel Dateipfad an, der von Secure Shell (SSH) zum Authentifizieren eines Benutzers auf einem Remote Computer verwendet wird.

SSH ermöglicht die Ausführung der Benutzerauthentifizierung über private und öffentliche Schlüssel als Alternative zur grundlegenden Kenn Wort Authentifizierung. Wenn der Remote Computer für die Schlüssel Authentifizierung konfiguriert ist, kann dieser Parameter verwendet werden, um den Schlüssel zur Identifizierung des Benutzers bereitzustellen.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: SSHHost, FilePathSSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nonewscope

Gibt an, dass dieses Cmdlet den angegebenen Befehl im aktuellen Bereich ausführt. Standardmäßig `Invoke-Command` führt Befehle in Ihrem eigenen Bereich aus.

Dieser Parameter ist nur in Befehlen gültig, die in der aktuellen Sitzung ausgeführt werden, d. h. in Befehlen, bei denen beide Parameter, **ComputerName** und **Session** , weglassen wurden.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InProcess
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Gibt den Netzwerkport auf dem Remote Computer an, der für diesen Befehl verwendet wird. Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören. Die Standardports sind 5985 (WinRM-Port für http) und 5986 (WinRM-Port für HTTPS).

Konfigurieren Sie vor der Verwendung eines alternativen Ports den WinRM-Listener auf dem Remotecomputer, um diesen Port abzuhören. Um den Listener zu konfigurieren, geben Sie die folgenden beiden Befehle an der PowerShell-Eingabeaufforderung ein:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Verwenden Sie den **Port** -Parameter nur, wenn dies erforderlich ist. Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird. Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.

```yaml
Type: System.Int32
Parameter Sets: ComputerName, FilePathComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remotedebug

Wird verwendet, um den aufgerufenen Befehl im Debugmodus in der PowerShell-Remote Sitzung auszuführen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, SSHHost, ContainerId, FilePathContainerId, SSHHostHashParam, FilePathSSHHost, FilePathSSHHostHash
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runasadministrator

Gibt an, dass dieses Cmdlet einen Befehl als Administrator aufruft.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Gibt die auszuführenden Befehle an. Schließen Sie die Befehle in geschweiften Klammern `{ }` ein, um einen Skriptblock zu erstellen.
Dieser Parameter ist erforderlich.

Standardmäßig werden alle Variablen im Befehl auf dem Remotecomputer ausgewertet. Um lokale Variablen in den Befehl einzuschließen, verwenden Sie **argumentlist**.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: InProcess, Session, ComputerName, Uri, VMId, VMName, SSHHost, ContainerId, SSHHostHashParam
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sitzung

Gibt ein Array von Sitzungen an, in denen dieses Cmdlet den Befehl ausführt. Geben Sie eine Variable ein, die **PSSession** -Objekte enthält, oder einen Befehl, der die **PSSession** -Objekte erstellt oder abruft, z `New-PSSession` . b. den `Get-PSSession` Befehl oder.

Wenn Sie eine **PSSession** erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her. Verwenden Sie eine **PSSession** , um eine Reihe verwandter Befehle auszuführen, die Daten gemeinsam nutzen. Verwenden Sie den **Computername** -Parameter, um einen einzelnen Befehl oder eine Reihe von nicht verknüpften Befehlen auszuführen. Weitere Informationen finden Sie unter [about_PSSessions](./About/about_PSSessions.md).

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: FilePathRunspace, Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessionname

Gibt einen Anzeigenamen für eine getrennte Sitzung an. Sie können den Namen verwenden, um in nachfolgenden Befehlen auf die Sitzung zu verweisen, z. b. einen- `Get-PSSession` Befehl. Dieser Parameter ist nur mit dem **InDisconnectedSession** -Parameter gültig.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String[]
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessionoption

Gibt erweiterte Optionen für die Sitzung an. Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.

Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt. Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.

Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind. Allerdings haben Sie Vorrang vor maximalen Werten, Kontingenten oder Grenzwerten, die in der Sitzungs Konfiguration festgelegt sind.

Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter `New-PSSessionOption` . Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).
Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshConnection

Dieser Parameter nimmt ein Array von Hash Tabellen an, in denen jede Hash Tabelle einen oder mehrere Verbindungsparameter enthält, die zum Herstellen einer Secure Shell (SSH)-Verbindung erforderlich sind. Der **SshConnection** -Parameter ist nützlich zum Erstellen mehrerer Sitzungen, in denen jede Sitzung andere Verbindungsinformationen erfordert.

Die Hash Tabelle verfügt über die folgenden Member:

- **Computername** (oder **Hostname** )
- **Port**
- **UserName**
- **KeyFilePath** (oder **identityfilepath** )

**Computername** (oder **Hostname** ) ist das einzige erforderliche Schlüssel-Wert-Paar.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam, FilePathSSHHostHash
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sshtransport

Gibt an, dass die Remote Verbindung mithilfe von Secure Shell (SSH) hergestellt wird.

Standardmäßig verwendet PowerShell Windows WinRM, um eine Verbindung mit einem Remote Computer herzustellen. Dieser Switch erzwingt, dass PowerShell den **Hostname** -Parameter zum Einrichten einer SSH-basierten Remote Verbindung verwendet.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.
Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.

Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

```yaml
Type: System.Int32
Parameter Sets: FilePathRunspace, Session, ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

Gibt den Benutzernamen für das Konto an, das zum Ausführen eines Befehls auf dem Remote Computer verwendet wird. Die Benutzer Authentifizierungsmethode hängt davon ab, wie Secure Shell (SSH) auf dem Remote Computer konfiguriert ist.

Wenn SSH für die einfache Kenn Wort Authentifizierung konfiguriert ist, werden Sie zur Eingabe des Benutzer Kennworts aufgefordert.

Wenn SSH für die Schlüssel basierte Benutzerauthentifizierung konfiguriert ist, kann ein Schlüssel Dateipfad über den Schlüssel **FilePath** -Parameter bereitgestellt werden, und es erfolgt keine Kenn Wort Eingabeaufforderung. Wenn sich die Client Benutzer Schlüsseldatei an einem bekannten SSH-Speicherort befindet, ist der **keyFilePath** -Parameter für die Schlüssel basierte Authentifizierung nicht erforderlich, und die Benutzerauthentifizierung erfolgt automatisch basierend auf dem Benutzernamen. Weitere Informationen finden Sie in der SSH-Dokumentation Ihrer Plattform zur Schlüssel basierten Benutzerauthentifizierung.

Dies ist kein erforderlicher Parameter. Wenn der **username** -Parameter nicht angegeben wird, wird der aktuell angemeldete Benutzername für die Verbindung verwendet.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: SSHHost, FilePathSSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -US-

Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll verwendet, um eine Verbindung mit dem Remote Computer herzustellen. Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte. Der **Parameter "** " ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-anstelle von http sendet.

Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMID

Gibt ein Array von IDs von virtuellen Computern an.

```yaml
Type: System.Guid[]
Parameter Sets: VMId, FilePathVMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Gibt ein Array von Namen von virtuellen Computern an.

```yaml
Type: System.String[]
Parameter Sets: VMName, FilePathVMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subsystem

Gibt das SSH-Subsystem an, das für die neue **PSSession** verwendet wird.

Gibt das Subsystem an, das auf dem Ziel verwendet werden soll, wie in sshd_config definiert.
Das Subsystem startet eine bestimmte Version von PowerShell mit vordefinierten Parametern.
Wenn das angegebene Subsystem auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl fehl.

Wenn dieser Parameter nicht verwendet wird, ist der Standardwert das "PowerShell"-Subsystem.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. ScriptBlock

Sie können einen Befehl in einem Skriptblock an die Pipeline übergeben `Invoke-Command` . Verwenden `$Input` Sie die automatische Variable, um die Eingabe Objekte im Befehl darzustellen.

## AUSGABEN

### System. Management. Automation. psremotingjob, System. Management. Automation. Runspaces. PSSession oder die Ausgabe des aufgerufenen Befehls

Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den **AsJob** -Parameter verwenden. Wenn Sie den **indisconnectedsession** -Parameter angeben, `Invoke-Command` gibt ein **PSSession** -Objekt zurück. Andernfalls wird die Ausgabe des aufgerufenen Befehls zurückgegeben, bei dem es sich um den Wert des **ScriptBlock** -Parameters handelt.

## HINWEISE

Wenn unter Windows Vista und höheren Versionen des Windows-Betriebssystems der **Computername** -Parameter von `Invoke-Command` zum Ausführen eines Befehls auf dem lokalen Computer verwendet werden soll, müssen Sie PowerShell mithilfe der Option **als Administrator ausführen** ausführen.

Wenn Sie Befehle auf mehreren Computern ausführen, stellt PowerShell eine Verbindung mit den Computern in der Reihenfolge her, in der Sie in der Liste angezeigt werden. Allerdings wird die Befehlsausgabe in der Reihenfolge angezeigt, in der Sie von den Remote Computern empfangen wird, die sich möglicherweise unterscheiden.

Fehler, die sich aus dem Befehl ergeben, der `Invoke-Command` ausführt, sind in den Befehls Ergebnissen enthalten.
Fehler, die in einem lokalen Befehl Fehler mit Abbruch sein würden, werden in einem Remotebefehl als Fehler ohne Abbruch behandelt. Durch diese Strategie wird sichergestellt, dass beim Beenden von Fehlern auf einem Computer der Befehl auf allen Computern, auf denen er ausgeführt wird, nicht geschlossen wird. Diese Vorgehensweise wird selbst dann verwendet, wenn ein Remotebefehl auf einem einzelnen Computer ausgeführt wird.

Wenn sich der Remote Computer nicht in einer Domäne befindet, der der lokale Computer vertraut, ist der Computer möglicherweise nicht in der Lage, die Anmelde Informationen des Benutzers zu authentifizieren. Um den Remote Computer der Liste der vertrauenswürdigen Hosts in der WS-Verwaltung hinzuzufügen, verwenden Sie den folgenden Befehl im `WSMAN` Anbieter, wobei `<Remote-Computer-Name>` der Name des Remote Computers ist:

`Set-Item -Path WSMan:\Localhost\Client\TrustedHosts -Value \<Remote-Computer-Name\>`

Wenn Sie eine **PSSession** mit dem **indisconnectedsession** -Parameter trennen, wird der Sitzungs Status **getrennt** , und die Verfügbarkeit ist **None**. Der Wert der **State** Eigenschaft bezieht sich auf die aktuelle Sitzung. Der Wert " **getrennt** " bedeutet, dass die **PSSession** nicht mit der aktuellen Sitzung verbunden ist. Dies bedeutet jedoch nicht, dass die **PSSession** von allen Sitzungen getrennt ist. Sie kann mit einer anderen Sitzung verbunden sein. Um festzustellen, ob Sie eine Sitzungsverbindung herstellen bzw. wiederherstellen können, verwenden Sie die **Availability** -Eigenschaft.

Ein **Availability** -Wert von **None** gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann. Der Wert **ausgelastet** gibt an, dass keine Verbindung mit der **PSSession** hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist. Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate](/dotnet/api/system.management.automation.runspaces.runspacestate). Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

Die Parameter " **Hostname** " und " **SshConnection** " wurden ab PowerShell 6,0 eingeschlossen. Sie wurden hinzugefügt, um PowerShell-Remoting basierend auf Secure Shell (SSH) bereitzustellen. PowerShell und SSH werden auf mehreren Plattformen (Windows, Linux, macOS) unterstützt, und PowerShell-Remoting funktioniert auf diesen Plattformen, auf denen PowerShell und SSH installiert und konfiguriert sind. Dies ist unabhängig vom vorherigen Windows-Remoting, das auf WinRM basiert, und viele der WinRM-spezifischen Features und Einschränkungen gelten nicht. Beispielsweise werden auf WinRM basierende Kontingente, Sitzungs Optionen, benutzerdefinierte Endpunkt Konfiguration und Features zum Trennen und Wiederherstellen von Verbindungen derzeit nicht unterstützt. Weitere Informationen zum Einrichten von PowerShell-SSH-Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## VERWANDTE LINKS

[about_PSSessions](./About/about_PSSessions.md)

[about_Remote](./About/about_Remote.md)

[about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md)

[about_Remote_Troubleshooting](./About/about_remote_troubleshooting.md)

[about_Remote_Variables](./About/about_Remote_Variables.md)

[about_Scopes](./About/about_scopes.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Item](../Microsoft.PowerShell.Management/Invoke-Item.md)

[New-PSSession](New-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)

[WSMan-Anbieter](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
