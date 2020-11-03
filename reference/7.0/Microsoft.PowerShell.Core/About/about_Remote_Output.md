---
description: Beschreibt, wie die Ausgabe von Remote Befehlen interpretiert und formatiert wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_output?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Output
ms.openlocfilehash: 4d298b945a9b6d45b26a76b3788d2a49b7d2a107
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223759"
---
# <a name="about-remote-output"></a>Informationen zur Remote Ausgabe

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt, wie die Ausgabe von Remote Befehlen interpretiert und formatiert wird.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Die Ausgabe eines Befehls, der auf einem Remote Computer ausgeführt wurde, könnte wie die Ausgabe desselben Befehls aussehen, der auf einem lokalen Computer ausgeführt wird. es gibt jedoch einige bedeutende Unterschiede.

In diesem Thema wird erläutert, wie die Ausgabe von Befehlen interpretiert, formatiert und angezeigt wird, die auf Remote Computern ausgeführt werden.

## <a name="displaying-the-computer-name"></a>Anzeigen des Computer namens

Wenn Sie mit dem Cmdlet "Invoke-Command" einen Befehl auf einem Remote Computer ausführen, gibt der Befehl ein Objekt zurück, das den Namen des Computers enthält, von dem die Daten generiert wurden. Der Name des Remote Computers wird in der pscomputername-Eigenschaft gespeichert.

Für viele Befehle wird der pscomputername standardmäßig angezeigt. Der folgende Befehl führt z. b. einen Get-Culture Befehl auf zwei Remote Computern aus: Server01 und Server02. Die Ausgabe, die unten angezeigt wird, enthält die Namen der Remote Computer, auf denen der Befehl ausgeführt wurde.

```powershell
C:\PS> invoke-command -script {get-culture} -comp Server01, Server02

LCID  Name    DisplayName                PSComputerName
----  ----    -----------                --------------
1033  en-US   English (United States)    Server01
1033  es-AR   Spanish (Argentina)        Server02
```

Sie können den hidecomputername-Parameter von Invoke-Command verwenden, um die pscomputername-Eigenschaft auszublenden. Dieser Parameter ist für Befehle vorgesehen, die nur Daten von einem Remote Computer sammeln.

Der folgende Befehl führt einen Get-Culture Befehl auf dem Remote Computer "Server01" aus. Er verwendet den hidecomputername-Parameter, um die pscomputername-Eigenschaft und zugehörige Eigenschaften auszublenden.

```powershell
C:\PS> invoke-command -scr {get-culture} -comp Server01 -HideComputerName

LCID             Name             DisplayName
----             ----             -----------
1033             en-US            English (United States)
```

Sie können auch die pscomputername-Eigenschaft anzeigen, wenn Sie nicht standardmäßig angezeigt wird.

Beispielsweise verwenden die folgenden Befehle das Format-Table-Cmdlet, um die pscomputername-Eigenschaft der Ausgabe eines Remote Get-Date Befehls hinzuzufügen.

```powershell
$dates = invoke-command -script {get-date} -computername Server01, Server02
$dates | format-table DateTime, PSComputerName -auto

DateTime                            PSComputerName
--------                            --------------
Monday, July 21, 2008 7:16:58 PM    Server01
Monday, July 21, 2008 7:16:58 PM    Server02
```

## <a name="displaying-the-machinename-property"></a>Anzeigen der MachineName-Eigenschaft

Mehrere Cmdlets, einschließlich "Get-Process", "Get-Service" und "Get-EventLog", verfügen über einen Computername-Parameter, mit dem die Objekte auf einem Remote Computer abgerufen werden.
Diese Cmdlets verwenden nicht PowerShell-Remoting, sodass Sie Sie auch auf Computern verwenden können, die nicht für Remoting in Windows PowerShell konfiguriert sind.

Die Objekte, die von diesen Cmdlets zurückgegeben werden, speichern den Namen des Remote Computers in der MachineName-Eigenschaft. (Diese Objekte haben keine pscomputername-Eigenschaft.)

Dieser Befehl ruft z. b. den PowerShell-Prozess auf den Remote Computern Server01 und Server02 ab. Die Standard Anzeige enthält nicht die MachineName-Eigenschaft.

```powershell
C:\PS> get-process PowerShell -computername server01, server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
920      38    97524     114504   575     9.66   2648 PowerShell
194       6    24256      32384   142            3020 PowerShell
352      27    63472      63520   577     3.84   4796 PowerShell
```

Sie können das Cmdlet "Format-Table" verwenden, um die "MachineName"-Eigenschaft der Prozess Objekte anzuzeigen.

Der folgende Befehl speichert beispielsweise die Prozesse in der $p-Variablen und verwendet dann einen Pipeline Operator (|), um die Prozesse in $p an den Format-Table-Befehl zu senden. Der Befehl verwendet den property-Parameter von Format-Table, um die MachineName-Eigenschaft in die Anzeige einzubeziehen.

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02
C:\PS> $P | format-table -property ID, ProcessName, MachineName -auto

