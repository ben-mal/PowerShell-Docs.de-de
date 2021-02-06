---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/05/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-rolecapability?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-RoleCapability
ms.openlocfilehash: a84dee14872ad5a7d0f7bac8e0057dc527855074
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99601104"
---
# Find-RoleCapability

## ZUSAMMENFASSUNG
Sucht nach Rollenfunktionen in Modulen.

## SYNTAX

### Alle

```
Find-RoleCapability [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>] 
[-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease] 
[-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] 
[-Repository <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das `Find-RoleCapability` Cmdlet sucht registrierte Depots nach PowerShell-Rollen Funktionen und-Modulen.

Für jede Rollen Funktion, die von gefunden wird `Find-RoleCapability` , wird ein **psgetrolecapabilityinfo** -Objekt zurückgegeben. **Psgetrolecapabilityinfo** -Objekte können über die Pipeline an das- `Install-Module` `Save-Module` Cmdlet oder das-Cmdlet gesendet werden.

PowerShell-Rollen Funktionen definieren, welche Befehle und Anwendungen für einen Benutzer am Just Enough Administration (Jea)-Endpunkt verfügbar sind. Rollen Funktionen werden durch Dateien mit einer `.psrc` Erweiterung definiert.

## BEISPIELE

### Beispiel 1: Suchen von Rollen Funktionen

`Find-RoleCapability` findet Rollen Funktionen in jedem registrierten Repository. Verwenden Sie den **Repository** -Parameter, um ein bestimmtes Repository zu durchsuchen.

```powershell
Find-RoleCapability
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
General-Lev2     1.0        JeaExamples    PSGallery
IIS-Lev1         1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### Beispiel 2: Suchen von Rollen Funktionen nach Namen

`Find-RoleCapability` sucht Rollen Funktionen anhand des Namens. Verwenden Sie Kommas, um ein Array von Namen voneinander zu trennen.

```powershell
Find-RoleCapability -Name General-Lev1, IIS-Lev2
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### Beispiel 3: Suchen und Speichern des Moduls einer Rollen Funktion

Das `Find-RoleCapability` Cmdlet sucht eine Rollen Funktion und sendet das Objekt über die Pipeline.
`Save-Module` speichert das Modul der Rollen Funktion in einem Dateisystem. `Get-ChildItem` zeigt den Inhalt des Modul Verzeichnisses an.

```
PS> Find-RoleCapability -Name General-Lev1 | Save-Module -Path C:\Test\Modules

PS> Get-ChildItem -Path C:\Test\Modules\JeaExamples\1.0\

    Directory: C:\Test\Modules\JeaExamples\1.0

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----          6/4/2019    16:37                RoleCapabilities
-a----          2/5/2019    18:46           1702 CreateRegisterPSSC.ps1
-a----          2/5/2019    18:46           7656 JeaExamples.psd1
-a----         10/1/2018    08:16            595 JeaExamples.psm1
```

`Find-RoleCapability` verwendet den **Name** -Parameter, um die Rolle " **General-Lev1** Role" anzugeben.
Das Objekt wird über die Pipeline gesendet. `Save-Module` verwendet den **path** -Parameter für den Speicherort des Dateisystems, um das Modul zu speichern. Nachdem das Modul gespeichert wurde, `Get-ChildItem` gibt den **Pfad** des Moduls an und zeigt den Inhalt des Verzeichnisses des **jeaexamples** -Moduls an.

### Beispiel 4: Suchen und Installieren des Moduls einer Rollen Funktion

`Find-RoleCapability` sucht das Modul und sendet das Objekt über die Pipeline. `Install-Module` installiert das-Modul. Verwenden Sie nach der Installation, `Get-InstalledModule` um die Ergebnisse anzuzeigen.

```
PS> Find-RoleCapability -Name General-Lev1 | Install-Module -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'JeaExamples'.
VERBOSE: InstallPackageLocal' - name='JeaExamples', version='1.0',
VERBOSE: Validating the 'JeaExamples' module contents
VERBOSE: Test-ModuleManifest successfully validated the module manifest file
VERBOSE: Module 'JeaExamples' was installed successfully to path

PS> Get-InstalledModule

Version    Name            Repository     Description
-------    ----            ----------     -----------
1.0        JeaExamples     PSGallery      Some example Jea roles for general server maintenance...
```

`Find-RoleCapability` verwendet den **Name** -Parameter, um die Rolle " **General-Lev1** Role" anzugeben.
Das Objekt wird über die Pipeline gesendet. `Install-Module` verwendet den **verbose** -Parameter, um Statusmeldungen während der Installation anzuzeigen. Nachdem die Installation abgeschlossen ist, wird in der `Get-InstalledModule` Ausgabe bestätigt, dass das **jeaexamples** -Modul installiert wurde.

## PARAMETERS

### -Allowprerelease

Schließt Ressourcen ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.

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

### -Allversions

Gibt an, dass dieses Cmdlet alle Versionen eines Moduls abruft. Der **allversions** -Parameter zeigt alle verfügbaren Versionen eines Moduls an.

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

Gibt die maximale Version des Moduls an, das in die Ergebnisse aufgenommen werden soll. Die Parameter " **MaximumVersion** " und "Requirements **dversion** " können nicht im selben Befehl verwendet werden.

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

Gibt die Mindestversion des Moduls an, das in den Ergebnissen enthalten sein soll. Der **MinimumVersion** -Parameter und der Requirements- **Version** -Parameter können nicht im selben Befehl verwendet werden.

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

Gibt den Namen des Moduls an, in dem nach Rollen Funktionen gesucht werden soll. Der Standardwert ist alle Module.

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

Gibt den Namen einer Rollen Funktion an. Der Standardwert ist alle Rollen Funktionen. Verwenden Sie Kommas, um ein Array von Ressourcennamen voneinander zu trennen.

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

Gibt ein Repository an, in dem nach Rollen Funktionen gesucht werden soll. Verwenden Sie Kommas, um ein Array von Repository-Namen zu trennen.

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

### System.Uri

### System. Management. Automation. PSCredential

## AUSGABEN

### PSGetRoleCapabilityInfo

Mit dem- `Find-RoleCapability` Cmdlet wird ein **psgetrolecapabilityinfo** -Objekt zurückgegeben.

## HINWEISE

> [!IMPORTANT]
> Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr. Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung. Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).

## VERWANDTE LINKS

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[Get-InstalledModule](Get-InstalledModule.md)

[Install-Module](Install-Module.md)

[New-PSRoleCapabilityFile](../Microsoft.PowerShell.Core/New-PSRoleCapabilityFile.md)

[Save-Module](Save-Module.md)
