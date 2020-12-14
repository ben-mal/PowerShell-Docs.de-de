---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: ee94ba7808cb364306826325cfbc3df2cf9834a5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892585"
---
# Update-Module

## ZUSAMMENFASSUNG
Lädt die neueste Version der angegebenen Module aus einem Onlinekatalog auf den lokalen Computer herunter und installiert diese

## SYNTAX

### Alle

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem `Update-Module` -Cmdlet wird die neueste Version eines Moduls aus einem Onlinekatalog installiert. Sie werden aufgefordert, das Update vor der Installation zu bestätigen. Updates werden nur für Module installiert, die mit auf dem lokalen Computer installiert wurden `Install-Module` . `Update-Module` sucht `$env:PSModulePath` nach installierten Modulen.

`Update-Module` Wenn keine Parameter angegeben sind, werden alle installierten Module aktualisiert. Verwenden Sie den **Name** -Parameter, um ein Modul anzugeben, das aktualisiert werden soll. Mithilfe des Parameters "Requirements **dversion** " können Sie ein Update auf die spezifische Version eines Moduls durchsetzen.

Wenn ein installiertes Modul bereits die neueste Version ist, wird das Modul nicht aktualisiert. Wenn das Modul in nicht gefunden wird `$env:PSModulePath` , wird ein Fehler angezeigt.

Verwenden Sie, um die installierten Module anzuzeigen `Get-InstalledModule` .

## BEISPIELE

### Beispiel 1: Aktualisieren aller Module

In diesem Beispiel werden alle installierten Module auf die neueste Version in einem Onlinekatalog aktualisiert.

```powershell
Update-Module
```

### Beispiel 2: Aktualisieren eines Moduls nach Name

In diesem Beispiel wird ein bestimmtes Modul auf die neueste Version in einem Onlinekatalog aktualisiert.

```powershell
Update-Module -Name SpeculationControl
```

`Update-Module` verwendet den **Name** -Parameter, um ein bestimmtes Modul, " **speculationcontrol**", zu aktualisieren.

### Beispiel 3: Anzeigen der was-wäre-wenn-Update-Module ausgeführt wird

In diesem Beispiel wird das was-wäre-wenn-Szenario veranschaulicht, um anzuzeigen, was geschieht, wenn `Update-Module` ausgeführt wird Der Befehl wird nicht ausgeführt.

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

`Update-Module` verwendet den **WhatIf** -Parameter zeigt an, was passieren würde, wenn `Update-Module` ausgeführt würde.

### Beispiel 4: Aktualisieren eines Moduls auf eine angegebene Version

In diesem Beispiel wird ein Modul auf eine bestimmte Version aktualisiert. Die Version muss im Onlinekatalog vorhanden sein, oder es wird ein Fehler angezeigt.

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

`Update-Module` verwendet den **Name** -Parameter, um das Modul " **speculationcontrol**" anzugeben. Der Requirements **dversion** -Parameter gibt die Version an, **1.0.14**.

### Beispiel 5: Aktualisieren eines Moduls ohne Bestätigung

Dieses Beispiel fordert keine Bestätigung zum Aktualisieren des Moduls auf die neueste Version aus einem Onlinekatalog an. Wenn das Modul bereits installiert ist, wird das Modul durch den **Force** -Parameter neu installiert.

```powershell
Update-Module -Name SpeculationControl -Force
```

`Update-Module` verwendet den **Name** -Parameter, um das Modul " **speculationcontrol**" anzugeben. Der **Force** -Parameter aktualisiert das Modul, ohne die Benutzer Bestätigung anzufordern.

## PARAMETERS

### -AcceptLicense

Akzeptieren Sie den Lizenzvertrag während der Installation automatisch, wenn dies für das Paket erforderlich ist.

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

Ermöglicht es Ihnen, ein Modul mit dem neueren Modul zu aktualisieren, das als Vorabversion markiert ist.

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

