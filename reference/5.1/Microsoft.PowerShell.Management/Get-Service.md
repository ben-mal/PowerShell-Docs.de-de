---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 0c007f1becd7364806cfd47e18cf05995b81e0f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215404"
---
# Get-Service

## ZUSAMMENFASSUNG
Ruft die Dienste auf einem lokalen Computer oder einem Remotecomputer ab.

## SYNTAX

### Standard (Standard)

```
Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-RequiredServices]
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### DisplayName

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] -DisplayName <String[]>
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### InputObject

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem " **Get-Service"-** Cmdlet werden Objekte abgerufen, die die Dienste auf einem lokalen Computer oder auf einem Remote Computer darstellen, einschließlich der Ausführung und Beendigung der Dienste.

Sie können dieses Cmdlet anweisen, nur bestimmte Dienste zu erhalten, indem Sie den Dienstnamen oder anzeigen amen der Dienste angeben, oder Sie können Dienst Objekte über die Pipeline an dieses Cmdlet übergeben.

## BEISPIELE

### Beispiel 1: alle Dienste auf dem Computer

```powershell
Get-Service
```

Mit diesem Befehl werden alle Dienste auf dem Computer abgerufen.
Dies verhält sich, als ob Sie eingegeben haben `Get-Service *` .
In der Standardanzeige werden der Status, der Dienstname und der Anzeigename der einzelnen Dienste angezeigt.

### Beispiel 2: erhalten von Diensten, die mit einer Such Zeichenfolge beginnen

```powershell
Get-Service "wmi*"
```

Mit diesem Befehl werden Dienste mit Dienstnamen abgerufen, die mit WMI beginnen (das Akronym für Windows-Verwaltungsinstrumentation).

### Beispiel 3: Anzeigen von Diensten, die eine Such Zeichenfolge enthalten

```powershell
Get-Service -Displayname "*network*"
```

Mit diesem Befehl werden Dienste angezeigt, deren Anzeige Name das Wort "Network" enthält.
Durch das Suchen des Anzeigenamens können Sie Netzwerkdienste suchen, selbst wenn der Dienstname nicht das Wort %%amp;quot;Net%%amp;quot; enthält, beispielsweise %%amp;quot;xmlprov%%amp;quot; (der Netzwerkbereitstellungsdienst).

### Beispiel 4: erhalten von Diensten, die mit einer Such Zeichenfolge und einem Ausschluss beginnen

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

Diese Befehle erhalten nur die Dienste, deren Dienstnamen mit "Win" beginnen, mit Ausnahme des WinRM-Diensts.

### Beispiel 5: Anzeigen von Diensten, die zurzeit aktiv sind

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

Mit diesem Befehl werden nur die Dienste angezeigt, die zurzeit aktiv sind.
Er verwendet das **Get-Service-** Cmdlet, um alle Dienste auf dem Computer zu erhalten.
Der Pipeline Operator (|) übergibt die Ergebnisse an das Where-Object-Cmdlet, das nur die Dienste auswählt, deren Status-Eigenschaft ausgeführt wird.

%%amp;quot;Status%%amp;quot; ist nur eine der Eigenschaften von Dienstobjekten.
Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Service | Get-Member` .

### Beispiel 6: erhalten der Dienste auf einem Remote Computer

```powershell
Get-Service -ComputerName "Server02"
```

Dieser Befehl ruft die Dienste auf dem Remotecomputer %%amp;quot;Server02%%amp;quot; ab.

Da der Computer *Name* -Parameter von **Get-Service** nicht Windows PowerShell-Remoting verwendet, können Sie diesen Parameter auch dann verwenden, wenn der Computer nicht für Remoting in Windows PowerShell konfiguriert ist.

### Beispiel 7: Auflisten der Dienste auf dem lokalen Computer, die über abhängige Dienste verfügen

```powershell
Get-Service |
  Where-Object {$_.DependentServices} |
    Format-List -Property Name, DependentServices, @{
      Label="NoOfDependentServices"; Expression={$_.dependentservices.count}
    }
```

