---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: 856e82d8166548921531e88488bd45c34d845772
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524721"
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

Mit dem- `Install-PackageProvider` Cmdlet werden übereinstimmende Paketverwaltung Anbieter installiert, die in mit **PowerShellGet** registrierten Paketquellen verfügbar sind. Standardmäßig schließt dies Module ein, die im Windows-PowerShell-Katalog mit dem Tag **packagemanagement** verfügbar sind. Der **PowerShellGet** -Paketverwaltung-Anbieter wird für die Suche nach Anbietern in diesen Depots verwendet.

Mit diesem Cmdlet werden auch übereinstimmende Paketverwaltung Anbieter installiert, die mit der Paketverwaltung Bootstrapping-Anwendung verfügbar sind.

Dieses Cmdlet installiert auch entsprechende Paketverwaltung Anbieter, die im Paketverwaltung Azure-BLOB-Speicher verfügbar sind. Verwenden Sie den Boots Trapper-Anbieter, um diese zu suchen und zu installieren.

Um das erste Mal auszuführen, erfordert packagemanagement eine Internetverbindung zum Herunterladen des nuget-Paket Anbieters. Wenn der Computer jedoch nicht über eine Internetverbindung verfügt und Sie den nuget-oder PowerShellGet-Anbieter verwenden müssen, können Sie ihn auf einem anderen Computer herunterladen und auf den Zielcomputer kopieren. Führen Sie hierzu die folgenden Schritte aus:

1. Führen `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` Sie aus, um den Anbieter von einem Computer mit Internetverbindung zu installieren.
1. Nach der Installation können Sie den Anbieter finden, der in `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\<ProviderName>\<ProviderVersion>` oder installiert ist `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\<ProviderName>\<ProviderVersion>` .
1. Platzieren `<ProviderName>` Sie den Ordner (in diesem Fall den nuget-Ordner) am entsprechenden Speicherort auf dem Zielcomputer. Wenn es sich bei dem Zielcomputer um einen Nano-Server handelt, müssen Sie `Install-PackageProvider` von Nano Server ausführen, um die richtigen nuget-Binärdateien herunterzuladen.
1. Starten Sie PowerShell neu, um den Paketanbieter automatisch zu laden. Alternativ können Sie ausführen, `Get-PackageProvider -ListAvailable` um alle Paketanbieter aufzulisten, die auf dem Computer verfügbar sind.
   Verwenden `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` Sie dann, um den Anbieter in die aktuelle Windows PowerShell-Sitzung zu importieren.

## BEISPIELE

### Beispiel 1: Installieren eines Paket Anbieters aus dem PowerShell-Katalog

Mit diesem Befehl wird der Anbieter des gistprovider-Pakets aus dem PowerShell-Katalog installiert.

```powershell
Install-PackageProvider -Name "GistProvider" -Verbose
```

### Beispiel 2: Installieren einer bestimmten Version eines Paket Anbieters

In diesem Beispiel wird eine angegebene Version des nuget-Paket Anbieters installiert.

Der erste Befehl sucht alle Versionen des Paket Anbieters namens nuget.
Mit dem zweiten Befehl wird eine angegebene Version des nuget-Paket Anbieters installiert.

```powershell
Find-PackageProvider -Name "NuGet" -AllVersions
Install-PackageProvider -Name "NuGet" -RequiredVersion "2.8.5.216" -Force
```

### Beispiel 3: Suchen eines Anbieters und Installieren des Anbieters

In diesem Beispiel werden `Find-PackageProvider` und die Pipeline verwendet, um nach dem GIST-Anbieter zu suchen und zu installieren.

```powershell
Find-PackageProvider -Name "GistProvider" | Install-PackageProvider -Verbose
```

### Beispiel 4: Installieren eines Anbieters im Modul Ordner des aktuellen Benutzers

Mit diesem Befehl wird ein Paketanbieter auf installiert, `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies` sodass er nur vom aktuellen Benutzer verwendet werden kann.

```powershell
Install-PackageProvider -Name GistProvider -Verbose -Scope CurrentUser
```

## PARAMETERS

### -Allversions

Gibt an, dass dieses Cmdlet alle verfügbaren Versionen des Paket Anbieters installiert. Standardmäßig wird `Install-PackageProvider` nur die höchste verfügbare Version zurückgegeben.

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

Gibt an, dass dieses Cmdlet alle Aktionen mit diesem Cmdlet erzwingt, die erzwungen werden können. Dies bedeutet derzeit, dass der **Force** -Parameter mit dem Parameter " **forcebootstrap** " identisch ist.

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

Gibt ein **softwareidentity** -Objekt an. Verwenden Sie das- `Find-PackageProvider` Cmdlet, um ein **softwareidentity** -Objekt zu erhalten, das über die Pipeline an `Install-PackageProvider`

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

Gibt die maximal zulässige Version des Paket Anbieters an, den Sie installieren möchten. Wenn Sie diesen Parameter nicht hinzufügen, wird `Install-PackageProvider` von die höchste verfügbare Version des Anbieters installiert.

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

Gibt die mindestens zulässige Version des Paket Anbieters an, den Sie installieren möchten. Wenn Sie diesen Parameter nicht hinzufügen, `Install-PackageProvider` installiert die höchste verfügbare Version des Pakets, das auch alle Anforderungen erfüllt, die durch den *MaximumVersion* -Parameter angegeben werden.

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

Gibt einen oder mehrere Paketanbieter-Modulnamen an. Trennen Sie mehrere Paketnamen durch Kommas.
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

Gibt die exakt zulässige Version des Paket Anbieters an, den Sie installieren möchten. Wenn Sie diesen Parameter nicht hinzufügen, wird `Install-PackageProvider` von die höchste verfügbare Version des Anbieters installiert, die auch eine beliebige maximale Version erfüllt, die durch den **MaximumVersion** -Parameter angegeben wird.

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

Gibt den Installationsbereich des Anbieters an. Zulässige Werte für diesen Parameter:

- **ALLUSERS** : installiert Anbieter an einem Speicherort, auf den alle Benutzer des Computers zugreifen können.
  Standardmäßig ist dies **$ENV:P rogramfiles\packagemanagement\providerassemblies.**

- **CurrentUser** : installiert Anbieter an einem Speicherort, an den Sie nur für den aktuellen Benutzer zugänglich sind. Standardmäßig ist dies **$ENV: localappdata\packagemanagement\providerassemblies.**

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

Gibt mindestens eine Paketquelle an. Verwenden Sie das `Get-PackageSource` Cmdlet, um eine Liste der verfügbaren Paketquellen zu erhalten.

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

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

Sie können ein **softwareidentity** -Objekt über die Pipeline an dieses Cmdlet übergeben. Verwenden `Find-PackageProvider` Sie, um ein **softwareidentity** -Objekt zu erhalten, das an weitergeleitet werden kann `Install-PackageProvider` .

## AUSGABEN

## HINWEISE

## VERWANDTE LINKS

[Find-PackageProvider](Find-PackageProvider.md)

[Get-PackageProvider](Get-PackageProvider.md)

[Import-PackageProvider](Import-PackageProvider.md)
