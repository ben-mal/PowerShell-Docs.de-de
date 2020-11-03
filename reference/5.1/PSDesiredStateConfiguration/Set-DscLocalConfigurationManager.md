---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 04/29/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/set-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DscLocalConfigurationManager
ms.openlocfilehash: 0d35aa56a52f0e6c17abd0e7b2707869e780324c
ms.sourcegitcommit: 0d4d3e47f6979876550591f62061096e7a568f7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "93218015"
---
# Set-DscLocalConfigurationManager

## ZUSAMMENFASSUNG

Wendet lokale Configuration Manager Einstellungen (LCM) auf Knoten an.

## SYNTAX

### Computernameset (Standard)

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Cimsessionset

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-DscLocalConfigurationManager` Cmdlet werden die LCM-Einstellungen oder die metakonfiguration auf Knoten angewendet. Geben Sie Computer an, indem Sie Computernamen angeben oder CIM-Sitzungen (Common Information Model) verwenden. Wenn Sie keinen Zielcomputer angeben, wendet das Cmdlet Einstellungen auf dem lokalen Computer an.

## BEISPIELE

### Beispiel 1: Anwenden von LCM-Einstellungen

```
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\"
```

Mit diesem Befehl werden die LCM-Einstellungen von `C:\DSC\Configurations\` auf die Zielknoten angewendet. Nach dem Empfang der Einstellungen werden diese vom LCM verarbeitet.

> [!WARNING]
> Wenn mehrere Meta-Mappen für denselben Computer vorhanden sind, die im angegebenen Ordner gespeichert sind, wird nur die erste Meta-of-Datei angewendet.

### Beispiel 2: Anwenden von LCM-Einstellungen mithilfe einer CIM-Sitzung

```
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\" -CimSession $Session
```

In diesem Beispiel werden die LCM-Einstellungen auf einen Computer angewendet, und die Einstellungen werden angewendet. Das Beispiel erstellt eine CIM-Sitzung für einen Computer namens Server01 zur Verwendung mit dem Cmdlet. Erstellen Sie alternativ ein Array von CIM-Sitzungen, um das Cmdlet für mehrere angegebene Computer anzuwenden.

Der erste Befehl erstellt eine CIM-Sitzung mit dem `New-CimSession` Cmdlet und speichert dann das **cimsession** -Objekt in der `$Session` Variablen. Der Befehl fordert Sie zur Eingabe eines Kennworts auf. Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.

Mit dem zweiten Befehl werden die LCM-Einstellungen für den Zielknoten von `C:\DSC\Configurations\` auf den Computer angewendet, der durch die in der Variablen gespeicherten **cimsession** -Objekte identifiziert wird `$Session` . In diesem Beispiel enthält die `$Session` Variable nur eine CIM-Sitzung für den Computer namens SERVER01. Der Befehl wendet die Einstellungen an. Nach dem Empfang der Einstellungen werden diese vom LCM verarbeitet.

## PARAMETERS

### -CimSession

Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus. Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " [New-cimsession](/powershell/module/CimCmdlets/New-CimSession) " oder " [Get-cimsession](/powershell/module/CimCmdlets/Get-CimSession) ".
Der Standardwert ist die aktuelle Sitzung auf dem lokalen Computer.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName

Gibt ein Array von Computernamen an. Dieser Parameter schränkt die Computer mit metakonfigurationsdokumenten im **path** -Parameter auf die im-Array angegebenen ein.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential

Gibt einen Benutzernamen und ein Kennwort als ein **PSCredential** -Objekt für den Zielcomputer an. Zum Abrufen eines **PSCredential** -Objekts verwenden Sie das Get-Credential-Cmdlet. Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help Get-Credential`.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt einen Dateipfad eines Ordners an, der Dateien mit den Konfigurationseinstellungen enthält. Das Cmdlet veröffentlicht diese LCM-Einstellungen und wendet Sie auf Computern an, die im angegebenen Pfad über Einstellungsdateien verfügen. Jeder Zielknoten muss eine Einstellungsdatei im folgenden Format aufweisen: `NetBIOS Name.meta.mof` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Gibt die maximale Anzahl von gleichzeitigen Vorgängen an, die zum Ausführen des Cmdlets erstellt werden können. Wenn dieser Parameter ausgelassen wird oder der Wert `0` eingegeben wird, berechnet Windows PowerShell basierend auf der Anzahl der CIM-Cmdlets, die auf dem Computer ausgeführt werden, eine optimale Drosselungs Grenze für das Cmdlet. Dieser Drosselungsgrenzwert gilt nur für das aktuelle Cmdlet, nicht für die Sitzung oder den PC.

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

[Get-DscLocalConfigurationManager](Get-DscLocalConfigurationManager.md)
