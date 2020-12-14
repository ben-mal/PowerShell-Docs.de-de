---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Module
ms.openlocfilehash: c6468d2f8226cb26ec5385c7d5a8a895155ad673
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892653"
---
# Find-Module

## ZUSAMMENFASSUNG
Sucht Module in einem Repository, die den angegebenen Kriterien entsprechen.

## SYNTAX

### Alle

```
Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>]
 [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>]
 [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>]
 [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>]
 [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]
```

## DESCRIPTION

Das- `Find-Module` Cmdlet sucht Module in einem Repository, die den angegebenen Kriterien entsprechen.
`Find-Module` Gibt ein **PSRepositoryItemInfo** -Objekt für jedes gefundene Modul zurück. Die Objekte können über die Pipeline an Cmdlets wie gesendet werden `Install-Module` .

Wenn Sie zum ersten Mal `Find-Module` versuchen, ein Repository zu verwenden, werden Sie möglicherweise aufgefordert, Updates zu installieren.
Wenn die Repository-Quelle nicht mit dem- `Register-PSRepository` Cmdlet registriert ist, wird ein Fehler zurückgegeben.

`Find-Module` Gibt die neueste Version eines Moduls zurück, wenn keine Parameter verwendet werden, um die Version einzuschränken. Um die Liste der Versionen eines-Repository zu erhalten, verwenden Sie den-Parameter **allversions**.

Wenn der **MinimumVersion** -Parameter angegeben wird, `Find-Module` gibt die Version des Moduls zurück, das gleich oder größer als das Minimum ist. Wenn eine neuere Version im Repository verfügbar ist, wird die neuere Version zurückgegeben.

Wenn der **MaximumVersion** -Parameter angegeben wird, `Find-Module` gibt die neueste Version des Moduls zurück, die die angegebene Version nicht überschreitet.

Wenn der Parameter "Requirements **dversion** " angegeben ist, `Find-Module` gibt nur die Modulversion zurück, die exakt mit der angegebenen Version identisch ist. `Find-Module` durchsucht alle verfügbaren Module, da Namenskonflikte zwischen Quellen auftreten können.