### -Confirm

Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Update-Module` .

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

Gibt ein Benutzerkonto an, das über die Berechtigung zum Aktualisieren eines Moduls verfügt.

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

Erzwingt ein Update der einzelnen angegebenen Module, ohne dass eine Bestätigung angefordert werden muss. Wenn das Modul bereits installiert ist, wird das Modul von **Force** neu installiert.

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

### -MaximumVersion

Gibt die maximale Version eines einzelnen zu aktualisierenden Moduls an. Dieser Parameter kann nicht hinzugefügt werden, wenn Sie versuchen, mehrere Module zu aktualisieren. Die Parameter " **MaximumVersion** " und "Requirements **dversion** " können nicht im selben Befehl verwendet werden.

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

Gibt die Namen von einem oder mehreren zu aktualisierenden Modulen an. `Update-Module` sucht `$env:PSModulePath` nach den zu Aktualisier-Modulen. Wenn `$env:PSModulePath` für den angegebenen Modulnamen keine Übereinstimmungen gefunden werden, tritt ein Fehler auf.

Platzhalter werden in Modulnamen akzeptiert. Wenn Sie dem angegebenen Namen Platzhalter Zeichen hinzufügen und keine Übereinstimmungen gefunden werden, tritt kein Fehler auf.

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

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert. Die Unterstützung für **passthru** -Parameter wurde in **PowerShellGet** 2.0.0 hinzugefügt.

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

Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit einer Internet Ressource herzustellen.

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

Gibt ein Benutzerkonto an, das über die Berechtigung zum Verwenden des Proxy Servers verfügt, der durch den **Proxy** Parameter angegeben wird.

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

### -Requirements dversion

Gibt die genaue Version an, auf die das vorhandene installierte Modul aktualisiert wird. Die Version, die von "Requirements **dversion** " angegeben wird, muss im Onlinekatalog vorhanden sein, oder es wird ein Fehler angezeigt. Wenn mehr als ein Modul in einem einzigen Befehl aktualisiert wird, können Sie "Requirements **dversion**" nicht verwenden.

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

### -Bereich

Gibt den Bereich der Installation des Moduls an. Die zulässigen Werte für diesen Parameter sind **ALLUSERS** und **CurrentUser**. Wenn der **Bereich** nicht angegeben wird, wird das Update im Bereich **CurrentUser** installiert.

Der Bereich " **ALLUSERS** " erfordert erhöhte Berechtigungen und installiert Module an einem Speicherort, auf den alle Benutzer des Computers zugreifen können:

`$env:ProgramFiles\PowerShell\Modules`

**CurrentUser** benötigt keine erhöhten Berechtigungen und installiert Module an einem Speicherort, auf den nur der aktuelle Benutzer des Computers zugreifen kann:

`$home\Documents\PowerShell\Modules`

Wenn kein **Bereich** definiert ist, wird der Standardwert basierend auf der PowerShellGet-Version festgelegt.

- In PowerShellGet Version 2.0.0 und höher ist der Standardwert **ALLUSERS** , wenn eine Sitzung mit erhöhten Rechten ausgeführt wird, und **CurrentUser** für alle anderen.
- In PowerShellGet 1. x-Versionen ist der Standardwert " **ALLUSERS**", für den eine Erhöhung der Installation erforderlich ist.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn ausgeführt wird `Update-Module` . Das Cmdlet wird nicht ausgeführt.

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

### System.String

### System. Management. Automation. PSCredential

### System.Uri

## AUSGABEN

### System.Object

## HINWEISE

Für PowerShell 5,1 oder niedriger ist der Standardbereich in einer Sitzung mit erhöhten Rechten **ALLUSERS** und in einer Sitzung ohne erhöhte Rechte **CurrentUser**. Modulupdates für **ALLUSERS**, `$env:ProgramFiles\PowerShell\Modules` , benötigen erhöhte Berechtigungen. Modulupdates für **CurrentUser**, `$home\Documents\PowerShell\Modules` , benötigen keine erhöhten Berechtigungen.

> [!IMPORTANT]
> Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1. Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen. Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.

`Update-Module` wird in PowerShell 3,0 oder höheren Versionen von PowerShell unter Windows 7 oder Windows 2008 R2 und höheren Versionen von Windows ausgeführt.

Wenn das Modul, das Sie mit dem **Name** -Parameter angeben, nicht mithilfe von installiert `Install-Module` wurde, tritt ein Fehler auf.

Sie können nur `Update-Module` Module ausführen, die Sie aus dem Onlinekatalog installiert haben, indem Sie Ausführen `Install-Module` .

Wenn `Update-Module` versucht, Binärdateien zu aktualisieren, die verwendet werden, `Update-Module` gibt einen Fehler zurück, der die Problem Prozesse identifiziert. Der Benutzer wird informiert, dass er `Update-Module` nach dem Beenden der Prozesse wiederholt werden soll.

## VERWANDTE LINKS

[Find-Module](Find-Module.md)

[Get-InstalledModule](Get-InstalledModule.md)

[Install-Module](Install-Module.md)

[Publish-Module](Publish-Module.md)

[Uninstall-Module](Uninstall-Module.md)
