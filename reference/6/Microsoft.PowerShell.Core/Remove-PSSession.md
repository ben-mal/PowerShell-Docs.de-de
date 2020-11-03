---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSession
ms.openlocfilehash: a6b980b022672fbc84549987e1cb5673f51e3dc4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217175"
---
# Remove-PSSession

## ZUSAMMENFASSUNG
Schließt mindestens eine PowerShell-Sitzung (pssessions).

## SYNTAX

### ID (Standard)

```
Remove-PSSession [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Sitzung

```
Remove-PSSession [-Session] <PSSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ContainerId

```
Remove-PSSession -ContainerId <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMId

```
Remove-PSSession -VMId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMName

```
Remove-PSSession -VMName <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Remove-PSSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Name

```
Remove-PSSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Computername

```
Remove-PSSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das **Remove-PSSession-** Cmdlet schließt PowerShell-Sitzungen ( **pssessions** ) in der aktuellen Sitzung.
Es beendet alle Befehle, die in den **pssessions** ausgeführt werden, beendet die **PSSession** und gibt die Ressourcen frei, die von der **PSSession** verwendet wurden.
Wenn die **PSSession** mit einem Remote Computer verbunden ist, schließt dieses Cmdlet auch die Verbindung zwischen dem lokalen Computer und dem Remote Computer.

Um eine **PSSession** zu entfernen, geben Sie *Name* , *Computer Name* , *ID* oder *InstanceId* der Sitzung ein.

Wenn Sie die *PSSession* in einer Variablen gespeichert haben, bleibt das Sitzungs Objekt in der Variablen, der Status der *PSSession* ist jedoch geschlossen.

## BEISPIELE

### Beispiel 1: Entfernen von Sitzungen mithilfe von IDs

```powershell
Remove-PSSession -Id 1, 2
```

Mit diesem Befehl werden die **pssessions** mit den IDs 1 und 2 entfernt.

### Beispiel 2: Entfernen aller Sitzungen in der aktuellen Sitzung

```powershell
Get-PSSession | Remove-PSSession
Remove-PSSession -Session (Get-PSSession)
$s = Get-PSSession
Remove-PSSession -Session $s
```

Diese Befehle entfernen alle **pssessions** in der aktuellen Sitzung.
Obwohl die drei Befehlsformate anders aussehen, haben sie die gleiche Wirkung.

### Beispiel 3: Schließen von Sitzungen mithilfe von Namen

```powershell
$r = Get-PSSession -ComputerName Serv*
$r | Remove-PSSession
```

Diese Befehle schließen die **pssessions** , die mit Computern verbunden sind, deren Namen mit "Serv" beginnen.

### Beispiel 4: Schließen von Sitzungen, die mit einem Port verbunden sind

```powershell
Get-PSSession | where {$_.port -eq 90} | Remove-PSSession
```

Dieser Befehl schließt die **pssessions** , die mit Port 90 verbunden sind.
Sie können dieses Befehls Format verwenden, um **pssessions** nach anderen Eigenschaften als *Computer Name* , *Name* , *InstanceId* und *ID* zu identifizieren.

### Beispiel 5: Schließen einer Sitzung basierend auf der Instanz-ID

```powershell
Get-PSSession | Format-Table ComputerName, InstanceID  -AutoSize
```

```Output
ComputerName InstanceId
------------ ----------------
Server01     875d231b-2788-4f36-9f67-2e50d63bb82a
localhost    c065ffa0-02c4-406e-84a3-dacb0d677868
Server02     4699cdbc-61d5-4e0d-b916-84f82ebede1f
Server03     4e5a3245-4c63-43e4-88d0-a7798bfc2414
TX-TEST-01   fc4e9dfa-f246-452d-9fa3-1adbdd64ae85 PS C:\> Remove-PSSession -InstanceID fc4e9dfa-f246-452d-9fa3-1adbdd64ae85
```

Diese Befehle zeigen, wie eine **PSSession** auf Grundlage Ihrer Instanz-ID oder **remoterunspaceid** geschlossen wird.

Der erste Befehl verwendet das **Get-PSSession** -Cmdlet, um die **pssessions** in der aktuellen Sitzung abzurufen.
Er verwendet einen Pipeline Operator (|), um die **pssessions** an das Format-Table-Cmdlet zu senden, das die **Computername** -und **InstanceId-** Eigenschaften in einer Tabelle formatiert.
Der *AutoSize* -Parameter komprimiert die Spalten für die Anzeige.

In der resultierenden Anzeige können Sie die zu schließende **PSSession** identifizieren und die *InstanceId* dieser **PSSession** kopieren und in den zweiten Befehl einfügen.

Der zweite Befehl verwendet das **Remove-PSSession-** Cmdlet, um die *PSSession* mit der angegebenen Instanz-ID zu entfernen.

### Beispiel 6: Erstellen einer Funktion, die alle Sitzungen in der aktuellen Sitzung löscht

```powershell
Function EndPSS { Get-PSSession | Remove-PSSession }
```

Diese Funktion löscht alle **pssessions** in der aktuellen Sitzung.
Nachdem Sie diese Funktion dem PowerShell-Profil hinzugefügt haben, geben Sie ein, um alle Sitzungen zu löschen `EndPSS` .

## PARAMETERS

### -ComputerName

Gibt ein Array von Namen von Computern an.
Dieses Cmdlet schließt die **pssessions** , die mit den angegebenen Computern verbunden sind.
Platzhalterzeichen sind zulässig.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen mindestens eines Computers ein.
Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Containerid

Gibt ein Array von IDs von Containern an. Mit diesem Cmdlet werden Sitzungen für jeden der angegebenen Container entfernt. Verwenden Sie den `docker ps` Befehl, um eine Liste der Container-IDs abzurufen. Weitere Informationen finden Sie in der Hilfe zum [docker PS](https://docs.docker.com/engine/reference/commandline/ps/) -Befehl.

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id

Gibt ein Array von IDs von Sitzungen an.
Dieses Cmdlet schließt die *pssessions* mit den angegebenen IDs.
Geben Sie eine oder mehrere IDs ein, die durch Kommas getrennt sind, oder verwenden Sie den Bereichs Operator (..), um einen Bereich von IDs anzugeben.

Eine ID ist eine Ganzzahl, die die **PSSession** in der aktuellen Sitzung eindeutig identifiziert.
Es ist einfacher zu merken und einzugeben als die *InstanceId* , aber Sie ist nur in der aktuellen Sitzung eindeutig.
Um die ID einer **PSSession** zu ermitteln, führen Sie das Get-PSSession-Cmdlet ohne Parameter aus.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Gibt ein Array von Instanz-IDs an.
Dieses Cmdlet schließt die **pssessions** mit den angegebenen Instanz-IDs.

Die Instanz-ID ist eine GUID, die eine **PSSession** in der aktuellen Sitzung eindeutig identifiziert.
Die Instanz-ID ist eindeutig, auch wenn mehrere Sitzungen auf einem einzelnen Computer ausgeführt werden.

Die Instanz-ID wird in der **InstanceId-** Eigenschaft des Objekts gespeichert, das eine **PSSession** darstellt.
Um die **InstanceId** der **pssessions** in der aktuellen Sitzung zu suchen, geben Sie ein `Get-PSSession | Format-Table Name, ComputerName, InstanceId` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt ein Array von anzeigen Amen von Sitzungen an.
Dieses Cmdlet schließt die **pssessions** mit den angegebenen anzeigen Amen.
Platzhalterzeichen sind zulässig.

Da der Anzeige Name einer **PSSession** möglicherweise nicht eindeutig ist, sollten Sie bei Verwendung des *Name* -Parameters auch den *WhatIf* -Parameter oder den *Confirm* -Parameter im **Remove-PSSession-** Befehl verwenden.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Sitzung

Gibt die Sitzungs Objekte der zu schließenden **pssessions** an.
Geben Sie eine Variable ein, die die **pssessions** oder einen Befehl enthält, der die **pssessions** erstellt oder abruft, z. b. einen New-PSSession-oder **Get-PSSession** -Befehl.
Sie können ein oder mehrere Sitzungs Objekte auch über die Pipeline an **Remove-PSSession** übergeben.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMID

Gibt ein Array mit der ID der virtuellen Computer an.
Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.
Verwenden Sie den folgenden Befehl, um die verfügbaren virtuellen Computer anzuzeigen:

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Gibt ein Array von Namen von virtuellen Computern an.
Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.
Verwenden Sie das Cmdlet **Get-VM** , um die für Sie verfügbaren virtuellen Computer anzuzeigen.

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System. Management. Automation. Runspaces. PSSession

Sie können ein Sitzungs Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Objekte zurück.

## HINWEISE

* Der *ID* -Parameter ist obligatorisch. Um alle **pssessions** in der aktuellen Sitzung zu löschen, geben Sie ein `Get-PSSession | Remove-PSSession` .
* Eine **PSSession** verwendet eine permanente Verbindung mit einem Remote Computer. Erstellen Sie eine **PSSession** , um eine Reihe von Befehlen auszuführen, die Daten gemeinsam nutzen. Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help about_PSSessions`.
* **Pssessions** sind spezifisch für die aktuelle Sitzung. Wenn Sie eine Sitzung beenden, werden die **pssessions** , die Sie in dieser Sitzung erstellt haben, zwangsweise geschlossen.

## VERWANDTE LINKS

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)
