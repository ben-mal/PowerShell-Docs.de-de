---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/start-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DscConfiguration
ms.openlocfilehash: c34754aeb7fce99030cf4ddb235e3e7e8161f3eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215287"
---
# Start-DscConfiguration

## ZUSAMMENFASSUNG
Wendet die Konfiguration auf Knoten an.

## SYNTAX

### Computernameandpathset (Standard)

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Cimsessionandpathset

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] -CimSession <CimSession[]> [-ThrottleLimit <Int32>]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Computernameanduseexistingset

```
Start-DscConfiguration [-Wait] [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-UseExisting] [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Cimsessionanduseexistingset

```
Start-DscConfiguration [-Wait] [-Force] -CimSession <CimSession[]> [-ThrottleLimit <Int32>] [-UseExisting]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das Cmdlet **Start-DscConfiguration** wendet die Konfiguration auf Knoten an.
Bei Verwendung mit dem Parameter *useexistierenden* wird die vorhandene Konfiguration auf dem Bereitstellungs Zielcomputer angewendet.
Geben Sie an, auf welche Computer Sie die Konfiguration anwenden möchten, indem Sie Computernamen angeben oder Common Information Model (CIM)-Sitzungen verwenden.

Standardmäßig erstellt dieses Cmdlet ein Auftrag und gibt ein **Job** Objekt zurück.
Weitere Informationen zu Hintergrund Aufträgen erhalten Sie, wenn Sie eingeben `Get-Help about_Jobs` .
Geben Sie den Parameter *Wait* an, um dieses Cmdlet interaktiv zu verwenden.

Geben Sie den Parameter *Verbose* an, um Details dazu anzuzeigen, was das Cmdlet durchführt, wenn es Konfigurationseinstellungen anwendet.

## BEISPIELE

### Beispiel 1: Anwenden von Konfigurationseinstellungen

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\"
```

Dieser Befehl wendet die Konfigurationseinstellungen von C:\DSC\Configurations\ auf alle Computer an, die über Einstellungen in diesem Ordner verfügen.
Der Befehl gibt **Job** -Objekte für jeden Zielknoten zurück, an den bereitgestellt wird.

### Beispiel 2: Anwenden von Konfigurationseinstellungen und warten auf den Abschluss der Konfiguration

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -Wait -Verbose
```

Dieser Befehl wendet die Konfiguration von C:\DSC\Configurations\ auf dem lokalen Computer an.
Der Befehl gibt **Job** -Objekte für jeden Zielknoten zurück, an den bereitgestellt wird, in diesem Fall nur für den lokalen Computer.
In diesem Beispiel wird der *verbose* -Parameter angegeben.
Daher sendet der Befehl Nachrichten an die Konsole, während er fortgesetzt wird.
Der Befehl enthält den *Wait* -Parameter.
Daher können Sie die Konsole erst verwenden, wenn der Befehl alle Konfigurationsaufgaben abgeschlossen hat.

### Beispiel 3: Anwenden von Konfigurationseinstellungen mithilfe einer CIM-Sitzung

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -CimSession $Session
```

In diesem Beispiel werden die Konfigurationseinstellungen für einen bestimmten Computer angewendet.
Das Beispiel erstellt eine CIM-Sitzung für einen Computer namens Server01 zur Verwendung mit dem Cmdlet.
Erstellen Sie alternativ ein Array von CIM-Sitzungen, um das Cmdlet für mehrere angegebene Computer anzuwenden.

Der erste Befehl erstellt eine CIM-Sitzung mithilfe des Cmdlets **New-CimSession** und speichert dann das **CimSession** -Objekt in der Variable $Session.
Der Befehl fordert Sie zur Eingabe eines Kennworts auf.
Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help NewCimSession`.

Mit dem zweiten Befehl werden die Konfigurationseinstellungen von c:\dsc\configurations\ auf die Computer angewendet, die von den in der $Session Variablen gespeicherten **cimsession** -Objekten identifiziert werden.
In diesem Beispiel enthält die Variable $Session eine CIM-Sitzung nur für den Computer namens Server01.
Der Befehl wendet die Konfiguration an.
Der Befehl erstellt **Job** -Objekte für jeden konfigurierten Computer.

## PARAMETERS

### -CimSession
Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.
Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/cimcmdlets/new-cimsession) " oder " [Get-cimsession](/powershell/module/cimcmdlets/get-cimsession) ".
Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Gibt ein Array von Computernamen an.
Dieser Parameter schränkt die Computer mit Konfigurations Dokumenten im *path* -Parameter auf die im-Array angegebenen ein.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Gibt einen Benutzernamen und ein Kennwort als ein **PSCredential** -Objekt für den Zielcomputer an.
Zum Abrufen eines **PSCredential** -Objekts verwenden Sie das Get-Credential-Cmdlet.
Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Get-Credential`.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Beendet den derzeit auf dem Bereitstellungs Zielcomputer laufenden Konfigurations Vorgang und startet den neuen Start-Configuration Vorgang.
Wenn die Eigenschaft " **erfrischendes Modus** " des lokalen Configuration Manager auf " **Pull** " festgelegt ist, wird Sie durch Angabe dieses Parameters in **Push** geändert.

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

### -Jobname
Gibt einen Anzeigenamen für einen Auftrag an.
Wenn Sie diesen Parameter angeben, wird das Cmdlet Auftrag ausgeführt und gibt ein **Job** -Objekt zurück.

Standardmäßig weist Windows PowerShell den Namen jobn zu, wobei N eine ganze Zahl ist.

Wenn Sie den Parameter *Wait* angeben, geben Sie diesen Parameter nicht an.

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

### -Path
Gibt einen Dateipfad eines Ordners an, der Dateien mit den Konfigurationseinstellungen enthält.
Dieses Cmdlet veröffentlicht diese Konfigurationseinstellungen und wendet Sie auf Computern an, die im angegebenen Pfad über Einstellungsdateien verfügen.
Jeder Zielknoten muss über eine Einstellungsdatei im folgenden Format verfügen: NetBIOS Name. mof.

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können.
Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet.
Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.

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

### -Useexistierenden
Gibt an, dass dieses Cmdlet die vorhandene Konfiguration anwendet.
Die Konfiguration kann auf dem Bereitstellungs Zielcomputer mithilfe von **Start-dscconfiguration** oder Veröffentlichung mithilfe des Publish-DscConfiguration-Cmdlets auf dem Zielcomputer vorhanden sein.

Bevor Sie diesen Parameter für dieses Cmdlet angeben, überprüfen Sie die Informationen unter [Neues in Windows PowerShell 5,0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameAndUseExistingSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait
Gibt an, dass das Cmdlet die Konsole blockiert, bis alle Konfigurationsaufgaben abgeschlossen sind.

Wenn Sie diesen Parameter angeben, geben Sie den Parameter *JobName* nicht an.

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

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[Windows PowerShell DSC – Übersicht](/powershell/scripting/dsc/overview/overview)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Stop-DscConfiguration](Stop-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)

[Update-DscConfiguration](Update-DscConfiguration.md)
