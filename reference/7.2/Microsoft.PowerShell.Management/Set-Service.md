---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: 0c6cac03f1acbda35069780f0c53eaf6685813ff
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601318"
---
# Set-Service

## ZUSAMMENFASSUNG
Startet, beendet und hält einen Dienst an und ändert seine Eigenschaften.

## SYNTAX

### Name (Standard)

```
Set-Service [-Name] <String> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>]
 [-SecurityDescriptorSddl <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Set-Service [-InputObject] <ServiceController> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-SecurityDescriptorSddl <String>]
 [-Status <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Set-Service` Cmdlet ändert die Eigenschaften eines Dienstanbieter, z. b. **Status**, **Beschreibung**, **Display Name** und **startupType**. `Set-Service` ein Dienst kann gestartet, beendet, angehalten oder angehalten werden. Um einen Dienst zu identifizieren, geben Sie seinen Dienstnamen ein, oder übermitteln Sie ein Dienst Objekt. Oder senden Sie einen Dienstnamen oder ein Dienst Objekt über die Pipeline an `Set-Service` .

## BEISPIELE

### Beispiel 1: Ändern eines anzeigen Amens

In diesem Beispiel wird der Anzeige Name eines dienstaners geändert. Verwenden Sie, um den ursprünglichen anzeigen Amen anzuzeigen `Get-Service` .

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

`Set-Service` verwendet den **Name** -Parameter, um den Namen des dienstanders ( **LanmanWorkstation**) anzugeben. Der **DisplayName** -Parameter gibt den neuen anzeigen Amen, **LanMan Workstation**, an.

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

`Set-Service` verwendet den **Name** -Parameter zum Angeben des Dienst namens ( **Bits**). Der **startupType** -Parameter legt den Dienst auf " **automatisch**" fest.

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

`Set-Service` verwendet den **Name** -Parameter, um den Dienst ( **WinRM**) anzugeben. Der **Status** Parameter verwendet den-Wert, der **ausgeführt** wird, um den Dienst zu starten. Der **passthru** -Parameter gibt ein **ServiceController** -Objekt aus, das die Ergebnisse anzeigt.

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

`Get-Service` verwendet den **Name** -Parameter, um den Dienst ( **Schedule**) anzugeben. Das-Objekt wird in der-Variable gespeichert `$S` . `Set-Service` verwendet den **Inputobject** -Parameter und gibt das gespeicherte Objekt an `$S` . Der **Status** Parameter legt den Dienst auf " **beendet**" fest.

### Beispiel 7: Beendigung eines Dienstanbieter auf einem Remote System

In diesem Beispiel wird ein Dienst auf einem Remote Computer angehalten.
Weitere Informationen finden Sie unter " [aufrufen-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".

```powershell
$Cred = Get-Credential
$S = Get-Service -Name Schedule
Invoke-Command -ComputerName server01.contoso.com -Credential $Cred -ScriptBlock {
  Set-Service -InputObject $S -Status Stopped
}
```

`Get-Credential` fordert zur Eingabe eines Benutzernamens und Kennworts auf und speichert die Anmelde Informationen in der `$Cred` Variablen. `Get-Service` verwendet den **Name** -Parameter, um den Zeit **Plan** Dienst anzugeben. Das-Objekt wird in der-Variable gespeichert `$S` .

`Invoke-Command` verwendet den **Computername** -Parameter, um einen Remote Computer anzugeben. Der **Credential** -Parameter verwendet die- `$Cred` Variable, um sich am Computer anzumelden. Der **ScriptBlock** Ruft auf `Set-Service` . Der **Inputobject** -Parameter gibt das gespeicherte Dienst Objekt an `$S` . Der **Status** Parameter legt den Dienst auf " **beendet**" fest.

### Beispiel 8: Ändern der Anmelde Informationen eines Dienstanbieter

In diesem Beispiel werden die Anmelde Informationen geändert, die zum Verwalten eines Dienstanbieter verwendet werden.

```powershell
$credential = Get-Credential
Set-Service -Name Schedule -Credential $credential
```

`Get-Credential` fordert zur Eingabe eines Benutzernamens und Kennworts auf und speichert die Anmelde Informationen in der `$credential` Variablen. `Set-Service` verwendet den **Name** -Parameter, um den Zeit **Plan** Dienst anzugeben. Der **Credential** -Parameter verwendet die `$credential` -Variable und aktualisiert den Zeit **Plan** Dienst.

### Beispiel 9: Ändern des securitydescriptors eines Dienstanbieter

In diesem Beispiel wird der **securityDescriptor** eines dienstanders geändert.

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
Set-Service -Name "BITS" -SecurityDescriptorSddl $SDDL
```

Der **securityDescriptor** wird in der `$SDDL` Variablen gespeichert. `Set-Service` verwendet den **Name** -Parameter, um den **Bits** -Dienst anzugeben. Der **securitydescriptorsddl** -Parameter verwendet `$SDDL` , um den **securityDescriptor** für den **Bits** -Dienst zu ändern.

## PARAMETERS

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

### -Credential

Gibt das Konto an, das vom Dienst als [Dienst Anmelde Konto](/windows/desktop/ad/about-service-logon-accounts)verwendet wird.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt. Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

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

### -Force

Gibt den Stoppmodus des Dienstanbieter an. Dieser Parameter funktioniert nur, wenn `-Status Stopped` verwendet wird. Wenn diese Option aktiviert ist, werden `Set-Service` die abhängigen Dienste beendet, bevor der Ziel Dienst beendet wird. Standardmäßig werden Ausnahmen ausgelöst, wenn andere laufende Dienste vom Ziel Dienst abhängen.

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

### -InputObject

Gibt ein **ServiceController** -Objekt an, das den zu ändernden Dienst darstellt. Geben Sie eine Variable ein, die das Objekt enthält, oder geben Sie einen Befehl oder Ausdruck ein, der das Objekt abruft, z `Get-Service` . b. einen Befehl. Sie können die Pipeline verwenden, um ein Dienst Objekt an zu senden `Set-Service` .

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
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

Gibt den Startmodus des Diensts an

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- **Automatisch** : der Dienst wurde gestartet oder vom Betriebssystem beim Systemstart gestartet.
  Wenn ein automatisch gestarteter Dienst von einem manuell gestarteten Dienst abhängig ist, wird der manuell gestartete Dienst beim Systemstart ebenfalls automatisch gestartet.
- **Automaticdelayedstart** : startet kurz nach dem Systemstart.
- **Deaktiviert** : der Dienst ist deaktiviert und kann nicht von einem Benutzer oder einer Anwendung gestartet werden.
- **Invalidvalue** : hat keine Auswirkung. Das Cmdlet gibt keinen Fehler zurück, aber der startupType des Dienstanbieter wird nicht geändert.
- **Manuell: der** Dienst wird nur manuell von einem Benutzer, über den Dienststeuerungs-Manager oder durch eine Anwendung gestartet.

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases: StartMode, SM, ST, StartType
Accepted values: Automatic, AutomaticDelayedStart, Disabled, InvalidValue, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status

Gibt den Status für den Dienst an.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- **Angeh** alten. Hält den Dienst an.
- **Wird ausgeführt**. Startet den Dienst.
- **Stopped**(Beendet): Dies ist der anfängliche Status des Kanals nach seiner Erstellung (es sei denn, im Portal wurde das automatische Starten gewählt). Beendet den Dienst.

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

### -SecurityDescriptor SDDL

Gibt den **securityDescriptor** für den Dienst im **SDDL** -Format an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sd

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

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

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

[Remove-Service](Remove-Service.md)
