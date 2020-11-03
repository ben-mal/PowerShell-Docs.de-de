---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/04/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-dscresource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-DscResource
ms.openlocfilehash: 170be8eb8e5f9f158b69c5505505e587e10c7e78
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210127"
---
# Find-DscResource

## ZUSAMMENFASSUNG
Sucht DSC-Ressourcen.

## SYNTAX

### Alle

```
Find-DscResource [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das `Find-DscResource` Cmdlet durchsucht registrierte Depots, um DSC-Ressourcen zu finden, die in Modulen enthalten sind. Standardmäßig durch `Find-DscResource` sucht alle registrierten Depots.

Für jedes Modul, das von gefunden `Find-DscResource` wird, wird ein **psgetdscresourceinfo** -Objekt zurückgegeben.
**Psgetdscresourceinfo** -Objekte können über die Pipeline an das `Install-Module` Cmdlet gesendet werden.
`Install-Module` installiert das-Modul.

## BEISPIELE

### Beispiel 1: Suchen aller DSC-Ressourcen

`Find-DscResource` gibt DSC-Ressourcen aus registrierten Depots zurück. Verwenden Sie den **Repository** -Parameter, um ein bestimmtes Repository zu durchsuchen.

```powershell
Find-DscResource
```

```Output
Name                           Version    ModuleName                     Repository
----                           -------    ----------                     ----------
Carbon_Privilege               2.8.1      Carbon                         PSGallery
Carbon_ScheduledTask           2.8.1      Carbon                         PSGallery
Carbon_Service                 2.8.1      Carbon                         PSGallery
PackageManagement              1.4        PackageManagement              PSGallery
PackageManagementSource        1.4        PackageManagement              PSGallery
PSModule                       2.1.4      PowerShellGet                  PSGallery
PSRepository                   2.1.4      PowerShellGet                  PSGallery
xArchive                       8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xDSCWebService                 8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xEnvironment                   8.7.0.0    xPSDesiredStateConfiguration   PSGallery
```

### Beispiel 2: Suchen einer DSC-Ressource anhand ihres Namens

`Find-DscResource` die DSC-Ressourcen werden nach Namen nach dem Namen angezeigt. Verwenden Sie Kommas, um ein Array von Ressourcennamen voneinander zu trennen.

```powershell
Find-DscResource -Name xWebsite, xWebApplication, xWebSiteDefaults
```

```Output
Name               Version    ModuleName            Repository
----               -------    ----------            ----------
xWebApplication    2.6.0.0    xWebAdministration    PSGallery
xWebsite           2.6.0.0    xWebAdministration    PSGallery
xWebSiteDefaults   2.6.0.0    xWebAdministration    PSGallery
```

`Find-DscResource` verwendet den **Name** -Parameter, um das angegebene Array von DSC-Ressourcen zu suchen.

### Beispiel 3: Suchen Sie eine DSC-Ressource, und installieren Sie Sie.

`Find-DscResource` findet eine DSC-Ressource und sendet das Objekt über die zu installierende Pipeline.
Verwenden Sie nach der Installation, `Get-InstalledModule` um die Ergebnisse anzuzeigen.

Mehrere Ressourcen aus demselben Modul können über die Pipeline an das gesendet werden `Install-Module` .
`Install-Module` versucht, das Modul nur einmal zu installieren.

```powershell
Find-DscResource -Name xWebsite | Install-Module
```

`Find-DscResource` verwendet den **Name** -Parameter, um die Ressource mit dem Namen **xwebsite** zu suchen. Das Objekt wird über die Pipeline an das `Install-Module` Cmdlet gesendet. `Install-Module` installiert das **xwebadministration** -Modul für die Ressource.

### Beispiel 4: Suchen aller DSC-Ressourcen in einem Modul

`Find-DscResource` sucht alle DSC-Ressourcen, die in einem angegebenen Modul enthalten sind. Standardmäßig wird die aktuelle Version angezeigt. Verwenden Sie zum Anzeigen anderer Versionen die **allversions** -oder Requirements **dversions** -Parameter.

```powershell
Find-DscResource -ModuleName xWebAdministration
```

```Output
Name                                Version    ModuleName              Repository
----                                -------    ----------              ----------
WebApplicationHandler               2.6.0.0    xWebAdministration      PSGallery
xIisFeatureDelegation               2.6.0.0    xWebAdministration      PSGallery
xIisHandler                         2.6.0.0    xWebAdministration      PSGallery
xIisLogging                         2.6.0.0    xWebAdministration      PSGallery
```

`Find-DscResource` verwendet den **ModuleName** -Parameter, um die **xwebadministration** anzugeben und die DSC-Ressourcen zu suchen, die im Modul enthalten sind. Die aktuelle Version der einzelnen Ressourcen wird angezeigt.

### Beispiel 5: Suchen nach einer DSC-Ressource nach Tag und erforderlicher Version

DSC-Ressourcen können mithilfe des Parameters- **Tags** und der Requirements- **Version** gefunden werden. **Tag** zeigt die aktuelle Version aller Ressourcen an, die das angegebene Tag im Repository enthalten.
"Requirements **dversion** " benötigt den Parameter " **ModuleName** ", und der **Name** -Parameter ist optional. Die Parameter " **Name** " und " **ModuleName** " begrenzen die Ausgabe. Verwenden Sie den **allversions** -Parameter, um die verfügbaren Versionen einer DSC-Ressource anzuzeigen.

```powershell
Find-DscResource -ModuleName xWebAdministration -Tag DSC -RequiredVersion 1.20
```

```output
Name                    Version    ModuleName             Repository
----                    -------    ----------             ----------
xIisFeatureDelegation   1.20.0.0   xWebAdministration     PSGallery
xIisHandler             1.20.0.0   xWebAdministration     PSGallery
xIisLogging             1.20.0.0   xWebAdministration     PSGallery
xIisMimeTypeMapping     1.20.0.0   xWebAdministration     PSGallery
```

### Beispiel 6: Suchen einer Ressource mithilfe eines Filters

`Find-DscResource` sucht alle Ressourcen und verwendet den **Filter** -Parameter, um die Ergebnisse nach **Domäne** anzugeben. Der **Filter** -Parameter findet den Filter Wert in der Beschreibung oder dem Modulnamen des Objekts. Verwenden `Select-Object` Sie das Cmdlet, um die Eigenschaften eines Objekts anzuzeigen.

```powershell
Find-DscResource -Filter Domain
```

```output
Name                    Version    ModuleName                 Repository
----                    -------    ----------                 ---------
xComputer               4.1.0.0    xComputerManagement        PSGallery
Computer                6.4.0.0    ComputerManagementDsc      PSGallery
xDSCDomainjoin          1.1        xDSCDomainjoin             PSGallery
xDisk                   1.0        xDisk                      PSGallery
xDSCFirewall            1.6.21     xDSCFirewall               PSGallery
dmAwsTagInstance        1.0.1      domainAwsDSCResources      PSGallery
```

## PARAMETERS

### -Allowprerelease

Schließt Ressourcen ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Allversions

Der **allversions** -Parameter zeigt jede verfügbare Version der DSC-Ressource an. Der **allversions** -Parameter kann nicht mit den Parametern **MinimumVersion** , **MaximumVersion** oder Requirements **dversion** verwendet werden.

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

### -Filter

Sucht Ressourcen basierend auf der Such Syntax des **packagemanagement** -Anbieters. Geben Sie z. b. die Wörter an, nach denen in den Eigenschaften **ModuleName** und **Description** gesucht werden soll.

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

### -MaximumVersion

Gibt die maximale Version der Ressource an, die in die Ergebnisse aufgenommen werden soll. Die Parameter " **MaximumVersion** " und "Requirements **dversion** " können nicht im selben Befehl verwendet werden.

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

Gibt die Mindestversion der Ressource an, die in den Ergebnissen enthalten sein soll. Der **MinimumVersion** -Parameter und der Requirements- **Version** -Parameter können nicht im selben Befehl verwendet werden.

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

### -ModuleName

Gibt ein Modul an, das die DSC-Ressource enthält.

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

Gibt den Namen einer Ressource an. Der Standardwert ist alle Ressourcen. Verwenden Sie Kommas, um ein Array von Ressourcennamen voneinander zu trennen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Proxy Credential

Gibt ein Benutzerkonto mit der Berechtigung an, den im **Proxy** Parameter angegebenen Proxy Server zu verwenden.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Repository

Gibt ein Repository an, in dem nach Ressourcen gesucht wird. Verwenden Sie Kommas, um ein Array von Repository-Namen zu trennen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Requirements dversion

Gibt die genaue Versionsnummer des Moduls an, das in die Ergebnisse aufgenommen werden soll. Die Parameter "Requirements **dversion** " und " **MinimumVersion** " können nicht im selben Befehl verwendet werden.

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

### -Tag

Gibt Tags an, die Module in einem Repository kategorisieren. Verwenden Sie Kommas, um ein Array von Tags voneinander zu trennen.

```yaml
Type: System.String[]
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

## AUSGABEN

### Psgetdscresourceinfo

`Find-DscResource` Gibt ein **psgetdscresourceinfo** -Objekt zurück.

## HINWEISE

## VERWANDTE LINKS

[Get-InstalledModule](Get-InstalledModule.md)

[Install-Module](Install-Module.md)

[Register-PSRepository](Register-PSRepository.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Uninstall-Module](Uninstall-Module.md)
