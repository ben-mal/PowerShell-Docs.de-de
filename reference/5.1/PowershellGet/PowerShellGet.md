---
Download Help Link: https://go.microsoft.com/fwlink/?LinkId=393271
Help Version: 5.2.0.0
keywords: powershell,cmdlet
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 130582b1b9f18a8f6ada7c009c6d25a7dab75e46
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890711"
---
# PowerShellGet-Modul

## Beschreibung

PowerShellGet ist ein Modul mit Befehlen zum ermitteln, installieren, aktualisieren und Veröffentlichen von PowerShell-Artefakten wie Modulen, DSC-Ressourcen, Rollen Funktionen und Skripts.

> [!IMPORTANT]
> Ab dem 2020 unterstützt die PowerShell-Katalog nicht mehr Transport Layer Security (TLS)-Versionen 1,0 und 1,1. Wenn Sie TLS 1,2 oder höher nicht verwenden, erhalten Sie eine Fehlermeldung, wenn Sie versuchen, auf die PowerShell-Katalog zuzugreifen. Verwenden Sie den folgenden Befehl, um sicherzustellen, dass Sie TLS 1,2 verwenden:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) im PowerShell-Blog.

## PowerShellGet-Cmdlets

### [Find-Command](Find-Command.md)
Sucht PowerShell-Befehle in Modulen.

### [Find-DscResource](Find-DscResource.md)
Sucht eine DSC-Ressource.

### [Find-Module](Find-Module.md)
Sucht Module in einem Repository, die den angegebenen Kriterien entsprechen.

### [Find-RoleCapability](Find-RoleCapability.md)
Sucht nach Rollenfunktionen in Modulen.

### [Find-Script](Find-Script.md)
Sucht nach einem Skript.

### [Get-InstalledModule](Get-InstalledModule.md)
Ruft eine Liste von Modulen auf dem Computer ab, die von PowerShellGet installiert wurden.

### [Get-InstalledScript](Get-InstalledScript.md)
Ruft ein installiertes Skript ab.

### [Get-PSRepository](Get-PSRepository.md)
Ruft PowerShell-Repository ab.

### [Install-Module](Install-Module.md)
Lädt ein oder mehrere Module aus einem Repository herunter und installiert Sie auf dem lokalen Computer.

### [Install-Script](Install-Script.md)
Installiert ein Skript.

### [New-ScriptFileInfo](New-ScriptFileInfo.md)
Erstellt eine Skriptdatei mit Metadaten

### [Publish-Module](Publish-Module.md)
Veröffentlicht ein angegebenes Modul aus dem lokalen Computer in einem Onlinekatalog

### [Publish-Script](Publish-Script.md)
Veröffentlicht ein Skript.

### [Register-PSRepository](Register-PSRepository.md)
Registriert ein PowerShell-Repository.

### [Save-Module](Save-Module.md)
Speichert ein Modul und seine Abhängigkeiten auf dem lokalen Computer, installiert das Modul jedoch nicht.

### [Save-Script](Save-Script.md)
Speichert ein Skript.

### [Set-PSRepository](Set-PSRepository.md)
Legt Werte für ein registriertes Repository fest.

### [Test-ScriptFileInfo](Test-ScriptFileInfo.md)
Überprüft einen Kommentar Block für ein Skript.

### [Uninstall-Module](Uninstall-Module.md)
Deinstalliert ein Modul.

### [Uninstall-Script](Uninstall-Script.md)
Deinstalliert ein Skript.

### [Unregister-PSRepository](Unregister-PSRepository.md)
Hebt die Registrierung eines Repositorys auf

### [Update-Module](Update-Module.md)
Lädt die neueste Version der angegebenen Module aus einem Onlinekatalog auf den lokalen Computer herunter und installiert diese

### [Update-ModuleManifest](Update-ModuleManifest.md)
Aktualisiert eine Modulmanifestdatei

### [Update-Script](Update-Script.md)
Aktualisiert ein Skript.

### [Update-ScriptFileInfo](Update-ScriptFileInfo.md)
Aktualisiert Informationen für ein Skript.
