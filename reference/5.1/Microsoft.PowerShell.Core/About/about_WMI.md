---
description: Windows-Verwaltungsinstrumentation (WMI) verwendet die Common Information Model (CIM) zur Darstellung von Systemen, Anwendungen, Netzwerken, Geräten und anderen verwaltbaren Komponenten des modernen Unternehmens.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI
ms.openlocfilehash: d24b952ee167e51815d6d9920e95bbc9a6bb9608
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223207"
---
# <a name="about-wmi"></a>Informationen zu WMI

## <a name="short-description"></a>KURZE BESCHREIBUNG

Windows-Verwaltungsinstrumentation (WMI) verwendet die Common Information Model (CIM) zur Darstellung von Systemen, Anwendungen, Netzwerken, Geräten und anderen verwaltbaren Komponenten des modernen Unternehmens.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Windows-Verwaltungsinstrumentation (WMI) ist die Microsoft-Implementierung von Web-Based Enterprise Management (WBEM), dem Industriestandard.

Klassisches WMI verwendet DCOM für die Kommunikation mit vernetzten Geräten, um Remote Systeme zu verwalten. Windows PowerShell 3,0 führt ein CIM-Anbieter Modell ein, das WinRM verwendet, um die Abhängigkeit von DCOM zu entfernen. Dieses CIM-Anbieter Modell verwendet auch neue WMI-Anbieter-APIs, mit denen Entwickler Windows PowerShell-Cmdlets in nativem Code (C) schreiben können \+ \+ .

Verwechseln Sie WMI-Anbieter nicht mit Windows PowerShell-Anbietern. Viele Windows-Features verfügen über einen zugeordneten WMI-Anbieter, der Ihre Verwaltungsfunktionen verfügbar macht. Zum Abrufen von WMI-Anbietern führen Sie eine WMI-Abfrage aus, mit der Instanzen der WMI-Klasse __Provider abgerufen werden, z. b. die folgende Abfrage.

```powershell
Get-WmiObject -Class __Provider
```

## <a name="three-components-of-wmi"></a>drei WMI-Komponenten

Die folgenden drei Komponenten von WMI interagieren mit Windows PowerShell: Namespaces, Anbieter und Klassen.

WMI-Namespaces organisieren WMI-Anbieter und WMI-Klassen in Gruppen verwandter Komponenten. Auf diese Weise ähneln sie .NET Framework Namespaces.
Namespaces sind keine physischen Speicherorte, sondern eher wie logische Datenbanken.
Alle WMI-Namespaces sind Instanzen der __Namespace System Klasse. Der standardmäßige WMI-Namespace ist root \/ CIMV2 (seit Microsoft Windows 2000). Wenn Sie Windows PowerShell zum Verwenden von WMI-Namespaces in der aktuellen Sitzung verwenden möchten, verwenden Sie einen Befehl mit dem folgenden Format.

```powershell
Get-WmiObject -Class __Namespace
```

Um WMI-Namespaces in anderen Namespaces zu erhalten, verwenden Sie den Namespace-Parameter, um den Speicherort der Suche zu ändern. Der folgende Befehl sucht nach WMI-Namespaces, die sich im Root/Cimv2/Applications-Namespace befinden.

```powershell
Get-WmiObject -Class __Namespace -Namespace root/CIMv2/applications
```

WMI-Namespaces sind hierarchisch. Daher muss beim Abrufen einer Liste aller Namespaces auf einem bestimmten System eine rekursive Abfrage gestartet werden, die mit dem Stamm Namespace beginnt.

WMI-Anbieter machen Informationen zu überschaubaren Windows-Objekten verfügbar. Ein Anbieter ruft Daten von einer-Komponente ab und übergibt diese Daten über WMI an eine Verwaltungs Anwendung, wie z. b. Windows PowerShell. Die meisten WMI-Anbieter sind dynamische Anbieter. Dies bedeutet, dass Sie die Daten dynamisch abrufen, wenn Sie über die Verwaltungs Anwendung angefordert werden.

## <a name="finding-wmi-classes"></a>Suchen von WMI-Klassen

In einer Standardinstallation von Windows 8 sind mehr als 1.100 WMI-Klassen in root \/ Cimv2 vorhanden. Mit diesen vielen WMI-Klassen identifiziert die Herausforderung die geeignete WMI-Klasse, die zum Ausführen einer bestimmten Aufgabe verwendet wird. Windows PowerShell 3,0 bietet zwei Möglichkeiten, um WMI-Klassen zu finden, die mit einem bestimmten Thema verknüpft sind.

Wenn Sie z. b. WMI-Klassen im Stamm-CIMV2-WMI-Namespace im Zusammenhang mit Datenträgern suchen möchten \\ , können Sie eine Abfrage wie die hier gezeigte verwenden.

```powershell
Get-WmiObject -List *disk*
```

Zum Ermitteln von WMI-Klassen, die sich auf den Arbeitsspeicher beziehen, können Sie eine Abfrage wie die hier gezeigte verwenden.

```powershell
Get-WmiObject -List *memory*
```

Die CIM-Cmdlets bieten außerdem die Möglichkeit, WMI-Klassen zu ermitteln. Verwenden Sie hierzu das Cmdlet "Get-CIMClass". Der hier gezeigte Befehl listet WMI-Klassen auf, die mit Video verknüpft sind.

```powershell
Get-CimClass *video*
```

Die Tabulator Erweiterung funktioniert bei der Änderung von WMI-Namespaces. Daher sind untergeordnete WMI-Namespaces durch die Verwendung der Tabulator Erweiterung leicht erkennbar. Im folgenden Beispiel werden mit dem Cmdlet "Get-CimClass" WMI-Klassen aufgelistet, die mit den Energie Einstellungen verknüpft sind.
Um es zu suchen, geben Sie den `root/CIMV2/` -Namespace ein, und drücken Sie dann mehrmals die Tab-Taste, bis der Power-Namespace angezeigt wird. Hier ist der Befehl:

```powershell
Get-CimClass *power* -Namespace root/cimv2/power
```
