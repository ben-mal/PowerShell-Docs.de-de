---
description: Windows PowerShell erstellt ein Windows-Ereignisprotokoll mit dem Namen "Windows PowerShell", um Windows PowerShell-Ereignisse aufzuzeichnen. Sie können dieses Protokoll in Ereignisanzeige oder mithilfe von Cmdlets anzeigen, die Ereignisse wie das `Get-EventLog` Cmdlet erhalten. Standardmäßig werden Windows PowerShell-Engine-und Anbieter Ereignisse im Ereignisprotokoll aufgezeichnet, aber Sie können die Ereignisprotokoll-Einstellungs Variablen verwenden, um das Ereignisprotokoll anzupassen. Beispielsweise können Sie Ereignisse zu Windows PowerShell-Befehlen hinzufügen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_eventlogs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Eventlogs
ms.openlocfilehash: eb92333c6a6e220e287dcbec1441d2d05aa9275b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223508"
---
# <a name="about-eventlogs"></a>Informationen zu Eventlogs

## <a name="short-description"></a>Kurze Beschreibung

Windows PowerShell erstellt ein Windows-Ereignisprotokoll mit dem Namen "Windows PowerShell", um Windows PowerShell-Ereignisse aufzuzeichnen. Sie können dieses Protokoll in Ereignisanzeige oder mithilfe von Cmdlets anzeigen, die Ereignisse wie das `Get-EventLog` Cmdlet erhalten. Standardmäßig werden Windows PowerShell-Engine-und Anbieter Ereignisse im Ereignisprotokoll aufgezeichnet, aber Sie können die Ereignisprotokoll-Einstellungs Variablen verwenden, um das Ereignisprotokoll anzupassen. Beispielsweise können Sie Ereignisse zu Windows PowerShell-Befehlen hinzufügen.

## <a name="long-description"></a>Lange Beschreibung

Das Windows PowerShell-Ereignisprotokoll zeichnet Details zu Windows PowerShell-Vorgängen auf, z. b. das Starten und Beenden der Programm-Engine und das Starten und Beenden der Windows PowerShell-Anbieter. Sie können auch Details zu Windows PowerShell-Befehlen protokollieren.

Das Windows PowerShell-Ereignisprotokoll befindet sich in der Gruppe Anwendungs-und Dienst Protokolle. Beim Windows PowerShell-Protokoll handelt es sich um ein klassisches Ereignisprotokoll, in dem die Windows Eventing-Technologie nicht verwendet wird. Um das Protokoll anzuzeigen, verwenden Sie die Cmdlets, die für Klassische Ereignisprotokolle wie entwickelt wurden `Get-EventLog` .

## <a name="viewing-the-windows-powershell-event-log"></a>Anzeigen des Windows PowerShell-Ereignis Protokolls

Sie können das Windows PowerShell-Ereignisprotokoll in Ereignisanzeige oder mithilfe der `Get-EventLog` -und- `Get-WmiObject` Cmdlets anzeigen. Geben Sie Folgendes ein, um den Inhalt des Windows PowerShell-Protokolls anzuzeigen:

```powershell
Get-EventLog -LogName "Windows PowerShell"
```

Verwenden Sie zum Überprüfen der Ereignisse und ihrer Eigenschaften das `Sort-Object` Cmdlet, das `Group-Object` Cmdlet und die Cmdlets, die das `Format` Verb (die `Format` Cmdlets) enthalten.

Geben Sie z. b. Folgendes ein, um die Ereignisse im Protokoll nach der Ereignis-ID gruppiert anzuzeigen:

```powershell
Get-EventLog "Windows PowerShell" | Format-Table -GroupBy EventID
```

Oder geben Sie Folgendes ein:

```powershell
Get-EventLog "Windows PowerShell" |
  Sort-Object EventID |
  Group-Object EventID
```

Wenn Sie alle klassischen Ereignisprotokolle anzeigen möchten, geben Sie Folgendes ein:

```powershell
Get-EventLog -List
```

