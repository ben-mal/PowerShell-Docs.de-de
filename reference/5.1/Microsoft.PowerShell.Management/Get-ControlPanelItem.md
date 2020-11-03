---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ControlPanelItem
ms.openlocfilehash: 51bc04b4de901a611330266b6b0f58471f998432
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215476"
---
# Get-ControlPanelItem

## ZUSAMMENFASSUNG
Ruft Systemsteuerungselemente ab.

## SYNTAX

### Regularname (Standard)

```
Get-ControlPanelItem [[-Name] <String[]>] [-Category <String[]>] [<CommonParameters>]
```

### CanonicalName

```
Get-ControlPanelItem -CanonicalName <String[]> [-Category <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-ControlPanelItem` Cmdlet werden System Steuerungselemente auf dem lokalen Computer abgerufen. Sie können damit Systemsteuerungselemente nach Name, Kategorie oder Beschreibung auch in Systemen ohne Benutzeroberfläche suchen.

Mit diesem Cmdlet werden nur die System Steuerungselemente abgerufen, die im System geöffnet werden können. Auf Computern ohne Systemsteuerung oder Datei-Explorer ruft dieses Cmdlet nur System Steuerungselemente ab, die ohne diese Komponenten geöffnet werden können.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt. Es funktioniert nur unter Windows 8 und Windows Server 2012 und neuer.

## BEISPIELE

### Beispiel 1: Abrufen aller Systemsteuerungselemente

Dieser Befehl ruft alle Systemsteuerungselemente auf dem lokalen Computer ab.

```powershell
Get-ControlPanelItem
```

```Output
Name                          CanonicalName                 Category                      Description
----                          -------------                 --------                      -----------
Action Center                 Microsoft.ActionCenter        {System and Security}         Review recent messages and...
Administrative Tools          Microsoft.AdministrativeTools {System and Security}         Configure administrative s...
AutoPlay                      Microsoft.AutoPlay            {Hardware}                    Change default settings fo...
BitLocker Drive Encryption    Microsoft.BitLockerDriveEn... {System and Security}         Protect your computer usin...
Color Management              Microsoft.ColorManagement     {All Control Panel Items}     Change advanced color mana...
Credential Manager            Microsoft.CredentialManager   {User Accounts}               Manage your Windows Creden...
Date and Time                 Microsoft.DateAndTime         {Clock, Language, and Region} Set the date, time, and ti...
...
```

### Beispiel 2: Abrufen von Systemsteuerungselementen nach Name

In diesem Beispiel werden System Steuerungselemente abgerufen, deren Namen Programm oder App enthalten.

```powershell
Get-ControlPanelItem -Name "*Program*", "*App*"
```

### Beispiel 3: Abrufen von Systemsteuerungselementen nach Kategorie

Mit diesem Befehl werden alle System Steuerungselemente in Kategorien abgerufen, deren Namen eine Sicherheit aufweisen.

```powershell
Get-ControlPanelItem -Category "*Security*"
```

### Beispiel 4: Öffnen eines Systemsteuerungselements

In diesem Beispiel wird das System Steuerungselement Windows-Firewall auf dem lokalen Computer geöffnet.

```powershell
Get-ControlPanelItem -Name "Windows Firewall" | Show-ControlPanelItem
```

Mit dem- `Get-ControlPanelItem` Cmdlet wird das System Steuerungselement abgerufen. Das `Show-ControlPanelItem` Cmdlet öffnet es.

### Beispiel 5: Abrufen von Systemsteuerungselementen auf einem Remotecomputer

In diesem Beispiel wird das BitLocker-Laufwerkverschlüsselung System Steuerungselement auf dem Remote Computer Server01 abgerufen.
Das `Invoke-Command` Cmdlet führt das `Get-ControlPanelItem` Cmdlet Remote aus.

```powershell
Invoke-Command -ComputerName "Server01" {Get-ControlPanelItem -Name "BitLocker*" }
```

### Beispiel 6: Suchen der Beschreibungen von Systemsteuerungselementen

In diesem Beispiel wird die **Description** -Eigenschaft der System Steuerungselemente durchsucht, um nur diejenigen zu erhalten, die das Name- **Gerät** enthalten.

```powershell
Get-ControlPanelItem | Where-Object {$_.Description -like "*Device*"}
```

```Output
Name                    CanonicalName                 Category    Description
----                    -------------                 --------    -----------
AutoPlay                Microsoft.AutoPlay            {Hardware}  Change default settings fo...
Devices and Printers    Microsoft.DevicesAndPrinters  {Hardware}  View and manage devices, p...
Sound                   Microsoft.Sound               {Hardware}  Configure your audio devic...
```

Mit dem- `Get-ControlPanelItem` Cmdlet werden alle System Steuerungselemente abgerufen. Mit dem- `Where-Object` Cmdlet werden die Elemente nach dem Wert der **Description** -Eigenschaft gefiltert.

## PARAMETERS

### -CanonicalName

Gibt die System Steuerungselemente als Zeichen folgen Array mit ihren kanonischen Namen oder namens Mustern an, die von diesem Cmdlet abgerufen werden. Platzhalter sind zulässig. Wenn Sie mehrere Namen eingeben, ruft dieses Cmdlet System Steuerungselemente ab, die mit einem der Namen identisch sind, als wären die Elemente in der Liste "Name" durch einen Operator "or" getrennt.

Standardmäßig ruft dieses Cmdlet alle System Steuerungselemente im System ab.

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

### -Kategorie

Gibt die Kategorien der System Steuerungselemente in den angegebenen Kategorien, die dieses Cmdlet abruft, als Zeichen folgen Array an. Geben Sie einen Kategorienamen oder ein Namensmuster ein. Platzhalter sind zulässig. Wenn Sie mehrere Namen eingeben, ruft dieses Cmdlet System Steuerungselemente ab, die mit einem der Namen identisch sind, als wären die Elemente in der Liste "Name" durch einen Operator "or" getrennt. Standardmäßig ruft dieses Cmdlet alle System Steuerungselemente im System ab.

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

### -Name

Gibt die Namen oder Namensmuster der Systemsteuerung an, die von diesem Cmdlet abgerufen werden, als Zeichen folgen Array.
Platzhalter sind zulässig. Sie können ein Name-oder Namensmuster auch über die Pipeline an dieses Cmdlet übergeben.

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können einen Namen oder ein Namensmuster über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Microsoft. PowerShell. Commands. controlpanelitem

Mit diesem Cmdlet werden System Steuerungselemente auf dem lokalen Computer abgerufen.

## HINWEISE

## VERWANDTE LINKS

[Show-ControlPanelItem](Show-ControlPanelItem.md)
