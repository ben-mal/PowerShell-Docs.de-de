---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: e2e4dc34fb84a54fb92cc4c809c84d67beafe576
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "93219092"
---
# Install-Module

## ZUSAMMENFASSUNG
Lädt ein oder mehrere Module aus einem Repository herunter und installiert Sie auf dem lokalen Computer.

## SYNTAX

### Nameparameterset (Standard)

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das `Install-Module` -Cmdlet ruft ein oder mehrere Module ab, die die angegebenen Kriterien aus einem Online-Repository erfüllen. Mit dem-Cmdlet wird überprüft, ob die Suchergebnisse gültige Module sind, und die Modul Ordner werden an den Installations Speicherort kopiert. Installierte Module werden nach der Installation nicht automatisch importiert.
Sie können filtern, welches Modul basierend auf den minimalen, maximalen und exakten Versionen der angegebenen Module installiert wird.

Wenn das Modul, das installiert wird, den gleichen Namen oder die gleiche Version aufweist oder Befehle in einem vorhandenen Modul enthält, werden Warnmeldungen angezeigt. Nachdem Sie bestätigt haben, dass Sie das Modul installieren und die Warnungen außer Kraft setzen möchten, verwenden Sie den `-Force` -Parameter und den- `-AllowClobber` Parameter. Abhängig von Ihren Repository-Einstellungen müssen Sie möglicherweise eine Eingabeaufforderung beantworten, damit die Modul Installation fortgesetzt werden kann.

