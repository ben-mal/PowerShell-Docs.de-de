---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: 498620ee79285f0c0fe2a001b99fe5dc179ea0ac
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217596"
---
# Convert-Path

## ZUSAMMENFASSUNG
Konvertiert einen Pfad von einem PowerShell-Pfad in einen PowerShell-Anbieter Pfad.

## SYNTAX

### Pfad (Standard)

```
Convert-Path [-Path] <String[]> [<CommonParameters>]
```

### LiteralPath

```
Convert-Path -LiteralPath <String[]> [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Convert-Path` Cmdlet wird ein Pfad von einem PowerShell-Pfad in einen PowerShell-Anbieter Pfad konvertiert.

## BEISPIELE

### Beispiel 1: Konvertieren des Arbeitsverzeichnisses in einen Standarddatei Systempfad

In diesem Beispiel wird das aktuelle Arbeitsverzeichnis, das durch einen Punkt () dargestellt wird `.` , in einen Standarddatei Systempfad konvertiert.

```
PS C:\> Convert-Path .
C:\
```

### Beispiel 2: Konvertieren eines Anbieter Pfads in einen Standard Registrierungs Pfad

In diesem Beispiel wird der PowerShell-Anbieter Pfad in einen Standard Registrierungs Pfad konvertiert.

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### Beispiel 3: Konvertieren eines Pfads in eine Zeichenfolge

In diesem Beispiel wird der Pfad in das Basisverzeichnis des aktuellen Anbieters (der File System-Anbieter) in eine Zeichenfolge konvertiert.

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## PARAMETERS

### -Literalpath

Gibt den zu konvertierenden Pfad als Zeichen folgen Array an. Der Wert des **literalpath** -Parameters wird genau so verwendet, wie er eingegeben wurde. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Gibt den zu konvertierenden PowerShell-Pfad an.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können einen Pfad, aber keinen literalen Pfad, an dieses Cmdlet weiterreichen.

## AUSGABEN

### System.String

Dieses Cmdlet gibt eine Zeichenfolge zurück, die den konvertierten Pfad enthält.

## HINWEISE

Die Cmdlets, die das Pfad-Substantiv enthalten, bearbeiten Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann. Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll. Verwenden Sie Sie wie " **dirname** ", " **normpath** ", " **realpath** ", " **Join** " oder andere Pfad Manipulatoren.

Sie können die Pfad-Cmdlets mit verschiedenen Anbietern verwenden, u. a. dem FileSystem-, Registry- und Certificate-Anbieter.

Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden. Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` . Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

`Convert-Path` Konvertiert nur vorhandene Pfade. Sie kann nicht verwendet werden, um einen Speicherort zu konvertieren, der noch nicht vorhanden ist.

## VERWANDTE LINKS

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Split-Path](Split-Path.md)

[Test-Path](Test-Path.md)

[Get-PSProvider](Get-PSProvider.md)

