---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: c27dac11cdd8ebbf1705ac3bba0c0aa5147d4fa8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599189"
---
# Get-Service

## ZUSAMMENFASSUNG
Ruft die Dienste auf dem Computer ab.

## SYNTAX

### Standard (Standard)

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### DisplayName

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### InputObject

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Service`Mit dem-Cmdlet werden Objekte abgerufen, die die Dienste auf einem Computer darstellen, einschließlich der Ausführung und Beendigung der Dienste. Wenn `Get-Service` ohne Parameter ausgeführt wird, werden standardmäßig alle Dienste des lokalen Computers zurückgegeben.

Sie können dieses Cmdlet anweisen, nur bestimmte Dienste zu erhalten, indem Sie den Dienstnamen oder anzeigen amen der Dienste angeben, oder Sie können Dienst Objekte über die Pipeline an dieses Cmdlet übergeben.

## BEISPIELE

### Beispiel 1: alle Dienste auf dem Computer

In diesem Beispiel werden alle Dienste auf dem Computer abgerufen. Dies verhält sich, als ob Sie eingegeben haben `Get-Service *` . In der Standardanzeige werden der Status, der Dienstname und der Anzeigename der einzelnen Dienste angezeigt.

```powershell
Get-Service
```

### Beispiel 2: erhalten von Diensten, die mit einer Such Zeichenfolge beginnen

In diesem Beispiel werden Dienste mit Dienstnamen abgerufen, die mit WMI (Windows-Verwaltungsinstrumentation) beginnen.

```powershell
Get-Service "wmi*"
```

### Beispiel 3: Anzeigen von Diensten, die eine Such Zeichenfolge enthalten

In diesem Beispiel werden Dienste mit einem anzeigen Amen angezeigt, der das Wort "Network" enthält. Durch das Durchsuchen des anzeigen Amens werden netzwerkbezogene Dienste auch dann gefunden, wenn der Dienst Name NET nicht enthält, wie z. b. xmlprov, den Netzwerk Bereitstellungs Dienst.

```powershell
Get-Service -Displayname "*network*"
```

### Beispiel 4: erhalten von Diensten, die mit einer Such Zeichenfolge und einem Ausschluss beginnen

In diesem Beispiel werden nur die Dienste mit Dienstnamen abgerufen, die mit " **Win**" beginnen, mit Ausnahme des WinRM-Diensts.

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### Beispiel 5: Anzeigen von Diensten, die zurzeit aktiv sind

In diesem Beispiel werden nur die Dienste mit dem Status "wird ausgeführt" angezeigt.

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

`Get-Service` Ruft alle Dienste auf dem Computer ab und sendet die Objekte in der Pipeline. Mit dem- `Where-Object` Cmdlet werden nur die Dienste ausgewählt, deren **Status** -Eigenschaft ausgeführt wird.

%%amp;quot;Status%%amp;quot; ist nur eine der Eigenschaften von Dienstobjekten. Um alle Eigenschaften anzuzeigen, geben Sie ein `Get-Service | Get-Member` .

### Beispiel 6: Auflisten der Dienste auf dem Computer, die über abhängige Dienste verfügen

In diesem Beispiel werden Dienste abgerufen, die über abhängige Dienste verfügen.

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

Das `Get-Service` Cmdlet ruft alle Dienste auf dem Computer ab und sendet die Objekte in der Pipeline. Mit dem- `Where-Object` Cmdlet werden die Dienste ausgewählt, deren **DependentServices** -Eigenschaft nicht NULL ist.

Die Ergebnisse werden über die Pipeline an das `Format-List` Cmdlet gesendet. Der **Property** -Parameter zeigt den Namen des Diensts, den Namen der abhängigen Dienste und eine berechnete Eigenschaft an, die die Anzahl der abhängigen Dienste für jeden Dienst anzeigt.

### Beispiel 7: Sortieren von Diensten nach Eigenschafts Wert

Dieses Beispiel zeigt, dass beim Sortieren von Diensten in aufsteigender Reihenfolge nach dem Wert der **Status** -Eigenschaft beendete Dienste vor dem Ausführen von Diensten angezeigt werden. Der Grund hierfür ist, dass der Wert von " **Status** " eine Enumeration ist, in der "beendet" den Wert "1" aufweist und "Running" den Wert 4 aufweist. Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

Verwenden Sie zum Auflisten der laufenden Dienste zuerst den **Absteig** enden Parameter des `Sort-Object` Cmdlets.

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

### Beispiel 8: erhalten der abhängigen Dienste eines Diensts

In diesem Beispiel werden die Dienste abgerufen, die für den WinRM-Dienst erforderlich sind. Der Wert der **ServicesDependedOn** -Eigenschaft des dienstangs wird zurückgegeben.

```powershell
Get-Service "WinRM" -RequiredServices
```

### Beispiel 9: erhalten eines Dienstanbieter über den Pipeline-Operator

In diesem Beispiel wird der WinRM-Dienst auf dem lokalen Computer abgerufen. Die in Anführungszeichen eingeschlossene Dienstnamen Zeichenfolge wird von der Pipeline an gesendet `Get-Service` .

```powershell
"WinRM" | Get-Service
```

## PARAMETERS

### -DependentServices

Gibt an, dass dieses Cmdlet nur die Dienste abruft, die vom angegebenen Dienst abhängen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName

Gibt die anzeigen amen der abzurufenden Dienste als Zeichen folgen Array an. Platzhalter sind zulässig.

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
Der Wert dieses Parameters qualifiziert den **Name** -Parameter. Geben Sie ein Namenselement oder-Muster ein, z `s*` . b.. Platzhalter sind zulässig.

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

Gibt als Zeichen folgen Array einen Dienst oder Dienste an, die dieses Cmdlet in den Vorgang einschließt. Der Wert dieses Parameters qualifiziert den **Name** -Parameter. Geben Sie ein Namenselement oder-Muster ein, z `s*` . b.. Platzhalter sind zulässig.

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

Gibt **ServiceController** -Objekte an, die die abzurufenden Dienste darstellen. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden. Sie können ein Dienst Objekt über die Pipeline an dieses Cmdlet übergeben.

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

Gibt die Dienstnamen der abzurufenden Dienste an. Platzhalter sind zulässig.

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

Gibt an, dass dieses Cmdlet nur die Dienste abruft, die dieser Dienst benötigt. Dieser Parameter ruft den Wert der **ServicesDependedOn** -Eigenschaft des Dienstanbieter ab.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: False
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

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

Ab PowerShell 6,0 werden den **ServiceController** -Objekten die folgenden Eigenschaften hinzugefügt: **username**, **Description**, **delayedaudestart**, **binarypathname** und **startupType** .

Sie können auch auf den `Get-Service` integrierten Alias verweisen `gsv` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Dieses Cmdlet kann nur dann Dienste anzeigen, wenn der aktuelle Benutzer über die Berechtigung verfügt, Sie anzuzeigen. Wenn dieses Cmdlet keine Dienste anzeigt, verfügen Sie möglicherweise nicht über die Berechtigung, diese anzuzeigen.

Geben Sie ein, um den Dienstnamen und den anzeigen amen der einzelnen Dienste auf dem System zu ermitteln `Get-Service` . Die Dienstnamen werden in der Spalte Name angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.

Wenn Sie in aufsteigender Reihenfolge nach dem Wert der **Status** Eigenschaft sortieren, werden beendete Dienste vor dem Ausführen von Diensten angezeigt. Die **Status** -Eigenschaft des dienstangs ist ein Enumerationswert, und die Statusnamen stellen ganzzahlige Werte dar Die Sortierreihenfolge basiert auf dem ganzzahligen Wert und nicht auf dem Namen. Beendet wird vor angezeigt, da die Ausführung von, da beendet ist, den Wert 1 hat und die Ausführung von den Wert 4 aufweist. Weitere Informationen finden Sie unter [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

## VERWANDTE LINKS

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)
