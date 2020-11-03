---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Service
ms.openlocfilehash: 71b9ac57b2ab27e26f3a7454662f231b6e1dd764
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216167"
---
# Start-Service

## ZUSAMMENFASSUNG
Startet beendete Dienste.

## SYNTAX

### Inputobject (Standard)

```
Start-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Standard

```
Start-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayName

```
Start-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Start-Service` Cmdlet sendet für jeden der angegebenen Dienste eine Start Meldung an den Windows-Dienst Controller. Wenn ein Dienst bereits ausgeführt wird, wird die Meldung ignoriert, ohne dass ein Fehler ausgegeben wird. Sie können die Dienste mit ihren Dienstnamen oder anzeigen Amen angeben, oder Sie können mit dem **Inputobject** -Parameter ein Dienst Objekt bereitstellen, das die Dienste darstellt, die Sie starten möchten.

## BEISPIELE

### Beispiel 1: Starten eines diensnamens mit seinem Namen

In diesem Beispiel wird der EventLog-Dienst auf dem lokalen Computer gestartet. Mit dem **Name** -Parameter wird der Dienst anhand seines Dienst namens identifiziert.

```powershell
Start-Service -Name "eventlog"
```

### Beispiel 2: Anzeigen von Informationen, ohne einen Dienst zu starten

Dieses Beispiel zeigt, was geschieht, wenn Sie die Dienste mit einem anzeigen Amen gestartet haben, der "Remote" enthält.

```powershell
Start-Service -DisplayName *remote* -WhatIf
```

Der **DisplayName** -Parameter identifiziert die Dienste anhand ihres anzeigen Amens anstelle des Dienst namens. Der **WhatIf** -Parameter bewirkt, dass das Cmdlet anzeigt, was passieren würde, wenn Sie den Befehl ausführen, aber keine Änderungen vornehmen.

### Beispiel 3: Starten Sie einen Dienst, und notieren Sie die Aktion in einer Textdatei.

In diesem Beispiel wird der Windows-Verwaltungsinstrumentation (WMI)-Dienst auf dem Computer gestartet, und der services.txt-Datei wird ein Datensatz der Aktion hinzugefügt.

```powershell
$s = Get-Service wmi
Start-Service -InputObject $s -PassThru | Format-List >> services.txt
```

Zuerst wird verwendet `Get-Service` , um ein Objekt zu erhalten, das den WMI-Dienst darstellt, und in der `$s` Variablen gespeichert. Als nächstes starten wir den Dienst. Ohne den **passthru** -Parameter `Start-Service` erstellt keine Ausgabe. Der Pipeline Operator (|) übergibt die Objekt Ausgabe an `Start-Service` das `Format-List` Cmdlet, um das Objekt als Liste seiner Eigenschaften zu formatieren. Der Anfüge Weiterleitungs Operator ( \> \> ) leitet die Ausgabe an die services.txt Datei um. Die Ausgabe wird am Ende der vorhandenen Datei hinzugefügt.

### Beispiel 4: Starten eines deaktivierten Dienstanbieter

Dieses Beispiel zeigt, wie ein Dienst gestartet wird, wenn der Starttyp des Dienstanbieter **deaktiviert** ist.

```
PS> Start-Service tlntsvr
Start-Service : Service 'Telnet (TlntSvr)' cannot be started due to the following error: Cannot start service TlntSvr on computer '.'.
At line:1 char:14
+ Start-Service  <<<< tlntsvr

PS> Get-CimInstance win32_service | Where-Object Name -eq "tlntsvr"
ExitCode  : 0
Name      : TlntSvr
ProcessId : 0
StartMode : Disabled
State     : Stopped
Status    : OK

PS> Set-Service tlntsvr -StartupType manual
PS> Start-Service tlntsvr
```

Beim ersten Versuch, den Telnet-Dienst (tlnzvr) zu starten, tritt ein Fehler auf. Der `Get-CimInstance` Befehl zeigt, dass die **StartMode** -Eigenschaft des tlnzvr-diensdienstanbieter **deaktiviert** ist. Mit dem- `Set-Service` Cmdlet wird der Starttyp in **manuell** geändert. Nun können wir den Befehl erneut übermitteln `Start-Service` . Dieses Mal wird der Befehl ohne Fehler verarbeitet. Führen Sie aus, um zu überprüfen, ob der Befehl erfolgreich war `Get-Service`

## PARAMETERS

### -DisplayName

Gibt die anzeigen amen der zu startenden Dienste an. Platzhalterzeichen sind zulässig.

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

Gibt die Dienste an, die von diesem Cmdlet ausgelassen werden. Der Wert dieses Parameters qualifiziert den **Name** -Parameter. Geben Sie ein Namenselement oder-Muster ein, z `s*` . b.. Platzhalterzeichen sind zulässig.

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

Gibt die Dienste an, die von diesem Cmdlet gestartet werden. Der Wert dieses Parameters qualifiziert den **Name** -Parameter. Geben Sie ein Namenselement oder-Muster ein, z `s*` . b.. Platzhalterzeichen sind zulässig.

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

Gibt **ServiceController** -Objekte an, die die zu startenden Dienste darstellen. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die Dienstnamen für die zu startenden Dienste an.

Der Parametername ist optional. Sie können " **Name** " oder den zugehörigen Alias " **Service** Name" verwenden, oder Sie können den Parameternamen weglassen.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Gibt ein Objekt zurück, das den Dienst darstellt. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### System. ServiceProcess. ServiceController, System. String

Sie können Objekte, die die Dienstnamen enthalten, über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine, System. ServiceProcess. ServiceController

Dieses Cmdlet generiert ein **System. ServiceProcess. ServiceController** -Objekt, das den Dienst darstellt, wenn Sie **passthru** angeben. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* Sie können auch auf den `Start-Service` integrierten Alias verweisen `sasv` . Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
* `Start-Service` Dienste können nur von gesteuert werden, wenn der aktuelle Benutzer über die entsprechende Berechtigung verfügt. Wenn ein Befehl nicht ordnungsgemäß verarbeitet wird, verfügen Sie u. U. nicht über die erforderlichen Berechtigungen.
* Geben Sie ein, um die Dienstnamen und anzeigen amen der Dienste auf dem System zu suchen `Get-Service` .
  Die Dienstnamen werden in der Spalte **Name** angezeigt, und die anzeigen Amen werden in der Spalte **Display Name** angezeigt.
* Sie können nur die Dienste starten, die den Starttyp manuell, automatisch oder automatisch (verzögerter Start) aufweisen. Sie können keine Dienste starten, die den Starttyp "deaktiviert" aufweisen. Wenn ein `Start-Service` Befehl mit der Meldung fehlschlägt `Cannot start service \<service-name\> on computer` , verwenden `Get-CimInstance` Sie, um den Starttyp des Dienstanbieter zu suchen, und verwenden Sie ggf. das `Set-Service` Cmdlet, um den Starttyp des Dienstanbieter zu ändern.
* Einige Dienste, beispielsweise der Dienst für Leistungsprotokolle und -warnungen (SysmonLog), werden automatisch beendet, wenn sie keine Vorgänge ausführen müssen. Wenn PowerShell einen Dienst startet, der sich fast sofort beendet, wird die folgende Meldung angezeigt: `Service \<display-name\> start failed.`

## VERWANDTE LINKS

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)

