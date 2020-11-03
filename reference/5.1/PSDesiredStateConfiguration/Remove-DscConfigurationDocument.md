---
external help file: Remove-DscConfigurationDocument.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DscConfigurationDocument
ms.openlocfilehash: d3e9b15dfeea94921503247adc08b291eed9d7d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215300"
---
# Remove-DscConfigurationDocument

## ZUSAMMENFASSUNG
Entfernt ein Konfigurations Dokument aus dem DSC-Konfigurations Speicher.

## SYNTAX

```
Remove-DscConfigurationDocument -Stage <Stage> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mit dem- `Remove-DscConfigurationDocument` Cmdlet wird ein Konfigurations Dokument (. MOF-Datei) aus dem Konfigurations Speicher für Windows PowerShell DSC (DSC) entfernt.
Während der Konfiguration `Start-DscConfiguration` kopiert das Cmdlet eine MOF-Datei in einen Ordner auf dem Zielcomputer.
Dieses Cmdlet entfernt dieses Konfigurations Dokument und führt zusätzliche Bereinigung durch.

Dieses Cmdlet ist nur als Teil des Updaterollup vom [November 2014 für Windows RT 8,1, Windows 8.1 und Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) aus der Microsoft-Support-Bibliothek verfügbar.

## BEISPIELE

### Beispiel 1: Entfernen des aktuellen Konfigurations Dokuments

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Remove-DscConfigurationDocument -Stage Current -CimSession $Session
```

Der erste Befehl erstellt eine CIM-Sitzung mithilfe des Cmdlets **New-CimSession** und speichert dann das **CimSession** -Objekt in der Variable $Session.
Der Befehl fordert Sie zur Eingabe eines Kennworts auf.
Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help New-CimSession`.

Mit dem zweiten Befehl wird das aktuelle Konfigurations Dokument für den Computer entfernt, der in der in $Session gespeicherten **cimsession** angegeben ist.

## PARAMETERS

### -AsJob
Gibt an, dass dieses Cmdlet den Befehl als Hintergrund Auftrag ausführt.

Wenn Sie den *AsJob* -Parameter angeben, gibt der Befehl ein Objekt zurück, das den Auftrag darstellt, und zeigt dann die Eingabeaufforderung an.
Sie können die Arbeit in der Sitzung fortsetzen, bis der Auftrag abgeschlossen ist.
Der Auftrag wird auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben.
Um den Auftrag zu verwalten, verwenden Sie die Job-Cmdlets.
Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet %%amp;quot;Receive-Job%%amp;quot;.

Um diesen Parameter verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein. unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie Windows PowerShell mit der Option als Administrator ausführen öffnen.
Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).

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

### -CimSession
Führt das Cmdlet in einer Remotesitzung oder auf einem Remotecomputer aus.
Geben Sie einen Computernamen oder ein Sitzungs Objekt ein, z. b. die Ausgabe eines Cmdlets " **New-cimsession** " oder " **Get-cimsession** ".

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

### -Force
Gibt an, dass dieses Cmdlet den laufenden Konfigurations Auftrag beendet, bevor das Konfigurations Dokument entfernt wird.
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

### -Phase
Gibt an, welches Konfigurationsdokument entfernt werden soll.
Sie können mehrere Dokumente angeben.
Zulässige Werte für diesen Parameter:

- Aktuell.
Entfernen Sie das Konfigurations Dokument, das den aktuellen Status des Systems beschreibt.
- Ausstehend.
Entfernen Sie das Konfigurations Dokument, das den ausstehenden Status des Systems beschreibt.
- Vorherige
Entfernen Sie das Konfigurations Dokument, das den vorherigen Zustand des Systems beschreibt.

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoveDscConfigurationDocument.Stage
Parameter Sets: (All)
Aliases:
Accepted values: Current, Pending, Previous

Required: True
Position: Named
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

### Keine

## AUSGABEN

### Keine

## HINWEISE

## VERWANDTE LINKS

[Windows PowerShell DSC – Übersicht](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)
