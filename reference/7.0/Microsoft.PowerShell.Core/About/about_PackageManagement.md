---
description: Packagemanagement ist ein Aggregator für Softwarepaket-Manager.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_packagemanagement?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PackageManagement
ms.openlocfilehash: 5b4b42dfce03831da5cc317276e78e0777ff73d6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223812"
---
# <a name="about-packagemanagement"></a>Informationen zu packagemanagement

## <a name="short-description"></a>KURZE BESCHREIBUNG
Packagemanagement ist ein Aggregator für Softwarepaket-Manager.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Die packagemanagement-Funktionalität wurde in Windows PowerShell 5,0 eingeführt.

Packagemanagement ist eine einheitliche Schnittstelle für Softwarepaket Verwaltungssysteme. Sie können die packagemanagement-Cmdlets ausführen, um Aufgaben für die Software Ermittlung, Installation und Inventur (SDII) auszuführen. Unabhängig von der zugrunde liegenden Installations Technologie können Sie die allgemeinen Cmdlets im packagemanagement-Modul ausführen, um Pakete zu suchen, zu installieren oder zu deinstallieren. Hinzufügen, entfernen und Abfragen von paketrepositorys und Ausführen von Abfragen auf einem Computer, um zu bestimmen, welche Softwarepakete installiert sind.

Packagemanagement unterstützt ein flexibles Plug-in-Modell, das die Unterstützung anderer Softwarepaket-Verwaltungssysteme ermöglicht.

Das packagemanagement-Modul ist in Windows PowerShell 5,0 und neueren Versionen von PowerShell enthalten und funktioniert auf drei Ebenen der Paket Verwaltungsstruktur: Paketanbieter, Paketquellen und Pakete selbst. Wir definieren einige Begriffe:

- Paket-Manager: Software Paketverwaltungssystem. In den packagemanagement-Begriffen handelt es sich hierbei um einen Paketanbieter.
- Paketanbieter: packagemanagement-Begriff für einen Paket-Manager. Beispiele hierfür sind Windows Installer, Chocolatey und andere.
- Paketquelle: eine URL, ein lokaler Ordner oder ein frei gegebener Netzwerkordner, den Sie als Repository für die Verwendung von Paket Anbietern konfigurieren.
- Package: eine Softwarekomponente, die von einem Paketanbieter verwaltet wird und die in einer bestimmten Paketquelle gespeichert ist.

Das packagemanagement-Modul umfasst die folgenden Cmdlets. Weitere Informationen finden Sie in der [packagemanagement](/powershell/module/packagemanagement) -Hilfe.

- `Get-PackageProvider`: Gibt eine Liste von Paket Anbietern zurück, die mit packagemanagement verbunden sind.
- `Get-PackageSource`: Ruft eine Liste der Paketquellen ab, die für einen Paketanbieter registriert sind.
- `Register-PackageSource`: Fügt eine Paketquelle für einen angegebenen Paketanbieter hinzu.
- `Set-PackageSource`: Legt Eigenschaften für eine vorhandene Paketquelle fest.
- `Unregister-PackageSource`: Entfernt eine registrierte Paketquelle.
- `Get-Package`: Gibt eine Liste der installierten Softwarepakete zurück.
- `Find-Package`: Findet Softwarepakete in verfügbaren Paketquellen.
- `Install-Package`: Installiert mindestens ein Softwarepaket.
- `Save-Package`: Speichert Pakete auf dem lokalen Computer, ohne Sie zu installieren.
- `Uninstall-Package`: Deinstalliert mindestens ein Softwarepaket.

### <a name="package-provider-bootstrapping-and-dynamic-cmdlet-parameters"></a>Paketanbieter-Bootstrapping und dynamische Cmdlet-Parameter

Standardmäßig wird packagemanagement mit einem kernbootstrap-Anbieter ausgeliefert. Sie können weitere Paketanbieter installieren, wenn Sie Sie benötigen, indem Sie Bootstrapping für die Anbieter durchstarten. Das heißt, dass auf eine Aufforderung zum automatischen Installieren des Anbieters von einem Webdienst aus reagiert wird. Sie können einen Paketanbieter mit einem beliebigen packagemanagement-Cmdlet angeben. Wenn der angegebene Anbieter nicht verfügbar ist, werden Sie von packagemanagement aufgefordert, den Anbieter zu Bootstrap (oder automatisch zu installieren). Wenn der Chocolatey-Anbieter nicht bereits installiert ist, wird in den folgenden Beispielen der Anbieter von packagemanagement installiert.

```powershell
Find-Package -Provider Chocolatey <PackageName>
```

Wenn der Chocolatey-Anbieter nicht bereits installiert ist, werden Sie beim Ausführen des vorherigen Befehls aufgefordert, ihn zu installieren.

```powershell
Install-Package <Chocolatey package Name> -ForceBootstrap
```

Wenn der Chocolatey-Anbieter nicht bereits installiert ist, wird der Anbieter installiert, wenn Sie den vorherigen Befehl ausführen. aber da der forcebootstrap-Parameter dem Befehl hinzugefügt wurde, werden Sie nicht aufgefordert, ihn zu installieren. sowohl der Anbieter als auch das Paket werden automatisch installiert.

Wenn Sie versuchen, ein Paket zu installieren, wenn der unterstützende Anbieter nicht bereits installiert ist und Sie dem Befehl den forcebootstrap-Parameter nicht hinzufügen, werden Sie von packagemanagement aufgefordert, den Anbieter zu installieren.

Durch die Angabe eines Paket Anbieters in Ihrem packagemanagement-Befehl können dynamische Parameter verfügbar gemacht werden, die für diesen Paketanbieter spezifisch sind. Wenn Sie Get-Help für ein bestimmtes packagemanagement-Cmdlet ausführen, wird eine Liste von Parametersätzen zurückgegeben, wobei dynamische Parameter für verfügbare Paketanbieter in separaten Parametersätzen gruppiert werden.

Weitere Informationen zum Projekt "packagemanagement"

Weitere Informationen zum geöffneten Entwicklungsprojekt packagemanagement, einschließlich der Erstellung eines packagemanagement-Paket Anbieters, finden Sie im Projekt packagemanagement auf GitHub unter https://oneget.org .

## <a name="see-also"></a>SIEHE AUCH

[Get-PackageProvider](xref:PackageManagement.Get-PackageProvider)

[Get-PackageSource](xref:PackageManagement.Get-PackageSource)

[Register-PackageSource](xref:PackageManagement.Register-PackageSource)

[Set-PackageSource](xref:PackageManagement.Set-PackageSource)

[Unregister-PackageSource](xref:PackageManagement.Unregister-PackageSource)

[Get-Package](xref:PackageManagement.Get-Package)

[Find-Package](xref:PackageManagement.Find-Package)

[Install-Package](xref:PackageManagement.Install-Package)

[Save-Package](xref:PackageManagement.Save-Package)

[Uninstall-Package](xref:PackageManagement.Uninstall-Package)
