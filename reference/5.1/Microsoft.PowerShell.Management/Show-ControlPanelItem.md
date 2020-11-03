---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ControlPanelItem
ms.openlocfilehash: 368e385d51437f9ac93b700c929b185dce30a644
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214404"
---
# Show-ControlPanelItem

## ZUSAMMENFASSUNG
Öffnet Systemsteuerungselemente.

## SYNTAX

### Regularname (Standard)

```
Show-ControlPanelItem [-Name] <String[]> [<CommonParameters>]
```

### CanonicalName

```
Show-ControlPanelItem -CanonicalName <String[]> [<CommonParameters>]
```

### ControlPanelItem

```
Show-ControlPanelItem [[-InputObject] <ControlPanelItem[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Show-ControlPanelItem` Cmdlet werden System Steuerungselemente auf dem lokalen Computer geöffnet. Sie können damit System Steuerungselemente nach Name, Kategorie oder Beschreibung auch auf Systemen ohne Benutzeroberfläche öffnen. Sie können System Steuerungselemente über die Pipeline aus dem `Get-ControlPanelItem` Cmdlet an übergeben `Show-ControlPanelItem` .

`Show-ControlPanelItem` durchsucht nur System Steuerungselemente, die im System geöffnet werden können. Auf Computern ohne **Systemsteuerung** oder **Datei-Explorer** werden `Show-ControlPanelItem` nur System Steuerungselemente durchsucht, die ohne diese Komponenten geöffnet werden können.

Dieses Cmdlet wurde in Windows PowerShell 3,0 eingeführt und funktioniert unter Windows 8, Windows Server 2012 und höheren Versionen.

## BEISPIELE

### Beispiel 1: Anzeigen eines System Steuerungs Elements

In diesem Beispiel wird das System Steuerungselement " **AutoPlay** " gestartet.

```powershell
Show-ControlPanelItem -Name "AutoPlay"
```

### Beispiel 2: Übergeben eines System Steuerungs Elements an dieses Cmdlet

In diesem Beispiel wird das System Steuerungselement **Windows Defender Firewall** auf dem lokalen Computer geöffnet.
Der Name des System Steuerungs Elements "Windows-Firewall" hat sich gegenüber den Versionen von Windows geändert. In diesem Beispiel wird ein Platzhalter Muster verwendet, um das System Steuerungselement zu finden.

```powershell
Get-ControlPanelItem -Name "*Firewall" | Show-ControlPanelItem
```

`Get-ControlPanelItem` Ruft das System Steuerungselement ab, das vom `Show-ControlPanelItem` Cmdlet geöffnet wird.

### Beispiel 3: Verwenden eines Dateinamens zum Öffnen eines Systemsteuerungselements

In diesem Beispiel wird das System Steuerungselement " **Programme und Funktionen** " mithilfe des Anwendungs namens geöffnet.

```powershell
appwiz.cpl
```

Diese Methode ist eine Alternative zur Verwendung eines- `Show-ControlPanelItem` Befehls.

> [!NOTE]
> In PowerShell können Sie die Dateierweiterung. cpl für System Steuerungs Dateien weglassen, da Sie im Wert der Umgebungsvariablen enthalten ist `$env:PathExt` .

## PARAMETERS

### -CanonicalName

Gibt System Steuerungselemente mithilfe der angegebenen kanonischen Namen oder Namensmuster an. Platzhalterzeichen sind zulässig. Wenn Sie mehrere Namen eingeben, öffnet dieses Cmdlet System Steuerungselemente, die mit einem der Namen identisch sind, als wären die Elemente in der Liste "Name" durch einen **or** -Operator getrennt.

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

Gibt die zu öffnenden System Steuerungselemente durch das Senden von System Steuerungselement-Objekten an. Geben Sie eine Variable ein, die System Steuerungselement-Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der System Steuerungselemente abruft, z `Get-ControlPanelItem` . b.

```yaml
Type: Microsoft.PowerShell.Commands.ControlPanelItem[]
Parameter Sets: ControlPanelItem
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die Namen von System Steuerungselementen an. Platzhalterzeichen sind zulässig. Wenn Sie mehrere Namen eingeben, öffnet dieses Cmdlet System Steuerungselemente, die mit einem der Namen identisch sind, als wären die Elemente in der Liste "Name" durch einen **or** -Operator getrennt.

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. String, Microsoft. PowerShell. Commands. controlpanelitem

Sie können ein Name-oder System Steuerungselement-Objekt über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet gibt keine Ausgabe zurück.

## HINWEISE

## VERWANDTE LINKS

[Get-ControlPanelItem](Get-ControlPanelItem.md)
