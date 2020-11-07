---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disconnect-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-PSSession
ms.openlocfilehash: e4036924c45a5fd1b031fa33c8b9226aa5a66c30
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347396"
---
# Disconnect-PSSession

## ZUSAMMENFASSUNG
Trennt eine Verbindung.

## SYNTAX

### Sitzung (Standard)

```
Disconnect-PSSession [-Session] <PSSession[]> [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Name

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Id

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das `Disconnect-PSSession` Cmdlet trennt eine PowerShell-Sitzung ("PSSession"), wie z. b. eine mit dem `New-PSSession` Cmdlet gestartete, aus der aktuellen Sitzung. Dadurch befindet sich die PSSession in einem getrennten Zustand. Sie können von der aktuellen Sitzung oder einer anderen Sitzung auf dem lokalen bzw. einem anderen Computer eine Verbindung mit der getrennten PSSession herstellen.

Das `Disconnect-PSSession` Cmdlet trennt nur geöffnete pssessions, die mit der aktuellen Sitzung verbunden sind. `Disconnect-PSSession` die Verbindung mit unterbrochenen oder geschlossenen pssessions oder interaktiven pssessions, die mithilfe des `Enter-PSSession` Cmdlets gestartet wurden, kann nicht getrennt werden, und es können keine pssessions getrennt werden, die mit anderen Sitzungen verbunden sind.

Um erneut eine Verbindung mit einer getrennten PSSession herzustellen, verwenden Sie die `Connect-PSSession` `Receive-PSSession` Cmdlets oder.

Wenn eine PSSession getrennt ist, werden die Befehle in der PSSession bis zum Ende ausgeführt, sofern keine Zeitüberschreitung für die PSSession eintritt oder die Befehle in der PSSession nicht durch einen vollen Ausgabepuffer blockiert werden. Um die Leerlaufzeitüberschreitung zu ändern, verwenden Sie den **IdleTimeoutSec** -Parameter. Verwenden Sie zum Ändern des Ausgabepuffer Modus den **outputbufferingmode** -Parameter. Sie können auch den **indisconnectedsession** -Parameter des `Invoke-Command` Cmdlets verwenden, um einen Befehl in einer getrennten Sitzung auszuführen.

Weitere Informationen zum Feature „Getrennte Sitzungen“ finden Sie unter [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).

Dieses Cmdlet wird in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Trennen einer Sitzung nach Name

Mit diesem Befehl wird die Verbindung der PSSession UpdateSession auf dem Computer Server01 von der aktuellen Sitzung getrennt. Der Befehl verwendet den **Name** -Parameter, um die PSSession zu identifizieren.

```
PS> Disconnect-PSSession -Name UpdateSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  UpdateSession   Server01        Disconnected  Microsoft.PowerShell          None
```

Die Ausgabe zeigt, dass der Trennungsversuch erfolgreich war. Der Sitzungszustand ist Disconnected und die Verfügbarkeit ist None. Das weist darauf hin, dass die Sitzung nicht anderweitig verwendet wird und die Verbindung wiederhergestellt werden kann.

### Beispiel 2: Trennen einer Sitzung von einem bestimmten Computer

Mit diesem Befehl wird die Verbindung der PSSession ITTask auf dem Computer Server12 von der aktuellen Sitzung getrennt.
Die ITTask-Sitzung wurde in der aktuellen Sitzung erstellt und stellt eine Verbindung mit dem Computer Server12 her. Der Befehl verwendet das `Get-PSSession` Cmdlet, um die Sitzung zu erhalten `Disconnect-PSSession` , und das Cmdlet, um die Verbindung zu trennen.

```
PS> Get-PSSession -ComputerName Server12 -Name ITTask |
  Disconnect-PSSession -OutputBufferingMode Drop -IdleTimeoutSec 86400
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  ITTask          Server12        Disconnected  ITTasks               None
```

Der `Disconnect-PSSession` Befehl verwendet den **outputbufferingmode** -Parameter, um den Ausgabemodus auf " **Drop** " festzulegen. Durch diese Einstellung wird sichergestellt, dass das in der Sitzung ausgeführte Skript auch bei vollem Ausgabepuffer weiter ausgeführt werden kann. Da das Skript seine Ausgabedaten in einen Bericht auf einer Dateifreigabe schreibt, können andere Ausgabedaten verloren gehen, ohne dass dies Konsequenzen hätte.

Außerdem verwendet der Befehl den **IdleTimeoutSec** -Parameter, um die Leerlaufzeitüberschreitung der Sitzung auf 24 Stunden zu erweitern. Diese Einstellung gibt diesem Administrator oder anderen Administratoren Zeit, die Sitzungsverbindung wiederherzustellen, damit das Skript ausgeführt und Fehler ggf. behoben werden können.

### Beispiel 3: Verwenden mehrerer pssessions auf mehreren Computern

Diese Reihe von Befehlen zeigt, wie das `Disconnect-PSSession` Cmdlet in einem Unternehmens Szenario verwendet werden kann. In diesem Fall startet ein neuer Techniker ein Skript in einer Sitzung auf einem Remotecomputer und stößt auf ein Problem. Der Techniker trennt die Verbindung mit der Sitzung, damit ein erfahrener Kollege eine Verbindung mit der Sitzung herstellen und das Problem beheben kann.

```
PS> $s = New-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
PS> Invoke-Command $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Get-PSSession -Name ITTask -ComputerName Srv1 | Disconnect-PSSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1 ITTask           Srv1            Disconnected  Microsoft.PowerShell          None

