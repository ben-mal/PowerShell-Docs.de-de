---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSnapin
ms.openlocfilehash: e74aff3e52c61f41a54664efbab9c0f195b0d409
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212780"
---
# Remove-PSSnapin

## ZUSAMMENFASSUNG
Entfernt Windows PowerShell-Snap-Ins aus der aktuellen Sitzung.

## SYNTAX

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mit dem Cmdlet " **Remove-PSSnapIn** " wird ein Windows PowerShell-Snap-in aus der aktuellen Sitzung entfernt.
Sie können es zum Entfernen von Snap-Ins verwenden, die Sie Windows PowerShell hinzugefügt haben. Sie können dieses Cmdlet nicht verwenden, um die mit Windows PowerShell installierten Snap-Ins zu entfernen.

Nachdem Sie ein Snap-in aus der aktuellen Sitzung entfernt haben, wird das Snap-in noch geladen, aber die Cmdlets und Anbieter im Snap-in sind in der Sitzung nicht mehr verfügbar.

## BEISPIELE

### Beispiel 1: Entfernen eines Snap-Ins

```
PS C:\> remove-pssnapin -Name Microsoft.Exchange
```

Mit diesem Befehl wird das **Microsoft. Exchange** -Snap-in aus der aktuellen Sitzung entfernt.
Wenn der Befehl abgeschlossen ist, sind die von dem Snap-In unterstützten Cmdlets und Anbieter in der Sitzung nicht mehr verfügbar.

### Beispiel 2: Entfernen von Snap-Ins mithilfe von Namen mit der Pipeline

```
PS C:\> Get-PSSnapIn smp* | Remove-PSSnapIn
```

Dieser Befehl entfernt die Windows PowerShell-Snap-Ins, deren Namen mit "SMP" beginnen, aus der aktuellen Sitzung.

Der Befehl verwendet das **Get-PSSnapin-** Cmdlet, um Objekte zu erhalten, die die Snap-Ins darstellen. Der Pipeline Operator (|) sendet die Ergebnisse an das **Remove-PSSnapIn** -Cmdlet, das Sie aus der Sitzung entfernt.
Die von diesem Snap-In unterstützten Anbieter und Cmdlets sind in der Sitzung nicht mehr verfügbar.

Wenn Sie Objekte über die Pipeline an **Remove-PSSnapIn** übergeben, werden die Namen der Objekte dem *Name* -Parameter zugeordnet, der Objekte aus der Pipeline annimmt, die über eine **Name** -Eigenschaft verfügen.

### Beispiel 3: Entfernen von Snap-Ins mithilfe von Namen

```
PS C:\> Remove-PSSnapin -Name *event*
```

Dieser Befehl entfernt alle Windows PowerShell-Snap-Ins, deren Namen das Ereignis enthalten.

## PARAMETERS

### -Name
Gibt die Namen der Windows PowerShell-Snap-Ins an, die aus der aktuellen Sitzung entfernt werden sollen.
Platzhalterzeichen (*) sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Gibt ein Objekt zurück, das das Snap-in darstellt.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### System. Management. Automation. pssnapininfo
Sie können ein Snap-in-Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine, System. Management. Automation. pssnapininfo
Dieses Cmdlet generiert ein **System. Management. Automation. pssnapininfo** -Objekt, das das Snap-in darstellt, wenn Sie den *passthru* -Parameter angeben.
Standardmäßig generiert **Remove-PSSnapIn** keine Ausgabe.

## HINWEISE

* **Remove-PSSnapIn** überprüft die Version von Windows PowerShell nicht, bevor ein Snap-in aus der Sitzung entfernt wird. Wenn ein Snap-In nicht entfernt werden kann, wird eine Warnung angezeigt und der Befehl führt zu einem Fehler.
* **Remove-PSSnapIn** wirkt sich nur auf die aktuelle Sitzung aus. Wenn Sie einen Add-PSSnapin-Befehl zu Ihrem Windows PowerShell-Profil hinzugefügt haben, sollten Sie den Befehl löschen, um das Snap-In aus zukünftigen Sitzungen zu entfernen. Anweisungen erhalten Sie, wenn Sie eingeben `Get-Help about_Profiles` .

## VERWANDTE LINKS

[Add-PSSnapin](Add-PSSnapin.md)

[Get-PSSnapin](Get-PSSnapin.md)
