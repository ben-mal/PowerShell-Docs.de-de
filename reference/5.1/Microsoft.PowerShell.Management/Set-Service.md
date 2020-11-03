---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: df4fda68508e21700235d2b772c6dd43c8e1fe1e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214415"
---
# Set-Service

## ZUSAMMENFASSUNG
Startet, beendet und hält einen Dienst an und ändert seine Eigenschaften.

## SYNTAX

### Name (Standard)

```
Set-Service [-ComputerName <String[]>] [-Name] <String> [-DisplayName <String>]
 [-Description <String>] [-StartupType <ServiceStartMode>] [-Status <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject

```
Set-Service [-ComputerName <String[]>] [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Status <String>] [-InputObject <ServiceController>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Set-Service` Cmdlet ändert die Eigenschaften eines Dienstanbieter, z. b. **Status** , **Beschreibung** , **Display Name** und **startupType** . `Set-Service` ein Dienst kann gestartet, beendet, angehalten oder angehalten werden. Um einen Dienst zu identifizieren, geben Sie seinen Dienstnamen ein, oder übermitteln Sie ein Dienst Objekt. Oder senden Sie einen Dienstnamen oder ein Dienst Objekt über die Pipeline an `Set-Service` .

## BEISPIELE

### Beispiel 1: Ändern eines anzeigen Amens

In diesem Beispiel wird der Anzeige Name eines dienstaners geändert. Verwenden Sie, um den ursprünglichen anzeigen Amen anzuzeigen `Get-Service` .

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

`Set-Service` verwendet den **Name** -Parameter, um den Namen des dienstanders ( **LanmanWorkstation** ) anzugeben. Der **DisplayName** -Parameter gibt den neuen anzeigen Amen, **LanMan Workstation** , an.

### Beispiel 2: Ändern des Starttyps der Dienste

In diesem Beispiel wird gezeigt, wie der Starttyp eines dienstaners geändert wird.

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

`Set-Service` verwendet den **Name** -Parameter zum Angeben des Dienst namens ( **Bits** ). Der **startupType** -Parameter legt den Dienst auf " **automatisch** " fest.

`Get-Service` verwendet den **Name** -Parameter, um den **Bits** -Dienst anzugeben, und sendet das Objekt über die Pipeline. `Select-Object` verwendet den **Property** -Parameter, um den **Bits** -Dienststatus anzuzeigen.

### Beispiel 3: Ändern der Beschreibung eines Dienstanbieter

In diesem Beispiel wird die Beschreibung des Bits-diendienstanders geändert und das Ergebnis angezeigt.

Das- `Get-CimInstance` Cmdlet wird verwendet, da es ein **Win32_Service** Objekt zurückgibt, das **die Beschreibung** des dienstaners enthält.

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

`Get-CimInstance` sendet das Objekt über die Pipeline an `Format-List` und zeigt den Namen und die Beschreibung des dienstanders an. Zu Vergleichszwecken wird der Befehl vor und nach dem Aktualisieren der Beschreibung ausgeführt.

`Set-Service` verwendet den **Name** -Parameter, um den **Bits** -Dienst anzugeben. Der **Description** -Parameter gibt den aktualisierten Text für die Beschreibung der Dienste an.

### Beispiel 4: Starten eines Dienstanbieter

In diesem Beispiel wird ein-Dienst gestartet.

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

`Set-Service` verwendet den **Name** -Parameter, um den Dienst ( **WinRM** ) anzugeben. Der **Status** Parameter verwendet den-Wert, der **ausgeführt** wird, um den Dienst zu starten. Der **passthru** -Parameter gibt ein **ServiceController** -Objekt aus, das die Ergebnisse anzeigt.

### Beispiel 5: aussetzen eines Dienstanbieter

In diesem Beispiel wird die Pipeline verwendet, um den Dienst anzuhalten.

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

`Get-Service` verwendet den **Name** -Parameter, um den Zeit **Plan** Dienst anzugeben, und sendet das Objekt über die Pipeline. `Set-Service` verwendet den **Status** Parameter, um den Dienst auf **angeh** alten festzulegen.

### Beispiel 6: Dienst Beendigung

In diesem Beispiel wird eine-Variable verwendet, um einen Dienst zu verhindern.

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

`Get-Service` verwendet den **Name** -Parameter, um den Dienst ( **Schedule** ) anzugeben. Das-Objekt wird in der-Variable gespeichert `$S` . `Set-Service` verwendet den **Inputobject** -Parameter und gibt das gespeicherte Objekt an `$S` . Der **Status** Parameter legt den Dienst auf " **beendet** " fest.

## PARAMETERS

### -ComputerName

Gibt Computer an. Geben Sie für Remote Computer den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen ein. Wenn der **Computername** -Parameter nicht angegeben wird, wird der Befehl auf dem lokalen Computer ausgeführt.

Dieser Parameter beruht nicht auf PowerShell-Remoting. Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Set-Service` .

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

### -Description

Gibt eine neue Beschreibung für den Dienst an.

Die Dienst Beschreibung wird in **Computer Verwaltung, Dienste** angezeigt. Die **Beschreibung** ist keine Eigenschaft des `Get-Service` **ServiceController** -Objekts. Um die Dienst Beschreibung anzuzeigen, verwenden Sie `Get-CimInstance` , die ein **Win32_Service** Objekt zurückgibt, das den Dienst darstellt.

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

### -DisplayName

Gibt einen neuen Anzeigenamen für den Dienst an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt ein **ServiceController** -Objekt an, das den zu ändernden Dienst darstellt. Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl oder Ausdruck ein, der das Objekt abruft, z `Get-Service` . b. einen Befehl. Sie können die Pipeline verwenden, um ein Dienst Objekt an zu senden `Set-Service` .

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt den Dienstnamen des zu ändernden Diensts an. Platzhalter Zeichen sind nicht zulässig. Sie können die Pipeline verwenden, um einen Dienstnamen an zu senden `Set-Service` .

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Gibt ein **ServiceController** -Objekt zurück, das die geänderten Dienste darstellt. Standardmäßig `Set-Service` generiert keine Ausgabe.

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

### -StartupType

Legt den Starttyp des Diensts fest. Zulässige Werte für diesen Parameter:

- **Automatisch** : der Dienst wurde gestartet oder vom Betriebssystem beim Systemstart gestartet.
  Wenn ein automatisch gestarteter Dienst von einem manuell gestarteten Dienst abhängig ist, wird der manuell gestartete Dienst beim Systemstart ebenfalls automatisch gestartet.
- **Deaktiviert** : der Dienst ist deaktiviert und kann nicht von einem Benutzer oder einer Anwendung gestartet werden.
- **Manuell: der** Dienst wird nur manuell von einem Benutzer, über den Dienststeuerungs-Manager oder durch eine Anwendung gestartet.
- **Boot** : gibt an, dass der Dienst ein Gerätetreiber ist, der vom System Lade Modul gestartet wurde. Dieser Wert gilt nur für Gerätetreiber.
- **System** : gibt an, dass es sich bei dem Dienst um einen Gerätetreiber handelt, der von der IoInitSystem ()-Funktion gestartet wurde. Dieser Wert gilt nur für Gerätetreiber.

 Der Standardwert ist **automatisch** .

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status

Gibt den Status für den Dienst an.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- **Angeh** alten. Hält den Dienst an.
- **Wird ausgeführt** . Startet den Dienst.
- **Stopped** (Beendet): Dies ist der anfängliche Status des Kanals nach seiner Erstellung (es sei denn, im Portal wurde das automatische Starten gewählt). Beendet den Dienst.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn ausgeführt wird `Set-Service` . Das Cmdlet wird nicht ausgeführt.

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

Sie können die Pipeline verwenden, um ein Dienst Objekt oder eine Zeichenfolge, die einen Dienstnamen enthält, an zu senden `Set-Service` .

## AUSGABEN

### System.ServiceProcess.ServiceController

Standardmäßig `Set-Service` gibt keine-Objekte zurück. Verwenden Sie den **passthru** -Parameter, um ein **ServiceController** -Objekt auszugeben.

## HINWEISE

`Set-Service` erfordert erweiterte Berechtigungen. Verwenden Sie die Option **als Administrator ausführen** .

`Set-Service` Es können nur Dienste gesteuert werden, wenn der aktuelle Benutzer über Berechtigungen zum Verwalten von Diensten verfügt. Wenn ein Befehl nicht ordnungsgemäß funktioniert, verfügen Sie möglicherweise nicht über die erforderlichen Berechtigungen.

Verwenden Sie, um den Dienstnamen oder anzeigen Amen eines Dienstanbieter zu suchen `Get-Service` . Die Dienstnamen befinden sich in der Spalte **Name** und die anzeigen Amen in der Spalte **Display Name** .

## VERWANDTE LINKS

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
