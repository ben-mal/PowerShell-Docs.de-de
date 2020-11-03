---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/install-script?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Script
ms.openlocfilehash: ecae1ba3a3aea6628817bab2f09fc23e23162f03
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215983"
---
# Install-Script

## ZUSAMMENFASSUNG
Installiert ein Skript.

## SYNTAX

### Nameparameterset (Standard)

```
Install-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Scope <String>] [-NoPathUpdate]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Install-Script [-InputObject] <PSObject[]> [-Scope <String>] [-NoPathUpdate] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Install-Script` Cmdlet ruft eine Skript Nutzlast aus einem Repository ab, überprüft, ob die Nutzlast ein gültiges PowerShell-Skript ist, und kopiert die Skriptdatei an einen angegebenen Installations Speicherort.

Die standardrepositorys `Install-Script` können mit den `Register-PSRepository` `Set-PSRepository` `Unregister-PSRepository` Cmdlets,, und konfiguriert werden `Get-PSRepository` . Wenn Sie mit mehreren Depots arbeiten, wird `Install-Script` das erste Skript, das den angegebenen Suchkriterien ( **Name** , **MinimumVersion** oder **MaximumVersion** ) entspricht, aus dem ersten Repository ohne Fehler installiert.

## BEISPIELE

### Beispiel 1: Suchen eines Skripts und Installieren des Skripts

```
PS C:\> Find-Script -Repository "Local1" -Name "Required-Script2"
Version    Name                           Type       Repository           Description
-------    ----                           ----       ----------           -----------
2.5        Required-Script2               Script     local1               Description for the Required-Script2 script

PS C:\> Find-Script -Repository "Local1" -Name "Required-Script2" | Install-Script
PS C:\> Get-Command -Name "Required-Script2"
CommandType     Name                      Version    Source
-----------     ----                      -------    ------
ExternalScript  Required-Script2.ps1      2.0       C:\Users\pattif\Documents\WindowsPowerShell\Scripts\Required-Script2.ps1

PS C:\> Get-InstalledScript -Name "Required-Script2"
Version    Name                  Type     Repository           Description
-------    ----                  ----     ----------           -----------
2.5        Required-Script2      Script   local1               Description for the Required-Script2 script

PS C:\> Get-InstalledScript -Name "Required-Script2" | Format-List *
Name                       : Required-Script2
Version                    : 2.5
Type                       : Script
Description                : Description for the Required-Script2 script
Author                     : pattif
CompanyName                :
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/15/2015 12:42:39 AM
LicenseUri                 : http://required-script2.com/license
ProjectUri                 : http://required-script2.com/
IconUri                    : http://required-script2.com/icon
Tags                       : {Tag1, Tag2, Tag-Required-Script2-2.5, PSScript...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script2 release notes
Dependencies               : {}
RepositorySourceLocation   : http://pattif-dev:8765/api/v2/
Repository                 : local1
PackageManagementProvider  : NuGet
InstalledLocation          : C:\Users\pattif\Documents\WindowsPowerShell\Scripts
```

Der erste Befehl sucht das Skript `Required-Script2` aus dem local1-Repository und zeigt die Ergebnisse an.

Mit dem zweiten Befehl `Required-Script2` wird das Skript gefunden und dann mithilfe des Pipeline Operators an das `Install-Script` Cmdlet übergeben, um es zu installieren.

Der dritte Befehl verwendet das `Get-Command` Cmdlet, um die Ergebnisse zu erhalten `Required-Script2` , und zeigt dann die Ergebnisse an.

Der vierte Befehl verwendet das `Get-InstalledScript` Cmdlet, um `Required-Script2` die Ergebnisse zu erhalten und anzuzeigen.

Mit dem fünften Befehl wird `Required-Script2` der Pipeline Operator abgerufen und verwendet, um ihn an das `Format-List` Cmdlet zu übergeben, um die Ausgabe zu formatieren.

### Beispiel 2: Installieren eines Skripts mit dem Bereich "ALLUSERS"

```
PS C:\> Install-Script -Repository "Local1" -Name "Required-Script3" -Scope "AllUsers"
PS C:\> Get-InstalledScript -Name "Required-Script3"
Version    Name                  Type       Repository    Description
-------    ----                  ----       ----------    -----------
2.5        Required-Script3      Script     local1        Description for the Required-Script3 script

PS C:\> Get-InstalledScript -Name "Required-Script3" | Format-List *
Name                       : Required-Script3
Version                    : 2.5
Type                       : Script
Description                : Description for the Required-Script3 script
Author                     : pattif
CompanyName                :
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/15/2015 12:42:45 AM
LicenseUri                 : http://required-script3.com/license
ProjectUri                 : http://required-script3.com/
IconUri                    : http://required-script3.com/icon
Tags                       : {Tag1, Tag2, Tag-Required-Script3-2.5, PSScript...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script3 release notes
Dependencies               : {}
RepositorySourceLocation   : http://pattif-dev:8765/api/v2/
Repository                 : local1
PackageManagementProvider  : NuGet
InstalledLocation          : C:\Program Files\WindowsPowerShell\Scripts
```

Der erste Befehl installiert das Skript mit dem Namen `Required-Script3` und weist es dem Bereich "ALLUSERS" zu.

Mit dem zweiten Befehl wird das installierte Skript abgerufen `Required-Script3` und Informationen darüber angezeigt.

Der dritte Befehl ruft `Required-Script3` den Pipeline Operator ab und verwendet ihn, um ihn an das `Format-List` Cmdlet zu übergeben, um die Ausgabe zu formatieren.

