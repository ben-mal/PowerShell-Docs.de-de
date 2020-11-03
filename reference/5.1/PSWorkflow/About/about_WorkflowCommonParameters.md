---
description: In diesem Thema werden die Parameter beschrieben, die für alle Windows PowerShell-Workflow Befehle gültig sind. Da Sie von der Windows PowerShell-Engine den Workflows hinzugefügt werden, können Sie diese Parameter für jeden Workflow verwenden, und Sie werden automatisch für die von Ihnen Autor Workflows aktiviert.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflowcommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über_WorkflowCommonParameters
ms.openlocfilehash: 386200475c1dab9735921edd60abbde20ee354c4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221855"
---
# <a name="about-workflowcommonparameters"></a>Informationen zu workflowcommonparameters

## <a name="short-description"></a>KURZE BESCHREIBUNG

In diesem Thema werden die Parameter beschrieben, die für alle Windows PowerShell-Workflow Befehle gültig sind. Da Sie von der Windows PowerShell-Engine den Workflows hinzugefügt werden, können Sie diese Parameter für jeden Workflow verwenden, und Sie werden automatisch für die von Ihnen Autor Workflows aktiviert.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Allgemeine Windows PowerShell-Workflow Parameter sind eine Reihe von Cmdlet-Parametern, die Sie mit allen Windows PowerShell-Workflows und-Aktivitäten verwenden können. Sie werden von der Windows PowerShell-Workflow-Engine, nicht vom Workflow Autor hinzugefügt und sind automatisch in Workflows und Aktivitäten verfügbar. Allerdings unterstützen Workflows, die drei Ebenen tief verschachtelt sind, keine allgemeinen Parameter, einschließlich der allgemeinen Workflow Parameter.

Alle Workflow Parameter sind optional und werden benannt (nicht Positions fähig). Sie nehmen keine Eingaben aus der Pipeline an.

Die meisten der allgemeinen Workflow Parameter verfügen über ein PS-Präfix, z `PSComputerName` `PSCredential` . b. und. Mit den "PS-prefixed"-Parametern werden die Verbindung und die Ausführungsumgebung für die Zielcomputer konfiguriert, die auch als "Remote Knoten" bezeichnet werden.

Viele der allgemeinen Workflow Parameter, wie z. b. `PSAllowRedirection` und `AsJob` , verfügen über Namen, die den in Windows PowerShell-Remoting und Hintergrund Aufträgen verwendeten Parametern ähneln. Diese Parameter funktionieren auf die gleiche Weise wie ähnliche Remoting-und Job-Parameter, sodass Sie das wissen, das Sie in Remoting und Aufträgen entwickelt haben, zum Verwalten von Workflows verwenden können.

Workflows werden in Windows PowerShell 3,0 eingeführt.

### <a name="parameter-descriptions"></a>Parameter Beschreibungen

In diesem Abschnitt werden die allgemeinen Workflow Parameter beschrieben.

#### <a name="-asjob-switchparameter"></a>-AsJob \<SwitchParameter\>

Führt den Workflow als Workflow Auftrag aus. Der Workflow Befehl gibt sofort ein Objekt zurück, das einen übergeordneten Auftrag darstellt. Der übergeordnete Auftrag enthält die untergeordneten Aufträge, die auf den einzelnen Ziel Computern ausgeführt werden. Um den Auftrag zu verwalten, verwenden Sie die Job-Cmdlets. Um die Auftragsergebnisse abzurufen, verwenden Sie [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job).

#### <a name="-jobname-string"></a>-Jobname \<String\>

Gibt einen anzeigen Amen für den Workflow Auftrag an. Standardmäßig erhalten Aufträge die Bezeichnung „Job\<n\>“, wobei \<n\> für eine Ordinalzahl steht.

Wenn Sie den Jobname-Parameter in einem Workflow Befehl verwenden, wird der Workflow als Auftrag ausgeführt, und der Workflow Befehl gibt ein Auftrags Objekt zurück, auch wenn Sie den- `AsJob` Parameter nicht in den Befehl einschließen.

Weitere Informationen zu Windows PowerShell-Hintergrundaufträgen finden Sie unter [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).

#### <a name="-psallowredirection-switchparameter"></a>-Psallowredirection \<SwitchParameter\>

Ermöglicht die Umleitung der Verbindung mit den Ziel Computern.

Wenn Sie den- `PSConnectionURI` Parameter verwenden, kann das Remote Ziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben. Standardmäßig umleitet Windows PowerShell Verbindungen nicht, Sie können jedoch den-Parameter verwenden, `PSAllowRedirection` um die Umleitung der Verbindung mit dem Zielcomputer zuzulassen.

Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie die- `MaximumConnectionRedirectionCount` Eigenschaft der `$PSSessionOption` Preference-Variablen festlegen oder die- `MaximumConnectionRedirectionCount` Eigenschaft des Werts von `PSSessionOption parameter` . Der Standardwert ist 5. Weitere Informationen finden Sie in der Beschreibung des Parameters und in der Datei " `PSSessionOption` [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)".