Id ProcessName MachineName
-- ----------- -----------
2648 PowerShell  Server02
3020 PowerShell  Server01
4796 PowerShell  Server02
```

Der folgende komplexere Befehl fügt die MachineName-Eigenschaft der Standardprozess Anzeige hinzu. Sie verwendet Hash Tabellen, um berechnete Eigenschaften anzugeben. Glücklicherweise müssen Sie es nicht verstehen, um es zu verwenden.

(Beachten Sie, dass das Graviszeichen ['] das Fortsetzungs Zeichen ist.)

```powershell
C:\PS> $p = get-process PowerShell -comp Server01, Server02

C:\PS> $p | format-table -property Handles, `
@{Label="NPM(K)";Expression={int}}, `
@{Label="PM(K)";Expression={int}}, `
@{Label="WS(K)";Expression={int}}, `
@{Label="VM(M)";Expression={int}}, `
@{Label="CPU(s)";Expression={if ($.CPU -ne $()){ $.CPU.ToString("N")}}}, `
Id, ProcessName, MachineName -auto

Handles NPM(K) PM(K)  WS(K) VM(M) CPU(s)   Id ProcessName MachineName
------- ------ -----  ----- ----- ------   -- ----------- -----------
920     38 97560 114532   576        2648 PowerShell  Server02
192      6 24132  32028   140        3020 PowerShell  Server01
438     26 48436  59132   565        4796 PowerShell  Server02

```

## <a name="deserialized-objects"></a>deserialisierte Objekte

Wenn Sie Remote Befehle ausführen, die die Ausgabe generieren, wird die Befehlsausgabe über das Netzwerk zurück an den lokalen Computer übertragen.

Da die meisten Live Microsoft .NET Framework-Objekte (z. b. die von PowerShell-Cmdlets zurückgegebenen Objekte) nicht über das Netzwerk übertragen werden können, werden die Live-Objekte "serialisiert". Das heißt, die Live-Objekte werden in XML-Darstellungen des-Objekts und der zugehörigen Eigenschaften konvertiert. Anschließend wird das XML-basierte serialisierte Objekt über das Netzwerk übertragen.

Auf dem lokalen Computer empfängt PowerShell das XML-basierte serialisierte Objekt und deserialisiert es, indem das XML-basierte Objekt in ein Standard-.NET Framework Objekt umgewandelt wird.

Das deserialisierte Objekt ist jedoch kein Live Objekt. Es handelt sich um eine Momentaufnahme des-Objekts zum Zeitpunkt der Serialisierung und enthält Eigenschaften, aber keine-Methoden. Sie können diese Objekte in PowerShell verwenden und verwalten, indem Sie Sie an Pipelines übergeben, ausgewählte Eigenschaften anzeigen und formatieren.

Die meisten deserialisierten Objekte werden automatisch für die Anzeige durch Einträge in den Types.ps1XML-oder Format.ps1XML-Dateien formatiert. Allerdings verfügt der lokale Computer möglicherweise nicht über Formatierungs Dateien für alle deserialisierten Objekte, die auf einem Remote Computer generiert wurden. Wenn Objekte nicht formatiert sind, werden alle Eigenschaften der einzelnen Objekte in der Konsole in einer streamingliste angezeigt.

Wenn Objekte nicht automatisch formatiert werden, können Sie die Formatierungs-Cmdlets wie Format-Table oder Format-List verwenden, um die ausgewählten Eigenschaften zu formatieren und anzuzeigen. Oder Sie können das Cmdlet "Out-GridView" verwenden, um die Objekte in einer Tabelle anzuzeigen.

Wenn Sie außerdem einen Befehl auf einem Remote Computer ausführen, der-Cmdlets verwendet, die nicht auf dem lokalen Computer vorhanden sind, werden die Objekte, die der Befehl zurückgibt, möglicherweise nicht ordnungsgemäß formatiert, da Sie nicht über die Formatierungs Dateien für diese Objekte auf dem Computer verfügen. Um Formatierungsdaten von einem anderen Computer zu erhalten, verwenden Sie die Cmdlets Get-FormatData und Export-FormatData.

Einige Objekttypen, z. b. DirectoryInfo-Objekte und GUIDs, werden wieder in Live Objekte konvertiert, wenn Sie empfangen werden. Diese Objekte benötigen keine besondere Behandlung oder Formatierung.

## <a name="ordering-the-results"></a>Reihenfolge der Ergebnisse

Die Reihenfolge der Computernamen im Computername-Parameter von Cmdlets legt die Reihenfolge fest, in der PowerShell eine Verbindung mit den Remote Computern herstellt. Die Ergebnisse werden jedoch in der Reihenfolge angezeigt, in der Sie vom lokalen Computer empfangen werden. Dies kann eine andere Reihenfolge sein.

Verwenden Sie das Cmdlet "Sort-Object", um die Reihenfolge der Ergebnisse zu ändern. Sie können nach der pscomputername-Eigenschaft oder der MachineName-Eigenschaft sortieren. Sie können auch nach einer anderen Eigenschaft des Objekts sortieren, sodass die Ergebnisse von verschiedenen Computern miteinander vermischt werden.

## <a name="see-also"></a>SIEHE AUCH

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table)

[Get-Process](xref:Microsoft.PowerShell.Management.Get-Process)

[Get-Service](xref:Microsoft.PowerShell.Management.Get-Service)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object)