Sie können auch das- `Get-WmiObject` Cmdlet verwenden, um die ereignisbezogenen Windows-Verwaltungsinstrumentation (WMI)-Klassen zu verwenden, um das Ereignisprotokoll zu überprüfen. Wenn Sie z. b. alle Eigenschaften der Ereignisprotokoll Datei anzeigen möchten, geben Sie Folgendes ein:

```powershell
Get-WmiObject Win32_NTEventlogFile |
  where LogFileName -EQ "Windows PowerShell" |
  Format-List -Property *
```

Geben Sie Folgendes ein, um die WMI-Klassen für Win32-Ereignisse zu finden:

```powershell
Get-WmiObject -List | where Name -Like "win32*event*"
```

Wenn Sie weitere Informationen benötigen, geben Sie "Get-Help Get-EventLog" und "Get-Help Get-WmiObject" ein.

## <a name="selecting-events-for-the-windows-powershell-event-log"></a>Auswählen von Ereignissen für das Windows PowerShell-Ereignisprotokoll

Sie können die Einstellungs Variablen für das Ereignisprotokoll verwenden, um zu bestimmen, welche Ereignisse im Windows PowerShell-Ereignisprotokoll aufgezeichnet werden.

Es gibt sechs Ereignisprotokoll-Einstellungs Variablen: zwei Variablen für jede der drei Protokollierungs Komponenten: die-Engine (das Windows PowerShell-Programm), die-Anbieter und die-Befehle. Die lifecycleevent-Variablen protokollieren normale Start-und Stop-Ereignisse. Die Integritäts Variablen protokollieren Fehlerereignisse.

In der folgenden Tabelle sind die Einstellungs Variablen für das Ereignisprotokoll aufgelistet.

|Variable                  |BESCHREIBUNG                                    |
|--------------------------|-----------------------------------------------|
|$LogEngineLifeCycleEvent  |Protokolliert den Start und das Ende von PowerShell.          |
|$LogEngineHealthEvent     |Protokolliert PowerShell-Programmfehler.                 |
|$LogProviderLifeCycleEvent|Protokolliert den Start und das Ende von PowerShell-Anbietern.|
|$LogProviderHealthEvent   |Protokolliert Fehler des PowerShell-Anbieters.                |
|$LogCommandLifeCycleEvent |Protokolliert den Start und den Abschluss von Befehlen.   |
|$LogCommandHealthEvent    |Protokolliert Befehls Fehler.                            |

(Informationen zu Windows PowerShell-Anbietern finden Sie unter [about_Providers](about_Providers.md).)

Standardmäßig sind nur die folgenden Ereignis Typen aktiviert:

* $LogEngineLifeCycleEvent
* $LogEngineHealthEvent
* $LogProviderLifeCycleEvent
* $LogProviderHealthEvent

Legen Sie zum Aktivieren eines Ereignis Typs die Preference-Variable für diesen Ereignistyp auf $true fest. Wenn Sie z. b. Befehls Lebenszyklus-Ereignisse aktivieren möchten, geben Sie Folgendes ein:

```powershell
$LogCommandLifeCycleEvent
```

Oder geben Sie Folgendes ein:

```powershell
$LogCommandLifeCycleEvent = $true
```

Wenn Sie einen Ereignistyp deaktivieren möchten, legen Sie die Preference-Variable für diesen Ereignistyp auf $false fest. Geben Sie z. b. Folgendes ein, um die Lebenszyklus Ereignisse von Befehlen zu deaktivieren:

```powershell
$LogProviderLifeCycleEvent = $false
```

Sie können jedes Ereignis deaktivieren, außer den Ereignissen, die angeben, dass die Windows PowerShell-Engine und die Kern Anbieter gestartet werden. Diese Ereignisse werden generiert, bevor die Windows PowerShell-profile ausgeführt werden und bevor das Host Programm Befehle annehmen kann.

Die Variablen Einstellungen gelten nur für die aktuelle Windows PowerShell-Sitzung.
Wenn Sie Sie auf alle Windows PowerShell-Sitzungen anwenden möchten, fügen Sie Sie Ihrem Windows PowerShell-Profil hinzu.

## <a name="logging-module-events"></a>Protokollieren von Modul Ereignissen

