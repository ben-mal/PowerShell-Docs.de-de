---
ms.date: 08/21/2020
keywords: powershell,cmdlet
title: Ausführen von Remotebefehlen
description: Erläutert die Methoden zum Ausführen von Befehlen auf Remotesystemen mithilfe von PowerShell.
ms.openlocfilehash: cff18a4f51c3ed8e3ed2c1f35862a88911e7ceb5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "94391407"
---
# <a name="running-remote-commands"></a>Ausführen von Remotebefehlen

Mit einem einzigen PowerShell-Befehl können Sie Befehle auf einem oder Hunderten von Computern ausführen. Windows PowerShell unterstützt das Remotecomputing mithilfe verschiedener Technologien, unter anderem WMI, RPC und WS-Management.

PowerShell Core unterstützt WMI, WS-Management und SSH-Remoting. In PowerShell 6 wird RPC nicht mehr unterstützt. Ab PowerShell 7 wird RPC nur in Windows unterstützt.

Weitere Informationen zu Remoting in PowerShell Core finden Sie in den folgenden Artikeln:

- [SSH-Remoting in PowerShell Core][ssh-remoting]
- [WSMan-Remoting in PowerShell Core][wsman-remoting]

## <a name="windows-powershell-remoting-without-configuration"></a>Windows PowerShell-Remoting ohne Konfiguration

Viele Windows PowerShell-Cmdlets verfügen über einen „ComputerName“-Parameter, mit dessen Hilfe Sie Daten auf einem oder mehreren Remotecomputern sammeln und Einstellungsänderungen vornehmen können. Diese Cmdlets verwenden unterschiedliche Kommunikationsprotokolle und funktionieren auf allen Windows-Betriebssystemen ohne besondere Konfiguration.

Zu diesem Cmdlets zählen:

- [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer)
- [Test-Connection](/powershell/module/microsoft.powershell.management/test-connection)
- [Clear-EventLog](/powershell/module/microsoft.powershell.management/clear-eventlog)
- [Get-EventLog](/powershell/module/microsoft.powershell.management/get-eventlog)
- [Get-HotFix](/powershell/module/microsoft.powershell.management/get-hotfix)
- [Get-Process](/powershell/module/microsoft.powershell.management/get-process)
- [Get-Service](/powershell/module/microsoft.powershell.management/get-service)
- [Set-Service](/powershell/module/microsoft.powershell.management/set-service)
- [Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/get-winevent)
- [Get-WmiObject](/powershell/module/microsoft.powershell.management/get-wmiobject)

In der Regel weisen Cmdlets, die Remoting ohne besondere Konfiguration unterstützen, den „ComputerName“-Parameter und nicht den „Session“-Parameter auf. Um diese Cmdlets in Ihrer Sitzung zu finden, geben Sie Folgendes ein:

```powershell
Get-Command | where { $_.parameters.keys -contains "ComputerName" -and $_.parameters.keys -notcontains "Session"}
```

## <a name="windows-powershell-remoting"></a>Windows PowerShell-Remoting

Über das WS-Management-Protokoll können Sie mit Windows PowerShell-Remoting jeden Windows PowerShell-Befehl auf einem oder mehreren Remotecomputern ausführen. Sie können dauerhafte Verbindungen herstellen, interaktive Sitzungen starten und Skripts auf Remotecomputern ausführen.

Um Windows PowerShell-Remoting zu verwenden, muss der Remotecomputer für die Remoteverwaltung konfiguriert sein.
Weitere Informationen und Anweisungen hierzu finden Sie unter [Informationen zu Remoteanforderungen](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).

Nachdem Sie Windows PowerShell-Remoting konfiguriert haben, stehen Ihnen viele Remotingstrategien zur Verfügung.
In diesem Artikel werden nur einige davon aufgeführt. Weitere Informationen finden Sie unter [Informationen zu Remote](/powershell/module/microsoft.powershell.core/about/about_remote).

### <a name="start-an-interactive-session"></a>Starten einer interaktiven Sitzung

Um eine interaktive Sitzung mit einem einzelnen Remotecomputer zu starten, verwenden Sie das Cmdlet [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession). Um beispielsweise eine interaktive Sitzung mit dem Remotecomputer „Server01“ zu starten, geben Sie Folgendes ein:

```powershell
Enter-PSSession Server01
```

Die Eingabeaufforderung ändert sich, und es wird der Name des Remotecomputers angezeigt. Alle Befehle, die Sie an der Eingabeaufforderung eingeben, werden auf dem Remotecomputer ausgeführt, und die Ergebnisse werden auf dem lokalen Computer angezeigt.

Um die interaktive Sitzung zu beenden, geben Sie Folgendes ein:

```powershell
Exit-PSSession
```

Weitere Informationen über die Cmdlets „Enter-PSSession“ und „Exit-PSSession“ finden Sie unter:

- [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession)
- [Exit-PSSession](/powershell/module/microsoft.powershell.core/exit-pssession)

### <a name="run-a-remote-command"></a>Ausführen eines Remotebefehls