PS> Get-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None
 2 ITTask          Srv2            Opened        Microsoft.PowerShell     Available
 3 ITTask          Srv30           Opened        Microsoft.PowerShell     Available

PS> Get-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None

PS> $s = Connect-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
PS> Invoke-Command -Session $s {dir $home\Scripts\PatchStatusOutput.ps1}
PS> Invoke-Command -Session $s {mkdir $home\Scripts\PatchStatusOutput}
PS> Invoke-Command -Session $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Disconnect-PSSession -Session $s
```

Der Techniker beginnt, Sitzungen auf mehreren Remotecomputern zu erstellen und in jeder Sitzung ein Skript auszuführen. Der erste Befehl verwendet das `New-PSSession` Cmdlet, um die ittask-Sitzung auf drei Remote Computern zu erstellen. Der Befehl speichert die Sitzungen in der $s-Variablen. Der zweite Befehl verwendet den **FilePath** -Parameter des `Invoke-Command` Cmdlets, um ein Skript in den Sitzungen in der $s Variablen auszuführen.

Das Skript, das auf dem Computer Srv1 ausgeführt wird, generiert unerwartete Fehler. Der Techniker wendet sich an seinen Vorgesetzten und bittet ihn um Hilfe. Der Manager weist den Techniker an, die Verbindung mit der Sitzung zu trennen, damit er untersuchen kann. Der zweite Befehl verwendet das `Get-PSSession` Cmdlet, um die ittask-Sitzung auf dem Srv1-Computer `Disconnect-PSSession` zu erhalten, und das Cmdlet, um die Verbindung zu trennen. Dieser Befehl hat keine Auswirkung auf die ittask-Sitzungen auf den anderen Computern.

Der dritte Befehl verwendet das `Get-PSSession` Cmdlet, um die ittask-Sitzungen zu erhalten. Die Ausgabe zeigt, dass die ITTask-Sitzungen auf den Computern Srv2 und Srv30 nicht vom Trennungsbefehl betroffen waren.

Der Manager meldet sich bei seinem Heimcomputer an, stellt eine Verbindung mit dem Unternehmensnetzwerk her, startet PowerShell und verwendet das `Get-PSSession` Cmdlet, um die ittask-Sitzung auf dem Srv1-Computer zu erhalten. Er verwendet die Anmeldeinformationen des Technikers, um auf die Sitzung zuzugreifen.

Als Nächstes verwendet der Manager das- `Connect-PSSession` Cmdlet, um eine Verbindung mit der ittask-Sitzung auf dem Srv1-Computer herzustellen. Der Befehl speichert die Sitzung in der $s-Variablen.

Der Manager verwendet das `Invoke-Command` Cmdlet, um einige Diagnose Befehle in der Sitzung in der `$s` Variablen auszuführen. Er erkennt, dass der Skriptfehler durch ein nicht gefundenes, erforderliches Verzeichnis verursacht wurde.
Der Manager verwendet die `MkDir` -Funktion, um das Verzeichnis zu erstellen, und dann startet er das `Get-PatchStatus.ps1` Skript neu und trennt die Verbindung mit der Sitzung. Der Manager meldet seine Ergebnisse an den Techniker, schlägt vor, dass er erneut eine Verbindung mit der Sitzung herstellt, um die Aufgaben abzuschließen, und fordert ihn auf, dem Skript einen Befehl hinzuzufügen, `Get-PatchStatus.ps1` der das erforderliche Verzeichnis erstellt, wenn es nicht vorhanden ist.

### Beispiel 4: Ändern des Timeout Werts für eine PSSession

In diesem Beispiel wird gezeigt, wie der Wert der **IdleTimeout** -Eigenschaft einer Sitzung korrigiert wird, damit die Verbindung getrennt werden kann.

Die Eigenschaft für die Leerlaufzeitüberschreitung einer Sitzung ist wichtig für getrennte Sitzungen, weil von ihr abhängt, wie lange eine getrennte Sitzung vor dem Löschen beibehalten wird. Sie können die Option für die Leerlaufzeitüberschreitung festlegen, wenn Sie eine Sitzung erstellen und wenn Sie die Verbindung trennen. Die Standardwerte für das Leerlauf Timeout einer Sitzung werden in der `$PSSessionOption` Einstellungs Variablen auf dem lokalen Computer und in der Sitzungs Konfiguration auf dem Remote Computer festgelegt. Die für die Sitzung festgelegten Werte haben Vorrang vor den in der Sitzungskonfiguration festgelegten Werten. Die Sitzungswerte dürfen jedoch die in der Sitzungskonfiguration festgelegten Kontingente, z. B. den **MaxIdleTimeoutMs** -Wert, nicht überschreiten.

```
PS> $Timeout = New-PSSessionOption -IdleTimeout 172800000
PS> $s = New-PSSession -Computer Server01 -Name ITTask -SessionOption $Timeout
PS> Disconnect-PSSession -Session $s
Disconnect-PSSession : The session ITTask cannot be disconnected because the specified
idle timeout value 172800(seconds) is either greater than the server maximum allowed
43200 (seconds) or less that the minimum allowed60(seconds).  Choose an idle time out
value that is within the allowed range and try again.

