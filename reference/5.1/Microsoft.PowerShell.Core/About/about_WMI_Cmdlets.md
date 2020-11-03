---
description: Enthält Hintergrundinformationen über die Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) und Windows PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI_Cmdlets
ms.openlocfilehash: c2099c005cedf64e9621d66d6757419320c9b43e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223191"
---
# <a name="about-wmi-cmdlets"></a>Informationen zu WMI-Cmdlets

## <a name="short-description"></a>KURZE BESCHREIBUNG

Enthält Hintergrundinformationen über die Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) und Windows PowerShell.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Dieses Thema enthält Informationen zur WMI-Technologie, den WMI-Cmdlets für Windows PowerShell, WMI-basiertes Remoting, WMI-Accelerators und WMI-Problembehandlung. Außerdem enthält dieses Thema Links zu weiteren Informationen über WMI.

### <a name="about-wmi"></a>Informationen zu WMI

Die Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) ist die Microsoft-Implementierung von WBEM (Web-Based Enterprise Management). Hierbei handelt es sich um eine Brancheninitiative zum Entwickeln einer Standardtechnologie für den Zugriff auf Verwaltungsinformationen in einer Unternehmensumgebung. WMI verwendet den Branchenstandard %%amp;quot;Common Information Model (CIM)%%amp;quot; zum Darstellen von Systemen, Anwendungen, Netzwerken, Geräten und anderen verwalteten Komponenten. CIM wird von der Distributed Management Task Force (DMTF) entwickelt und verwaltet. Sie können WMI verwenden, um sowohl lokale als auch Remote Computer zu verwalten. Beispielsweise können Sie mit WMI folgende Aktionen ausführen:

- Starten Sie einen Prozess auf einem Remote Computer.
- Starten Sie einen Computer remote neu.
- Sie erhalten eine Liste der Anwendungen, die auf einem lokalen Computer oder einem Remote Computer installiert sind.
- Abfragen der Windows-Ereignisprotokolle auf einem lokalen Computer oder einem Remote Computer.

### <a name="the-wmi-cmdlets-for-windows-powershell"></a>die WMI-Cmdlets für Windows PowerShell

Windows PowerShell implementiert WMI-Funktionen über eine Reihe von Cmdlets, die standardmäßig in Windows PowerShell verfügbar sind. Sie können diese Cmdlets verwenden, um die End-to-End-Aufgaben abzuschließen, die zum Verwalten von lokalen Computern und Remote Computern erforderlich sind.

Die folgenden WMI-Cmdlets sind enthalten.

|Cmdlet           |BESCHREIBUNG                                   |
|-----------------|----------------------------------------------|
|Get-WmiObject    |Ruft Instanzen von WMI-Klassen oder-Informationen ab.  |
|                 |Informationen zu den verfügbaren Klassen.                  |
|Invoke-WmiMethod |Ruft WMI-Methoden auf.                            |
|Register-WmiEvent|Abonniert ein WMI-Ereignis.                    |
|Remove-WmiObject |Löscht WMI-Klassen und -Instanzen.            |
|Set-WmiInstance  |Erstellt oder ändert Instanzen von WMI-Klassen. |

### <a name="sample-commands"></a>Beispiel Befehle
Mit dem folgenden Befehl werden die BIOS-Informationen für den lokalen Computer angezeigt.

```powershell
C:\PS> get-wmiobject win32_bios | format-list *
```

Mit dem folgenden Befehl werden Informationen zum WinRM-Dienst für drei Remote Computer angezeigt.

```powershell
$wql = "select * from win32_service where name='WinRM'"
get-wmiobject -query $wql -computername server01, server01, server03
```

Mit dem folgenden komplexeren Befehl werden alle Instanzen eines Programms beendet.

```powershell
C:\PS> notepad.exe
C:\PS> $wql = "select * from win32_process where name='notepad.exe'"
C:\PS> $np = get-wmiobject -query $wql
C:\PS> $np | remove-wmiobject
```

### <a name="wmi-based-remoting"></a>WMI-basiertes Remoting

Obwohl die Möglichkeit zur Verwaltung eines lokalen Systems über WMI nützlich ist, sind dies die Remoting-Funktionen, die WMI zu einem leistungsfähigen Verwaltungs Tool machen. WMI verwendet das verteilte Component Object Model (DCOM) von Microsoft, um eine Verbindung mit Systemen herzustellen und diese zu verwalten. Möglicherweise müssen Sie einige Systeme so konfigurieren, dass DCOM-Verbindungen zulässig sind.
Firewalleinstellungen und gesperrte DCOM-Berechtigungen können die Fähigkeit von WMI blockieren, Systeme Remote zu verwalten.

### <a name="wmi-type-accelerators"></a>WMI-typacceleratoren

Windows PowerShell enthält WMI-typaccelerators. Diese WMI-typaccelerators (Verknüpfungen) ermöglichen einen direkteren Zugriff auf WMI-Objekte, als es bei einem nicht-Typ-Accelerator-Ansatz möglich wäre.

Die folgenden typacceleratoren werden von WMI unterstützt:

[Wmisearcher]: eine Verknüpfung für die Suche nach WMI-Objekten.

[WMIClass]: eine Verknüpfung für den Zugriff auf die statischen Eigenschaften und Methoden einer Klasse.

[WMI]: eine Verknüpfung zum erhalten einer einzelnen Instanz einer Klasse.

