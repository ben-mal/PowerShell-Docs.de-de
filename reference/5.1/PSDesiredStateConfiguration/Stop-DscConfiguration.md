---
external help file: Stop-DscConfiguration.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/19/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/stop-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DscConfiguration
ms.openlocfilehash: 93c8585ae948dfa360a2ae8e2563670de8fd6e93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213599"
---
# Stop-DscConfiguration

## ZUSAMMENFASSUNG
Beendet einen Konfigurations Auftrag, der ausgeführt wird.

## SYNTAX

### Alle

```
Stop-DscConfiguration [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Stop-DscConfiguration` Cmdlet wird ein Konfigurations Auftrag angehalten, auf dem ausgeführt wird. Legen Sie mithilfe von Common Information Model (CIM)-Sitzungen fest, auf welche Computer dieses Cmdlet angewendet wird. Wenn kein Konfigurations Auftrag ausgeführt wird, gibt dieses Cmdlet eine Warnmeldung zurück.

`Stop-DscConfiguration` ist nur als Teil des Updaterollup vom [November 2014 für Windows RT 8,1, Windows 8.1 und Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) aus der Microsoft-Support-Bibliothek verfügbar. Bevor Sie dieses Cmdlet verwenden, lesen Sie die Informationen unter [Neues in Windows PowerShell 5,0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)

## BEISPIELE

### Beispiel 1: Abbrechen eines Konfigurations Auftrags

In diesem Beispiel wird eine CIM-Sitzung mithilfe des `New-CimSession` Cmdlets erstellt. Das **cimsession** -Objekt wird zum Abbrechen eines laufenden Konfigurations Auftrags verwendet.

```powershell
$Session = New-CimSession -ComputerName Server01 -Credential ACCOUNTS\User01
Stop-DscConfiguration -CimSession $Session
```

`New-CimSession` verwendet den Computer **Name** -Parameter, um den Server01-Computer anzugeben. Der **Credential** -Parameter gibt das Benutzerkonto an. Das **cimsession** -Objekt wird in der- `$Session` Variable gespeichert. Wenn der Befehl ausgeführt wird, werden Sie zur Eingabe des Kennworts für das Benutzerkonto aufgefordert.

`Stop-DscConfiguration` verwendet den **cimsession** -Parameter und das in gespeicherte-Objekt `$Session` , um den Konfigurations Auftrag zu unterbinden.

## PARAMETERS

### -AsJob

Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt. Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).

Um den **AsJob** -Parameter zu verwenden, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein. Unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option **als Administrator ausführen** öffnen. Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

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

### -CimSession

Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus. Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe von `New-CimSession` oder `Get-CimSession` .

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

`Stop-DscConfiguration` unterstützt den **Confirm** -Parameter nicht. Wenn der **Confirm** -Parameter verwendet wird, wird ein Fehler angezeigt.

Für PowerShell-Cmdlets, die **Confirm** unterstützen, werden Sie mithilfe des-Parameters zur Überprüfung aufgefordert, bevor ein Befehl ausgeführt wird.

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

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

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

### -ThrottleLimit

Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.

Wenn dieser Parameter ausgelassen wird oder wenn der Wert `0` eingegeben wird, berechnet PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze. Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.

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

## AUSGABEN

### Keine

## HINWEISE

## VERWANDTE LINKS

[Get-CimSession](../CimCmdlets/Get-CimSession.md)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[New-CimSession](../CimCmdlets/New-CimSession.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)

[Update-DscConfiguration](Update-DscConfiguration.md)

[Windows PowerShell DSC – Übersicht](/powershell/scripting/dsc/overview/overview)
