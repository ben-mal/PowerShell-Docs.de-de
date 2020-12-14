---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=2113634
Help Version: 7.0.1.0
keywords: powershell,cmdlet
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 01b1bce187cd0526e56abc812f91b44a2c022a29
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890854"
---
# PackageManagement-Modul

## Beschreibung

In diesem Thema werden die Hilfe Themen für die Paketverwaltung-Cmdlets angezeigt.

> [!IMPORTANT]
> Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1. Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen. Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.

## PackageManagement-Cmdlets

### [Find-Package](Find-Package.md)
Findet Softwarepakete in verfügbaren Paketquellen.

### [Find-PackageProvider](Find-PackageProvider.md)
Gibt eine Liste von Paketverwaltung Paket Anbietern zurück, die für die Installation verfügbar sind.

### [Get-Package](Get-Package.md)
Gibt eine Liste aller Softwarepakete zurück, die mit **packagemanagement** installiert wurden.

### [Get-PackageProvider](Get-PackageProvider.md)
Gibt eine Liste von Paket Anbietern zurück, die mit Paketverwaltung verbunden sind.

### [Get-PackageSource](Get-PackageSource.md)
Ruft eine Liste der Paketquellen ab, die für einen Paketanbieter registriert sind.

### [Import-PackageProvider](Import-PackageProvider.md)
Fügt der aktuellen Sitzung Paketverwaltung Paketanbieter hinzu.

### [Install-Package](Install-Package.md)
Installiert mindestens ein Softwarepaket.

### [Install-PackageProvider](Install-PackageProvider.md)
Installiert einen oder mehrere Paketverwaltung Paketanbieter.

### [Register-PackageSource](Register-PackageSource.md)
Fügt eine Paketquelle für einen angegebenen Paketanbieter hinzu.

### [Save-Package](Save-Package.md)
Speichert Pakete auf dem lokalen Computer, ohne Sie zu installieren.

### [Set-PackageSource](Set-PackageSource.md)
Ersetzt eine Paketquelle für einen angegebenen Paketanbieter.

### [Uninstall-Package](Uninstall-Package.md)
Deinstalliert mindestens ein Softwarepaket.

### [Unregister-PackageSource](Unregister-PackageSource.md)
Entfernt eine registrierte Paketquelle.