Ab Windows PowerShell 3,0 können Sie Ausführungs Ereignisse für die Cmdlets und Funktionen in Windows PowerShell-Modulen und-Snap-Ins aufzeichnen, indem Sie die logpipelineexecutiondetails-Eigenschaft von Modulen und Snap-Ins auf "true" festlegen. In Windows PowerShell 2,0 ist dieses Feature nur für Snap-Ins verfügbar.

Wenn der logpipelineexecutiondetails-Eigenschafts Wert "true ()" lautet `$true` , schreibt Windows PowerShell Cmdlet-und Funktions Ausführungs Ereignisse in der Sitzung in das Windows PowerShell-Protokoll in Ereignisanzeige. Die Einstellung ist nur in der aktuellen Sitzung gültig.

Verwenden Sie die folgende Befehlssequenz, um die Protokollierung von Ausführungs Ereignissen von Cmdlets und Funktionen in einem Modul zu aktivieren.

```powershell
Import-Module <ModuleName>
$m = Get-Module <ModuleName>
$m.LogPipelineExecutionDetails = $true
```

Verwenden Sie die folgende Befehlssequenz, um die Protokollierung von Ausführungs Ereignissen von Cmdlets in einem Snap-in zu aktivieren.

```powershell
$m = Get-PSSnapin <SnapInName> [-Registered]
$m.LogPipelineExecutionDetails = $True
```

Wenn Sie die Protokollierung deaktivieren möchten, verwenden Sie dieselbe Befehlssequenz, um den Eigenschafts Wert auf false () festzulegen `$false` .

Sie können auch die Gruppenrichtlinie Einstellung "Modul Protokollierung aktivieren" verwenden, um die Modul-und Snap-in-Protokollierung zu aktivieren und zu deaktivieren. Der Richtlinien Wert enthält eine Liste der Namen von Modulen und Snap-Ins. Platzhalter werden unterstützt.

Wenn "Modul Protokollierung aktivieren" für ein Modul festgelegt ist, ist der Wert der logpipelineexecutiondetails-Eigenschaft des Moduls in allen Sitzungen "true" und kann nicht geändert werden.

Die Gruppenrichtlinien Einstellung "Modul Protokollierung aktivieren" befindet sich in den folgenden Gruppenrichtlinie Pfaden:

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
     Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

Die Richtlinie für die Benutzerkonfiguration hat Vorrang vor der Computer Konfigurationsrichtlinie, und beide Richtlinien haben Vorrang vor dem Wert der logpipelineexecutiondetails-Eigenschaft von Modulen und Snap-Ins.

Weitere Informationen zu dieser Gruppenrichtlinie Einstellung finden Sie unter [about_Group_Policy_Settings](about_Group_Policy_Settings.md).

## <a name="security-and-auditing"></a>Sicherheit und Überwachung

Das Windows PowerShell-Ereignisprotokoll dient zum Angeben von Aktivitäten und zum Bereitstellen von Betriebs Details zur Problembehandlung.

Wie bei den meisten Windows-basierten Anwendungs Ereignisprotokollen ist das Windows PowerShell-Ereignisprotokoll jedoch nicht als sicher konzipiert. Sie sollte nicht verwendet werden, um die Sicherheit zu überwachen oder vertrauliche oder proprietäre Informationen aufzuzeichnen.

Ereignisprotokolle sind so konzipiert, dass Sie von Benutzern gelesen und verstanden werden können. Benutzer können aus dem Protokoll lesen und in das Protokoll schreiben. Ein böswilliger Benutzer könnte ein Ereignisprotokoll auf einem lokalen Computer oder einem Remote Computer lesen, falsche Daten aufzeichnen und die Protokollierung ihrer Aktivitäten verhindern.

## <a name="notes"></a>Notizen

Autoren von Modul Autoren können ihren Modulen Protokollierungsfunktionen hinzufügen. Weitere Informationen finden Sie unter [Schreiben eines Windows PowerShell-Moduls](/powershell/scripting/developer/module/writing-a-windows-powershell-module).

## <a name="see-also"></a>Weitere Informationen

[Get-EventLog](xref:Microsoft.PowerShell.Management.Get-EventLog)

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Preference_Variables](about_Preference_Variables.md)
