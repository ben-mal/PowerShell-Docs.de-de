---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: 277bfc0ae4662e0c822ae7c227490eaf887c8ecb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209948"
---
# Set-PSRepository

## ZUSAMMENFASSUNG
Legt Werte für ein registriertes Repository fest.

## SYNTAX

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Set-PSRepository` Cmdlet werden Werte für ein registriertes modulrepository festgelegt. Die Einstellungen sind für den aktuellen Benutzer persistent und gelten für alle Versionen von PowerShell, die für diesen Benutzer installiert wurden.

## BEISPIELE

### Beispiel 1: Festlegen der Installations Richtlinie für ein Repository

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

Mit diesem Befehl wird die Installations Richtlinie für das **myinternalsource** -Repository auf " **vertrauenswürdig** " festgelegt, sodass Sie vor der Installation von Modulen aus dieser Quelle nicht aufgefordert werden.

### Beispiel 2: Festlegen der Quell-und Veröffentlichungs Speicherorte für ein Repository

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

Mit diesem Befehl werden der Quell Speicherort und der Veröffentlichungsort für **myinternalsource** auf die angegebenen URIs festgelegt.

## PARAMETERS

### -Credential

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

### -Installationpolicy

Gibt die Installations Richtlinie an. Gültige Werte sind: **vertrauenswürdig** , **nicht vertrauenswürdig** .

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

Gibt den Namen des Repository an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Packagemanagementprovider

Gibt den Paket Verwaltungs Anbieter an.

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

### -Publishlocation

Gibt den URI des Veröffentlichungs Speicher Orts an. Beispielsweise ist für nuget-basierte Depots der Veröffentlichungs Speicherort vergleichbar mit `https://someNuGetUrl.com/api/v2/Packages` .

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

### -Scriptpublishlocation

Gibt den Speicherort der Skript Veröffentlichung an.

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

### -Scriptsourcelokation

Gibt den Quell Speicherort des Skripts an.

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

### -Sourcelokation

Gibt den URI zum Ermitteln und Installieren von Modulen aus diesem Repository an. Beispielsweise ist der Quell Speicherort für nuget-basierte Depots vergleichbar mit `https://someNuGetUrl.com/api/v2` .

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

### System. Management. Automation. PSCredential

### System.Uri

## AUSGABEN

### System.Object

## HINWEISE

## VERWANDTE LINKS

[Get-PSRepository](Get-PSRepository.md)

[Register-PSRepository](Register-PSRepository.md)

[Unregister-PSRepository](Unregister-PSRepository.md)
