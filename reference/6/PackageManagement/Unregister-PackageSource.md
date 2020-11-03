---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/unregister-packagesource?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PackageSource
ms.openlocfilehash: 21735007c50f208c4150c02628ab1475f18fd6e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214767"
---
# Unregister-PackageSource

## ZUSAMMENFASSUNG
Entfernt eine registrierte Paketquelle.

## SYNTAX

### Sourcebysearch

```
Unregister-PackageSource [[-Source] <String>] [-Location <String>] [-Credential <PSCredential>]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### Sourcebyinputobject

```
Unregister-PackageSource -InputObject <PackageSource[]> [-Credential <PSCredential>] [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nuget: sourcebyinputobject

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### Nuget: sourcebysearch

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### PowerShellGet: sourcebyinputobject

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### PowerShellGet: sourcebysearch

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Unregister-PackageSource` Cmdlet wird eine registrierte Paketquelle entfernt. Paketquellen werden immer von einem Paketanbieter verwaltet. Verwenden Sie das-Cmdlet, um Paketquellen zu suchen `Get-PackageSource` .

## BEISPIELE

### Beispiel 1: Aufheben der Registrierung einer Paketquelle für den nuget-Anbieter

Mit dem- `Unregister-PackageSource` Cmdlet wird die Registrierung einer Paketquelle auf dem lokalen Computer aufgehoben. Der **Speicherort** und die **Anbieter** Parameter können verwendet werden, um die zu entfernende Quelle weiter anzugeben.

```
PS> Unregister-PackageSource -Source MyNuGet
```

Das `Unregister-PackageSource` Cmdlet verwendet den **Source** -Parameter, um anzugeben, welche Quelle entfernt werden soll.

### Beispiel 2: Verwenden eines packagesource-Objekts zum Aufheben der Registrierung eines Pakets

In diesem Beispiel werden `Get-PackageSource` und `Unregister-PackageSource` zum Aufheben der Registrierung einer Paketquelle verwendet. Das **packagesource** -Objekt wird in einer Variablen gespeichert.

```
PS> $pkgsource = Get-PackageSource -Name MyNuGet
PS> Unregister-PackageSource -InputObject $pkgsource
```

Die `$pkgsource` Variable speichert die vom Cmdlet erstellte **packagesource** `Get-PackageSource` .
`Unregister-PackageSource` verwendet `$pkgsource` als Eingabe für den **Inputobject** -Parameter.

Als Alternative `Unregister-PackageSource` kann das Cmdlet einen Wert für den **Inputobject** -Parameter angeben:

`Unregister-PackageSource -InputObject ( Get-PackageSource -Name MyNuGet )`

## PARAMETERS

### -Configfile

Gibt eine Konfigurationsdatei an.

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Zugreifen auf den Computer und zum Ausführen von Befehlen verfügt. Geben Sie einen Benutzernamen ein, z. b. **USER01** , **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

Wenn der **Credential** -Parameter nicht angegeben wird, wird das aktuelle Benutzerkonto verwendet.

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

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer. Überschreibt Einschränkungen, die eine erfolgreiche Ausführung verhindern `Unregister-PackageSource` , mit Ausnahme der Sicherheit.

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

Gibt an, dass `Unregister-PackageSource` **packagemanagement** zwingt, den Paketanbieter für die angegebene Paketquelle automatisch zu deinstallieren.

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

Akzeptiert Pipeline Eingaben, die das **packagesource** -Objekt aus dem `Get-PackageSource` Cmdlet angeben. **Inputobject** akzeptiert das **packagesource** -Objekt als `Get-PackageSource` Wert oder eine Variable, die das Objekt enthält.

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource[]
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location

Gibt den Speicherort an, auf den eine Paketquelle verweist. Der Wert dieses Parameters kann ein URI, ein Dateipfad oder ein beliebiges anderes Zielformat sein, das vom Paketanbieter unterstützt wird.

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Packagemanagementprovider

Gibt den **packagemanagement** -Anbieter an.

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName

Gibt den Anbieter Namen an.

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publishlocation

Gibt den Veröffentlichungs Speicherort an.

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
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
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
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
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skipvalidate

Ein Schalter, der die Validierung der Anmelde Informationen einer Paketquelle überspringt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Gibt den anzeigen amen der Paketquelle an.

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Fordert Sie zur Bestätigung auf, bevor `Unregister-PackageSource` ausgeführt wird.

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

Zeigt, was geschieht, wenn das `Unregister-PackageSource` Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

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

### `Unregister-PackageSource` akzeptiert **packagesource** -Objekte aus der Pipeline als Eingabe.

## AUSGABEN

### `Unregister-PackageSource` generiert keine Ausgabe.

## HINWEISE

Durch das Einschließen eines Paket Anbieters in einen Befehl können dynamische Parameter für ein Cmdlet verfügbar gemacht werden. Dynamische Parameter sind für einen Paketanbieter spezifisch. Das `Get-Help` -Cmdlet listet die Parametersätze eines Cmdlets auf und schließt den Parametersatz des Anbieters ein.

## VERWANDTE LINKS

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Set-PackageSource](Set-PackageSource.md)