PS> Invoke-Command -ComputerName Server01 {Get-PSSessionConfiguration Microsoft.PowerShell} |
 Format-List -Property *

Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/microsoft.powershell
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
SecurityDescriptorSddl        : O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GXGW;;;WD)
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 2147483647
Uri                           : http://schemas.microsoft.com/powershell/microsoft.powershell
SDKVersion                    : 2
Name                          : microsoft.powershell
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
ParentResourceUri             : http://schemas.microsoft.com/powershell/microsoft.powershell
Enabled                       : true
MaxShells                     : 25
MaxShellsPerUser              : 25
Permission                    : BUILTIN\Administrators AccessAllowed
PSComputerName                : localhost
RunspaceId                    : aea84310-6dbf-4c21-90ac-13980039925a
PSShowComputerName            : True


PS> $s.Runspace.ConnectionInfo
ConnectionUri                     : http://Server01/wsman
ComputerName                      : Server01
Scheme                            : http
Port                              : 80
AppName                           : /wsman
Credential                        :
ShellUri                          : http://schemas.microsoft.com/powershell/Microsoft.PowerShell
AuthenticationMechanism           : Default
CertificateThumbprint             :
MaximumConnectionRedirectionCount : 5
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
UseCompression                    : True
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
NoEncryption                      : False
UseUTF16                          : False
OutputBufferingMode               : Drop
IncludePortInSPN                  : False
Culture                           : en-US
UICulture                         : en-US
OpenTimeout                       : 180000
CancelTimeout                     : 60000
OperationTimeout                  : 180000
IdleTimeout                       : 172800000