In den folgenden Beispielen wird die [PowerShell-Katalog](https://www.powershellgallery.com/) als einziges registriertes Repository verwendet. `Get-PSRepository` zeigt die registrierten Depots an. Wenn Sie über mehrere registrierte Repository verfügen, verwenden Sie den `-Repository` -Parameter, um den Namen des Repository anzugeben.

## BEISPIELE

### Beispiel 1: Suchen nach einem Modul nach Name

In diesem Beispiel wird ein Modul im standardrepository gefunden.

```powershell
Find-Module -Name PowerShellGet
```

```Output
Version   Name              Repository           Description
-------   ----              ----------           -----------
2.1.0     PowerShellGet     PSGallery            PowerShell module with commands for discovering...
```

Das `Find-Module` Cmdlet verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.

### Beispiel 2: Suchen von Modulen mit ähnlichen Namen

In diesem Beispiel wird das Platzhalter Zeichen ( `*` ) verwendet, um Module mit ähnlichen Namen zu suchen.

```powershell
Find-Module -Name PowerShell*
```

```Output
Version   Name                            Repository    Description
-------   ----                            ----------    -----------
0.4.0     powershell-yaml                 PSGallery     Powershell module for serializing and...
2.1.0     PowerShellGet                   PSGallery     PowerShell module with commands for...
1.9       Powershell.Helper.Extension     PSGallery     # Powershell.Helper.Extension...
3.1       PowerShellHumanizer             PSGallery     PowerShell Humanizer wraps Humanizer...
4.0       PowerShellISEModule             PSGallery     a module that adds capability to the ISE
```

Das `Find-Module` Cmdlet verwendet den **Name** -Parameter mit dem Platzhalter Sternchen ( `*` ), um alle Module zu suchen, die **PowerShell** enthalten.

### Beispiel 3: Suchen eines Moduls nach minimaler Version

Dieses Beispiel sucht nach der Mindestversion eines Moduls. Wenn das Repository eine neuere Version des Moduls enthält, wird die neuere Version zurückgegeben.

```powershell
Find-Module -Name PowerShellGet -MinimumVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

Das `Find-Module` Cmdlet verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben. Die **MinimumVersion** gibt Version **1.6.5** an. `Find-Module` gibt PowerShellGet Version **2.1.0** zurück, da Sie die Mindestversion überschreitet und die aktuelle Version ist.

### Beispiel 4: Suchen eines Moduls nach spezifischer Version

In diesem Beispiel wird ein-Objekt zurückgegeben, das die spezifische Version eines Moduls darstellt. Wenn die angegebene Version nicht gefunden wird, wird ein Fehler zurückgegeben.

```powershell
Find-Module -Name PowerShellGet -RequiredVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
1.6.5     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

Das `Find-Module` Cmdlet verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben. Der Requirements **dversion** -Parameter gibt die Version **1.6.5** an.

### Beispiel 5: Suchen eines Moduls in einem bestimmten Repository

In diesem Beispiel wird der **Repository** -Parameter verwendet, um ein Modul in einem bestimmten Repository zu suchen.

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

Das `Find-Module` Cmdlet verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben. Der **Repository** -Parameter gibt an, um das **psgallery** -Repository zu durchsuchen

### Beispiel 6: Suchen eines Moduls in mehreren Depots

In diesem Beispiel wird verwendet `Register-PSRepository` , um ein Repository anzugeben. `Find-Module` verwendet das Repository, um nach einem Modul zu suchen.

```powershell
Register-PSRepository -Name MySource -SourceLocation https://www.myget.org/F/powershellgetdemo/
Find-Module -Name Contoso* -Repository PSGallery, MySource
```

```Output
Repository    Version   Name             Description
----------    -------   ----             -----------
PSGallery     2.0.0.0   ContosoServer    Cmdlets and DSC resources for managing Contoso Server...
MySource      1.2.0.0   ContosoClient    Cmdlets and DSC resources for managing Contoso Client...
```

Mit dem- `Register-PSRepository` Cmdlet wird ein neues Repository registriert. Mit dem **Name** -Parameter wird der Name **MySource** zugewiesen. Der **sourcelokation** -Parameter gibt die Adresse des Repository an.

Das `Find-Module` Cmdlet verwendet den **Name** -Parameter mit dem Platzhalter Sternchen ( `*` ),  um das Modul "Configuration Manager" anzugeben. Der **Repository** -Parameter gibt an, dass zwei Depots, **psgallery** und **MySource**, durchsucht werden sollen.

### Beispiel 7: Suchen eines Moduls, das eine DSC-Ressource enthält

Dieser Befehl gibt Module zurück, die DSC-Ressourcen enthalten. Der **includes** -Parameter verfügt über vier vordefinierte Funktionen, die verwendet werden, um das Repository zu durchsuchen. Verwenden Sie Tab-Complete, um die vier Funktionen anzuzeigen, die vom **includes** -Parameter unterstützt werden.

```powershell
Find-Module -Repository PSGallery -Includes DscResource
```

```Output
Version     Name                            Repository    Description
-------     ----                            ----------    -----------
2.7.0       Carbon                          PSGallery     Carbon is a PowerShell module...
8.5.0.0     xPSDesiredStateConfiguration    PSGallery     The xPSDesiredStateConfiguration module...
1.3.1       PackageManagement               PSGallery     PackageManagement (a.k.a. OneGet) is...
2.7.0.0     xWindowsUpdate                  PSGallery     Module with DSC Resources...
3.2.0.0     xCertificate                    PSGallery     This module includes DSC resources...
3.1.0.0     xPowerShellExecutionPolicy      PSGallery     This DSC resource can change the user...
```

Das `Find-Module` Cmdlet verwendet den **Repository** -Parameter, um das Repository **psgallery** zu durchsuchen.
Der **includes** -Parameter gibt **dscresource** an. Hierbei handelt es sich um eine Funktion, nach der der Parameter im Repository suchen kann.

### Beispiel 8: Suchen eines Moduls mit einem Filter

Wenn Sie in diesem Beispiel Module suchen, wird ein Filter verwendet, um das Repository zu durchsuchen.

Bei einem nuget-basierten Repository durchsucht der **Filter** Parameter den Namen, die Beschreibung und die Tags für das Argument.

```powershell
Find-Module -Filter AppDomain
```

```Output
Version    Name              Repository           Description
-------    ----              ----------           -----------
1.0.0.0  AppDomainConfig     PSGallery            Manipulate AppDomain configuration...
1.1.0    ClassExplorer       PSGallery            Quickly search the AppDomain for classes...
```

Das `Find-Module` Cmdlet verwendet den **Filter** -Parameter, um das Repository nach **AppDomain** zu durchsuchen.

## PARAMETERS

### -Allowprerelease

Schließt in die als Vorabversion markierten Ergebnis Module ein.

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

Gibt an, dass alle Versionen eines Moduls in die Ergebnisse eingeschlossen werden sollen. Der **allversions** -Parameter kann nicht mit den Parametern **MinimumVersion**, **MaximumVersion** oder Requirements **dversion** verwendet werden.

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

### -Command

Gibt ein Array von Befehlen an, die in Modulen gesucht werden sollen. Bei einem Befehl kann es sich um eine Funktion oder einen Workflow handeln.

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

### -Credential

Gibt ein Benutzerkonto an, das über Rechte zum Installieren eines Moduls für einen angegebenen Paketanbieter oder eine angegebene Quelle verfügt.

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

### -Dscresource

Gibt den Namen oder einen Teil des Namens von Modulen an, die DSC-Ressourcen enthalten. Gemäß PowerShell-Konventionen führt eine- **oder** -Suche durch, wenn Sie mehrere Argumente bereitstellen.

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

### -Filter

Gibt einen Filter an, der auf der anbieterspezifischen Such Syntax für **packagemanagement** basiert. Bei nuget-Modulen entspricht dieser Parameter dem Suchen mithilfe der Suchleiste auf der [PowerShell-Katalog](https://www.powershellgallery.com/) Website.

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

### -Includababhängigkeiten

Gibt an, dass dieser Vorgang alle Module einschließt, die von dem im **Name** -Parameter angegebenen Modul abhängig sind.

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

### -Includes

Gibt nur die Module zurück, die bestimmte Arten von PowerShell-Funktionen enthalten. Beispielsweise möchten Sie möglicherweise nur Module suchen, die **dscresource** enthalten. Die zulässigen Werte für diesen Parameter lauten wie folgt:

- Cmdlet
- DscResource
- Funktion
- RoleCapability

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: DscResource, Cmdlet, Function, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVersion

Gibt die maximale oder neueste Version des Moduls an, das in den Suchergebnissen enthalten sein soll.
**MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

Gibt die Mindestversion des Moduls an, das in den Ergebnissen enthalten sein soll. **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt die Namen der Module an, die im Repository gesucht werden sollen. Eine durch Trennzeichen getrennte Liste von Modulnamen wird akzeptiert. Platzhalter werden akzeptiert.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Proxy Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.

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

Verwenden Sie den **Repository** -Parameter, um anzugeben, welches Repository nach einem Modul durchsucht werden soll. Wird verwendet, wenn mehrere Depots registriert sind. Akzeptiert eine durch Trennzeichen getrennte Liste von Depots. Verwenden Sie zum Registrieren eines Repository `Register-PSRepository` . Verwenden Sie, um registrierte Depots anzuzeigen `Get-PSRepository` .

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

Gibt die genaue Versionsnummer des Moduls an, das in die Ergebnisse aufgenommen werden soll. "Requirements **dversion** " kann nicht im gleichen Befehl wie " **MinimumVersion** " oder " **MaximumVersion**" verwendet werden.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rolecapability

Gibt ein Array von Rollen Funktionen an.

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

### -Tag

Gibt ein Array von-Tags an. Beispiele hierfür sind " **desiredStatus econfiguration**", " **DSC**", " **dscresourcekit**" oder " **psmodule**".

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

### System.String[]

### System.String

### System.Uri

### System. Management. Automation. PSCredential

## AUSGABEN

### PSRepositoryItemInfo

`Find-Module` erstellt **PSRepositoryItemInfo** -Objekte, die über die Pipeline an Cmdlets wie gesendet werden können, z `Install-Module` . b..

## HINWEISE

> [!IMPORTANT]
> Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1. Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen. Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.

## VERWANDTE LINKS

[Get-PSRepository](Get-PSRepository.md)

[Install-Module](Install-Module.md)

[Publish-Module](Publish-Module.md)

[Save-Module](Save-Module.md)

[Uninstall-Module](Uninstall-Module.md)

[Update-Module](Update-Module.md)

[Register-PSRepository](Register-PSRepository.md)