Zum Ausführen eines Befehls auf einem oder mehreren Computern verwenden Sie das Cmdlet [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command). Um beispielsweise einen [Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture)-Befehl auf den Remotecomputern „Server01“ und „Server02“ auszuführen, geben Sie Folgendes ein:

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-UICulture}
```

Die Ausgabe wird an den Computer zurückgegeben.

```output
LCID    Name     DisplayName               PSComputerName
----    ----     -----------               --------------
1033    en-US    English (United States)   server01.corp.fabrikam.com
1033    en-US    English (United States)   server02.corp.fabrikam.com
```

### <a name="run-a-script"></a>Ausführen eines Skripts

Zum Ausführen eines Skripts auf einem oder mehreren Remotecomputern verwenden Sie den Parameter „FilePath“ des Cmdlets `Invoke-Command`. Das Skript muss sich auf dem lokalen Computer befinden oder für diesen verfügbar sein. Die Ergebnisse werden an den lokalen Computer zurückgegeben.

Der folgende Befehl führt beispielsweise das Skript „DiskCollect.ps1“ auf den Remotecomputern „Server01“ und „Server02“ aus.

```powershell
Invoke-Command -ComputerName Server01, Server02 -FilePath c:\Scripts\DiskCollect.ps1
```

### <a name="establish-a-persistent-connection"></a>Herstellen einer dauerhaften Verbindung

Verwenden Sie das Cmdlet `New-PSSession`, um eine permanente Sitzung auf einem Remotecomputer zu erstellen. Das folgende Beispiel erstellt Remotesitzungen auf „Server01“ und „Server02. Die Sitzungsobjekte werden in der Variablen `$s` gespeichert.

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

Nachdem die Sitzungen nun hergestellt sind, können Sie jeden beliebigen Befehl in diesen ausführen. Und da die Sitzungen permanent sind, können Sie Daten von einem Befehl sammeln und in einem anderen Befehl verwenden.

Beispielsweise führt der folgende Befehl einen „Get-HotFix“-Befehl in den Sitzungen in der Variablen „$s“ aus und speichert die Ergebnisse dann in der Variablen „$h“. Die Variable „$h“ wird in jeder der Sitzungen in „$s“ erstellt, ist jedoch in der lokalen Sitzung nicht vorhanden.

```powershell
Invoke-Command -Session $s {$h = Get-HotFix}
```

Nun können Sie die Daten in der Variablen `$h` in der gleichen Sitzung mit anderen Befehlen verwenden. Die Ergebnisse werden auf dem lokalen Computer angezeigt. Beispiel:

```powershell
Invoke-Command -Session $s {$h | where {$_.InstalledBy -ne "NTAUTHORITY\SYSTEM"}}
```

### <a name="advanced-remoting"></a>Erweitertes Remoting

Dies sind nur die grundlegenden Möglichkeiten, die die Remoteverwaltung von Windows PowerShell bietet. Mithilfe von Cmdlets, die mit Windows PowerShell installiert werden, können Sie Remotesitzungen sowohl von lokaler Seite als auch von Remoteseite aus einrichten und konfigurieren, angepasste und eingeschränkte Sitzungen erstellen, Benutzern über eine Remotesitzung den Import von Befehlen ermöglichen, die tatsächlich implizit in der Remotesitzung ausgeführt werden, die Sicherheit einer Remotesitzung konfigurieren und vieles mehr.

Windows PowerShell umfasst einen WSMan-Anbieter. Der Anbieter erstellt ein `WSMAN:`-Laufwerk, dass es Ihnen ermöglicht, durch eine Hierarchie von Konfigurationseinstellungen auf dem lokalen Computer und den Remotecomputern zu navigieren.

Weitere Informationen zum WSMan-Anbieter finden Sie unter [WS-Management-Anbieter](/powershell/module/microsoft.wsman.management/about/about_wsman_provider) und [Informationen zu WS-Management-Cmdlets](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets). Geben Sie alternativ in der Windows PowerShell-Konsole `Get-Help wsman` ein.

Weitere Informationen finden Sie in folgenden Quellen:

- [Häufig gestellte Fragen zu Remote](/powershell/module/microsoft.powershell.core/about/about_remote_faq)
- [Register-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)
- [Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession)

Hilfe zu Remotingfehlern finden Sie unter [about_Remote_Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_Remote_Troubleshooting).

## <a name="see-also"></a>Weitere Informationen

- [about_Remote](/powershell/module/microsoft.powershell.core/about/about_remote_faq)
- [about_Remote_FAQ](/powershell/module/microsoft.powershell.core/about/about_remote_faq)
- [about_Remote_Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements)
- [about_Remote_Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_Remote_Troubleshooting)
- [about_PSSessions](/powershell/module/microsoft.powershell.core/about/about_PSSessions)
- [about_WS-Management_Cmdlets](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets)
- [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession)
- [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)
- [Register-PSSessionConfiguration](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)
- [WSMan-Anbieter](/powershell/module/microsoft.wsman.management/about/about_wsman_provider)

[wsman-remoting]: WSMan-Remoting-in-PowerShell-Core.md
[ssh-remoting]: SSH-Remoting-in-PowerShell-Core.md