[Wmisearcher] ist eine typbeschleunigung für einen ManagementObjectSearcher. Es kann einen Zeichenfolgenkonstruktor verwenden, um einen Suchvorgang zu erstellen, für den Sie dann einen get ()-Vorgang ausführen können.

Beispiel:

```powershell
PS> $s = [WmiSearcher]'Select * from Win32_Process where Handlecount > 1000'
PS> $s.Get() |sort handlecount |ft handlecount,__path,name -auto

count  __PATH                                              name
-----  ------                                              ----
1105   \\SERVER01\root\cimv2:Win32_Process.Handle="3724"   PowerShell...
1132   \\SERVER01\root\cimv2:Win32_Process.Handle="1388"   winlogon.exe
1495   \\SERVER01\root\cimv2:Win32_Process.Handle="2852"   iexplore.exe
1699   \\SERVER01\root\cimv2:Win32_Process.Handle="1204"   OUTLOOK.EXE
1719   \\SERVER01\root\cimv2:Win32_Process.Handle="1912"   iexplore.exe
2579   \\SERVER01\root\cimv2:Win32_Process.Handle="1768"   svchost.exe
```

[WMIClass] ist eine typbeschleunigung für ManagementClass. Dies hat einen Zeichenfolgenkonstruktor, der einen lokalen oder absoluten WMI-Pfad zu einer WMI-Klasse annimmt und ein Objekt zurückgibt, das an diese Klasse gebunden ist.

Beispiel:

```powershell
PS> $c = [WMICLASS]"root\cimv2:WIn32_Process"
PS> $c |fl *
Name             : Win32_Process
__GENUS          : 1
__CLASS          : Win32_Process
__SUPERCLASS     : CIM_Process
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Process
__PROPERTY_COUNT : 45
__DERIVATION     : {CIM_Process, CIM_LogicalElement,
                   CIM_ManagedSystemElement}
__SERVER         : SERVER01
__NAMESPACE      : ROOT\cimv2
__PATH           : \\SERVER01\ROOT\cimv2:Win32_Process
```

[WMI] ist eine typbeschleunigung für ManagementObject. Dies hat einen Zeichenfolgenkonstruktor, der einen lokalen oder absoluten WMI-Pfad zu einer WMI-Instanz annimmt und ein an diese Instanz gebundenes Objekt zurückgibt.

Beispiel:

```powershell
PS> $p = [WMI]'\\SERVER01\root\cimv2:Win32_Process.Handle="1204"'
PS> $p.Name
OUTLOOK.EXE
```

### <a name="wmi-troubleshooting"></a>WMI-Problembehandlung

Die folgenden Probleme sind die häufigsten Probleme, die auftreten können, wenn Sie versuchen, eine Verbindung mit einem Remote Computer herzustellen.

Problem 1: der Remote Computer ist nicht online.

Wenn ein Computer offline ist, können Sie mithilfe von WMI keine Verbindung mit ihm herstellen.
Sie erhalten ggf. eine Fehlermeldung der folgenden Art:

```
Remote server machine does not exist or is unavailable
```

Wenn Sie diese Fehlermeldung erhalten, überprüfen Sie, ob der Computer online ist. Versuchen Sie, den Remote Computer zu pingen.

Problem 2: Sie verfügen nicht über lokale Administratorrechte auf dem Remote Computer.

Um WMI Remote verwenden zu können, müssen Sie über lokale Administratorrechte auf dem Remote Computer verfügen. Andernfalls wird der Zugriff auf diesen Computer verweigert.

So überprüfen Sie die Namespace Sicherheit:

1. Klicken Sie im Startmenü mit der rechten Maustaste auf Arbeitsplatz, und klicken Sie dann auf verwalten.
2. Erweitern Sie in der Computer Verwaltung Dienste und Anwendungen, klicken Sie mit der rechten Maustaste auf WMI-Steuerung, und klicken Sie dann auf Eigenschaften.
3. Klicken Sie im Dialogfeld Eigenschaften von WMI-Steuerung auf die Registerkarte Sicherheit.

Problem 3: eine Firewall blockiert den Zugriff auf den Remote Computer.

WMI verwendet die Protokolle DCOM (verteiltes com) und RPC (Remote Prozedur Aufruf), um das Netzwerk zu durchlaufen. Standardmäßig blockieren viele Firewalls DCOM-und RPC-Datenverkehr. Wenn die Firewall diese Protokolle blockiert, tritt bei der Verbindung ein Fehler auf. Beispielsweise ist die Windows-Firewall in Microsoft Windows XP Service Pack 2 so konfiguriert, dass der gesamte nicht angeforderte Netzwerk Datenverkehr, einschließlich DCOM und WMI, automatisch blockiert wird. In der Standardkonfiguration lehnt die Windows-Firewall eine eingehende WMI-Anforderung ab, und Sie erhalten die folgende Fehlermeldung:

```
Remote server machine does not exist or is unavailable
```

## <a name="see-also"></a>SIEHE AUCH

[Informationen zu WMI](/windows/win32/wmisdk/about-wmi)

[WMI-Problembehandlung](/windows/win32/wmisdk/wmi-troubleshooting)

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[Invoke-WmiMethod](xref:Microsoft.PowerShell.Management.Invoke-WmiMethod)

[Register-WmiEvent](xref:Microsoft.PowerShell.Management.Register-WmiEvent)

[Remove-WmiObject](xref:Microsoft.PowerShell.Management.Remove-WmiObject)

[Set-WmiInstance](xref:Microsoft.PowerShell.Management.Set-WmiInstance)
