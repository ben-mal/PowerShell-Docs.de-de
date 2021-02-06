---
description: Listet die Cmdlets auf, die für die Verwendung mit PowerShell-Anbietern konzipiert sind.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 1f023c5a66265f561ef6644afdc45cd0149f35b7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602124"
---
# <a name="about-core-commands"></a>Informationen zu Kern Befehlen

## <a name="short-description"></a>KURZE BESCHREIBUNG
Listet die Cmdlets auf, die für die Verwendung mit PowerShell-Anbietern konzipiert sind.

## <a name="long-description"></a>LANGE BESCHREIBUNG

PowerShell umfasst einen Satz von Cmdlets, die speziell für die Verwaltung der Elemente in den Daten speichern entwickelt wurden, die von PowerShell-Anbietern verfügbar gemacht werden.
Sie können diese Cmdlets auf die gleiche Weise verwenden, um alle unterschiedlichen Datentypen zu verwalten, die die Anbieter für Sie verfügbar machen. Wenn Sie weitere Informationen zu Anbietern benötigen, geben Sie "Get-Help about_Providers" ein.

Beispielsweise können Sie mit dem Cmdlet "Get-ChildItem" die Dateien in einem Dateisystem Verzeichnis, die Schlüssel unter einem Registrierungsschlüssel oder die Elemente auflisten, die von einem Anbieter verfügbar gemacht werden, den Sie schreiben oder herunterladen.

Im folgenden finden Sie eine Liste der PowerShell-Cmdlets, die für die Verwendung mit Anbietern entwickelt wurden:

ChildItem-Cmdlets

- Get-ChildItem

Content-Cmdlets

- Add-Content
- Clear-Content
- Get-Content
- Set-Content

Item-Cmdlets

- Clear-Item
- Copy-Item
- Get-Item
- Invoke-Item
- Move-Item
- New-Item
- Remove-Item
- Rename-Item
- Set-Item

ItemProperty-Cmdlets

- Clear-ItemProperty
- Copy-ItemProperty
- Get-ItemProperty
- Move-ItemProperty
- New-ItemProperty
- Remove-ItemProperty
- Rename-ItemProperty
- Set-ItemProperty

Location-Cmdlets

- Get-Location
- Pop-Location
- Push-Location
- Set-Location

Pfad-Cmdlets

- Join-Path
- Convert-Path
- Split-Path
- Resolve-Path
- Test-Path

PSDrive-Cmdlets

- Get-PSDrive
- New-PSDrive
- Remove-PSDrive

Psprovider-Cmdlets

- Get-PSProvider

Weitere Informationen zu einem Cmdlet erhalten Sie, indem Sie eingeben `get-help <cmdlet-name>` .

## <a name="see-also"></a>SIEHE AUCH

[about_Providers](about_Providers.md)

