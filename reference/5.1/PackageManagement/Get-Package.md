---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/22/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Package
ms.openlocfilehash: bc6ba83a6f0d585e166b1bdc419c8b9c7148e47c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892881"
---
# Get-Package

## ZUSAMMENFASSUNG
Gibt eine Liste aller Softwarepakete zurück, die mit **packagemanagement** installiert wurden.

## SYNTAX

### MSI-Datei

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-AdditionalArguments <String[]>] [<CommonParameters>]
```

### Programs

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-IncludeWindowsInstaller] [-IncludeSystemComponent] [<CommonParameters>]
```

### NuGet

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### PowerShellGet

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Scope <String>] [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Package` Cmdlet wird eine Liste aller Softwarepakete auf dem lokalen Computer zurückgegeben, die mit **packagemanagement** installiert wurden. Sie können `Get-Package` auf Remote Computern ausführen, indem Sie Sie als Teil eines- `Invoke-Command` oder- `Enter-PSSession` Befehls oder-Skripts ausführen.

## BEISPIELE

### Beispiel 1: alle installierten Pakete erhalten

Mit dem- `Get-Package` Cmdlet werden alle Pakete abgerufen, die auf dem lokalen Computer installiert sind.

```powershell
Get-Package
```

```Output
Name           Version      Source                                     ProviderName
----           -------      ------                                     ------------
posh-git       0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
```

### Beispiel 2: Get-Pakete, die auf einem Remote Computer installiert sind

Mit diesem Befehl wird eine Liste der Pakete abgerufen, die von **packagemanagement** auf einem Remote Computer installiert wurden. Mit diesem Befehl werden Sie aufgefordert, das Kennwort des angegebenen Benutzers anzugeben.

```
PS> Invoke-Command -ComputerName Server01 -Credential CONTOSO\TestUser -ScriptBlock {Get-Package}
```

`Invoke-Command` verwendet den **Computername** -Parameter, um einen Remote Computer anzugeben, **Server01**. Der **Credential** -Parameter gibt eine Domäne und einen Benutzernamen mit Berechtigungen zum Ausführen von Befehlen auf dem Computer an. Der **ScriptBlock** -Parameter führt das `Get-Package` Cmdlet auf dem Remote Computer aus.

### Beispiel 3: Paket für einen angegebenen Anbieter erhalten

Mit diesem Befehl werden die auf dem lokalen Computer installierten Softwarepakete von einem bestimmten Anbieter abgerufen.

```powershell
Get-Package -ProviderName PowerShellGet -AllVersions
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.2.2        https://www.powershellgallery.com/api/v2   PowerShellGet
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
posh-git              0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
PowerShellGet         2.0.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

`Get-Package` verwendet den **providerName** -Parameter, um einen bestimmten Anbieter, **PowerShellGet**, anzugeben.
Mit dem Parameter **alle Versionen** wird jede installierte Version angezeigt.

### Beispiel 4: beziehen einer exakten Version eines bestimmten Pakets

Mit diesem Befehl wird eine bestimmte Version eines installierten Pakets abgerufen. Es können mehr als eine Version eines Pakets installiert werden.

```powershell
Get-Package -Name PackageManagement -ProviderName PowerShellGet -RequiredVersion 1.3.1
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

`Get-Package` verwendet den **Name** -Parameter, um den Paketnamen, **packagemanagement**, anzugeben. Der **providerName** -Parameter gibt den Anbieter **PowerShellGet** an. Der **erforderliche-Version-** Parameter gibt eine installierte Version an.

### Beispiel 5: Deinstallieren eines Pakets

In diesem Beispiel werden Paketinformationen abgerufen und dann das Paket deinstalliert.

```powershell
Get-Package -Name posh-git -RequiredVersion 0.7.3 | Uninstall-Package
```

`Get-Package` verwendet den **Name** -Parameter zum Angeben des Paket namens **Posh-git**. Der Parameter "Requirements **dversion** " ist eine bestimmte Version des Pakets. Das Objekt wird über die Pipeline an das `Uninstall-Package` Cmdlet gesendet. `Uninstall-Package` entfernt das Paket.

## PARAMETERS

### -Allowclobber

Überschreibt Warnmeldungen zu Konflikten mit vorhandenen Befehlen. Überschreibt vorhandene Befehle mit demselben Namen wie Befehle, die von einem Modul installiert werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Allowprereleaseversions

Schließt Pakete ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Allversions

Gibt an, dass `Get-Package` alle verfügbaren Versionen des Pakets zurückgibt. Standardmäßig wird `Get-Package` nur die neueste verfügbare Version zurückgegeben.

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

### -Destination

Gibt den Pfad zu einem Verzeichnis an, das extrahierte Paketdateien enthält.

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Excludeversion

Wechseln Sie zum Ausschließen der Versionsnummer im Ordner Pfad.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Forcebootstrap

Gibt an, dass `Get-Package` **packagemanagement** zwingt, den Paketanbieter automatisch zu installieren.

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

### -Installupdate

Gibt an, dass dieses Cmdlet Updates installiert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVersion

Gibt die maximale Paketversion an, die Sie suchen möchten.

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

Gibt die minimale Paketversion an, die Sie suchen möchten. Wenn eine höhere Version verfügbar ist, wird diese Version zurückgegeben.

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

Gibt einen oder mehrere Paketnamen oder Paketnamen mit Platzhalter Zeichen an. Trennen Sie mehrere Paketnamen durch Kommas.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Nopathupdate

**Nopathupdate** gilt nur für das `Install-Script` Cmdlet. **Nopathupdate** ist ein vom Anbieter hinzugefügter dynamischer Parameter, der von nicht unterstützt wird `Get-Package` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Packagemanagementprovider

Gibt den Namen eines Paket Verwaltungs Anbieters an.

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName

Gibt einen oder mehrere Paketanbieter Namen an. Trennen Sie mehrere Paketanbieter Namen durch Kommas.
Verwenden `Get-PackageProvider` Sie, um eine Liste der verfügbaren Paketanbieter zu erhalten.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Requirements dversion

Gibt die genaue Version des zu suchenden Pakets an.

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

### -Bereich

Gibt den Suchbereich für das Paket an.

```yaml
Type: System.String
Parameter Sets: NuGet, PowerShellGet
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skipabhängigkeiten

Switch, der angibt, dass das Suchen nach Paketabhängigkeiten übersprungen werden soll

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skippublishercheck

Ermöglicht es Ihnen, eine Paketversion zu erhalten, die neuer als die installierte Version ist. Beispielsweise wird ein installiertes Paket, das von einem vertrauenswürdigen Verleger digital signiert ist, aber eine neue Version ist nicht digital signiert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

Gibt an, ob nach Paketen mit einem Modul, einem Skript oder einer der beiden Optionen gesucht werden soll.

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Additionalarguments

Gibt zusätzliche Argumente an.

```yaml
Type: System.String[]
Parameter Sets: msi
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Includesystemcomponent

Gibt an, dass dieses Cmdlet Systemkomponenten in die Ergebnisse einschließt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Include WindowsInstaller

Gibt an, dass dieses Cmdlet die Windows Installer in die Ergebnisse einschließt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs
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

### Software Identity []

## HINWEISE

Durch das Einschließen eines Paket Anbieters in einen Befehl können dynamische Parameter für ein Cmdlet verfügbar gemacht werden. Dynamische Parameter sind für einen Paketanbieter spezifisch. Das `Get-Help` -Cmdlet listet die Parametersätze eines Cmdlets auf und schließt den Parametersatz des Anbieters ein. Beispielsweise `Get-Package` ist für den **PowerShellGet** -Parameter festgelegt, der `-NoPathUpdate` , und enthält `AllowClobber` `SkipPublisherCheck` .

> [!IMPORTANT]
> Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1. Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen. Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.

## VERWANDTE LINKS

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Enter-PSSession](../Microsoft.PowerShell.Core/Enter-PSSession.md)

[Find-Package](Find-Package.md)

[Get-Help](../Microsoft.PowerShell.Core/Get-Help.md)

[Get-PackageProvider](Get-PackageProvider.md)

[Get-PackageSource](Get-PackageSource.md)

[Install-Package](Install-Package.md)

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[Save-Package](Save-Package.md)

[Uninstall-Package](Uninstall-Package.md)
