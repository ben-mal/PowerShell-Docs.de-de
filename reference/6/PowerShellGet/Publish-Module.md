---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Module
ms.openlocfilehash: dd7721fbf482bca78823d9bad5b8f40f76b7d8bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215940"
---
# Publish-Module

## ZUSAMMENFASSUNG
Veröffentlicht ein angegebenes Modul aus dem lokalen Computer in einem Onlinekatalog

## SYNTAX

### Modulenameparameterset (Standard)

```
Publish-Module -Name <String> [-RequiredVersion <String>] [-NuGetApiKey <String>]
 [-Repository <String>] [-Credential <PSCredential>] [-FormatVersion <Version>]
 [-ReleaseNotes <String[]>] [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ProjectUri <Uri>] [-Exclude <String[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Modulepathparameterset

```
Publish-Module -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-FormatVersion <Version>] [-ReleaseNotes <String[]>]
 [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ProjectUri <Uri>] [-Force]
 [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das `Publish-Module` -Cmdlet veröffentlicht ein Modul in einem nuget-basierten Onlinekatalog mithilfe eines API-Schlüssels, der als Teil des Benutzerprofils im Katalog gespeichert wird. Sie können entweder den Namen des Moduls angeben, das veröffentlicht werden soll, oder Sie geben den Pfad zum Ordner an, der das Modul enthält.

Wenn Sie ein Modul nach Name angeben, `Publish-Module` veröffentlicht das erste Modul, das durch Ausführen von gefunden wird `Get-Module -ListAvailable <Name>` . Wenn Sie eine Mindestversion eines zu veröffentlichenden Moduls angeben, `Publish-Module` veröffentlicht das erste Modul mit einer Version, die größer oder gleich der von Ihnen angegebenen Mindestversion ist.

Die Veröffentlichung eines Moduls erfordert Metadaten, die auf der Seite „Katalog“ des Moduls angezeigt werden. Die erforderlichen Metadaten enthalten den Modulnamen, die Version, die Beschreibung und den Autor. Obwohl die meisten Metadaten aus dem Modul Manifest entnommen werden, müssen einige Metadaten in `Publish-Module` Parametern angegeben werden, wie z. b. **Tag** , **Releasenote** , **iconuri** , **projecturi** und **licentaruri** , da diese Parameter den Feldern in einem nuget-basierten Katalog entsprechen.

## BEISPIELE

### Beispiel 1: Veröffentlichen eines Moduls

In diesem Beispiel wird mydscmodule mithilfe des API-Schlüssels im Onlinekatalog veröffentlicht, um das Onlinekatalog Konto des Modul Besitzers anzugeben. Wenn mydscmodule kein gültiges Manifest-Modul ist, das einen Namen, eine Version, eine Beschreibung und einen Autor angibt, tritt ein Fehler auf.

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73"
```

### Beispiel 2: Veröffentlichen eines Moduls mit Katalog Metadaten

In diesem Beispiel wird mydscmodule mithilfe des API-Schlüssels im Onlinekatalog veröffentlicht, um das Katalog Konto des Modul Besitzers anzugeben. Die zusätzlichen bereitgestellten Metadaten werden auf der Webseite für das Modul im Katalog angezeigt. Der Besitzer fügt zwei suchtags für das Modul hinzu und bezieht sich auf Active Directory. Es wird ein kurzer Versions Hinweis hinzugefügt. Wenn mydscmodule kein gültiges Manifest-Modul ist, das einen Namen, eine Version, eine Beschreibung und einen Autor angibt, tritt ein Fehler auf.

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73" -LicenseUri "http://contoso.com/license" -Tag "Active Directory","DSC" -ReleaseNote "Updated the ActiveDirectory DSC Resources to support adding users."
```

## PARAMETERS

### -Allowprerelease

Ermöglicht das Veröffentlichen von Modulen, die als Vorabversion markiert sind.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Fordert Sie zur Bestätigung auf, bevor Sie den ausführen `Publish-Module` .

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

Gibt ein Benutzerkonto an, das über Rechte zum Veröffentlichen eines Moduls für einen angegebenen Paketanbieter oder eine angegebene Quelle verfügt.

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

### -Ausschließen

Definiert Dateien, die aus dem veröffentlichten Modul ausgeschlossen werden sollen.

```yaml
Type: System.String[]
Parameter Sets: ModuleNameParameterSet
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Format Version

Akzeptiert nur gültige Werte, die durch das **validateset** -Attribut angegeben werden.

Weitere Informationen finden Sie unter [validateset-Attribut Deklaration](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) und [validatesetattribute](/dotnet/api/system.management.automation.validatesetattribute).

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:
Accepted values: 2.0

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Iconuri

Gibt die URL eines Symbols für das Modul an. Das angegebene Symbol wird auf der Katalog Webseite für das Modul angezeigt.

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

### -Licenaburi

Gibt die URL der Lizenzierungs Bedingungen für das Modul an, das Sie veröffentlichen möchten.

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

### -Name

Gibt den Namen des Moduls an, das Sie veröffentlichen möchten. `Publish-Module` sucht nach dem angegebenen Modulnamen in `$Env:PSModulePath` .

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nugetapikey

Gibt den API-Schlüssel an, den Sie zum Veröffentlichen eines Moduls im Onlinekatalog verwenden möchten. Der API-Schlüssel ist Teil Ihres Profils im Onlinekatalog. Sie finden Sie auf der Seite Benutzerkonto im Katalog. Der API-Schlüssel ist eine nuget-spezifische Funktionalität.

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

### -Path

Gibt den Pfad zu dem Modul an, das Sie veröffentlichen möchten. Dieser Parameter akzeptiert den Pfad zu dem Ordner, der das Modul enthält.

```yaml
Type: System.String
Parameter Sets: ModulePathParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Projecturi

Gibt die URL einer Webseite zu diesem Projekt an.

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

### -Releasenotes

Gibt eine Zeichenfolge mit Anmerkungen zu dieser Version oder Kommentaren an, die für Benutzer dieser Version des Moduls verfügbar sein sollen.

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

### -Repository

Gibt den anzeigen Amen eines Repository an, das durch Ausführen von registriert wurde `Register-PSRepository` . Das Repository muss über einen **publishlocation** verfügen, bei dem es sich um einen gültigen nuget-URI handelt.
**Publishlocation** kann durch Ausführen von festgelegt werden `Set-PSRepository` .

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

### -Requirements dversion

Gibt die exakte Version eines einzelnen zu veröffentlichenden Moduls an.

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skipautomatictags

Entfernt das Einschließen von Befehlen und Ressourcen als Tags. Überspringt das automatische Hinzufügen von Tags zu einem Modul.

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

### -Tags

Fügt dem Modul, das Sie veröffentlichen, ein oder mehrere Tags hinzu. Beispiele hierfür sind "desiredStatus econfiguration", "DSC", "dscresourcekit" oder "psmodule". Trennen Sie mehrere Tags durch Kommas.

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

### -WhatIf

Zeigt, was geschieht, wenn die ausgeführt wird `Publish-Module` . Das Cmdlet wird nicht ausgeführt.

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

### System.String

### System. Management. Automation. PSCredential

## AUSGABEN

### System.Object

## HINWEISE

`Publish-Module` wird in PowerShell 3,0 oder höheren Versionen von PowerShell unter Windows 7 oder Windows 2008 R2 und höheren Versionen von Windows ausgeführt.

Die Veröffentlichung eines Moduls erfordert Metadaten, die auf der Seite „Katalog“ des Moduls angezeigt werden. Die erforderlichen Metadaten enthalten den Modulnamen, die Version, die Beschreibung und den Autor. Die meisten Metadaten werden aus dem Modul Manifest entnommen, aber einige Metadaten können in `Publish-Module` Parametern angegeben werden, wie z. b. **Tag** , **Releasenote** , **iconuri** , **projecturi** und **licentaruri**. Weitere Informationen finden Sie unter [Paket Manifest-Werte, die Auswirkungen auf die PowerShell-Katalog-Benutzeroberfläche](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui)haben.

## VERWANDTE LINKS

[Find-Module](Find-Module.md)

[Install-Module](Install-Module.md)

[Register-PSRepository](Register-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)

[Uninstall-Module](Uninstall-Module.md)

[Update-Module](Update-Module.md)