#### <a name="-psapplicationname-string"></a>-Psapplicationname \<String\>

Gibt das Anwendungs namens Segment des Verbindungs-URI an, der zum Herstellen der Verbindung mit den Ziel Computern verwendet wird. Verwenden Sie diesen Parameter, um den Anwendungsnamen anzugeben, wenn Sie den- `ConnectionURI` Parameter nicht im Befehl verwenden.

Der Standardwert ist der Wert der Einstellungs `$PSSessionApplicationName` Variablen auf dem lokalen Computer. Wenn diese Einstellungsvariable nicht definiert ist, ist der Standardwert „WSMan“. Dieser Wert ist für die meisten Verwendungsarten geeignet. Weitere Informationen finden Sie unter [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

Der WinRM-Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus. Der Wert dieses Parameters sollte mit dem Wert der- `URLPrefix` Eigenschaft eines Listener auf dem Remote Computer identisch sein.

#### <a name="-psauthentication-authenticationmechanism"></a>-Psauthentication \<AuthenticationMechanism\>

Gibt den Mechanismus an, der zum Authentifizieren der Anmelde Informationen des Benutzers beim Herstellen einer Verbindung mit den Ziel Computern verwendet wird.

Gültige Werte sind:

- **Standard**
- **Grundlegend**
- **CredSSP**
- **Digest**
- **Kerberos**
- **Verhandelt**
- **NegotiateWithImplicitCredential**

Der Standardwert lautet **Default**.

Informationen zu den Werten dieses Parameters finden Sie in der Beschreibung der- `System.Management.Automation.Runspaces.AuthenticationMechanism` Enumeration in MSDN.

> [!WARNING]
> Die Credential Security Support Provider (CredSSP)-Authentifizierung, in der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle gedacht, die Authentifizierung bei mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remote-Netzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

#### <a name="-psauthenticationlevel-authenticationlevel"></a>-Psauthenticationlevel \<AuthenticationLevel\>

Gibt die Authentifizierungs Ebene für die Verbindungen mit den Ziel Computern an.
Der Standardwert lautet **Default**.

Gültige Werte sind:

|Name |BESCHREIBUNG |
|---------|---------|
|**Unverändert** | Die Authentifizierungsebene ist identisch mit der des vorherigen Befehls. |
|**Standard** | Windows-Authentifizierung. |
|**None** | Keine COM-Authentifizierung.   |
|**Herstellen einer Verbindung** | COM-Authentifizierung auf Verbindungsebene.|
|**Call** | COM-Authentifizierung auf Aufrufebene.   |
|**Lohn** | COM-Authentifizierung auf Paketebene.|
|**PacketIntegrity** | COM-Authentifizierung auf Paketintegritätsebene.  |
|**PacketPrivacy** | COM-Authentifizierung auf Paketdatensicherheitsebene. |

#### <a name="-pscertificatethumbprint-string"></a>-Pscertifipagethumbprint \<String\>

Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.

Verwenden Sie zum erhalten eines Zertifikats das [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) oder [Get-ChildItem] (.. /.. /Microsoft.PowerShell.Management/Get-ChildItem.MD)-Cmdlets im Windows PowerShell-CERT:-Laufwerk.

#### <a name="-pscomputername-string"></a>-Pscomputername \<String[]\>

Gibt die Liste der Computer an, die die Zielknoten des Workflows sind.
Befehle oder Aktivitäten in einem Workflow werden auf den Computern ausgeführt, die mithilfe dieses Parameters angegeben werden. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen von mindestens einem Computer in eine durch Kommas getrennte Liste ein. Um den lokalen Computer anzugeben, geben Sie den Computernamen, „localhost“ oder einen Punkt (.) ein.

Um den lokalen Computer in den Wert des- `PSComputerName` Parameters einzuschließen, öffnen Sie Windows PowerShell mit der Option "als Administrator ausführen".

Wenn dieser Parameter im Befehl weggelassen wird, oder wenn der Wert `$null` oder eine leere Zeichenfolge ist, ist das Workflow Ziel der lokale Computer, und Windows PowerShell-Remoting wird nicht verwendet, um den Befehl auszuführen.

Um eine IP-Adresse im Wert des- `ComputerName` Parameters zu verwenden, muss der-Befehl den- `PSCredential` Parameter enthalten. Außerdem muss der Computer für den HTTPS-Transport konfiguriert sein, oder die IP-Adresse des Remotecomputers muss in der WinRM TrustedHosts-Liste auf dem lokalen Computer enthalten sein. Anweisungen zum Hinzufügen eines Computer namens zur Liste "Treuhänder Hosts *" finden Sie unter "Vorgehensweise beim Hinzufügen eines Computers zur Liste vertrauenswürdiger Hosts"* in [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).

#### <a name="-psconfigurationname-string"></a>-Psconfigurationname \<String\>

Gibt die Sitzungs Konfigurationen an, die zum Konfigurieren von Sitzungen auf den Ziel Computern verwendet werden. Geben Sie eine Sitzungs Konfiguration auf den Ziel Computern (nicht auf dem Workflow Server Computer) ein. Der Standardwert ist `Microsoft.PowerShell.Workflow`.

#### <a name="-psconnectionretrycount-uint"></a>-Psconnectionretrycount \<UInt\>

Gibt die maximale Anzahl von versuchen an, eine Verbindung mit den einzelnen Ziel Computern herzustellen, wenn beim ersten Verbindungsversuch ein Fehler auftritt. Geben Sie eine Zahl zwischen 1 und 4.294.967.295 (uint. MaxValue) ein. Der Standardwert 0 (null) stellt keine Wiederholungs Versuche dar.

#### <a name="-psconnectionretryintervalsec-uint"></a>-Psconnectionretryintervalsec \<UInt\>

Gibt die Verzögerung zwischen Verbindungs Wiederholungs versuchen in Sekunden an. Der Standardwert ist 0 (null). Dieser Parameter ist nur gültig, wenn der Wert von psconnectionretrycount mindestens 1 ist.

#### <a name="-psconnectionuri-systemuri"></a>-Psconnectionuri \<System.Uri\>

Gibt einen Uniform Resource Identifier (URI) an, der den Verbindungs Endpunkt für den Workflow auf dem Bereitstellungs Zielcomputer definiert. Der URI muss vollqualifiziert sein.

Das Format dieser Zeichenfolge lautet wie folgt:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

Der Standardwert ist `http://localhost:5985/WSMAN`.

Wenn Sie keinen angeben `PSConnectionURI` , können Sie die `PSUseSSL` -,-, `PSComputerName` `PSPort` -und-Parameter verwenden, `PSApplicationName` um die `PSConnectionURI` Werte anzugeben.

Gültige Werte für das Transport-Segment des URI sind **http** und **https**.
Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS. Um die Standardports für Windows PowerShell-Remoting zu verwenden, geben Sie Port 5985 für HTTP bzw. 5986 für HTTPS an.

#### <a name="-pscredential-pscredential"></a>-PSCredential \<PSCredential\>

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen eines Workflows auf dem Zielcomputer verfügt. Der Standardwert ist der aktuelle Benutzer. Dieser Parameter ist nur gültig, wenn der pscomputername-Parameter im Befehl enthalten ist.

Geben Sie einen Benutzernamen ein, z. b. "USER01" oder "Domain01\User01", oder geben Sie eine Variable ein, die ein- `PSCredential` Objekt enthält, wie z. b. ein vom `Get-Credential` Cmdlet zurückgegeben. Wenn Sie nur einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

#### <a name="-pselapsedtimeoutsec-uint32"></a>-Pselapsedtimeoutsec \<UInt32\>

Bestimmt, wie lange der Workflow und alle zugehörigen Ressourcen im System verwaltet werden. Wenn das Timeout abläuft, wird der Workflow gelöscht, auch wenn er noch verarbeitet wird. Geben Sie einen Wert zwischen 10 und 4.294.967.295 ein. Der Standardwert 0 (null) bedeutet, dass kein abgelaufener Timeout vorliegt.

#### <a name="-psparametercollection-hashtable"></a>-Psparametercollection \<Hashtable[]\>

Gibt verschiedene allgemeine Workflow Parameterwerte für verschiedene Zielcomputer an.

Geben Sie eine durch Trennzeichen getrennte Liste von Hash Tabellen mit einer Hash Tabelle für jeden Zielcomputer ein. In jeder Hash Tabelle ist der erste Schlüssel, `PSComputerName` und sein Wert ist der Name des Ziel Computers. Platzhalter Zeichen sind im Computernamen zulässig. Bei den restlichen Schlüsseln in der Hash Tabelle ist der Schlüssel der Parameter Name, und der Wert ist der Parameterwert.

Beispiel:

```powershell
-PSParameterCollection @{PSComputerName="*"; PSElapsedTimeoutSec=20},
@{PSComputerName="Server02"},
@{PSComputerName="Server03"},
@{PSComputerName="Server01"; PSElapsedTimeoutSec=10}
```

Im obigen Beispiel verfügen alle Verbindungen über einen Standardwert von pselapsedtimeoutsec von 20 Sekunden, mit Ausnahme von Server01, der den Standardwert überschreibt, indem er das eigene Timeout von 10 Sekunden angibt.

#### <a name="-pspersist-boolean"></a>-Pspersist \<Boolean\>

Fügt dem Workflow Prüfpunkte hinzu, zusätzlich zu allen Prüfpunkten, die im Workflow angegeben werden.

Dieser Parameter kann die Prüfpunkte in einem Workflow nicht unterdrücken, wie z. b. die, die mit dem `PSPersist` allgemeinen Aktivitäts Parameter, der- `Checkpoint-Workflow` Aktivität oder der-Variablen angegeben werden `$PSPersistPreference` .

Ein "Prüfpunkt" oder "Persistenzpunkt" ist eine Momentaufnahme des Workflow Status und der Daten, die erfasst werden, während der Workflow ausgeführt wird und in einem persistenten Speicher auf einem Datenträger oder in einer SQL-Datenbank gespeichert wird. Der Windows PowerShell-Workflow verwendet die gespeicherten Daten, um einen angehaltenen oder unterbrochenen Workflow vom letzten Persistenzpunkt wieder aufzunehmen, anstatt den Workflow neu zu starten.

Gültige Werte:

- ( *Standard* ) Wenn Sie diesen Parameter weglassen, wird am Anfang und Ende des Workflows zusätzlich zu den im Workflow angegebenen Prüfpunkten ein Prüfpunkt hinzugefügt.

- `$True`. Fügt zusätzlich zu allen Prüfpunkten, die im Workflow angegeben werden, einen Prüfpunkt am Anfang und Ende des Workflows sowie einen Prüfpunkt nach jeder Aktivität hinzu.

- `$False`. Es werden keine Prüfpunkte hinzugefügt. Prüfpunkte werden nur dann übernommen, wenn Sie im Workflow angegeben werden.

#### <a name="-psport-int32"></a>-Psport \<Int32\>

Gibt den Netzwerkport auf den Ziel Computern an. Die Standardports sind 5985 (der WinRM-Port für HTTP) und 5986 (der WinRM-Port für HTTPS).

Verwenden Sie den psport-Parameter nur, wenn dies erforderlich ist. Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird. Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird. Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren.

#### <a name="-psprivatemetadata-hashtable"></a>-Psprivatemetadata \<Hashtable\>

Stellt angepasste Informationen für Workflow Aufträge bereit. Geben Sie eine Hash Tabelle ein. Die Schlüssel und Werte werden für jeden Workflow angepasst. Informationen zu den privaten Metadaten eines Workflows finden Sie im Hilfethema für den Workflow.

Dieser Parameter wird nicht von der Windows PowerShell-Workflow-Engine verarbeitet.
Stattdessen übergibt die Engine die Hash Tabelle direkt an den Workflow.

#### <a name="-psrunningtimeoutsec-uint32"></a>-Psrunningtimeoutsec \<UInt32\>

Gibt die Laufzeit des Workflows in Sekunden an, ausgenommen der Zeit, in der der Workflow angehalten wird. Wenn die Workflow Ausführung nach Ablauf der Zeit nicht vollständig ist, wird die Ausführung des Workflows von der Windows PowerShell-Workflow-Engine erzwungen.

#### <a name="-pssessionoption-pssessionoption"></a>-Pssessionoption \<PSSessionOption\>

Legt Erweiterte Optionen für die Sitzungen auf den Ziel Computern fest. Geben Sie ein- `PSSessionOption` Objekt ein, z. b. ein-Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen.

Die Standardwerte für die Sitzungs Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt. Andernfalls verwendet die Sitzung die Werte, die in der Sitzungs Konfiguration angegeben sind.

Eine Beschreibung der Sitzungs Optionen, einschließlich der Standardwerte, finden Sie im Hilfethema für das `New-PSSessionOption` Cmdlet (.. /.. /Microsoft.PowerShell.Core/New-PSSessionOption.md). Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

#### <a name="-psusessl-switchparameter"></a>-Psusessl \<SwitchParameter\>

Verwendet das Secure Sockets Layer (SSL)-Protokoll, um eine Verbindung mit dem Zielcomputer herzustellen. Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden. UseSSL bietet zusätzlichen Schutz, indem die Daten über HTTPS, anstelle von HTTP gesendet werden. Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port für den Befehl nicht verfügbar ist, tritt ein Fehler beim Befehl auf.

## <a name="see-also"></a>SIEHE AUCH

- [Informationen über_ActivityCommonParameters](about_ActivityCommonParameters.md)
- [about_Workflows](about_Workflows.md)
- [Invoke-AsWorkflow](xref:PSWorkflowUtility.Invoke-AsWorkflow)
- [New-PSWorkflowExecutionOption](xref:PSWorkflow.New-PSWorkflowExecutionOption)
- [New-PSWorkflowSession](xref:PSWorkflow.New-PSWorkflowSession)
