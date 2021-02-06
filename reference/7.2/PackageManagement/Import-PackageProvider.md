---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 6c19d1cbc7b7e4dc37e24c466f83efae688f3cec
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99603701"
---
# Import-PackageProvider

## ZUSAMMENFASSUNG
Fügt der aktuellen Sitzung Paketverwaltung Paketanbieter hinzu.

## SYNTAX

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Import-PackageProvider` Cmdlet wird der aktuellen Sitzung mindestens ein Paketanbieter hinzugefügt.
Der von Ihnen importierte Anbieter muss auf dem lokalen Computer installiert sein.

Führen Sie aus, um eine Liste der verfügbaren Anbieter zu erhalten `Get-PackageProvider -ListAvailable` .
Beachten Sie, dass sich der Name eines Paket Anbieters vom Modulnamen unterscheiden kann.

Aus Sicherheitsgründen erfordert **packagemanagement** , dass c#-basierte Anbieter einen enthalten `provider.manifest` . Weitere Informationen zum Erstellen eines Anbieters mit `provider.manifest` injiziertem finden Sie in den `.csproj` Projektdateien unter [https://github.com/oneget/oneget](https://github.com/oneget/oneget) .

## BEISPIELE

### Beispiel 1: Importieren eines Paket Anbieters vom lokalen Computer

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

Dieser Befehl importiert den nuget-Anbieter, nachdem er auf dem lokalen Computer installiert wurde.

### Beispiel 2: Importieren einer bestimmten Version eines Paket Anbieters

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

Mit diesem Befehl wird eine bestimmte Version des nuget-Paket Anbieters ermittelt, installiert und importiert.

## PARAMETERS

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.
Importiert einen Paketanbieter erneut.

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

### -MaximumVersion

Gibt die maximal zulässige Version des Paket Anbieters an, den Sie importieren möchten. Wenn Sie diesen Parameter nicht hinzufügen, `Import-PackageProvider` importiert die höchste verfügbare Version des Anbieters.

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

Gibt die minimale zulässige Version des Paket Anbieters an, den Sie importieren möchten. Wenn Sie diesen Parameter nicht hinzufügen, `Import-PackageProvider` importiert die höchste verfügbare Version des Pakets, das auch eine beliebige maximale Version erfüllt, die mithilfe des *MaximumVersion* -Parameters angegeben wird.

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

Gibt einen oder mehrere Paketanbieter Namen an. Platzhalter sind nicht zulässig.

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

### -Requirements dversion

Gibt die genaue Version des Paket Anbieters an, den Sie importieren möchten. Wenn Sie diesen Parameter nicht hinzufügen, `Import-PackageProvider` importiert die höchste verfügbare Version des Anbieters, der auch jede mit dem **MaximumVersion** -Parameter angegebene maximale Version erfüllt.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Microsoft. packagemanagement. Implementation. packageprovider

Sie können ein von zurück gegebenes **packageprovider** -Objekt über die Pipeline an übergeben `Get-PackageProvider` `Import-PackageProvider` .

## AUSGABEN

## HINWEISE

> [!IMPORTANT]
> Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr. Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung. Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).

## VERWANDTE LINKS

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Unregister-PackageSource](Unregister-PackageSource.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Get-PackageProvider](Get-PackageProvider.md)