### Beispiel 3: Installieren eines Skripts und seiner Abhängigkeiten

```
PS C:\> Find-Script -Repository "Local1" -Name "Script-WithDependencies2" -IncludeDependencies
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.0        Script-WithDependencies2    Script     local1        Description for the Script-WithDependencies2 script
2.5        RequiredModule1             Module     local1        RequiredModule1 module
2.5        RequiredModule2             Module     local1        RequiredModule2 module
2.5        RequiredModule3             Module     local1        RequiredModule3 module
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script

PS C:\> Install-Script -Repository "Local1" -Name "Script-WithDependencies2"
PS C:\> Get-InstalledScript
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script
2.0        Script-WithDependencies2    Script     local1        Description for the Script-WithDependencies2 script

PS C:\> Get-InstalledModule
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        RequiredModule1             Module     local1        RequiredModule1 module
2.5        RequiredModule2             Module     local1        RequiredModule2 module
2.5        RequiredModule3             Module     local1        RequiredModule3 module

PS C:\> Find-Script -Repository "Local1" -Name "Required-Script*"
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script

PS C:\> Install-Script -Repository "Local1" -Name "Required-Script*"
PS C:\> Get-InstalledScript
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script
```

Der erste Befehl sucht das Skript `Script-WithDependencies2` und seine Abhängigkeiten im Repository local1 und zeigt die Ergebnisse an.

Mit dem zweiten Befehl wird installiert `Script-WithDependencies2` .

Der dritte Befehl verwendet das `Get-InstalledScript` Script-Cmdlet, um installierte Skripts zu erhalten und die Ergebnisse anzuzeigen.

Der vierte Befehl verwendet das `Get-InstalledModule` Cmdlet, um installierte Module zu erhalten und die Ergebnisse anzuzeigen.

Der fünfte Befehl verwendet das `Find-Script` Cmdlet, um Skripts zu suchen, bei denen der Name mit beginnt, `Required-Script` und zeigt die Ergebnisse an.

Der sechste Befehl installiert die Skripts, bei denen der Name mit beginnt, `Required-Script` im local1-Repository.

Der letzte Befehl ruft installierte Skripts ab und zeigt die Ergebnisse an.

## PARAMETERS

### -AcceptLicense

Akzeptieren Sie den Lizenzvertrag während der Installation automatisch, wenn dies für das Modul erforderlich ist.

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

### -Allowprerelease

Ermöglicht das Installieren eines als Vorabversion markierten Skripts.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
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

### -Credential

Gibt ein Benutzerkonto an, das über Rechte zum Installieren eines Skripts für einen angegebenen Paketanbieter oder eine angegebene Quelle verfügt.

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

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

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

Wird für Pipeline Eingaben verwendet.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaximumVersion

Gibt die maximale Version eines einzelnen Skripts an, das installiert werden soll. Sie können diesen Parameter nicht hinzufügen, wenn Sie versuchen, mehrere Skripts zu installieren. Die Parameter " **MaximumVersion** " und "Requirements **dversion** " schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

Gibt die Mindestversion eines einzelnen Skripts an, das installiert werden soll. Sie können diesen Parameter nicht hinzufügen, wenn Sie versuchen, mehrere Skripts zu installieren. Der **MinimumVersion** -Parameter und der Requirements- **Version** -Parameter schließen sich gegenseitig aus. beide Parameter können nicht im selben Befehl verwendet werden.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt ein Array von Namen von Skripts an, die installiert werden sollen.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nopathupdate

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

### -PassThru

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

Gibt den anzeigen Amen eines Repository an, das beim `Register-PSRepository` Cmdlet registriert wurde. Der Standardwert ist alle registrierten Depots.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Requirements dversion

Gibt die genaue Versionsnummer des zu installierenden Skripts an.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Bereich

Gibt den Bereich der Installation des Skripts an.
Gültige Werte sind: AllUsers und CurrentUser.

Mit dem Bereich "ALLUSERS" können Module an einem Speicherort installiert werden, der für alle Benutzer des Computers zugänglich ist, d `$env:ProgramFiles\WindowsPowerShell\Scripts` . h..

Mit dem Bereich CurrentUser können Module nur für installiert werden `$home\Documents\WindowsPowerShell\Scripts` , damit das Modul nur für den aktuellen Benutzer verfügbar ist.

Wenn kein **Bereich** definiert ist, wird der Standardwert basierend auf der aktuellen Sitzung festgelegt:

- Für eine PowerShell-Sitzung mit erhöhten Rechten wird der Gültigkeits **Bereich** auf ALLUSERS eingestellt.
- Für PowerShell-Sitzungen ohne erhöhte Rechte in [PowerShellGet, Version 2.0.0](https://www.powershellgallery.com/packages/PowerShellGet) und höher, liegt der Gültigkeits **Bereich** bei CurrentUser.
- Bei nicht erhöhten PowerShell-Sitzungen in PowerShellGet-Versionen 1.6.7 und früher ist der Gültigkeits **Bereich** nicht definiert und `Install-Module` schlägt fehl.

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

### System.String[]

### System. Management. Automation. psobject []

### System.String

### System.Uri

### System. Management. Automation. PSCredential

## AUSGABEN

### System.Object

## HINWEISE

## VERWANDTE LINKS

[Find-Script](Find-Script.md)

[Publish-Script](Publish-Script.md)

[Save-Script](Save-Script.md)

[Uninstall-Script](Uninstall-Script.md)

[Update-Script](Update-Script.md)