In diesen Beispielen wird die [PowerShell-Katalog](https://www.powershellgallery.com/) als einziges registriertes Repository verwendet. `Get-PSRepository` zeigt die registrierten Depots an. Wenn Sie über mehrere registrierte Repository verfügen, verwenden Sie den `-Repository` -Parameter, um den Namen des Repository anzugeben.

## BEISPIELE

### Beispiel 1: Suchen und Installieren eines Moduls

In diesem Beispiel wird ein Modul im Repository gefunden und das Modul installiert.

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

Der `Find-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben. Standardmäßig wird die neueste Version des Moduls aus dem Repository heruntergeladen. Das Objekt wird über die Pipeline an das `Install-Module` Cmdlet gesendet. `Install-Module` installiert das Modul für alle Benutzer in `$env:ProgramFiles\PowerShell\Modules` .

### Beispiel 2: Installieren eines Moduls nach Name

In diesem Beispiel ist die neueste Version des **PowerShellGet** -Moduls installiert.

```powershell
Install-Module -Name PowerShellGet
```

Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben. Standardmäßig wird die neueste Version des Moduls aus dem Repository heruntergeladen und installiert.

### Beispiel 3: Installieren eines Moduls mit der Mindestversion

In diesem Beispiel ist die Mindestversion des **PowerShellGet** -Moduls installiert. Der **MinimumVersion** -Parameter gibt die niedrigste Version des Moduls an, das installiert werden soll. Wenn eine neuere Version des Moduls verfügbar ist, wird diese Version heruntergeladen und für alle Benutzer installiert.

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben. Der **MinimumVersion** -Parameter gibt an, dass Version **2.0.1** aus dem Repository heruntergeladen und installiert wird. Da Version **2.0.4** verfügbar ist, wird diese Version heruntergeladen und für alle Benutzer installiert.

### Beispiel 4: Installieren einer bestimmten Version eines Moduls

In diesem Beispiel wird eine bestimmte Version des **PowerShellGet** -Moduls installiert.

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben. Der Parameter "Requirements **dversion** " gibt an, dass Version **2.0.0** heruntergeladen und für alle Benutzer installiert wird.

### Beispiel 5: Installieren eines Moduls nur für den aktuellen Benutzer

In diesem Beispiel wird die neueste Version eines Moduls heruntergeladen und installiert, nur für den aktuellen Benutzer.

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

Der `Install-Module` verwendet den **Name** -Parameter, um das **PowerShellGet** -Modul anzugeben.
`Install-Module` herunterladen und Installieren der neuesten Version von **PowerShellGet** in das Verzeichnis des aktuellen Benutzers `$home\Documents\PowerShell\Modules` .

## PARAMETERS

### -AcceptLicense

Bei Modulen, die eine Lizenz erfordern, akzeptiert " **akzeptlicense** " den Lizenzvertrag während der Installation automatisch. Weitere Informationen finden Sie unter Module, die die [Zustimmung zur Lizenz erfordern](/powershell/scripting/gallery/concepts/module-license-acceptance).

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

### -Allowclobber

Überschreibt Warnmeldungen zu Installations Konflikten in Bezug auf vorhandene Befehle auf einem Computer.
Überschreibt vorhandene Befehle mit demselben Namen wie Befehle, die von einem Modul installiert werden.
**Allowclobber** und **Force** können in einem Befehl verwendet werden `Install-Module` .

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

Ermöglicht das Installieren eines als Vorabversion markierten Moduls.

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

Sie werden zur Bestätigung aufgefordert, bevor Sie das `Install-Module` Cmdlet ausführen.

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

### -Force

Installiert ein Modul und überschreibt Warnmeldungen zu Modul Installations Konflikten. Wenn ein Modul mit dem gleichen Namen bereits auf dem Computer vorhanden ist, ermöglicht **Force** die Installation mehrerer Versionen. Wenn ein Modul mit dem gleichen Namen und der gleichen Version vorhanden ist, wird diese Version von **Force** überschrieben. **Force** und **allowclobber** können in einem Befehl verwendet werden `Install-Module` .

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

Gibt die maximale Version eines einzelnen Moduls an, das installiert werden soll. Die installierte Version muss kleiner oder gleich **MaximumVersion** sein. Wenn Sie mehrere Module installieren möchten, können Sie **MaximumVersion** nicht verwenden. **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden `Install-Module` .

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

Gibt die Mindestversion eines einzelnen zu installierenden Moduls an. Die installierte Version muss größer oder gleich **MinimumVersion** sein. Wenn eine neuere Version des Moduls verfügbar ist, wird die neuere Version installiert. Wenn Sie mehrere Module installieren möchten, können Sie **MinimumVersion** nicht verwenden.
**MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden `Install-Module` .

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

Gibt die genauen Namen der Module an, die aus dem Onlinekatalog installiert werden sollen. Eine durch Trennzeichen getrennte Liste von Modulnamen wird akzeptiert. Der Modulname muss mit dem Modulnamen im Repository identisch sein. Verwenden `Find-Module` Sie, um eine Liste von Modulnamen zu erhalten.

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

### -PassThru

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
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

Verwenden Sie den **Repository** -Parameter, um anzugeben, welches Repository zum herunterladen und Installieren eines Moduls verwendet wird. Wird verwendet, wenn mehrere Depots registriert sind. Gibt den Namen eines registrierten Repository im Befehl an `Install-Module` . Verwenden Sie zum Registrieren eines Repository `Register-PSRepository` .
Verwenden Sie, um registrierte Depots anzuzeigen `Get-PSRepository` .

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

Gibt die exakte Version eines einzelnen Moduls an, das installiert werden soll. Wenn keine Entsprechung im Repository für die angegebene Version vorhanden ist, wird ein Fehler angezeigt. Wenn Sie mehrere Module installieren möchten, können Sie "Requirements **dversion** " nicht verwenden. "Requirements **dversion** " kann nicht im gleichen `Install-Module` Befehl wie " **MinimumVersion** " oder " **MaximumVersion** " verwendet werden.

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

Gibt den Bereich der Installation des Moduls an. Die zulässigen Werte für diesen Parameter sind **ALLUSERS** und **CurrentUser**.

Der Bereich " **ALLUSERS** " installiert Module an einem Speicherort, auf den alle Benutzer des Computers zugreifen können:

`$env:ProgramFiles\PowerShell\Modules`

**CurrentUser** installiert Module an einem Speicherort, auf den nur der aktuelle Benutzer des Computers zugreifen kann. Beispiel:

`$home\Documents\PowerShell\Modules`

Wenn kein **Bereich** definiert ist, wird der Standardwert basierend auf der PowerShellGet-Version festgelegt.

- In PowerShellGet Version 2.0.0 und höher ist der Standardwert **CurrentUser** , der keine Erhöhung der Rechte für die Installation erfordert.
- In PowerShellGet 1. x-Versionen ist der Standardwert " **ALLUSERS** ", für den eine Erhöhung der Installation erforderlich ist.

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

### -Skippublishercheck

Ermöglicht es Ihnen, eine neuere Version eines Moduls zu installieren, die bereits auf dem Computer vorhanden ist. Wenn ein vorhandenes Modul z. b. Digital von einem vertrauenswürdigen Verleger signiert ist, die neue Version jedoch nicht Digital von einem vertrauenswürdigen Herausgeber signiert wurde.

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

### -WhatIf

Zeigt, was geschieht, wenn ein `Install-Module` Befehl ausgeführt wurde. Das Cmdlet wird nicht ausgeführt.

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

### PSRepositoryItemInfo

`Find-Module` erstellt **PSRepositoryItemInfo** -Objekte, die über die Pipeline an gesendet werden können `Install-Module` .

### System.String[]

### System. Management. Automation. psobject []

### System.String

### System. Management. Automation. PSCredential

### System.Uri

## AUSGABEN

### Microsoft. PowerShell. Commands. PSRepositoryItemInfo

Wenn Sie den **passthru** -Parameter verwenden, gibt `Install-Module` ein **PSRepositoryItemInfo** -Objekt für das Modul aus. Dies sind die gleichen Informationen, die Sie vom `Find-Module` Cmdlet erhalten.

## HINWEISE

`Install-Module` wird in PowerShell 5,0 oder höheren Versionen unter Windows 7 oder Windows 2008 R2 und neueren Versionen von Windows ausgeführt.

Als bewährte Sicherheitsmaßnahme sollten Sie den Code eines Moduls auswerten, bevor Sie zum ersten Mal Cmdlets oder Funktionen ausführen. Um das Ausführen von Modulen zu verhindern, die bösartigen Code enthalten, werden installierte Module nach der Installation nicht automatisch importiert.

Wenn der durch den **Name** -Parameter angegebene Modulname im Repository nicht vorhanden ist, `Install-Module` gibt einen Fehler zurück.

Verwenden Sie den **Name** -Parameter, und geben Sie ein durch Trennzeichen getrenntes Array von Modulnamen an, um mehrere Module zu installieren. Wenn Sie mehrere Modulnamen angeben, können Sie **MinimumVersion** , **MaximumVersion** oder Requirements **dversion** nicht verwenden. `Find-Module` erstellt **PSRepositoryItemInfo** -Objekte, die über die Pipeline an gesendet werden können `Install-Module` . Die Pipeline ist eine andere Möglichkeit, mehrere Module anzugeben, die mit einem einzigen Befehl installiert werden sollen.

Standardmäßig werden Module für den Bereich von **ALLUSERS** in installiert `$env:ProgramFiles\PowerShell\Modules` . Der Standardwert verhindert Verwechslungen bei der Installation von PowerShell DSC-Ressourcen.

Bei einer Modul Installation tritt ein Fehler auf, und Sie kann nicht importiert werden, wenn Sie im Ordner nicht über einen-,-oder-Wert `.psm1` `.psd1` `.dll` mit demselben Namen verfügt. Verwenden Sie den **Force** -Parameter, um das Modul zu installieren.

Wenn die Version eines vorhandenen Moduls mit dem im **Name** -Parameter angegebenen Namen übereinstimmt und der **MinimumVersion** -Parameter oder der Requirements **dversion** -Parameter nicht verwendet wird, wird der Hintergrund `Install-Module` fortgesetzt, das Modul wird jedoch nicht installiert.

Wenn die Version eines vorhandenen Moduls größer als der Wert des **MinimumVersion** -Parameters ist oder gleich dem Wert des Parameters "Requirements **dversion** " ist, wird `Install-Module` im Hintergrund fortgesetzt, das Modul wird jedoch nicht installiert.

Wenn das vorhandene Modul nicht mit den Werten in den Parametern **Minimum Version** oder Requirements **dversion** identisch ist, tritt im Befehl ein Fehler auf `Install-Module` . Wenn beispielsweise die Version des vorhandenen installierten Moduls niedriger ist als der **MinimumVersion** -Wert oder nicht gleich dem Wert "Requirements- **Version** ".

Bei einer Modul Installation werden auch alle abhängigen Module installiert, die vom Modul Herausgeber benötigt werden.
Der Verleger gibt die erforderlichen Module und deren Versionen im Modul Manifest an.

## VERWANDTE LINKS

[Find-Module](Find-Module.md)

[Get-PSRepository](Get-PSRepository.md)

[Import-Module](../Microsoft.PowerShell.Core/Import-Module.md)

[Publish-Module](Publish-Module.md)

[Register-PSRepository](Register-PSRepository.md)

[Uninstall-Module](Uninstall-Module.md)

[Update-Module](Update-Module.md)

[about_Module](../Microsoft.PowerShell.Core/About/about_Modules.md)
