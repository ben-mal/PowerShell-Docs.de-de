---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: ed69b50019b3393eeeda42a250d65d4dfb809a51
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215783"
---
# Install-PackageProvider

## ZUSAMMENFASSUNG
Installiert einen oder mehrere Paketverwaltung Paketanbieter.

## SYNTAX

### Packagebysearch (Standard)

```
Install-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Credential <PSCredential>] [-Scope <String>] [-Source <String[]>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Packagebyinputobject

```
Install-PackageProvider [-Scope <String>] [-InputObject] <SoftwareIdentity[]> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem **install-packageprovider** -Cmdlet werden übereinstimmende Paketverwaltung Anbieter installiert, die in mit **PowerShellGet** registrierten Paketquellen verfügbar sind.
Standardmäßig schließt dies Module ein, die im PowerShell-Katalog mit dem Tag **packagemanagement** verfügbar sind.
Der **PowerShellGet** -Paketverwaltung-Anbieter wird für die Suche nach Anbietern in diesen Depots verwendet.

Mit diesem Cmdlet werden auch übereinstimmende Paketverwaltung Anbieter installiert, die mit der Paketverwaltung Bootstrapping-Anwendung verfügbar sind.

Dieses Cmdlet installiert auch entsprechende Paketverwaltung Anbieter, die im Paketverwaltung Azure-BLOB-Speicher verfügbar sind.
Verwenden Sie den Boots Trapper-Anbieter, um diese zu suchen und zu installieren.

Um das erste Mal auszuführen, erfordert packagemanagement eine Internetverbindung zum Herunterladen des nuget-Paket Anbieters.
Wenn der Computer jedoch nicht über eine Internetverbindung verfügt und Sie den nuget-oder PowerShellGet-Anbieter verwenden müssen, können Sie ihn auf einem anderen Computer herunterladen und auf den Zielcomputer kopieren.
Führen Sie hierzu die folgenden Schritte aus:

1.
Führen `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` Sie aus, um den Anbieter von einem Computer mit Internetverbindung zu installieren.

2.
Nach der Installation können Sie den Anbieter finden, der in `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` oder installiert ist `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` .

3.
Platzieren \<ProviderName\> Sie den Ordner (in diesem Fall den nuget-Ordner) am entsprechenden Speicherort auf dem Zielcomputer.
Wenn es sich bei dem Zielcomputer um einen Nano-Server handelt, müssen Sie **install-packageprovider** von Nano Server ausführen, um die richtigen nuget-Binärdateien herunterzuladen.

4.
Starten Sie PowerShell neu, um den Paketanbieter automatisch zu laden.
Alternativ können Sie ausführen, `Get-PackageProvider -ListAvailable` um alle Paketanbieter aufzulisten, die auf dem Computer verfügbar sind.
Verwenden `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` Sie dann, um den Anbieter in die aktuelle PowerShell-Sitzung zu importieren.

## BEISPIELE

### Beispiel 1: Installieren eines Paket Anbieters aus dem PowerShell-Katalog

```
PS C:\> Install-PackageProvider -Name "Gistprovider" -Verbose
```

Mit diesem Befehl wird der gistprovider aus dem PowerShell-Katalog installiert.

