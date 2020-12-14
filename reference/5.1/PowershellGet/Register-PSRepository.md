---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: 07f70f4fad6057ad689befaafd1d41f819a4538c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892762"
---
# Register-PSRepository

## ZUSAMMENFASSUNG
Registriert ein PowerShell-Repository.

## SYNTAX

### Nameparameterset (Standard)

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### Psgalleryparameterset

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Register-PSRepository` Cmdlet wird das standardrepository für PowerShell-Module registriert. Nachdem ein Repository registriert wurde, können Sie aus den `Find-Module` `Install-Module` Cmdlets, und darauf verweisen `Publish-Module` . Das registrierte Repository wird das standardrepository in `Find-Module` und `Install-Module` .

Registrierte Repositorys sind benutzerspezifisch. Sie sind nicht in einem systemweiten Kontext registriert.

Jedes registrierte Repository ist einem oneget-Paketanbieter zugeordnet, der mit dem **packagemanagementprovider** -Parameter angegeben wird. Jeder oneget-Anbieter ist für die Interaktion mit einem bestimmten Repository konzipiert. Der nuget-Anbieter ist beispielsweise für die Interaktion mit nuget-basierten Depots konzipiert. Wenn ein oneget-Anbieter während der Registrierung nicht angegeben wird, versucht PowerShellGet, einen oneget-Anbieter zu finden, der den angegebenen Quell Speicherort verarbeiten kann.

## BEISPIELE

### Beispiel 1: Registrieren eines Repository

```powershell
$parameters = @{
  Name = "myNuGetSource"
  SourceLocation = "https://www.myget.org/F/powershellgetdemo/api/v2"
  PublishLocation = "https://www.myget.org/F/powershellgetdemo/api/v2/Packages"
  InstallationPolicy = 'Trusted'
}
Register-PSRepository @parameters
Get-PSRepository
```

```Output
Name                SourceLocation          OneGetProvider       InstallationPolicy
----                --------------          --------------       ------------------
PSGallery           http://go.micro...      NuGet                Untrusted
myNuGetSource       https://myget.c...      NuGet                Trusted
```

Der erste Befehl wird `https://www.myget.org/F/powershellgetdemo/` als Repository für den aktuellen Benutzer registriert. Nachdem Sie mynugetsource registriert haben, können Sie beim Suchen, installieren und Veröffentlichen von Modulen explizit darauf verweisen. Da der **packagemanagementprovider** -Parameter nicht angegeben wird, ist das Repository nicht explizit einem oneget-Paketanbieter zugeordnet, sodass PowerShellGet verfügbare Paketanbieter abruft und dem nuget-Anbieter zuordnet.

Mit dem zweiten Befehl werden registrierte Depots abgerufen und die Ergebnisse angezeigt.

## PARAMETERS

### -Credential

Gibt die Anmelde Informationen eines Kontos an, das über Rechte zum Registrieren eines Repository verfügt.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Default

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PSGalleryParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Installationpolicy

Gibt die Installations Richtlinie an. Gültige Werte sind: vertrauenswürdig, nicht vertrauenswürdig. Der Standardwert ist nicht vertrauenswürdig.

Die Installations Richtlinie eines Repository gibt das PowerShell-Verhalten bei der Installation aus diesem Repository an. Wenn Sie Module aus einem nicht vertrauenswürdigen Repository installieren, wird der Benutzer zur Bestätigung aufgefordert.

Sie können die **installationpolicy** mit dem- `Set-PSRepository` Cmdlet festlegen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Trusted, Untrusted

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt den Namen des zu registrierenden Repository an. Sie können diesen Namen verwenden, um das Repository in Cmdlets anzugeben, `Find-Module` z `Install-Module` . b. und.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Packagemanagementprovider

Gibt einen oneget-Paketanbieter an. Wenn Sie keinen Wert für diesen Parameter angeben, fragt PowerShellGet verfügbare Paketanbieter ab und ordnet dieses Repository dem ersten Paketanbieter zu, der angibt, dass das Repository behandelt werden kann.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
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

### -Publishlocation

Gibt den URI des Veröffentlichungs Speicher Orts an. Beispielsweise ist für nuget-basierte Depots der Veröffentlichungs Speicherort vergleichbar mit `https://someNuGetUrl.com/api/v2/Packages` .

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scriptpublishlocation

Gibt den Speicherort der Skript Veröffentlichung an.

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scriptsourcelokation

Gibt den Quell Speicherort des Skripts an.

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sourcelokation

Gibt den URI zum Ermitteln und Installieren von Modulen aus diesem Repository an. Ein URI kann ein nuget-Server Feed (häufigste Situation), ein HTTP-, HTTPS-, FTP-oder Datei Speicherort sein.

Beispielsweise ist der Quell Speicherort für nuget-basierte Depots vergleichbar mit `https://someNuGetUrl.com/api/v2` .

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. PSCredential

### System.Uri

## AUSGABEN

### System.Object

## HINWEISE

> [!IMPORTANT]
> Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1. Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen. Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.

## VERWANDTE LINKS

[Get-PSRepository](Get-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)

[Unregister-PSRepository](Unregister-PSRepository.md)