```Output
Name                  : AudioEndpointBuilder
DependentServices     : {AudioSrv}
NoOfDependentServices : 1

Name                  : Dhcp
DependentServices     : {WinHttpAutoProxySvc}
NoOfDependentServices : 1
...
```

Der erste Befehl verwendet das **Get-Service-** Cmdlet, um die Dienste auf dem Computer zu erhalten.
Ein Pipeline Operator (|) sendet die Dienste an das **Where-Object-** Cmdlet, das die Dienste auswählt, deren **DependentServices** -Eigenschaft nicht NULL ist.

Die Ergebnisse werden mit einem anderen Pipelineoperator an das Cmdlet %%amp;quot;Format-List%%amp;quot; gesendet.
Der Befehl verwendet den *Property* -Parameter, um den Namen des Diensts, den Namen der abhängigen Dienste und eine berechnete Eigenschaft anzuzeigen, die die Anzahl der abhängigen Dienste anzeigt, die jeder Dienst besitzt.

### Beispiel 8: Sortieren von Diensten nach Eigenschafts Wert

```powershell
Get-Service "s*" | Sort-Object status
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  stisvc             Windows Image Acquisition (WIA)
Stopped  SwPrv              MS Software Shadow Copy Provider
Stopped  SysmonLog          Performance Logs and Alerts
Running  Spooler            Print Spooler
Running  srservice          System Restore Service
Running  SSDPSRV            SSDP Discovery Service
Running  ShellHWDetection   Shell Hardware Detection
Running  Schedule           Task Scheduler
Running  SCardSvr           Smart Card
Running  SamSs              Security Accounts Manager
Running  SharedAccess       Windows Firewall/Internet Connectio...
Running  SENS               System Event Notification
Running  seclogon           Secondary Logon
```

Dieser Befehl zeigt, dass beim Sortieren von Diensten in aufsteigender Reihenfolge nach dem Wert der **Status** -Eigenschaft beendete Dienste vor dem Ausführen von Diensten angezeigt werden.
Dies liegt daran, dass der Wert von "Status" eine Enumeration ist, in der "beendet" den Wert "1" aufweist und "Running" den Wert 4 aufweist.

Verwenden Sie zum Auflisten der laufenden Dienste zuerst den *Absteig* enden Parameter des Sort-Object-Cmdlets.

### Beispiel 9: Dienste auf mehreren Computern

```powershell
Get-Service -Name "WinRM" -ComputerName "localhost", "Server01", "Server02" |
 Format-Table -Property MachineName, Status, Name, DisplayName -auto
```

```Output
MachineName    Status  Name  DisplayName
------------   ------  ----  -----------
localhost      Running WinRM Windows Remote Management (WS-Management)
Server01       Running WinRM Windows Remote Management (WS-Management)
Server02       Running WinRM Windows Remote Management (WS-Management)
```

Dieser Befehl verwendet das **Get-Service-** Cmdlet, um einen Get-Service WinRM-Befehl auf zwei Remote Computern und dem lokalen Computer ("localhost") auszuführen.

Der Befehl wird auf den Remote Computern ausgeführt, und die Ergebnisse werden an den lokalen Computer zurückgegeben.
Ein Pipeline Operator (|) sendet die Ergebnisse an das **Format-Table-** Cmdlet, das die Dienste als Tabelle formatiert.
Der **Format-Table-** Befehl verwendet den *Property* -Parameter, um die Eigenschaften anzugeben, die in der Tabelle angezeigt werden, einschließlich der **MachineName** -Eigenschaft.

### Beispiel 10: erhalten der abhängigen Dienste eines Diensts

```powershell
Get-Service "WinRM" -RequiredServices
```

Mit diesem Befehl werden die für den WinRM-Dienst erforderlichen Dienste abgerufen.

Der Befehl gibt den Wert der **ServicesDependedOn** -Eigenschaft des Dienstanbieter zurück.

### Beispiel 11: erhalten eines Dienstanbieter über den Pipeline-Operator

```powershell
"WinRM" | Get-Service
```

Mit diesem Befehl wird der WinRM-Dienst auf dem lokalen Computer abgerufen.
Dieses Beispiel zeigt, dass Sie eine Dienstnamen Zeichenfolge (in Anführungszeichen eingeschlossen) über die Pipeline an **Get-Service** übergeben können.

