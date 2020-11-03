---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-command?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Command
ms.openlocfilehash: 0e168279c342be404a2298f3ba767bed912d4af5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214772"
---
# Find-Command

## ZUSAMMENFASSUNG
Sucht PowerShell-Befehle in Modulen.

## SYNTAX

### Alle

```
Find-Command [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Find-Command` Cmdlet findet PowerShell-Befehle, z. b. Cmdlets, Aliase, Funktionen und Workflows. `Find-Command` durchsucht Module in registrierten Depots.

Für jeden von gefundenen Befehl `Find-Command` wird ein **psgetcommandinfo** -Objekt zurückgegeben. Das **psgetcommandinfo** -Objekt kann über die Pipeline an das `Install-Module` Cmdlet gesendet werden.
`Install-Module` installiert das Modul, das den Befehl enthält.

## BEISPIELE

### Beispiel 1: Suchen aller Befehle in einem angegebenen Repository

Mit dem- `Find-Command` Cmdlet wird ein registriertes Repository nach Modulen durchsucht.

```powershell
Find-Command -Repository PSGallery | Select-Object -First 10
```

```output
Name                                Version    ModuleName          Repository
----                                -------    ----------          ----------
Disable-AzureRmDataCollection       5.8.3      AzureRM.profile     PSGallery
Disable-AzureRmContextAutosave      5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmDataCollection        5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmContextAutosave       5.8.3      AzureRM.profile     PSGallery
Remove-AzureRmEnvironment           5.8.3      AzureRM.profile     PSGallery
Get-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Set-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Add-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Get-AzureRmSubscription             5.8.3      AzureRM.profile     PSGallery
Connect-AzureRmAccount              5.8.3      AzureRM.profile     PSGallery
```

`Find-Command` verwendet den **Repository** -Parameter, um den Namen eines registrierten Repository anzugeben. Die Objekte werden über die Pipeline gesendet. `Select-Object` empfängt die Objekte und verwendet den **ersten** Parameter, um die ersten 10 Ergebnisse anzuzeigen.

### Beispiel 2: Suchen eines Befehls anhand des Namens

`Find-Command` kann den Namen eines Befehls verwenden, um das Modul in einem Repository zu suchen. Es ist möglich, dass ein Befehls Name in mehreren **modulenames** vorhanden ist.

```powershell
Find-Command -Repository PSGallery -Name Get-TargetResource
```

```Output
Name                  Version    ModuleName                      Repository
----                  -------    ----------                      ----------
Get-TargetResource    3.1.0.0    xPowerShellExecutionPolicy      PSGallery
Get-TargetResource    1.0.0      xInternetExplorerHomePage       PSGallery
Get-TargetResource    1.2.0.0    SystemLocaleDsc                 PSGallery
```

`Find-Command` verwendet den **Repository** -Parameter, um den **psgallery** zu durchsuchen. Der **Name** -Parameter gibt den Befehl **Get-targetresource** an.

### Beispiel 3: Suchen nach Befehlen nach Name und Installieren des Moduls

`Find-Command` kann den Befehl und das Modul suchen und dann das Objekt an senden `Install-Module` . Wenn ein Befehl in mehreren Modulen enthalten ist, verwenden Sie den `Find-Command` **Module-Name-** Parameter des Cmdlets.
Andernfalls können Module installiert werden, die Sie nicht installieren möchten.

```powershell
PS> Find-Command -Name Get-TargetResource -Repository PSGallery -ModuleName SystemLocaleDsc |
    Install-Module

PS> Get-InstalledModule

Version   Name               Repository   Description
-------   ----               ----------   -----------
1.2.0.0   SystemLocaleDsc    PSGallery    This DSC Resource allows configuration of the Windows...
```

`Find-Command` verwendet den **Name** -Parameter, um den Befehl " **Get-targetresource** " anzugeben. Der **Repository** -Parameter durchsucht den **psgallery** . Der **ModuleName** -Parameter gibt das Modul an, das Sie installieren möchten, **systemlocaledsc** . Das-Objekt wird an die Pipeline gesendet, `Install-Module` und das-Modul wird installiert. Nachdem die Installation abgeschlossen ist, können Sie verwenden, `Get-InstalledModule` um die Ergebnisse anzuzeigen.

### Beispiel 4: Suchen eines Befehls und Speichern des Moduls

```
PS> Find-Command -Name Invoke-ScriptAnalyzer -Repository PSGallery | Save-Module -Path C:\Test\Modules -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'PSScriptAnalyzer'.
VERBOSE: Module 'PSScriptAnalyzer' was saved successfully to path 'C:\Test\Modules\PSScriptAnalyzer\1.18.0'.
```

`Find-Command`verwendet die Parameter **Name** und **Repository** , um im **psgallery** -Repository nach dem Befehl " **Aufruf-scriptanalyzer** " zu suchen. Das Objekt wird über die Pipeline an gesendet `Save-Module` . Der **path** -Parameter bestimmt den Speicherort, an dem das Modul gespeichert wird. **Verbose** ist ein optionaler Parameter, zeigt jedoch die Status Ausgabe in der PowerShell-Konsole an. Die ausführliche Ausgabe ist von Vorteil bei der Problembehandlung.

## PARAMETERS

### -Allowprerelease

Schließt Module ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.

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

Gibt an, dass dieses Cmdlet alle Versionen eines Moduls abruft.

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

Sucht Module basierend auf der Such Syntax des **packagemanagement** -Anbieters. Geben Sie z. b. die Wörter an, nach denen in den Eigenschaften **ModuleName** und **Description** gesucht werden soll.

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

Gibt den Namen eines Moduls an, in dem nach Befehlen gesucht werden soll. Der Standardwert ist alle Module.

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

Gibt den Namen des Befehls an, nach dem in einem Repository gesucht werden soll. Verwenden Sie Kommas, um ein Array von Befehlsnamen zu trennen.

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

Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy** -Parameter angegeben wird.

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

Gibt das Repository für die Suche nach Befehlen an. Verwenden Sie Kommas, um ein Array von Repository-Namen zu trennen. Der Standardwert ist alle Depots.

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

Gibt die Version des Moduls an, das in die Ergebnisse aufgenommen werden soll.

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

### PSGetCommandInfo

`Find-Command` Gibt ein **psgetcommandinfo** -Objekt aus.

## HINWEISE

## VERWANDTE LINKS

[Get-InstalledModule](Get-InstalledModule.md)

[Install-Module](Install-Module.md)

[Save-Module](Save-Module.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Uninstall-Module](Uninstall-Module.md)
