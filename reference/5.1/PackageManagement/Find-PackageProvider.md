---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-PackageProvider
ms.openlocfilehash: dc4450e1c9f8b9506ee57948e4cec2d0541c181d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213348"
---
# Find-PackageProvider

## ZUSAMMENFASSUNG
Gibt eine Liste von Paketverwaltung Paket Anbietern zurück, die für die Installation verfügbar sind.

## SYNTAX

```
Find-PackageProvider [[-Name] <String[]>] [-AllVersions] [-Source <String[]>] [-IncludeDependencies]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## DESCRIPTION

Das Cmdlet " **Find-packageprovider** " findet übereinstimmende packagemanagement-Anbieter, die in mit PowerShellGet registrierten Paketquellen verfügbar sind.
Dies sind Paketanbieter, die für die Installation mit dem Cmdlet „Install-PackageProvider“ verfügbar sind.
Standardmäßig schließt dies Module ein, die im PowerShell-Katalog mit den Tags " **packagemanagement** " und " **Provider** " verfügbar sind.

" **Find-packageprovider** " findet auch übereinstimmende Paketverwaltung Anbieter, die im Paketverwaltung Azure-BLOB-Speicher verfügbar sind.
Verwenden Sie den Boots Trapper-Anbieter, um diese zu suchen und zu installieren.

## BEISPIELE

### Beispiel 1: Suchen aller verfügbaren Paketanbieter

```
PS C:\> Find-PackageProvider
```

Dieser Befehl ruft eine Liste aller Paketanbieter ab, die in den von Paketverwaltung unterstützten Depots verfügbar sind.
Standardmäßig sind diese Paketanbieter auf dem PowerShell-Katalog und mithilfe der Paketverwaltung Bootstrapping-Anwendung verfügbar.

### Beispiel 2: Suchen aller Versionen eines Anbieters

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
```

Dieser Befehl sucht alle Versionen des Paket Anbieters namens nuget.

### Beispiel 3: Suchen eines Anbieters aus einer angegebenen Quelle

```
PS C:\> Find-PackageProvider -Name "Gistprovider" -Source "PSGallery"
```

Dieser Befehl sucht einen Paketanbieter, der mit einer angegebenen Paketquelle verfügbar ist.

## PARAMETERS

### -Allversions

Gibt an, dass dieses Cmdlet alle verfügbaren Versionen des Paket Anbieters zurückgibt.
Standardmäßig gibt " **Find-packageprovider** " nur die neueste verfügbare Version zurück.

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

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Suchen nach Paket Anbietern verfügt.

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

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.
Dies entspricht derzeit dem *forcebootstrap* -Parameter.

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

### -Forcebootstrap

Gibt an, dass dieses Cmdlet Paketverwaltung zum automatischen Installieren des Paket Anbieters erzwingt.

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

### -Includababhängigkeiten

Gibt an, dass dieses Cmdlet Abhängigkeiten enthält.

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

### -MaximumVersion

Gibt die maximal zulässige Version des Paket Anbieters an, den Sie suchen möchten.
Wenn Sie diesen Parameter nicht hinzufügen, findet " **Find-packageprovider** " die höchste verfügbare Version des Anbieters.

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

### -MinimumVersion

Gibt die mindestens zulässige Version des Paket Anbieters an, den Sie suchen möchten.
Wenn Sie diesen Parameter nicht hinzufügen, findet " **Find-packageprovider** " die höchste verfügbare Version des Pakets, das auch eine beliebige maximale, vom *MaximumVersion* -Parameter angegebene Version erfüllt.

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

### -Name

Gibt einen oder mehrere Paketanbieter-Modulnamen oder Anbieter Namen mit Platzhalter Zeichen an.
Trennen Sie mehrere Paketnamen durch Kommas.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Proxy

Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.

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

### -Requirements dversion

Gibt die genau zulässige Version des Paket Anbieters an, den Sie suchen möchten.
Wenn Sie diesen Parameter nicht hinzufügen, findet " **Find-packageprovider** " die höchste verfügbare Version des Anbieters, die auch eine beliebige maximale Version erfüllt, die durch den *MaximumVersion* -Parameter angegeben wird.

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

### -Source

Gibt mindestens eine Paketquelle an.
Mit dem Cmdlet "Get-PackageSource" können Sie eine Liste der verfügbaren Paketquellen erhalten.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

### Microsoft. packagemanagement. Packaging. softwareidentity

Dieses Cmdlet gibt ein **softwareidentity** -Objekt zurück.
Ein **softwareidentity** -Objekt kann an " **install-packageprovider** " weitergeleitet werden, um die Ergebnisse von " **Find-packageprovider** " zu installieren.

## HINWEISE

## VERWANDTE LINKS

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Unregister-PackageSource](Unregister-PackageSource.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Install-PackageProvider](Install-PackageProvider.md)