## PARAMETERS

### -ComputerName

Ruft die Dienste ab, die auf den angegebenen Computern ausgeführt werden.
Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines Remote Computers ein.
Geben Sie den Computernamen, einen Punkt (.) oder einen localhost ein, um den lokalen Computer anzugeben.

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting.
Sie können den *Computername* -Parameter von **Get-Service** auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DependentServices

Gibt an, dass dieses Cmdlet nur die Dienste abruft, die vom angegebenen Dienst abhängen.

Standardmäßig ruft dieses Cmdlet alle Dienste ab.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName

Gibt die anzeigen amen der abzurufenden Dienste als Zeichen folgen Array an.
Platzhalter sind zulässig.
Standardmäßig ruft dieses Cmdlet alle Dienste auf dem Computer ab.

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Ausschließen

Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die von diesem Cmdlet aus dem Vorgang ausgeschlossen werden.
Der Wert dieses Parameters qualifiziert den *Name* -Parameter.
Geben Sie ein Namenselement oder -muster wie %%amp;quot;s*%%amp;quot; ein.
Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Include

Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die dieses Cmdlet in den Vorgang einschließt.
Der Wert dieses Parameters qualifiziert den *Name* -Parameter.
Geben Sie ein Namenselement oder -muster wie %%amp;quot;s*%%amp;quot; ein.
Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

Gibt **ServiceController** -Objekte an, die die abzurufenden Dienste darstellen.
Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.
Sie können ein Dienst Objekt auch über die Pipeline an dieses Cmdlet übergeben.

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die Dienstnamen der abzurufenden Dienste an.
Platzhalter sind zulässig.
Standardmäßig ruft dieses Cmdlet alle Dienste auf dem Computer ab.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Requirements dservices

Gibt an, dass dieses Cmdlet nur die Dienste abruft, die dieser Dienst benötigt.

Dieser Parameter ruft den Wert der **ServicesDependedOn** -Eigenschaft des Dienstanbieter ab.
Standardmäßig ruft dieses Cmdlet alle Dienste ab.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. ServiceProcess. ServiceController, System. String

Sie können ein Dienst Objekt oder einen Dienstnamen über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### System.ServiceProcess.ServiceController

Dieses Cmdlet gibt Objekte zurück, die die Dienste auf dem Computer darstellen.

## HINWEISE

Sie können auch über den integrierten Alias "GSV" auf " **Get-Service** " verweisen. Weitere Informationen finden Sie unter %%amp;quot;about_Aliases%%amp;quot;.

Dieses Cmdlet kann nur dann Dienste anzeigen, wenn der aktuelle Benutzer über die Berechtigung verfügt, Sie anzuzeigen.
Wenn dieses Cmdlet keine Dienste anzeigt, verfügen Sie möglicherweise nicht über die Berechtigung, diese anzuzeigen.

Geben Sie ein, um den Dienstnamen und den anzeigen amen der einzelnen Dienste auf dem System zu ermitteln `Get-Service` .
Die Dienstnamen werden in der Spalte %%amp;quot;Name%%amp;quot; und die Anzeigenamen in der Spalte %%amp;quot;DisplayName%%amp;quot; aufgeführt.

Wenn Sie aufsteigend nach Statuswert sortieren, werden Dienste mit dem Status %%amp;quot;Stopped%%amp;quot; vor Diensten mit dem Status %%amp;quot;Running%%amp;quot; angezeigt.
Die Status-Eigenschaft eines Diensts ist ein Enumerationswert, in dem die Namen der Status ganzzahlige Werte darstellen.
Die Sortierung basiert auf dem ganzzahligen Wert, nicht dem Namen.
%%amp;quot;Running%%amp;quot; wird vor %%amp;quot;Stopped%%amp;quot; angezeigt, da %%amp;quot;Stopped%%amp;quot; über den Wert %%amp;quot;1%%amp;quot; verfügt. %%amp;quot;Running%%amp;quot; verfügt über den Wert %%amp;quot;4%%amp;quot;.

## VERWANDTE LINKS

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