### Beispiel 2: Installieren einer bestimmten Version eines Paket Anbieters

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
PS C:\> Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.216" -Force
```

In diesem Beispiel wird eine angegebene Version des nuget-Paket Anbieters installiert.

Der erste Befehl sucht alle Versionen des Paket Anbieters namens nuget.
Mit dem zweiten Befehl wird eine angegebene Version des nuget-Paket Anbieters installiert.

### Beispiel 3: Suchen eines Anbieters und Installieren des Anbieters

```
PS C:\> Find-PackageProvider -Name "Gistprovider" | Install-PackageProvider -Verbose
```

Dieser Befehl verwendet " **Find-packageprovider** " und die Pipeline, um nach dem GIST-Anbieter zu suchen und zu installieren.

### Beispiel 4: Installieren eines Anbieters im Modul Ordner des aktuellen Benutzers

```
PS C:\> Install-PackageProvider -Name Gistprovider -Verbose -Scope CurrentUser
```

Dieser Befehl installiert einen Paketanbieter, um zu $ENV: localappdata\packagemanagement\providerassemblys, sodass nur der aktuelle Benutzer Sie verwenden kann.

## PARAMETERS

### -Allversions

Gibt an, dass dieses Cmdlet alle verfügbaren Versionen des Paket Anbieters installiert.
Standardmäßig gibt **install-packageprovider** nur die höchste verfügbare Version zurück.

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

Gibt ein Benutzerkonto an, das über die Berechtigung zum Installieren von Paket Anbietern verfügt.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Gibt an, dass dieses Cmdlet alle Aktionen mit diesem Cmdlet erzwingt, die erzwungen werden können.
Dies bedeutet derzeit, dass der *Force* -Parameter mit dem Parameter " *forcebootstrap* " identisch ist.

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

Gibt an, dass dieses Cmdlet den Paketanbieter automatisch installiert.

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

### -InputObject

Gibt ein **softwareidentity** -Objekt an.
Verwenden Sie das Cmdlet " **Find-packageprovider** ", um ein **softwareidentity** -Objekt zu erhalten, das an " **install-packageprovider** " übergeben wird.

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity[]
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaximumVersion

Gibt die maximal zulässige Version des Paket Anbieters an, den Sie installieren möchten.
Wenn Sie diesen Parameter nicht hinzufügen, installiert **install-packageprovider** die höchste verfügbare Version des Anbieters.

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumVersion

Gibt die mindestens zulässige Version des Paket Anbieters an, den Sie installieren möchten.
Wenn Sie diesen Parameter nicht hinzufügen, installiert **install-packageprovider** die höchste verfügbare Version des Pakets, das auch alle Anforderungen erfüllt, die durch den *MaximumVersion* -Parameter angegeben werden.

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt einen oder mehrere Paketanbieter-Modulnamen an.
Trennen Sie mehrere Paketnamen durch Kommas.
Platzhalterzeichen werden nicht unterstützt.

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy

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

Gibt die exakt zulässige Version des Paket Anbieters an, den Sie installieren möchten.
Wenn Sie diesen Parameter nicht hinzufügen, installiert **install-packageprovider** die höchste verfügbare Version des Anbieters, der auch eine beliebige maximale Version erfüllt, die durch den *MaximumVersion* -Parameter angegeben wird.

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bereich

Gibt den Installationsbereich des Anbieters an.
Die zulässigen Werte für diesen Parameter sind: **ALLUSERS** und **CurrentUser** .

Der Bereich " **ALLUSERS** " installiert Anbieter an einem Speicherort, auf den alle Benutzer des Computers zugreifen können.
Standardmäßig ist dies **$ENV:P rogramfiles\packagemanagement\providerassemblies.**

Der Bereich " **CurrentUser** " installiert Anbieter an einem Speicherort, an den Sie nur für den aktuellen Benutzer zugänglich sind.
Standardmäßig ist dies **$ENV: localappdata\packagemanagement\providerassemblies.**

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Gibt mindestens eine Paketquelle an.
Verwenden Sie das Cmdlet "Get-PackageSource", um eine Liste der verfügbaren Paketquellen zu erhalten.

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: False
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

### Microsoft. packagemanagement. Packaging. softwareidentity

Sie können ein **softwareidentity** -Objekt über die Pipeline an dieses Cmdlet übergeben.
Verwenden Sie Find-PackageProvider, um ein **softwareidentity** -Objekt abzurufen, das an **install-packageprovider** weitergeleitet werden kann.

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[Find-PackageProvider](Find-PackageProvider.md)

[Get-PackageProvider](Get-PackageProvider.md)

[Import-PackageProvider](Import-PackageProvider.md)