PS> Disconnect-PSSession $s -IdleTimeoutSec 43200
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Disconnected  Microsoft.PowerShell          None

PS> $s.Runspace.ConnectionInfo.IdleTimeout
43200000
```

Der erste Befehl verwendet das `New-PSSessionOption` Cmdlet, um ein Sitzungs Options Objekt zu erstellen. Er verwendet den **IdleTimeout** -Parameter, um eine Leerlaufzeitüberschreitung von 48 Stunden (172.800.000 Millisekunden) festzulegen. Der Befehl speichert das Sitzungsoptionsobjekt in der $Timeout-Variablen.

Der zweite Befehl verwendet das `New-PSSession` Cmdlet, um die ittask-Sitzung auf dem Server01-Computer zu erstellen. Der Befehl speichert die Sitzung in der $s-Variablen. Der Wert des **SessionOption** -Parameters entspricht der Leerlaufzeitüberschreitung von 48 Stunden in der $Timeout-Variablen.

Der dritte Befehl trennt die Verbindung der in der $s-Variablen enthaltenen ITTask-Sitzung. Der Befehl verursacht einen Fehler, weil der Wert für die Leerlaufzeitüberschreitung der Sitzung das **MaxIdleTimeoutMs** -Kontingent in der Sitzungskonfiguration überschreitet. Da die Leerlaufzeitüberschreitung erst verwendet wird, wenn die Sitzung getrennt ist, bleibt dieser Verstoß während der laufenden Sitzung unentdeckt.

Der vierte Befehl verwendet das `Invoke-Command` Cmdlet, um einen `Get-PSSessionConfiguration` Befehl für die Microsoft. PowerShell-Sitzungs Konfiguration auf dem Server01-Computer auszuführen. Der Befehl verwendet das `Format-List` Cmdlet, um alle Eigenschaften der Sitzungs Konfiguration in einer Liste anzuzeigen. Die Ausgabe zeigt, dass die **maxidletimeoutms** -Eigenschaft, die den maximal zulässigen **IdleTimeout** -Wert für Sitzungen festlegt, die die Sitzungs Konfiguration verwenden, 43,2 Millionen Millisekunden (12 Stunden) beträgt.

Der fünfte Befehl ruft die Sitzungsoptionswerte der Sitzung in der $s-Variablen ab. Die Werte vieler Sitzungs Optionen sind Eigenschaften der **ConnectionInfo** -Eigenschaft der **Runspace** -Eigenschaft der Sitzung. Die Ausgabe zeigt, dass der Wert der **IdleTimeout** -Eigenschaft der Sitzung 172,8 Millionen Millisekunden (48 Stunden) beträgt, wodurch das **maxidletimeoutms** -Kontingent von 12 Stunden in der Sitzungs Konfiguration verletzt wird. Um diesen Konflikt zu lösen, können Sie mit dem **ConfigurationName** -Parameter eine andere Sitzungs Konfiguration auswählen oder den **IdleTimeout** -Parameter verwenden, um das Leerlauf Timeout der Sitzung zu verringern.

Der sechste Befehl trennt die Sitzungsverbindung. Er verwendet den **IdleTimeoutSec** -Parameter, um die Leerlaufzeitüberschreitung auf den Maximalwert von 12 Stunden festzulegen.

Der siebte Befehl ruft den Wert der **IdleTimeout** -Eigenschaft der getrennten Sitzung ab, der in Millisekunden gemessen wird. Die Ausgabe bestätigt, dass der Befehl erfolgreich ausgeführt wurde.

## PARAMETERS

### -Id

Trennt die Verbindung von Sitzungen mit der angegebenen Sitzungs-ID. Geben Sie eine oder mehrere IDs (durch Kommas getrennt) ein, oder verwenden Sie den Bereichsoperator (..), um einen Bereich von IDs anzugeben.

Verwenden Sie das-Cmdlet, um die ID einer Sitzung zu erhalten `Get-PSSession` . Die Instanz-ID wird in der **ID** -Eigenschaft der Sitzung gespeichert.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Idletimeoutsec

Ändert den Wert für die Leerlaufzeitüberschreitung der getrennten PSSession. Geben Sie einen Wert in Sekunden ein. Der minimale Wert beträgt 60 Sekunden (1 Minute).

Die Leerlaufzeitüberschreitung bestimmt, wie lange die getrennte PSSession auf dem Remotecomputer beibehalten wird. Wenn der Wert abläuft, wird die PSSession gelöscht.

Ab dem Zeitpunkt der Trennung befinden sich getrennte PSSessions im Leerlauf, selbst wenn die Befehle in der getrennten Sitzung ausgeführt werden.

Der Standardwert für die Leerlaufzeitüberschreitung einer Sitzung wird durch den Wert der **IdleTimeoutMs** -Eigenschaft der Sitzungskonfiguration festgelegt. Der Standardwert beträgt 7.200.000 Millisekunden (2 Stunden).

Der Wert dieses Parameters hat Vorrang vor dem Wert der **IdleTimeout** -Eigenschaft der $PSSessionOption-Einstellungsvariablen und dem Standardwert für die Leerlaufzeitüberschreitung in der Sitzungskonfiguration. Allerdings darf dieser Wert nicht den Wert der **MaxIdleTimeoutMs** -Eigenschaft der Sitzungskonfiguration überschreiten. Der Standardwert von **MaxIdleTimeoutMs** beträgt 12 Stunden (43.200.000 Millisekunden).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Trennt die Verbindung von Sitzungen mit den angegebenen Instanz-IDs.

Die Instanz-ID ist eine GUID, die eine Sitzung auf einem lokalen oder Remotecomputer eindeutig identifiziert. Die Instanz-ID ist eindeutig, sogar über mehrere Sitzungen auf mehreren Computern.

Verwenden Sie das-Cmdlet, um die Instanz-ID einer Sitzung zu erhalten `Get-PSSession` . Die Instanz-ID wird in der **InstanceId-** Eigenschaft der Sitzung gespeichert.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Trennt die Verbindung von Sitzungen mit den angegebenen Anzeigenamen. Platzhalter sind zulässig.

Verwenden Sie das-Cmdlet, um den anzeigen Amen einer Sitzung zu erhalten `Get-PSSession` . Der Anzeigename wird in der **Name** -Eigenschaft der Sitzung gespeichert.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Sitzung

Trennt die Verbindung der angegebenen PSSessions. Geben Sie PSSession-Objekte ein, z. b. die vom `New-PSSession` Cmdlet zurückgegebenen Objekte. Sie können ein PSSession-Objekt auch über die Pipeline an weiterleiten `Disconnect-PSSession` .

Mit dem `Get-PSSession` -Cmdlet können alle pssessions, die auf einem Remote Computer beendet werden, einschließlich pssessions, die getrennt sind, und pssessions, die mit anderen Sitzungen auf anderen Computern verbunden sind, erhalten. `Disconnect-PSSession` trennt nur die PSSession, die mit der aktuellen Sitzung verbunden sind. Wenn Sie andere pssessions an weiterleiten `Disconnect-PSSession` , `Disconnect-PSSession` schlägt der Befehl fehl.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit

Legt die Drosselungs Grenze für den `Disconnect-PSSession` Befehl fest.

Die Drosselungsgrenze ist die maximale Anzahl gleichzeitiger Verbindungen, die zum Ausführen dieses Befehls hergestellt werden können. Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.

Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -Outputbufferingmode

Bestimmt, wie die Befehlsausgabe in der getrennten Sitzung verwaltet wird, wenn der Ausgabepuffer voll ist. Der Standardwert ist **Block**.

Wenn der Befehl in der getrennten Sitzung Ausgabedaten zurückgibt und sich der Ausgabepuffer füllt, legt der Wert dieses Parameters tatsächlich fest, ob der Befehl weiter ausgeführt wird, während die Sitzung getrennt ist. Durch den Wert **Block** wird der Befehl angehalten, bis die Sitzungsverbindung wiederhergestellt wird. Beim Wert **Drop** kann der Befehl abgeschlossen werden, obwohl Daten verloren gehen können. Bei Verwendung des **Drop** -Werts wird die Befehlsausgabe an eine Datei auf dem Datenträger umgeleitet.

Gültige Werte sind:

- **Block** : Wenn der Ausgabepuffer voll ist, wird die Ausführung angehalten, bis der Puffer gelöscht wird.
- **Drop** : Wenn der Ausgabepuffer voll ist, wird die Ausführung fortgesetzt. Sobald neue Ausgabedaten gespeichert werden, wird die älteste Ausgabe verworfen.
- **None** : Es wurde kein Ausgabepuffer Modus angegeben. Der Wert der **OutputBufferingMode** -Eigenschaft der Sitzungskonfiguration wird für die getrennte Sitzung verwendet.

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Block
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](./About/about_CommonParameters.md).

## EINGABEN

### System. Management. Automation. Runspaces. PSSession

Sie können eine Sitzung an die Pipeline übergeben `Disconnect-PSSession` .

## AUSGABEN

### System. Management. Automation. Runspaces. PSSession

`Disconnect-PSSession` Gibt ein-Objekt zurück, das die getrennte Sitzung darstellt.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

- Das- `Disconnect-PSSession` Cmdlet funktioniert nur, wenn auf dem lokalen Computer und dem Remote Computer PowerShell 3,0 oder höher ausgeführt wird.
- Wenn Sie das `Disconnect-PSSession` Cmdlet in einer getrennten Sitzung verwenden, hat der Befehl keine Auswirkungen auf die Sitzung und generiert keine Fehler.
- Die Verbindung getrennter Loopbacksitzungen mit interaktiven Sicherheitstoken (die mit dem **EnableNetworkAccess** -Parameter erstellt werden) kann nur von dem Computer wiederhergestellt werden, auf dem die Sitzung erstellt wurde. Diese Einschränkung schützt den Computer vor böswilligem Zugriff.
- Wenn Sie eine PSSession trennen, nimmt sie den Sitzungszustand **Disconnected** und die Verfügbarkeit **None** an.

  Der Wert der **State** Eigenschaft bezieht sich auf die aktuelle Sitzung. Folglich bedeutet der Wert **Disconnected** , dass die PSSession nicht mit der aktuellen Sitzung verbunden ist. Er bedeutet jedoch nicht, dass die PSSession von allen Sitzungen getrennt ist. Sie kann mit einer anderen Sitzung verbunden sein. Um festzustellen, ob Sie eine Sitzungsverbindung herstellen bzw. wiederherstellen können, verwenden Sie die **Availability** -Eigenschaft.

  Ein **Availability** -Wert von **None** gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann. Der Wert **Busy** gibt an, dass Sie keine Verbindung mit der PSSession herstellen können, weil sie mit einer anderen Sitzung verbunden ist.

  Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate-Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).

  Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability-Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

## VERWANDTE LINKS

[Connect-PSSession](Connect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Receive-PSSession](Receive-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Remove-PSSession](Remove-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)

[about_Remote_Disconnected_Sessions](About/about_Remote_Disconnected_Sessions.md)
