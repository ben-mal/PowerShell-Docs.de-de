---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: 9aff0ff794bea42da7690a77357c1d76f747a004
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892156"
---
# Save-Module

## ZUSAMMENFASSUNG
Speichert ein Modul und seine Abhängigkeiten auf dem lokalen Computer, installiert das Modul jedoch nicht.

## SYNTAX

### Nameandpathparameterset (Standard)

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nameandliteralpathparameterset

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Inputobjectandliteralpathparameterset

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Inputobjectandpathparameterset

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem `Save-Module` -Cmdlet werden ein Modul und alle Abhängigkeiten von einem registrierten Repository heruntergeladen.
`Save-Module` Hiermit wird die aktuellste Version eines Moduls heruntergeladen und gespeichert. Die Dateien werden in einem angegebenen Pfad auf dem lokalen Computer gespeichert. Das Modul ist nicht installiert, aber der Inhalt kann von einem Administrator überprüft werden. Das gespeicherte Modul kann dann an den entsprechenden `$env:PSModulePath` Speicherort des Offline Computers kopiert werden.

`Get-PSRepository` zeigt die registrierten Depots des lokalen Computers an. Sie können mit dem `Find-Module` Cmdlet registrierte Depots durchsuchen.

## BEISPIELE

### Beispiel 1: Speichern eines Moduls

In diesem Beispiel werden ein Modul und seine Abhängigkeiten auf dem lokalen Computer gespeichert.

```powershell
Save-Module -Name PowerShellGet -Path C:\Test\Modules -Repository PSGallery
Get-ChildItem -Path C:\Test\Modules
```

```Output
    Directory: C:\Test\Modules

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     13:31                PackageManagement
d-----         7/1/2019     13:31                PowerShellGet
```

`Save-Module` verwendet den **Name** -Parameter, um das Modul " **PowerShellGet**" anzugeben. Der **path** -Parameter gibt an, wo das heruntergeladene Modul gespeichert werden soll. Der **Repository** -Parameter gibt ein registriertes Repository, **psgallery**, an. Nachdem der Download abgeschlossen ist, `Get-ChildItem` zeigt den Inhalt des **Pfads** an, in dem die Dateien gespeichert werden.

### Beispiel 2: Speichern einer bestimmten Version eines Moduls

In diesem Beispiel wird gezeigt, wie ein Parameter wie **MaximumVersion** oder Requirements **dversion** verwendet wird, um eine Modulversion anzugeben.

```powershell
Save-Module -Name PowerShellGet -Path C:\Test\Modules -Repository PSGallery -MaximumVersion 2.1.0
Get-ChildItem -Path C:\Test\Modules\PowerShellGet\
```

```Output
    Directory: C:\Test\Modules\PowerShellGet

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     13:40                2.1.0
```

`Save-Module` verwendet den **Name** -Parameter, um das Modul " **PowerShellGet**" anzugeben. Der **path** -Parameter gibt an, wo das heruntergeladene Modul gespeichert werden soll. Der **Repository** -Parameter gibt ein registriertes Repository, **psgallery**, an. **MaximumVersion** gibt an, dass Version **2.1.0** heruntergeladen und gespeichert wird. Nachdem der Download abgeschlossen ist, `Get-ChildItem` zeigt den Inhalt des **Pfads** an, in dem die Dateien gespeichert werden.

### Beispiel 3: Suchen und Speichern einer bestimmten Version eines Moduls

In diesem Beispiel wird eine erforderliche Modulversion im Repository gefunden und auf dem lokalen Computer gespeichert.

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery -RequiredVersion 1.6.5 |
  Save-Module -Path C:\Test\Modules
Get-ChildItem -Path C:\Test\Modules\PowerShellGet
```

```Output
    Directory: C:\Test\Modules\PowerShellGet

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     14:04                1.6.5
```

`Find-Module` verwendet den **Name** -Parameter, um das Modul " **PowerShellGet**" anzugeben. Der **Repository** -Parameter gibt ein registriertes Repository, **psgallery**, an. Requirements **dversion** gibt Version **1.6.5** an.

Das Objekt wird über die Pipeline an gesendet `Save-Module` . Der **path** -Parameter gibt an, wo das heruntergeladene Modul gespeichert werden soll. Nachdem der Download abgeschlossen ist, `Get-ChildItem` zeigt den Inhalt des **Pfads** an, in dem die Dateien gespeichert werden.

## PARAMETERS

### -AcceptLicense

Akzeptieren Sie den Lizenzvertrag automatisch, wenn dies für das Paket erforderlich ist.

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

Ermöglicht das Speichern eines als Vorabversion markierten Moduls.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Fordert Sie zur Bestätigung auf, bevor Sie den ausführen `Save-Module` .

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

Gibt ein Benutzerkonto an, das über Rechte zum Speichern eines Moduls verfügt.

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

Erzwingt das `Save-Module` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.

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

Akzeptiert ein **PSRepositoryItemInfo** -Objekt. Geben `Find-Module` Sie z. b. eine Ausgabe an eine Variable ein, und verwenden Sie diese Variable als **Inputobject** -Argument.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObjectAndLiteralPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Literalpath

Gibt einen Pfad zu einem oder mehreren Speicherorten an. Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein. PowerShell interpretiert keine Zeichen, die in einfache Anführungszeichen eingeschlossen sind, als Escapesequenzen.

```yaml
Type: System.String
Parameter Sets: NameAndLiteralPathParameterSet, InputObjectAndLiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaximumVersion

Gibt die maximale oder neueste Version des zu speichernden Moduls an. Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

Gibt die minimale Version eines einzelnen Moduls an, das gespeichert werden soll. Sie können diesen Parameter nicht hinzufügen, wenn Sie versuchen, mehrere Module zu installieren. Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Gibt ein Array von Namen von Modulen an, die gespeichert werden sollen.

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Gibt den Speicherort auf dem lokalen Computer zum Speichern eines gespeicherten Moduls an. Akzeptiert Platzhalter Zeichen.

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 1
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

Gibt den anzeigen Amen eines Repository an, das durch Ausführen von registriert wurde `Register-PSRepository` . Verwenden `Get-PSRepository` Sie, um registrierte Depots anzuzeigen.

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Requirements dversion

Gibt die genaue Versionsnummer des zu speichernden Moduls an.

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn die ausgeführt wird `Save-Module` . Das Cmdlet wird nicht ausgeführt.

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

> [!IMPORTANT]
> Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1. Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen. Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.

## VERWANDTE LINKS
